---
title: CheckBox 스타일 및 템플릿
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], CheckBox
- templates [WPF], CheckBox
- parts [WPF], CheckBox
- ControlTemplate [WPF], CheckBox
- CheckBox [WPF], styles and templates
- styles [WPF], CheckBox
ms.assetid: bfdaec96-d101-4d3d-864d-c27e6b621d03
ms.openlocfilehash: b3f417a676b141a4a6dbccfe51bf5b7abe669198
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61912420"
---
# <a name="checkbox-styles-and-templates"></a>CheckBox 스타일 및 템플릿
이 항목에서는 스타일 및 템플릿에 대해 설명 합니다 <xref:System.Windows.Controls.CheckBox> 제어 합니다. 기본값을 수정할 수 있습니다 <xref:System.Windows.Controls.ControlTemplate> 고유한 모양을 제어할 수 있습니다. 자세한 내용은 [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](customizing-the-appearance-of-an-existing-control.md)을 참조하세요.  
  
## <a name="checkbox-parts"></a>확인란을 선택 파트  
 <xref:System.Windows.Controls.CheckBox> 컨트롤에 명명된 된 파트가 없습니다.  
  
## <a name="checkbox-states"></a>CheckBox 상태  
 다음 표에서 대 한 시각적 상태를 <xref:System.Windows.Controls.CheckBox> 제어 합니다.  
  
|VisualState 이름|VisualStateGroup 이름|설명|  
|----------------------|---------------------------|-----------------|  
|보통|CommonStates|기본 상태입니다.|  
|MouseOver|CommonStates|마우스 포인터가 컨트롤 위에 있습니다.|  
|누름|CommonStates|컨트롤을 눌렀습니다.|  
|사용 안 함|CommonStates|컨트롤이 비활성화되었습니다.|  
|포커스 있음|FocusStates|컨트롤에 포커스가 있습니다.|  
|포커스 없음|FocusStates|컨트롤에 포커스가 없습니다.|  
|선택한 상태|CheckStates|<xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A>가 `true`인 경우|  
|선택 취소 되어 있음|CheckStates|<xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A>가 `false`인 경우|  
|비활성화|CheckStates|<xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A>가 `true`이고 <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A>이 `null`인 경우|  
|유효|ValidationStates|컨트롤에서 사용 된 <xref:System.Windows.Controls.Validation> 클래스 및 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `false`합니다.|  
|InvalidUnfocused|ValidationStates|합니다 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `true` 가 컨트롤에 포커스가 있습니다.|  
|InvalidFocused|ValidationStates|합니다 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `true` 가 컨트롤에 포커스가 없는 합니다.|  
  
## <a name="checkbox-controltemplate-example"></a>확인란 ControlTemplate 예제  
 다음 예제에서는 정의 하는 방법을 보여 줍니다는 <xref:System.Windows.Controls.ControlTemplate> 에 대 한는 <xref:System.Windows.Controls.CheckBox> 제어 합니다.  
  
 [!code-xaml[ControlTemplateExamples#CheckBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/checkbox.xaml#checkbox)]  
  
 앞의 예제에서는 다음 리소스를 하나 이상 사용합니다.  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 전체 샘플을 보려면 [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [Control 스타일 및 템플릿](control-styles-and-templates.md)
- [컨트롤 사용자 지정](control-customization.md)
- [스타일 지정 및 템플릿](styling-and-templating.md)
- [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](customizing-the-appearance-of-an-existing-control.md)
