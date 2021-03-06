---
title: '방법: Windows Forms ProgressBar 컨트롤에서 표시하는 값 설정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ProgressBar control [Windows Forms], setting value displayed
- progress controls [Windows Forms], setting value displayed
ms.assetid: 0e5010ad-1e9a-4271-895e-5a3d24d37a26
ms.openlocfilehash: 42a9e0f67f00c1a706b72ab0eeb522e99d8a8dfe
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61912849"
---
# <a name="how-to-set-the-value-displayed-by-the-windows-forms-progressbar-control"></a>방법: Windows Forms ProgressBar 컨트롤에서 표시하는 값 설정
> [!IMPORTANT]
>  <xref:System.Windows.Forms.ToolStripProgressBar> 컨트롤은 <xref:System.Windows.Forms.ProgressBar> 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 <xref:System.Windows.Forms.ProgressBar> 컨트롤을 계속 유지하도록 선택할 수 있습니다.  
  
 합니다 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 내에서 지정된 된 값을 표시 하려면 여러 가지 방법으로 사용 하면는 <xref:System.Windows.Forms.ProgressBar> 제어 합니다. 어떤 방법을 선택 하는 작업에 또는 해결 하려는 문제에 따라 달라 집니다. 다음 표에서 선택할 수 있습니다 방법을 보여 줍니다.  
  
|방식|설명|  
|--------------|-----------------|  
|값을 설정 합니다 <xref:System.Windows.Forms.ProgressBar> 직접 제어 합니다.|이 방법은 포함 될, 데이터 원본에서 레코드를 읽기와 같은 항목의 총 개수를 알고 있는 작업에 유용 합니다. 또한 값을 한 번 또는 두 번 설정 해야 하는 경우 이것이 쉬운 것입니다. 마지막으로, 진행률 표시줄이 표시 되는 값을 감소 하는 경우에이 프로세스를 사용 합니다.|  
|향상 된 <xref:System.Windows.Forms.ProgressBar> 고정된 값으로 표시 합니다.|이 방식은 최소값 및 최대값, 경과 시간 또는 알려진된 총에서 처리 된 파일 수와 같은 간에 단순한 수를 표시 하는 경우에 유용 합니다.|  
|향상 된 <xref:System.Windows.Forms.ProgressBar> 달라 지는 값으로 표시 합니다.|이 방식은 다릅니다의 횟수를 표시 된 값을 변경 해야 할 경우에 유용 합니다. 일련의 파일을 디스크에 쓰는 동안 사용 되는 하드 디스크 공간의 크기 예가 표시 됩니다.|  
  
 진행률 표시줄이 표시 되는 값을 설정 하는 가장 직접적인 방법은 설정 된 경우는 <xref:System.Windows.Forms.ProgressBar.Value%2A> 속성입니다. 디자인 타임 또는 런타임 시 수행할 수 있습니다.  
  
### <a name="to-set-the-progressbar-value-directly"></a>ProgressBar 값을 직접 설정 하려면  
  
1. 설정 된 <xref:System.Windows.Forms.ProgressBar> 컨트롤의 <xref:System.Windows.Forms.ProgressBar.Minimum%2A> 고 <xref:System.Windows.Forms.ProgressBar.Maximum%2A> 값입니다.  
  
2. 코드에서 컨트롤의 설정 <xref:System.Windows.Forms.ProgressBar.Value%2A> 속성을 설정 하는 최소값과 최대값 사이의 정수 값입니다.  
  
    > [!NOTE]
    >  설정 하는 경우는 <xref:System.Windows.Forms.ProgressBar.Value%2A> 경계 외부에 의해 설정 된 속성을 <xref:System.Windows.Forms.ProgressBar.Minimum%2A> 및 <xref:System.Windows.Forms.ProgressBar.Maximum%2A> 속성, 컨트롤 throw는 <xref:System.ArgumentException> 예외.  
  
     다음 코드 예제를 설정 하는 방법을 보여 줍니다는 <xref:System.Windows.Forms.ProgressBar> 직접 값입니다. 코드를 데이터 원본에서 레코드를 읽고 데이터 레코드를 읽을 때마다 진행률 표시줄 및 레이블을 업데이트 합니다. 이 예제에서는 폼에는 <xref:System.Windows.Forms.Label> 컨트롤을 <xref:System.Windows.Forms.ProgressBar> 컨트롤과 라는 행이 있는 데이터 테이블 `CustomerRow` 사용 하 여 `FirstName` 및 `LastName` 필드.  
  
    ```vb  
    Public Sub CreateNewRecords()  
       ' Sets the progress bar's Maximum property to  
       ' the total number of records to be created.  
       ProgressBar1.Maximum = 20  
  
       ' Creates a new record in the dataset.  
       ' NOTE: The code below will not compile, it merely  
       ' illustrates how the progress bar would be used.  
       Dim anyRow As CustomerRow = DatasetName.ExistingTable.NewRow  
       anyRow.FirstName = "Stephen"  
       anyRow.LastName = "James"  
       ExistingTable.Rows.Add(anyRow)  
  
       ' Increases the value displayed by the progress bar.  
       ProgressBar1.Value += 1  
       ' Updates the label to show that a record was read.  
       Label1.Text = "Records Read = " & ProgressBar1.Value.ToString()  
    End Sub  
    ```  
  
    ```csharp  
    public void createNewRecords()  
    {  
       // Sets the progress bar's Maximum property to  
       // the total number of records to be created.  
       progressBar1.Maximum = 20;  
  
       // Creates a new record in the dataset.  
       // NOTE: The code below will not compile, it merely  
       // illustrates how the progress bar would be used.  
       CustomerRow anyRow = DatasetName.ExistingTable.NewRow();  
       anyRow.FirstName = "Stephen";  
       anyRow.LastName = "James";  
       ExistingTable.Rows.Add(anyRow);  
  
       // Increases the value displayed by the progress bar.  
       progressBar1.Value += 1;  
       // Updates the label to show that a record was read.  
       label1.Text = "Records Read = " + progressBar1.Value.ToString();  
    }  
    ```  
  
     값을 설정할 수 있으며 증가 하는 메서드를 호출 하는 다음 일정된 한 간격으로 진행 되는 진행률을 표시 하는 경우는 <xref:System.Windows.Forms.ProgressBar> 해당 간격에 따라 컨트롤의 값입니다. 타이머 및 여기서 진행률 전체에 대 한 백분율로 측정 하지 않는 다른 시나리오에 유용 합니다.  
  
### <a name="to-increase-the-progress-bar-by-a-fixed-value"></a>고정된 값으로 진행률 표시줄을 증가 시키려면  
  
1. 설정 된 <xref:System.Windows.Forms.ProgressBar> 컨트롤의 <xref:System.Windows.Forms.ProgressBar.Minimum%2A> 고 <xref:System.Windows.Forms.ProgressBar.Maximum%2A> 값입니다.  
  
2. 컨트롤의 설정 <xref:System.Windows.Forms.ProgressBar.Step%2A> 진행률 표시줄의 증가 크기를 나타내는 정수를 속성 값을 표시 합니다.  
  
3. 호출 된 <xref:System.Windows.Forms.ProgressBar.PerformStep%2A> 에 설정 된 값으로 표시 되는 값을 변경 하는 방법의 <xref:System.Windows.Forms.ProgressBar.Step%2A> 속성입니다.  
  
     다음 코드 예제는 진행률 표시줄 복사 작업에서 파일의 수를 유지할 수 있습니다 하는 방법을 보여 줍니다.  
  
     다음 예제에서는 각 파일을 메모리로 읽는 진행률 표시줄 및 레이블 읽기의 총 파일 수를 반영 하도록 업데이트 됩니다. 이 예제에서는 폼에는 <xref:System.Windows.Forms.Label> 컨트롤 및 <xref:System.Windows.Forms.ProgressBar> 제어 합니다.  
  
    ```vb  
    Public Sub LoadFiles()  
       ' Sets the progress bar's minimum value to a number representing  
       ' no operations complete -- in this case, no files read.  
       ProgressBar1.Minimum = 0  
       ' Sets the progress bar's maximum value to a number representing  
       ' all operations complete -- in this case, all five files read.  
       ProgressBar1.Maximum = 5  
       ' Sets the Step property to amount to increase with each iteration.  
       ' In this case, it will increase by one with every file read.  
       ProgressBar1.Step = 1  
  
       ' Dimensions a counter variable.  
       Dim i As Integer  
       ' Uses a For...Next loop to iterate through the operations to be  
       ' completed. In this case, five files are to be copied into memory,  
       ' so the loop will execute 5 times.  
       For i = 0 To 4  
          ' Insert code to copy a file  
          ProgressBar1.PerformStep()  
          ' Update the label to show that a file was read.  
          Label1.Text = "# of Files Read = " & ProgressBar1.Value.ToString  
       Next i  
    End Sub  
    ```  
  
    ```csharp  
    public void loadFiles()  
    {  
       // Sets the progress bar's minimum value to a number representing  
       // no operations complete -- in this case, no files read.  
       progressBar1.Minimum = 0;  
       // Sets the progress bar's maximum value to a number representing  
       // all operations complete -- in this case, all five files read.  
       progressBar1.Maximum = 5;  
       // Sets the Step property to amount to increase with each iteration.  
       // In this case, it will increase by one with every file read.  
       progressBar1.Step = 1;  
  
       // Uses a for loop to iterate through the operations to be  
       // completed. In this case, five files are to be copied into memory,  
       // so the loop will execute 5 times.  
       for (int i = 0; i <= 4; i++)  
       {  
          // Inserts code to copy a file  
          progressBar1.PerformStep();  
          // Updates the label to show that a file was read.  
          label1.Text = "# of Files Read = " + progressBar1.Value.ToString();  
       }  
    }  
    ```  
  
     마지막으로 증가할 때마다 고유 금액이 있도록 진행률 표시줄에 표시 되는 값을 늘릴 수 있습니다. 이렇게 하면 되는 추적 일련의 하드 디스크, 다양 한 크기의 파일을 쓰거나 전체 백분율로 진행률을 측정 같은 고유 작업을 하는 경우에 유용 합니다.  
  
### <a name="to-increase-the-progress-bar-by-a-dynamic-value"></a>동적 값으로 진행률 표시줄을 증가 시키려면  
  
1. 설정 된 <xref:System.Windows.Forms.ProgressBar> 컨트롤의 <xref:System.Windows.Forms.ProgressBar.Minimum%2A> 고 <xref:System.Windows.Forms.ProgressBar.Maximum%2A> 값입니다.  
  
2. 호출 된 <xref:System.Windows.Forms.ProgressBar.Increment%2A> 지정한 정수로 표시 되는 값을 변경 하는 방법입니다.  
  
     다음 코드 예제에서는 어떻게 복사 작업 동안 사용 된 디스크 공간의 양을 진행률 표시줄을 계산할 수를 보여 줍니다.  
  
     다음 예제에서는 각 파일은 하드 디스크에 기록 될 때 진행률 표시줄 및 레이블을 사용 가능한 하드 디스크 공간의 크기를 반영 하도록 업데이트 됩니다. 이 예제에서는 폼에는 <xref:System.Windows.Forms.Label> 컨트롤 및 <xref:System.Windows.Forms.ProgressBar> 제어 합니다.  
  
    ```vb  
    Public Sub ReadFiles()  
       ' Sets the progress bar's minimum value to a number   
       ' representing the hard disk space before the files are read in.  
       ' You will most likely have to set this using a system call.  
       ' NOTE: The code below is meant to be an example and  
       ' will not compile.  
       ProgressBar1.Minimum = AvailableDiskSpace()  
       ' Sets the progress bar's maximum value to a number   
       ' representing the total hard disk space.  
       ' You will most likely have to set this using a system call.  
       ' NOTE: The code below is meant to be an example   
       ' and will not compile.  
       ProgressBar1.Maximum = TotalDiskSpace()  
  
       ' Dimension a counter variable.  
       Dim i As Integer  
       ' Uses a For...Next loop to iterate through the operations to be  
       ' completed. In this case, five files are to be written to the disk,  
       ' so it will execute the loop 5 times.  
       For i = 1 To 5  
          ' Insert code to read a file into memory and update file size.  
          ' Increases the progress bar's value based on the size of   
          ' the file currently being written.  
          ProgressBar1.Increment(FileSize)  
          ' Updates the label to show available drive space.  
          Label1.Text = "Current Disk Space Used = " &_   
          ProgressBar1.Value.ToString()  
       Next i  
    End Sub  
    ```  
  
    ```csharp  
    public void readFiles()  
    {  
       // Sets the progress bar's minimum value to a number   
       // representing the hard disk space before the files are read in.  
       // You will most likely have to set this using a system call.  
       // NOTE: The code below is meant to be an example and   
       // will not compile.  
       progressBar1.Minimum = AvailableDiskSpace();  
       // Sets the progress bar's maximum value to a number   
       // representing the total hard disk space.  
       // You will most likely have to set this using a system call.  
       // NOTE: The code below is meant to be an example   
       // and will not compile.  
       progressBar1.Maximum = TotalDiskSpace();  
  
       // Uses a for loop to iterate through the operations to be  
       // completed. In this case, five files are to be written  
       // to the disk, so it will execute the loop 5 times.  
       for (int i = 1; i<= 5; i++)  
       {  
          // Insert code to read a file into memory and update file size.  
          // Increases the progress bar's value based on the size of   
          // the file currently being written.  
          progressBar1.Increment(FileSize);  
          // Updates the label to show available drive space.  
          label1.Text = "Current Disk Space Used = " + progressBar1.Value.ToString();  
       }  
    }  
    ```  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.ProgressBar>
- <xref:System.Windows.Forms.ToolStripProgressBar>
- [ProgressBar 컨트롤 개요](progressbar-control-overview-windows-forms.md)
- [ProgressBar 컨트롤](progressbar-control-windows-forms.md)
