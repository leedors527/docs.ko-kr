---
title: 교차 유효성 검사를 사용하여 기계 학습 모델 학습 - ML.NET
description: 모델의 예측에 대한 정확도 수준을 강화하기 위해 ML.NET에서 교차 유효성 검사를 사용하여 기계 학습 모델을 학습하는 방법 알아보기
ms.date: 11/07/2018
ms.custom: mvc,how-to
ms.openlocfilehash: 41b99415d736b6583a8d43434c031e677e6f3ac8
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2018
ms.locfileid: "53145964"
---
# <a name="train-a-machine-learning-model-using-cross-validation---mlnet"></a><span data-ttu-id="b6690-103">교차 유효성 검사를 사용하여 기계 학습 모델 학습 - ML.NET</span><span class="sxs-lookup"><span data-stu-id="b6690-103">Train a machine learning model using cross-validation - ML.NET</span></span>

<span data-ttu-id="b6690-104">[교차 유효성 검사](https://en.wikipedia.org/wiki/Cross-validation_(statistics))는 ML 애플리케이션에 대한 유용한 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="b6690-104">[Cross-validation](https://en.wikipedia.org/wiki/Cross-validation_(statistics)) is a useful technique for ML applications.</span></span> <span data-ttu-id="b6690-105">실행 간에 모델 품질의 분산을 예측하고 평가를 위해 설정된 별도 테스트를 추출할 필요를 제거할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6690-105">It helps estimate the variance of the model quality from one run to another and also eliminates the need to extract a separate test set for evaluation.</span></span>

<span data-ttu-id="b6690-106">(모든 전처리가 하나의 학습 파이프라인에 있으면) ML.NET는 자동으로 기능화를 올바르게 적용한 다음, '계층 열' 개념을 사용하여 관련 예제가 분리되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6690-106">ML.NET automatically applies featurization correctly (as long as all of the preprocessing resides in one learning pipeline) then use the 'stratification column' concept to make sure that related examples don't get separated.</span></span>

<span data-ttu-id="b6690-107">임의의 90/10 학습-테스트 분할 및 5가지 교차 유효성 검사를 사용하는 아이리스 데이터 세트에 대한 학습 예제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b6690-107">Here's a training example on an Iris dataset using randomized 90/10 train-test split, and a 5-fold cross-validation:</span></span>

```csharp
// Create a new context for ML.NET operations. It can be used for exception tracking and logging, 
// as a catalog of available operations and as the source of randomness.
var mlContext = new MLContext();

// Step one: read the data as an IDataView.
// First, we define the reader: specify the data columns and where to find them in the text file.
var reader = mlContext.Data.TextReader(new TextLoader.Arguments
{
    Column = new[] {
        // We read the first 11 values as a single float vector.
        new TextLoader.Column("SepalLength", DataKind.R4, 0),
        new TextLoader.Column("SepalWidth", DataKind.R4, 1),
        new TextLoader.Column("PetalLength", DataKind.R4, 2),
        new TextLoader.Column("PetalWidth", DataKind.R4, 3),
        // Label: kind of iris.
        new TextLoader.Column("Label", DataKind.TX, 4),
    },
    Separator = ","
});

// Read the data.
var data = reader.Read(dataPath);

// Build the training pipeline.
var dynamicPipeline =
    // Concatenate all the features together into one column 'Features'.
    mlContext.Transforms.Concatenate("Features", "SepalLength", "SepalWidth", "PetalLength", "PetalWidth")
    // Note that the label is text, so it needs to be converted to key.
    .Append(mlContext.Transforms.Categorical.MapValueToKey("Label"), TransformerScope.TrainTest)
    // Use the multi-class SDCA model to predict the label using features.
    .Append(mlContext.MulticlassClassification.Trainers.StochasticDualCoordinateAscent());

// Split the data 90:10 into train and test sets, train and evaluate.
var (trainData, testData) = mlContext.MulticlassClassification.TrainTestSplit(data, testFraction: 0.1);

// Train the model.
var model = dynamicPipeline.Fit(trainData);
// Compute quality metrics on the test set.
var metrics = mlContext.MulticlassClassification.Evaluate(model.Transform(testData));
Console.WriteLine(metrics.AccuracyMicro);

// Now run the 5-fold cross-validation experiment, using the same pipeline.
var cvResults = mlContext.MulticlassClassification.CrossValidate(data, dynamicPipeline, numFolds: 5);

// The results object is an array of 5 elements. For each of the 5 folds, we have metrics, model and scored test data.
// Let's compute the average micro-accuracy.
var microAccuracies = cvResults.Select(r => r.metrics.AccuracyMicro);
Console.WriteLine(microAccuracies.Average());
```