---
title: 숫자 시퀀스에서 최소값 찾기
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 78203093-f242-4572-9b31-9495b10926aa
ms.openlocfilehash: 84002609c550cc2de76f9948bf77f9fd88261f64
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62038456"
---
# <a name="find-the-minimum-value-in-a-numeric-sequence"></a>숫자 시퀀스에서 최소값 찾기
<xref:System.Linq.Enumerable.Min%2A> 연산자를 사용하여 숫자 값 시퀀스의 최소값을 반환합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 제품의 최저 단가를 찾습니다.  
  
 이 쿼리를 Northwind 샘플 데이터베이스에 대해 실행하면 `2.5000`이 출력됩니다.  
  
 [!code-csharp[DLinqQueryExamples#9](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#9)]
 [!code-vb[DLinqQueryExamples#9](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#9)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 주문의 최소 운송 금액을 찾습니다.  
  
 이 쿼리를 Northwind 샘플 데이터베이스에 대해 실행하면 `0.0200`이 출력됩니다.  
  
 [!code-csharp[DLinqQueryExamples#10](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#10)]
 [!code-vb[DLinqQueryExamples#10](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#10)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 Min을 사용하여 각 범주에서 최저 단가의 `Products`를 찾습니다. 출력은 범주별로 정렬됩니다.  
  
 [!code-csharp[DLinqQueryExamples#11](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#11)]
 [!code-vb[DLinqQueryExamples#11](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#11)]  
  
 Northwind 샘플 데이터베이스에 대해 이전 쿼리를 실행할 경우 결과는 다음과 비슷합니다.  
  
 `1`  
  
 `Guaraná Fantástica`  
  
 `2`  
  
 `Aniseed Syrup`  
  
 `3`  
  
 `Teatime Chocolate Biscuits`  
  
 `4`  
  
 `Geitost`  
  
 `5`  
  
 `Filo Mix`  
  
 `6`  
  
 `Tourtière`  
  
 `7`  
  
 `Longlife Tofu`  
  
 `8`  
  
 `Konbu`  
  
## <a name="see-also"></a>참고자료

- [집계 쿼리](../../../../../../docs/framework/data/adonet/sql/linq/aggregate-queries.md)
- [샘플 데이터베이스 다운로드](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
