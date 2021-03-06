---
title: 함수 오버로드 확인(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 9c648054-3808-4a69-9d3e-98e6a4f9c5ca
ms.openlocfilehash: 0248fdd3f3ba6afb5c7edca740d9aad3ca74bd03
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62034179"
---
# <a name="function-overload-resolution-entity-sql"></a>함수 오버로드 확인(Entity SQL)
이 항목에서는 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 함수의 확인 방법에 대해 설명합니다.  
  
 함수의 서명이 고유하다면 함수 두 개 이상을 동일한 이름으로 정의할 수 있습니다.  
  
 이런 경우 특정 식이 어느 함수를 참조하는지 확인하려면 다음 기준을 적용해야 합니다. 이 기준은 차례로 적용됩니다. 하나의 함수에만 적용되는 첫 번째 기준은 확인된 함수입니다.  
  
1. **매개 변수 번호**합니다. 함수의 매개 변수 개수가 식에 지정된 것과 동일합니다.  
  
2. **형식의 정확한 일치**합니다. 함수의 각 인수 형식이 매개 변수 형식과 정확하게 일치하거나 null 리터럴입니다.  
  
3. **하위 형식의 일치**합니다. 함수의 각 인수 형식이 매개 변수 형식과 정확하게 일치하거나 그 형식의 하위 형식입니다. 또는 인수가 null 리터럴입니다. 여러 함수가 필요한 하위 형식 변환의 개수에서만 차이가 나는 경우, 하위 형식 변환의 개수가 가장 적은 함수가 확인된 함수입니다.  
  
4. **하위 형식 또는 형식 승격의 일치**합니다. 함수의 각 인수 형식이 매개 변수 형식과 정확하게 일치하거나 그 하위 형식이거나 그 형식으로 승격될 수 있습니다. 또는 인수가 null 리터럴입니다. 여러 함수가 하위 형식 변환 및 승격의 개수에서만 차이가 나는 경우, 하위 형식 변환 및 승격의 개수가 가장 적은 함수가 확인된 함수입니다.  
  
 이 중 어느 기준을 통해서도 하나의 함수가 선택되지 않는다면 함수 호출 식이 모호한 것입니다.  
  
 이러한 규칙을 사용하여 함수를 하나 추출할 수 있는 경우라도 인수가 매개 변수와 일치하지 않을 수 있습니다. 이런 경우에 오류가 발생합니다.  
  
 사용자 정의 함수의 경우에는 이 함수와 더 잘 일치하는 서명이 있는 모델 정의 함수가 있더라도 인라인 쿼리 함수 정의가 우선적으로 적용됩니다.  
  
## <a name="see-also"></a>참고자료

- [엔터티 SQL 참조](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [Entity SQL 개요](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
- [함수](../../../../../../docs/framework/data/adonet/ef/language-reference/functions-entity-sql.md)
