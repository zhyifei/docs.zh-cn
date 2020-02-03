---
title: 设置 ProgressBar 控件显示的值
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ProgressBar control [Windows Forms], setting value displayed
- progress controls [Windows Forms], setting value displayed
ms.assetid: 0e5010ad-1e9a-4271-895e-5a3d24d37a26
ms.openlocfilehash: 79ce1e576652d00b323d31dfc6551e168ea0a9a0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743799"
---
# <a name="how-to-set-the-value-displayed-by-the-windows-forms-progressbar-control"></a><span data-ttu-id="fd010-102">如何：设置 Windows 窗体 ProgressBar 控件显示的值</span><span class="sxs-lookup"><span data-stu-id="fd010-102">How to: Set the Value Displayed by the Windows Forms ProgressBar Control</span></span>
> [!IMPORTANT]
> <span data-ttu-id="fd010-103"><xref:System.Windows.Forms.ToolStripProgressBar> 控件取代了 <xref:System.Windows.Forms.ProgressBar> 控件并添加了功能；但是，可以选择保留 <xref:System.Windows.Forms.ProgressBar> 控件以实现向后兼容并供将来使用。</span><span class="sxs-lookup"><span data-stu-id="fd010-103">The <xref:System.Windows.Forms.ToolStripProgressBar> control replaces and adds functionality to the <xref:System.Windows.Forms.ProgressBar> control; however, the <xref:System.Windows.Forms.ProgressBar> control is retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="fd010-104">.NET Framework 提供了几种不同的方法来在 <xref:System.Windows.Forms.ProgressBar> 控件中显示给定的值。</span><span class="sxs-lookup"><span data-stu-id="fd010-104">The .NET Framework gives you several different ways to display a given value within the <xref:System.Windows.Forms.ProgressBar> control.</span></span> <span data-ttu-id="fd010-105">选择哪种方法取决于手头的任务或要解决的问题。</span><span class="sxs-lookup"><span data-stu-id="fd010-105">Which approach you choose will depend on the task at hand or the problem you are solving.</span></span> <span data-ttu-id="fd010-106">下表显示了可以选择的方法。</span><span class="sxs-lookup"><span data-stu-id="fd010-106">The following table shows the approaches you can choose.</span></span>  
  
|<span data-ttu-id="fd010-107">方法</span><span class="sxs-lookup"><span data-stu-id="fd010-107">Approach</span></span>|<span data-ttu-id="fd010-108">说明</span><span class="sxs-lookup"><span data-stu-id="fd010-108">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="fd010-109">直接设置 <xref:System.Windows.Forms.ProgressBar> 控件的值。</span><span class="sxs-lookup"><span data-stu-id="fd010-109">Set the value of the <xref:System.Windows.Forms.ProgressBar> control directly.</span></span>|<span data-ttu-id="fd010-110">此方法对于你知道将涉及的项（如从数据源读取记录）的总数的任务非常有用。</span><span class="sxs-lookup"><span data-stu-id="fd010-110">This approach is useful for tasks where you know the total of the item measured that will be involved, such as reading records from a data source.</span></span> <span data-ttu-id="fd010-111">此外，如果只需设置一次或两次该值，这就是一种简单的方法。</span><span class="sxs-lookup"><span data-stu-id="fd010-111">Additionally, if you only need to set the value once or twice, this is an easy way to do it.</span></span> <span data-ttu-id="fd010-112">最后，如果需要减少进度栏显示的值，请使用此过程。</span><span class="sxs-lookup"><span data-stu-id="fd010-112">Finally, use this process if you need to decrease the value displayed by the progress bar.</span></span>|  
|<span data-ttu-id="fd010-113">按固定值增加 <xref:System.Windows.Forms.ProgressBar> 显示。</span><span class="sxs-lookup"><span data-stu-id="fd010-113">Increase the <xref:System.Windows.Forms.ProgressBar> display by a fixed value.</span></span>|<span data-ttu-id="fd010-114">当显示最小值和最大值之间的简单计数时，此方法非常有用，例如已用时间或已处理的文件数。</span><span class="sxs-lookup"><span data-stu-id="fd010-114">This approach is useful when you are displaying a simple count between the minimum and maximum, such as elapsed time or the number of files that have been processed out of a known total.</span></span>|  
|<span data-ttu-id="fd010-115">按变化的值增加 <xref:System.Windows.Forms.ProgressBar> 显示。</span><span class="sxs-lookup"><span data-stu-id="fd010-115">Increase the <xref:System.Windows.Forms.ProgressBar> display by a value that varies.</span></span>|<span data-ttu-id="fd010-116">当你需要将显示的值更改为不同数量的次数时，此方法非常有用。</span><span class="sxs-lookup"><span data-stu-id="fd010-116">This approach is useful when you need to change the displayed value a number of times in different amounts.</span></span> <span data-ttu-id="fd010-117">例如，显示将一系列文件写入磁盘时使用的硬盘空间量。</span><span class="sxs-lookup"><span data-stu-id="fd010-117">An example would be showing the amount of hard-disk space being consumed while writing a series of files to the disk.</span></span>|  
  
 <span data-ttu-id="fd010-118">设置进度栏显示的值的最直接方式是设置 "<xref:System.Windows.Forms.ProgressBar.Value%2A>" 属性。</span><span class="sxs-lookup"><span data-stu-id="fd010-118">The most direct way to set the value displayed by a progress bar is by setting the <xref:System.Windows.Forms.ProgressBar.Value%2A> property.</span></span> <span data-ttu-id="fd010-119">这可以在设计时或运行时执行。</span><span class="sxs-lookup"><span data-stu-id="fd010-119">This can be done either at design time or at run time.</span></span>  
  
### <a name="to-set-the-progressbar-value-directly"></a><span data-ttu-id="fd010-120">直接设置 ProgressBar 值</span><span class="sxs-lookup"><span data-stu-id="fd010-120">To set the ProgressBar value directly</span></span>  
  
1. <span data-ttu-id="fd010-121">设置 <xref:System.Windows.Forms.ProgressBar> 控件的 <xref:System.Windows.Forms.ProgressBar.Minimum%2A> 和 <xref:System.Windows.Forms.ProgressBar.Maximum%2A> 值。</span><span class="sxs-lookup"><span data-stu-id="fd010-121">Set the <xref:System.Windows.Forms.ProgressBar> control's <xref:System.Windows.Forms.ProgressBar.Minimum%2A> and <xref:System.Windows.Forms.ProgressBar.Maximum%2A> values.</span></span>  
  
2. <span data-ttu-id="fd010-122">在代码中，将控件的 <xref:System.Windows.Forms.ProgressBar.Value%2A> 属性设置为一个整数值，该值介于已建立的最小值和最大值之间。</span><span class="sxs-lookup"><span data-stu-id="fd010-122">In code, set the control's <xref:System.Windows.Forms.ProgressBar.Value%2A> property to an integer value between the minimum and maximum values you have established.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="fd010-123">如果在 <xref:System.Windows.Forms.ProgressBar.Minimum%2A> 和 <xref:System.Windows.Forms.ProgressBar.Maximum%2A> 属性所建立的边界之外设置 <xref:System.Windows.Forms.ProgressBar.Value%2A> 属性，控件将引发 <xref:System.ArgumentException> 异常。</span><span class="sxs-lookup"><span data-stu-id="fd010-123">If you set the <xref:System.Windows.Forms.ProgressBar.Value%2A> property outside the boundaries established by the <xref:System.Windows.Forms.ProgressBar.Minimum%2A> and <xref:System.Windows.Forms.ProgressBar.Maximum%2A> properties, the control throws an <xref:System.ArgumentException> exception.</span></span>  
  
     <span data-ttu-id="fd010-124">下面的代码示例演示如何直接设置 <xref:System.Windows.Forms.ProgressBar> 值。</span><span class="sxs-lookup"><span data-stu-id="fd010-124">The following code example illustrates how to set the <xref:System.Windows.Forms.ProgressBar> value directly.</span></span> <span data-ttu-id="fd010-125">此代码从数据源读取记录，并在每次读取数据记录时更新进度栏和标签。</span><span class="sxs-lookup"><span data-stu-id="fd010-125">The code reads records from a data source and updates the progress bar and label every time a data record is read.</span></span> <span data-ttu-id="fd010-126">此示例要求窗体具有 <xref:System.Windows.Forms.Label> 控件、<xref:System.Windows.Forms.ProgressBar> 控件和数据表，其中的行称为 `CustomerRow`，`FirstName` 和 `LastName` 字段。</span><span class="sxs-lookup"><span data-stu-id="fd010-126">This example requires that your form has a <xref:System.Windows.Forms.Label> control, a <xref:System.Windows.Forms.ProgressBar> control, and a data table with a row called `CustomerRow` with `FirstName` and `LastName` fields.</span></span>  
  
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
  
     如果正在按固定间隔显示进度，则可以设置此值，然后调用一个方法，该方法将按该间隔增加 <xref:System.Windows.Forms.ProgressBar> 控件的值。 <span data-ttu-id="fd010-128">这适用于不以整体百分比度量进度的计时器和其他方案。</span><span class="sxs-lookup"><span data-stu-id="fd010-128">This is useful for timers and other scenarios where you are not measuring progress as a percentage of the whole.</span></span>  
  
### <a name="to-increase-the-progress-bar-by-a-fixed-value"></a><span data-ttu-id="fd010-129">按固定值增大进度栏</span><span class="sxs-lookup"><span data-stu-id="fd010-129">To increase the progress bar by a fixed value</span></span>  
  
1. <span data-ttu-id="fd010-130">设置 <xref:System.Windows.Forms.ProgressBar> 控件的 <xref:System.Windows.Forms.ProgressBar.Minimum%2A> 和 <xref:System.Windows.Forms.ProgressBar.Maximum%2A> 值。</span><span class="sxs-lookup"><span data-stu-id="fd010-130">Set the <xref:System.Windows.Forms.ProgressBar> control's <xref:System.Windows.Forms.ProgressBar.Minimum%2A> and <xref:System.Windows.Forms.ProgressBar.Maximum%2A> values.</span></span>  
  
2. <span data-ttu-id="fd010-131">将控件的 <xref:System.Windows.Forms.ProgressBar.Step%2A> 属性设置为一个整数，该整数表示进度栏的显示值的增加量。</span><span class="sxs-lookup"><span data-stu-id="fd010-131">Set the control's <xref:System.Windows.Forms.ProgressBar.Step%2A> property to an integer representing the amount to increase the progress bar's displayed value.</span></span>  
  
3. <span data-ttu-id="fd010-132">调用 <xref:System.Windows.Forms.ProgressBar.PerformStep%2A> 方法以更改 <xref:System.Windows.Forms.ProgressBar.Step%2A> 属性中设置的数量所显示的值。</span><span class="sxs-lookup"><span data-stu-id="fd010-132">Call the <xref:System.Windows.Forms.ProgressBar.PerformStep%2A> method to change the value displayed by the amount set in the <xref:System.Windows.Forms.ProgressBar.Step%2A> property.</span></span>  
  
     <span data-ttu-id="fd010-133">下面的代码示例说明了进度栏如何维护复制操作中的文件计数。</span><span class="sxs-lookup"><span data-stu-id="fd010-133">The following code example illustrates how a progress bar can maintain a count of the files in a copy operation.</span></span>  
  
     <span data-ttu-id="fd010-134">在下面的示例中，将每个文件读入内存中时，会更新进度栏和标签以反映读取的文件总数。</span><span class="sxs-lookup"><span data-stu-id="fd010-134">In the following example, as each file is read into memory, the progress bar and label are updated to reflect the total files read.</span></span> <span data-ttu-id="fd010-135">此示例要求窗体具有 <xref:System.Windows.Forms.Label> 控件和 <xref:System.Windows.Forms.ProgressBar> 控件。</span><span class="sxs-lookup"><span data-stu-id="fd010-135">This example requires that your form has a <xref:System.Windows.Forms.Label> control and a <xref:System.Windows.Forms.ProgressBar> control.</span></span>  
  
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
  
     最后，您可以增大进度栏显示的值，以便每个增加都是唯一的。 <span data-ttu-id="fd010-137">当您跟踪一系列独特操作（如将不同大小的文件写入硬盘，或以整体百分比度量进度）时，这非常有用。</span><span class="sxs-lookup"><span data-stu-id="fd010-137">This is useful when you are keeping track of a series of unique operations, such as writing files of different sizes to a hard disk, or measuring progress as a percentage of the whole.</span></span>  
  
### <a name="to-increase-the-progress-bar-by-a-dynamic-value"></a><span data-ttu-id="fd010-138">按动态值增大进度栏</span><span class="sxs-lookup"><span data-stu-id="fd010-138">To increase the progress bar by a dynamic value</span></span>  
  
1. <span data-ttu-id="fd010-139">设置 <xref:System.Windows.Forms.ProgressBar> 控件的 <xref:System.Windows.Forms.ProgressBar.Minimum%2A> 和 <xref:System.Windows.Forms.ProgressBar.Maximum%2A> 值。</span><span class="sxs-lookup"><span data-stu-id="fd010-139">Set the <xref:System.Windows.Forms.ProgressBar> control's <xref:System.Windows.Forms.ProgressBar.Minimum%2A> and <xref:System.Windows.Forms.ProgressBar.Maximum%2A> values.</span></span>  
  
2. <span data-ttu-id="fd010-140">调用 <xref:System.Windows.Forms.ProgressBar.Increment%2A> 方法，以更改指定的整数显示的值。</span><span class="sxs-lookup"><span data-stu-id="fd010-140">Call the <xref:System.Windows.Forms.ProgressBar.Increment%2A> method to change the value displayed by an integer you specify.</span></span>  
  
     <span data-ttu-id="fd010-141">下面的代码示例说明了进度栏如何计算在复制操作过程中使用的磁盘空间量。</span><span class="sxs-lookup"><span data-stu-id="fd010-141">The following code example illustrates how a progress bar can calculate how much disk space has been used during a copy operation.</span></span>  
  
     <span data-ttu-id="fd010-142">在以下示例中，将每个文件写入硬盘时，会更新进度栏和标签以反映可用的硬盘空间量。</span><span class="sxs-lookup"><span data-stu-id="fd010-142">In the following example, as each file is written to the hard disk, the progress bar and label are updated to reflect the amount of hard-disk space available.</span></span> <span data-ttu-id="fd010-143">此示例要求窗体具有 <xref:System.Windows.Forms.Label> 控件和 <xref:System.Windows.Forms.ProgressBar> 控件。</span><span class="sxs-lookup"><span data-stu-id="fd010-143">This example requires that your form has a <xref:System.Windows.Forms.Label> control and a <xref:System.Windows.Forms.ProgressBar> control.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="fd010-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fd010-144">See also</span></span>

- <xref:System.Windows.Forms.ProgressBar>
- <xref:System.Windows.Forms.ToolStripProgressBar>
- [<span data-ttu-id="fd010-145">ProgressBar 控件概述</span><span class="sxs-lookup"><span data-stu-id="fd010-145">ProgressBar Control Overview</span></span>](progressbar-control-overview-windows-forms.md)
- [<span data-ttu-id="fd010-146">ProgressBar 控件</span><span class="sxs-lookup"><span data-stu-id="fd010-146">ProgressBar Control</span></span>](progressbar-control-windows-forms.md)
