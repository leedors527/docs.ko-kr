---
title: '방법: 3차원 장면 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- scenes [WPF], 3-D
- 3-D scenes
ms.assetid: adb4a598-71a2-4dd5-b677-ea3fc11b78b2
ms.openlocfilehash: 8e176cb437055787da86d56770dd71323134fa33
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61910184"
---
# <a name="how-to-create-a-3-d-scene"></a>방법: 3차원 장면 만들기
이 예제에서는 회전 된 문서의 플랫 시트 처럼 보이는 3 차원 개체를 만드는 방법을 보여 줍니다. <xref:System.Windows.Controls.Viewport3D> 다음 구성 요소와 함께 하는 데이 간단한 3 차원 장면 만들기:  
  
- 카메라를 사용 하 여 만들어집니다는 <xref:System.Windows.Media.Media3D.PerspectiveCamera>합니다. 카메라 볼 수는 3 차원 장면의 부분을 지정 합니다.  
  
- 메시를 사용 하 여 3 차원 개체 (용지의)의 모양을 지정 만들어집니다 합니다 <xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A> 속성의 <xref:System.Windows.Media.Media3D.GeometryModel3D>합니다.  
  
- 자료를 사용 하 여 개체 (이 샘플에서는 선형 그라데이션) 화면에 표시할 지정 된 된 <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> 속성의 <xref:System.Windows.Media.Media3D.GeometryModel3D>합니다.  
  
- 사용 하 여 개체에서 우수한 성능을 나타내는 광원 만들어집니다 <xref:System.Windows.Media.Media3D.DirectionalLight>합니다.  
  
## <a name="example"></a>예제  
 아래 코드에는 XAML에서 3 차원 장면을 만드는 방법을 보여 줍니다.  
  
 [!code-xaml[3DGallery_snip#Basic3DShapeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/Basic3DShapeExample.xaml#basic3dshapeexamplewholepage)]  
  
## <a name="example"></a>예제  
 아래 코드에는 프로시저 코드에서 같은 3 차원 장면을 만드는 방법을 보여 줍니다.  
  
 [!code-csharp[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Basic3DShapeExample.cs#basic3dshapecodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/basic3dshapeexample.vb#basic3dshapecodeexamplewholepage)]  
  
## <a name="see-also"></a>참고자료

- [3차원 그래픽 개요](3-d-graphics-overview.md)
