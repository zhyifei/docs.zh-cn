---
title: 设置进度栏控件显示的值
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ProgressBar control [Windows Forms], setting value displayed
- progress controls [Windows Forms], setting value displayed
ms.assetid: 0e5010ad-1e9a-4271-895e-5a3d24d37a26
ms.openlocfilehash: d295079a96ca19a4e4c98e113a3f3051c6403182
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141806"
---
# <a name="how-to-set-the-value-displayed-by-the-windows-forms-progressbar-control"></a>如何：设置 Windows 窗体 ProgressBar 控件显示的值
> [!IMPORTANT]
> <xref:System.Windows.Forms.ToolStripProgressBar> 控件取代了 <xref:System.Windows.Forms.ProgressBar> 控件并添加了功能；但是，可以选择保留 <xref:System.Windows.Forms.ProgressBar> 控件以实现向后兼容并供将来使用。  
  
 .NET 框架为您提供了几种在<xref:System.Windows.Forms.ProgressBar>控件中显示给定值的不同方法。 您选择的方法将取决于手头的任务或正在解决的问题。 下表显示了您可以选择的方法。  
  
|方法|说明|  
|--------------|-----------------|  
|直接设置<xref:System.Windows.Forms.ProgressBar>控件的值。|此方法对于知道将涉及的项总数（例如从数据源读取记录）的任务非常有用。 此外，如果您只需要设置该值一次或两次，这是一种简单的方法。 最后，如果需要减小进度条显示的值，请使用此过程。|  
|增加<xref:System.Windows.Forms.ProgressBar>显示值。|当您在最小值和最大值之间显示简单计数（如已用时间或从已知总数中处理的文件数）时，此方法非常有用。|  
|增加<xref:System.Windows.Forms.ProgressBar>显示量，该值各不相同。|当您需要以不同数量多次更改显示的值时，此方法非常有用。 例如，显示在将一系列文件写入磁盘时消耗的硬盘空间量。|  
  
 设置进度条显示的值的最直接方法是设置<xref:System.Windows.Forms.ProgressBar.Value%2A>属性。 这可以在设计时或运行时完成。  
  
### <a name="to-set-the-progressbar-value-directly"></a>直接设置进度栏值  
  
1. 设置<xref:System.Windows.Forms.ProgressBar>控件和<xref:System.Windows.Forms.ProgressBar.Minimum%2A><xref:System.Windows.Forms.ProgressBar.Maximum%2A>值。  
  
2. 在代码中，将控件的属性<xref:System.Windows.Forms.ProgressBar.Value%2A>设置为已建立的最小值和最大值之间的整数值。  
  
    > [!NOTE]
    > 如果将<xref:System.Windows.Forms.ProgressBar.Value%2A>属性设置为 和<xref:System.Windows.Forms.ProgressBar.Minimum%2A><xref:System.Windows.Forms.ProgressBar.Maximum%2A>属性建立的边界之外，则控件将引发异常。 <xref:System.ArgumentException>  
  
     以下代码示例说明了如何直接设置<xref:System.Windows.Forms.ProgressBar>值。 代码从数据源读取记录，并在每次读取数据记录时更新进度栏和标签。 此示例要求窗体<xref:System.Windows.Forms.Label>具有控件、<xref:System.Windows.Forms.ProgressBar>控件和具有名为`CustomerRow`和`FirstName`字段`LastName`的行的数据表。  
  
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
  
     如果要显示按固定间隔继续的进度，则可以设置该值，然后调用一个方法，该方法按该间隔增加<xref:System.Windows.Forms.ProgressBar>控件的值。 这对于计时器和其他方案非常有用，因为计时器和其他方案没有将进度作为整个百分比来衡量。  
  
### <a name="to-increase-the-progress-bar-by-a-fixed-value"></a>将进度条增加一个固定值  
  
1. 设置<xref:System.Windows.Forms.ProgressBar>控件和<xref:System.Windows.Forms.ProgressBar.Minimum%2A><xref:System.Windows.Forms.ProgressBar.Maximum%2A>值。  
  
2. 将控件的属性<xref:System.Windows.Forms.ProgressBar.Step%2A>设置为表示金额的整数，以增加进度条的显示值。  
  
3. 调用<xref:System.Windows.Forms.ProgressBar.PerformStep%2A>方法以更改<xref:System.Windows.Forms.ProgressBar.Step%2A>属性中设置的金额显示的值。  
  
     以下代码示例说明了进度栏如何维护复制操作中文件的计数。  
  
     在下面的示例中，当每个文件读入内存时，进度栏和标签将更新以反映读取的总文件。 此示例要求窗体具有控件<xref:System.Windows.Forms.Label>和<xref:System.Windows.Forms.ProgressBar>控件。  
  
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
  
     最后，您可以增加进度条显示的值，以便每次增加都是唯一的量。 当您跟踪一系列独特的操作（例如将不同大小的文件写入硬盘或测量进度作为整个百分比）时，这非常有用。  
  
### <a name="to-increase-the-progress-bar-by-a-dynamic-value"></a>按动态值增加进度条  
  
1. 设置<xref:System.Windows.Forms.ProgressBar>控件和<xref:System.Windows.Forms.ProgressBar.Minimum%2A><xref:System.Windows.Forms.ProgressBar.Maximum%2A>值。  
  
2. 调用<xref:System.Windows.Forms.ProgressBar.Increment%2A>方法以更改指定整数显示的值。  
  
     以下代码示例说明了进度条如何计算复制操作期间使用的磁盘空间量。  
  
     在下面的示例中，当每个文件写入硬盘时，进度栏和标签将更新以反映可用的硬盘空间量。 此示例要求窗体具有控件<xref:System.Windows.Forms.Label>和<xref:System.Windows.Forms.ProgressBar>控件。  
  
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
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.ProgressBar>
- <xref:System.Windows.Forms.ToolStripProgressBar>
- [ProgressBar 控件概述](progressbar-control-overview-windows-forms.md)
- [ProgressBar 控件](progressbar-control-windows-forms.md)
