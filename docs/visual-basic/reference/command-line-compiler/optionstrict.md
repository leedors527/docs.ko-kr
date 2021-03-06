---
title: -optionstrict
ms.date: 07/20/2015
f1_keywords:
- -optionstrict
helpviewer_keywords:
- -optionstrict compiler option [Visual Basic]
- optionstrict compiler option [Visual Basic]
- /optionstrict compiler option [Visual Basic]
ms.assetid: c7b10086-0fa4-49db-b3c8-4ae0db5957da
ms.openlocfilehash: e18fe451ea4a80ac959ed61b66394920f8bf177f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61788936"
---
# <a name="-optionstrict"></a>-optionstrict
암시적 형식 변환을 제한 하려면 엄격한 형식 의미 체계를 적용 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
-optionstrict[+ | -]  
-optionstrict[:custom]  
```  
  
## <a name="arguments"></a>인수  
 `+` &#124; `-`  
 선택 사항입니다. `-optionstrict+` 옵션으로 암시적 형식 변환을 제한 합니다. 이 옵션의 기본값은 `-optionstrict-`합니다. 합니다 `-optionstrict+` 옵션은 동일 `-optionstrict`합니다. 관대 한 형식 의미 체계를 둘 다를 사용할 수 있습니다.  
  
 `custom`  
 필수 요소. 엄격한 언어 의미 체계를 준수 하지 않을 경우 경고 합니다.  
  
## <a name="remarks"></a>설명  
 때 `-optionstrict+` 가 적용 된 경우 확장 형식 변환만 암시적으로 만들 수 있습니다. 암시적 축소 형식 변환, 할당 하는 등을 `Decimal` 입력 개체를 정수 형식 개체로, 오류로 보고 됩니다.  
  
 암시적 축소 형식 변환에 대 한 경고를 생성 하려면 사용 하 여 `-optionstrict:custom`입니다. 사용 하 여 `-nowarn:numberlist` 특정 경고를 무시 하 고 `-warnaserror:numberlist` 특정 경고를 오류로 처리 하도록 합니다.  
  
### <a name="to-set--optionstrict-in-the-visual-studio-ide"></a>-Optionstrict Visual Studio IDE에서 설정 하려면  
  
1. **솔루션 탐색기**에서 프로젝트를 선택합니다. 에 **프로젝트** 메뉴에서 클릭 **속성입니다.**   
  
2. **컴파일** 탭을 클릭합니다.  
  
3. 값을 수정 합니다 **Option Strict** 상자입니다.  
  
### <a name="to-set--optionstrict-programmatically"></a>-Optionstrict를 프로그래밍 방식으로 설정 하려면  
  
- 참조 [Option Strict 문](../../../visual-basic/language-reference/statements/option-strict-statement.md)합니다.  
  
## <a name="example"></a>예제  
 다음 코드에서는 `Test.vb` 엄격한 형식 의미 체계를 사용 합니다.  
  
```console
vbc -optionstrict+ test.vb  
```  
  
## <a name="see-also"></a>참고자료

- [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)
- [-optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [-optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)
- [-optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [-nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md)
- [-warnaserror (Visual Basic)](../../../visual-basic/reference/command-line-compiler/warnaserror.md)
- [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Option Strict 문](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [옵션 대화 상자, 프로젝트, Visual Basic 기본값](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
