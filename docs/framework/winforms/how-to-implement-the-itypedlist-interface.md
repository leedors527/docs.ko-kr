---
title: '방법: ITypedList 인터페이스 구현'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ITypedList interface
- BindingList(Of T) class
- data binding [Windows Forms], implementing
- IBindingList interface
ms.assetid: 834cc15c-50bc-4a8b-a610-313d6a217357
ms.openlocfilehash: 2463a9c77a9836ff251e799056cc5131bf6c99e0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61800859"
---
# <a name="how-to-implement-the-itypedlist-interface"></a>방법: ITypedList 인터페이스 구현
구현 된 <xref:System.ComponentModel.ITypedList> 인터페이스 바인딩 가능한 목록에 대 한 스키마 검색을 사용 하도록 설정 합니다.  
  
## <a name="example"></a>예제  
 다음 코드 예제를 구현 하는 방법에 설명 합니다 <xref:System.ComponentModel.ITypedList> 인터페이스입니다. 라는 제네릭 형식은 `SortableBindingList` 에서 파생 되는 <xref:System.ComponentModel.BindingList%601> 클래스를 구현 합니다 <xref:System.ComponentModel.ITypedList> 인터페이스입니다. 이라는 간단한 클래스 `Customer` 의 헤더에 바인딩되는 데이터를 제공 된 <xref:System.Windows.Forms.DataGridView> 제어 합니다.  
  
 [!code-csharp[System.ComponentModel.ITypedList#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.ITypedList/CS/SortableBindingList.cs#1)]
 [!code-vb[System.ComponentModel.ITypedList#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.ITypedList/VB/SortableBindingList.vb#1)]  
  
 [!code-csharp[System.ComponentModel.ITypedList#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.ITypedList/CS/Customer.cs#10)]
 [!code-vb[System.ComponentModel.ITypedList#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.ITypedList/VB/Customer.vb#10)]  
  
 [!code-csharp[System.ComponentModel.ITypedList#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.ITypedList/CS/Form1.cs#100)]
 [!code-vb[System.ComponentModel.ITypedList#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.ITypedList/VB/Form1.vb#100)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
- System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조  
  
## <a name="see-also"></a>참고자료

- <xref:System.ComponentModel.ITypedList>
- <xref:System.ComponentModel.BindingList%601>
- <xref:System.ComponentModel.IBindingList>
- [데이터 바인딩 및 Windows Forms](data-binding-and-windows-forms.md)
