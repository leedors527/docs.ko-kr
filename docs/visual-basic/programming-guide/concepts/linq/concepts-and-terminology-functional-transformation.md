---
title: 개념과 용어 (함수 변환) (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 24fd244d-ebae-4721-8858-89bb544aea0b
ms.openlocfilehash: c6308185b39651095482dca434ce25d717bd5e6b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61663481"
---
# <a name="concepts-and-terminology-functional-transformation-visual-basic"></a>개념과 용어 (함수 변환) (Visual Basic)
이 항목에서는 순수 함수 변환의 개념과 용어에 대해 소개합니다. 데이터 변환에 대한 함수 변환 방법은 전통적인 명령형 프로그래밍보다 신속하게 프로그래밍할 수 있고 표현이 다양하며 디버깅과 유지 관리가 쉬운 코드를 생성합니다.  
  
 이 단원의 항목에서는 함수형 프로그래밍에 대해 전체적으로 설명하지 않고 XML의 모양을 쉽게 변환하는 데 사용할 수 있는 몇 가지 함수형 프로그래밍 기능만 살펴봅니다.  
  
## <a name="what-is-pure-functional-transformation"></a>순수 함수 변환이란?  
 *순수 함수 변환*에서 *순수 함수*라는 일련의 함수는 구조화된 데이터의 집합을 원래 형태에서 다른 형태로 변환하는 방법을 정의합니다. "순수"라는 단어는 함수가 *구성 가능(composable)* 함을 의미합니다. 구성 가능한 함수에는 다음과 같은 특징이 있습니다.  
  
- *자체 포함*됩니다. 프로그램의 나머지 부분과 상호 종속되거나 얽히는 일 없이 함수가 자유롭게 정렬되고 다시 정렬될 수 있습니다. 순수 변환은 환경에 대한 지식이 없고 환경에 영향을 미치지 않습니다. 즉, 변환에 사용되는 함수가 *의도하지 않은 결과*를 발생시키지 않습니다.  
  
- *상태 비저장*입니다. 동일한 입력에 대해 동일한 함수나 특정 함수 집합을 실행하면 항상 같은 결과가 발생합니다. 순수 변환은 이전 사용에 대한 기록을 갖고 있지 않습니다.  
  
> [!IMPORTANT]
>  이 자습서의 나머지 부분에서 "순수 함수"라는 용어는 특정 언어 기능이 아니라 프로그래밍 방법을 나타내기 위해 일반적인 의미에서 사용되었습니다.  
>   
>  참고 순수 함수는 Visual Basic에서는 함수로 구현 되어야 합니다.  
>   
>  또한 순수 함수와 C++의 순수 가상 메서드를 혼동하면 안 됩니다. 순수 가상 메서드의 경우 포함하는 클래스가 추상 클래스이고 메서드 본문이 제공되지 않습니다.  
  
### <a name="functional-programming"></a>함수형 프로그래밍  
 *함수형 프로그래밍*은 순수 함수 변환을 직접 지원하는 프로그래밍 방법입니다.  
  
 지금까지 ML, Scheme, Haskell 및 F#과 같은 범용 함수형 프로그래밍 언어는 주로 학계에서 관심을 가졌습니다. 있었지만 항상 Visual Basic의 순수 함수 변환을 작성할 수, 이렇게 하면 어렵게 따라서 하지 있게 되었습니다 대부분의 프로그래머에 게 매력적인 옵션. 그러나 이후 버전의 Visual Basic을 사용 하 여 새로운 언어와 같은 구문이 람다 식 및 형식 유추 있도록 함수형 프로그래밍 훨씬 쉽고 더 생산적으로 합니다.  
  
 함수형 프로그래밍에 대한 자세한 내용은 [함수형 프로그래밍 및 명령형 프로그래밍 비교 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/functional-programming-vs-imperative-programming.md)합니다.  
  
#### <a name="domain-specific-fp-languages"></a>영역별 FP 언어  
 범용 프로그래밍 언어가 널리 채택되지는 않았지만 특정 영역별 함수형 프로그래밍 언어는 보다 성공적이었습니다. 예를 들어, CSS 스타일시트는 많은 웹 페이지의 모양과 느낌을 결정하는 데 사용되고 XSLT(Extensible Stylesheet Language Transformation) 스타일시트는 XML 데이터 조작에서 광범위하게 사용됩니다. XSLT에 대한 자세한 내용은 [XSLT 변환](../../../../standard/data/xml/xslt-transformations.md)을 참조하세요.  
  
## <a name="terminology"></a>용어  
 다음 표에는 함수 변환과 관련된 몇 가지 용어가 정의되어 있습니다.  
  
 고차(1급) 함수  
 프로그램 개체로 취급할 수 있는 함수입니다. 예를 들어, 고차 함수는 다른 함수로 전달되거나 다른 함수에서 반환될 수 있습니다. Visual basic에서 대리자와 람다 식은 고차 함수를 지 원하는 언어 기능 됩니다. 고차 함수를 작성하려면 하나 이상의 인수를 선언하여 대리자를 사용하며, 고차 함수를 호출할 때는 흔히 람다 식을 사용합니다. 대부분의 표준 쿼리 연산자가 고차 함수입니다.  
  
 자세한 내용은 [표준 쿼리 연산자 개요 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)합니다.  
  
 람다 식  
 대리자 형식이 예상되는 곳에서 항상 사용할 수 있는 인라인 익명 함수입니다. 이는 람다 식에 대한 간략한 정의이지만 이 자습서의 목적에 적합합니다.  
  
 자세한 내용은 [람다 식](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)을 참조하세요.  
  
 컬렉션  
 대개 동일한 형식을 갖고 있는 구조화된 데이터 집합입니다. LINQ와 호환되려면 컬렉션은 <xref:System.Collections.IEnumerable> 인터페이스나 <xref:System.Linq.IQueryable> 인터페이스(또는 해당하는 제네릭 항목인 <xref:System.Collections.Generic.IEnumerator%601> 또는 <xref:System.Linq.IQueryable%601> 중 하나)를 구현해야 합니다.  
  
 튜플(익명 형식)  
 수학적 개념인 튜플은 각각 특정한 형식을 가진 개체의 유한 시퀀스입니다. 튜플을 정렬된 목록이라고 하기도 합니다. 익명 형식은 이 개념을 언어에 구현한 것입니다. 익명 형식을 사용하여 명명되지 않은 클래스 형식을 선언하고 해당 형식의 개체를 동시에 인스턴스화할 수 있습니다.  
  
 자세한 내용은 [익명 형식](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)합니다.  
  
 형식 유추(암시적 형식 지정)  
 명시적 형식 선언이 없는 경우 컴파일러에서 변수의 형식을 결정하도록 하는 기능입니다.  
  
 자세한 내용은 [로컬 형식 유추](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)합니다.  
  
 지연된 실행 및 지연 계산  
 확인된 값이 실제로 필요할 때까지 식의 계산을 지연하는 것입니다. 지연된 실행은 컬렉션에서 지원됩니다.  
  
 자세한 내용은 [기본 쿼리 작업 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-query-operations.md) 하 고 [지연 된 실행과 지연 계산은 linq to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/deferred-execution-and-lazy-evaluation-in-linq-to-xml.md)합니다.  
  
 이러한 언어 기능은 이 단원 전반의 코드 샘플에서 사용됩니다.  
  
## <a name="see-also"></a>참고자료

- [순수 함수 변환 (Visual Basic) 소개](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md)
- [함수형 프로그래밍과 명령형 프로그래밍 비교 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/functional-programming-vs-imperative-programming.md)
