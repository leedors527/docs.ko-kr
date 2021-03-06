---
title: 복합 형식
ms.date: 03/30/2017
ms.assetid: 63efbd23-11d4-4871-bc88-ad01b9837553
ms.openlocfilehash: 9d63660c441192bbc9ecb48bb3a86030b46461cc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61880017"
---
# <a name="complex-type"></a>복합 형식
A *복합 형식* 에서 다양 한 구조적된 속성을 정의 하기 위한 템플릿입니다 [엔터티 형식](../../../../docs/framework/data/adonet/entity-type.md) 또는 다른 복합 형식입니다. 각 템플릿에는 다음 정보가 들어 있습니다.  
  
-   고유한 이름 (필수)  
  
    > [!NOTE]
    >  복합 형식의 이름은 동일한 네임스페이스 내의 엔터티 형식 이름과 달라야 합니다.  
  
-   데이터를 하나 이상의 형태로 [속성](../../../../docs/framework/data/adonet/property.md)합니다. 필요에 따라  
  
    > [!NOTE]
    >  복합 형식의 속성은 다른 복합 형식일 수 있습니다.  
  
 복합 형식은 기본 형식 속성이나 다른 복합 형식의 형태로 데이터 페이로드를 전달할 수 있다는 점에서 엔터티 형식과 비슷합니다. 그러나 복합 형식과 엔터티 형식 사이에는 약간의 중요한 차이점이 존재합니다.  
  
-   복합 형식은 식별자를 포함하지 않으므로 독립적으로 존재할 수 없습니다. 복합 형식은 엔터티 형식 또는 다른 복합 형식의 속성으로만 존재할 수 있습니다.  
  
-   복합 형식에 참여할 수 없습니다 [연결](../../../../docs/framework/data/adonet/association-type.md)합니다. 연결의 어느 end도 복합 형식이 수 있어 [탐색 속성](../../../../docs/framework/data/adonet/navigation-property.md) 복합 형식을 정의할 수 없습니다.  
  
## <a name="example"></a>예제  
 합니다 [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) 개념 스키마 정의 언어를 호출 하는 도메인 특정 언어 (DSL)를 사용 하 여 ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) 개념적 모델을 정의 합니다. 다음 CSDL에서는 기본 형식 속성 `StreetAddress`, `City`, `StateOrProvince`, `Country` 및 `PostalCode`가 있는 복합 형식 Address를 정의합니다.  
  
 [!code-xml[EDM_Example_Model#ComplexTypeExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books2.edmx#complextypeexample)]  
  
 위의 `Address` 복합 형식을 엔터티 형식의 속성으로 정의하려면 엔터티 형식 정의에서 속성 형식을 선언해야 합니다. 다음 CSDL에서는 `Address` 속성을 엔터티 형식(Publisher)의 복합 형식으로 선언합니다.  
  
 [!code-xml[EDM_Example_Model#EntityWithComplexType](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books3.edmx#entitywithcomplextype)]  
  
## <a name="see-also"></a>참고자료

- [엔터티 데이터 모델의 주요 개념](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [엔터티 데이터 모델](../../../../docs/framework/data/adonet/entity-data-model.md)
