---
title: OpenFileDialog 구성 요소 개요(Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- OpenFileDialog
helpviewer_keywords:
- OpenFileDialog component [Windows Forms], about OpenFileDialog
- Open File dialog box [Windows Forms], displaying in Windows Forms
ms.assetid: cd717300-46b6-4f82-8207-b218fa7fa407
ms.openlocfilehash: ec275a5923d332d23205c79442fa23bc6e402e3f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61804561"
---
# <a name="openfiledialog-component-overview-windows-forms"></a>OpenFileDialog 구성 요소 개요(Windows Forms)
Windows Forms <xref:System.Windows.Forms.OpenFileDialog> 구성 요소는 미리 구성된 대화 상자입니다. 동일 **열려 있는 파일** Windows 운영 체제에서 노출 하는 대화 상자. <xref:System.Windows.Forms.CommonDialog> 클래스에서 상속됩니다.  
  
## <a name="using-this-component"></a>이 구성 요소를 사용 하 여  
 고유한 대화 상자를 구성 하는 대신 파일 선택을 위한 간단한 솔루션으로 Windows 기반 응용 프로그램 내에서이 구성 요소를 사용 합니다. 표준 Windows 대화 상자를 사용하여 기본 기능이 사용자에게 익숙한 응용 프로그램을 만듭니다. 그러나 때 사용 하는 <xref:System.Windows.Forms.OpenFileDialog> 구성 요소를 사용자 고유의 파일 열기 논리를 작성 해야 합니다.  
  
 사용 된 <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> 런타임에 대화 상자를 표시 하는 방법입니다. 사용자가 다중 선택 파일을 사용 하 여 열 수를 설정할 수 있습니다.는 <xref:System.Windows.Forms.OpenFileDialog.Multiselect%2A> 속성입니다. 또한 사용할 수는 <xref:System.Windows.Forms.OpenFileDialog.ShowReadOnly%2A> 속성을 읽기 전용 확인란이 대화 상자에 나타납니다. <xref:System.Windows.Forms.OpenFileDialog.ReadOnlyChecked%2A> 속성은 읽기 전용 확인란이 선택 되었는지 여부를 나타냅니다. 마지막으로 <xref:System.Windows.Forms.FileDialog.Filter%2A> 속성 대화 상자에서 "파일 형식" 상자에 표시 되는 형식을 결정 합니다는 현재 파일 이름 필터 문자열을 설정 합니다.  
  
 폼에 추가 될 때를 <xref:System.Windows.Forms.OpenFileDialog> 구성 요소가 Windows Forms 디자이너 아래쪽에 있는 트레이에 나타납니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.OpenFileDialog>
- [OpenFileDialog 구성 요소](openfiledialog-component-windows-forms.md)
