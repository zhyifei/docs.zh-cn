---
title: "控制流中异步程序 (Visual Basic 中) |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: b0443af7-c586-4cb0-b476-742ae4098a96
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 15e02fbc023db9ae2f3ee9f40598faa7c9c027a0
ms.contentlocale: zh-cn
ms.lasthandoff: 03/13/2017

---
# <a name="control-flow-in-async-programs-visual-basic"></a><span data-ttu-id="4b748-102">异步程序 (Visual Basic 中) 中的控制流</span><span class="sxs-lookup"><span data-stu-id="4b748-102">Control Flow in Async Programs (Visual Basic)</span></span>
<span data-ttu-id="4b748-103">你可以编写和维护异步程序更轻松地使用`Async`和`Await`关键字。</span><span class="sxs-lookup"><span data-stu-id="4b748-103">You can write and maintain asynchronous programs more easily by using the `Async` and `Await` keywords.</span></span> <span data-ttu-id="4b748-104">但是，结果可能会让您大吃一惊如果您不了解您的程序的运行方式。</span><span class="sxs-lookup"><span data-stu-id="4b748-104">However, the results might surprise you if you don't understand how your program operates.</span></span> <span data-ttu-id="4b748-105">通过一个简单的异步程序，以显示当控件移动，从一种方法对另一台和哪些信息的控制流传输每次此主题跟踪。</span><span class="sxs-lookup"><span data-stu-id="4b748-105">This topic traces the flow of control through a simple async program to show you when control moves from one method to another and what information is transferred each time.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4b748-106">`Async` 和 `Await` 关键字是在 Visual Studio 2012 中引入的。</span><span class="sxs-lookup"><span data-stu-id="4b748-106">The `Async` and `Await` keywords were introduced in Visual Studio 2012.</span></span>  
  
 <span data-ttu-id="4b748-107">一般情况下，将包含与异步代码的方法的标记[异步](../../../../visual-basic/language-reference/modifiers/async.md)修饰符。</span><span class="sxs-lookup"><span data-stu-id="4b748-107">In general, you mark methods that contain asynchronous code with the [Async](../../../../visual-basic/language-reference/modifiers/async.md) modifier.</span></span> <span data-ttu-id="4b748-108">在使用 async 修饰符标记的方法，您可以使用[Await (Visual Basic 中)](../../../../visual-basic/language-reference/operators/await-operator.md)运算符来指定该方法暂停以等待完成异步调用过程的位置。</span><span class="sxs-lookup"><span data-stu-id="4b748-108">In a method that's marked with an async modifier, you can use an [Await (Visual Basic)](../../../../visual-basic/language-reference/operators/await-operator.md) operator to specify where the method pauses to wait for a called asynchronous process to complete.</span></span> <span data-ttu-id="4b748-109">有关详细信息，请参阅[使用 Async 和 Await (Visual Basic 中) 的异步编程](../../../../visual-basic/programming-guide/concepts/async/index.md)。</span><span class="sxs-lookup"><span data-stu-id="4b748-109">For more information, see [Asynchronous Programming with Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md).</span></span>  
  
 <span data-ttu-id="4b748-110">下面的示例使用异步方法以字符串形式指定的网站的内容下载并显示字符串的长度。</span><span class="sxs-lookup"><span data-stu-id="4b748-110">The following example uses async methods to download the contents of a specified website as a string and to display the length of the string.</span></span> <span data-ttu-id="4b748-111">此示例包含以下两种方法。</span><span class="sxs-lookup"><span data-stu-id="4b748-111">The example contains the following two methods.</span></span>  
  
-   <span data-ttu-id="4b748-112">`startButton_Click`后者调用`AccessTheWebAsync`并显示结果。</span><span class="sxs-lookup"><span data-stu-id="4b748-112">`startButton_Click`, which calls `AccessTheWebAsync` and displays the result.</span></span>  
  
-   <span data-ttu-id="4b748-113">`AccessTheWebAsync`它作为字符串的网站的内容下载，并返回字符串的长度。</span><span class="sxs-lookup"><span data-stu-id="4b748-113">`AccessTheWebAsync`, which downloads the contents of a website as a string and returns the length of the string.</span></span> <span data-ttu-id="4b748-114">`AccessTheWebAsync`使用异步<xref:System.Net.Http.HttpClient>方法， <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>，以下载内容。</xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29> </xref:System.Net.Http.HttpClient></span><span class="sxs-lookup"><span data-stu-id="4b748-114">`AccessTheWebAsync` uses an asynchronous <xref:System.Net.Http.HttpClient> method, <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>, to download the contents.</span></span>  
  
 <span data-ttu-id="4b748-115">编号的显示行显示在整个程序来帮助你了解如何在程序运行，还将说明在被标记为每个点会发生什么情况的关键点。</span><span class="sxs-lookup"><span data-stu-id="4b748-115">Numbered display lines appear at strategic points throughout the program to help you understand how the program runs and to explain what happens at each point that is marked.</span></span> <span data-ttu-id="4b748-116">显示行标记"ONE"通过"六个。"</span><span class="sxs-lookup"><span data-stu-id="4b748-116">The display lines are labeled "ONE" through "SIX."</span></span> <span data-ttu-id="4b748-117">标签表示在其中程序到达这些代码行的顺序。</span><span class="sxs-lookup"><span data-stu-id="4b748-117">The labels represent the order in which the program reaches these lines of code.</span></span>  
  
 <span data-ttu-id="4b748-118">下面的代码演示了该程序的概述。</span><span class="sxs-lookup"><span data-stu-id="4b748-118">The following code shows an outline of the program.</span></span>  
  
```vb  
Class MainWindow  
  
    Private Async Sub StartButton_Click(sender As Object, e As RoutedEventArgs) Handles StartButton.Click  
  
        ' ONE  
        Dim getLengthTask As Task(Of Integer) = AccessTheWebAsync()  
  
        ' FOUR  
        Dim contentLength As Integer = Await getLengthTask  
  
        ' SIX  
        ResultsTextBox.Text &=  
            String.Format(vbCrLf & "Length of the downloaded string: {0}." & vbCrLf, contentLength)  
  
    End Sub  
  
    Async Function AccessTheWebAsync() As Task(Of Integer)  
  
        ' TWO  
        Dim client As HttpClient = New HttpClient()   
        Dim getStringTask As Task(Of String) =   
            client.GetStringAsync("http://msdn.microsoft.com")  
  
        ' THREE  
        Dim urlContents As String = Await getStringTask  
  
        ' FIVE  
        Return urlContents.Length  
    End Function  
  
End Class  
  
```  
  
 <span data-ttu-id="4b748-119">每个标记的位置中，"ONE"通过"六，"显示有关该程序的当前状态信息。</span><span class="sxs-lookup"><span data-stu-id="4b748-119">Each of the labeled locations, "ONE" through "SIX," displays information about the current state of the program.</span></span> <span data-ttu-id="4b748-120">将生成以下输出。</span><span class="sxs-lookup"><span data-stu-id="4b748-120">The following output is produced.</span></span>  
  
```  
  
ONE:   Entering startButton_Click.  
           Calling AccessTheWebAsync.  
  
TWO:   Entering AccessTheWebAsync.  
           Calling HttpClient.GetStringAsync.  
  
THREE: Back in AccessTheWebAsync.  
           Task getStringTask is started.  
           About to await getStringTask & return a Task<int> to startButton_Click.  
  
FOUR:  Back in startButton_Click.  
           Task getLengthTask is started.  
           About to await getLengthTask -- no caller to return to.  
  
FIVE:  Back in AccessTheWebAsync.  
           Task getStringTask is complete.  
           Processing the return statement.  
           Exiting from AccessTheWebAsync.  
  
SIX:   Back in startButton_Click.  
           Task getLengthTask is finished.  
           Result from AccessTheWebAsync is stored in contentLength.  
           About to display contentLength and exit.  
  
Length of the downloaded string: 33946.  
```  
  
## <a name="set-up-the-program"></a><span data-ttu-id="4b748-121">设置程序</span><span class="sxs-lookup"><span data-stu-id="4b748-121">Set Up the Program</span></span>  
 <span data-ttu-id="4b748-122">您可以从 MSDN 下载本主题使用的代码，或者您可以自行构建。</span><span class="sxs-lookup"><span data-stu-id="4b748-122">You can download the code that this topic uses from MSDN, or you can build it yourself.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4b748-123">若要运行该示例，必须具有 Visual Studio 2012 或更高版本和.NET Framework 4.5 或更高版本安装在您的计算机上。</span><span class="sxs-lookup"><span data-stu-id="4b748-123">To run the example, you must have Visual Studio 2012 or newer and  the .NET Framework 4.5 or newer installed on your computer.</span></span>  
  
### <a name="download-the-program"></a><span data-ttu-id="4b748-124">下载程序</span><span class="sxs-lookup"><span data-stu-id="4b748-124">Download the Program</span></span>  
 <span data-ttu-id="4b748-125">您可以下载的应用程序中的相应主题[异步示例︰ 异步程序中的控制流](http://go.microsoft.com/fwlink/?LinkId=255285)。</span><span class="sxs-lookup"><span data-stu-id="4b748-125">You can download the application for this topic from [Async Sample: Control Flow in Async Programs](http://go.microsoft.com/fwlink/?LinkId=255285).</span></span> <span data-ttu-id="4b748-126">以下步骤打开并运行该程序。</span><span class="sxs-lookup"><span data-stu-id="4b748-126">The following steps open and run the program.</span></span>  
  
1.  <span data-ttu-id="4b748-127">解压缩下载的文件，然后启动 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="4b748-127">Unzip the downloaded file, and then start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="4b748-128">在菜单栏上，依次选择 **“文件”**、 **“打开”**和 **“项目/解决方案”**。</span><span class="sxs-lookup"><span data-stu-id="4b748-128">On the menu bar, choose **File**, **Open**, **Project/Solution**.</span></span>  
  
3.  <span data-ttu-id="4b748-129">导航到保存已解压缩的示例代码的文件夹，打开解决方案 (.sln) 文件，然后选择 F5 键以生成并运行项目。</span><span class="sxs-lookup"><span data-stu-id="4b748-129">Navigate to the folder that holds the unzipped sample code, open the solution (.sln) file, and then choose the F5 key to build and run the project.</span></span>  
  
### <a name="build-the-program-yourself"></a><span data-ttu-id="4b748-130">您自行生成程序</span><span class="sxs-lookup"><span data-stu-id="4b748-130">Build the Program Yourself</span></span>  
 <span data-ttu-id="4b748-131">下面的 Windows Presentation Foundation (WPF) 项目包含本主题的代码示例。</span><span class="sxs-lookup"><span data-stu-id="4b748-131">The following Windows Presentation Foundation (WPF) project contains the code example for this topic.</span></span>  
  
 <span data-ttu-id="4b748-132">若要运行项目，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="4b748-132">To run the project, perform the following steps:</span></span>  
  
1.  <span data-ttu-id="4b748-133">启动 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="4b748-133">Start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="4b748-134">在菜单栏上，依次选择“文件” ****、“新建” ****、“项目” ****。</span><span class="sxs-lookup"><span data-stu-id="4b748-134">On the menu bar, choose **File**, **New**, **Project**.</span></span>  
  
     <span data-ttu-id="4b748-135">**“新建项目”** 对话框随即打开。</span><span class="sxs-lookup"><span data-stu-id="4b748-135">The **New Project** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="4b748-136">在**已安装的模板**窗格中，选择**Visual Basic**，然后选择**WPF 应用程序**从项目类型列表。</span><span class="sxs-lookup"><span data-stu-id="4b748-136">In the **Installed Templates** pane, choose **Visual Basic**, and then choose **WPF Application** from the list of project types.</span></span>  
  
4.  <span data-ttu-id="4b748-137">输入`AsyncTracer`作为项目的名称，然后选择**确定**按钮。</span><span class="sxs-lookup"><span data-stu-id="4b748-137">Enter `AsyncTracer` as the name of the project, and then choose the **OK** button.</span></span>  
  
     <span data-ttu-id="4b748-138">新项目将出现在**解决方案资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="4b748-138">The new project appears in **Solution Explorer**.</span></span>  
  
5.  <span data-ttu-id="4b748-139">在 Visual Studio 代码编辑器中，选择 **“MainWindow.xaml”** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="4b748-139">In the Visual Studio Code Editor, choose the **MainWindow.xaml** tab.</span></span>  
  
     <span data-ttu-id="4b748-140">如果看不到选项卡，打开快捷菜单中的 MainWindow.xaml**解决方案资源管理器**，然后选择**查看代码**。</span><span class="sxs-lookup"><span data-stu-id="4b748-140">If the tab isn’t visible, open the shortcut menu for MainWindow.xaml in **Solution Explorer**, and then choose **View Code**.</span></span>  
  
6.  <span data-ttu-id="4b748-141">在**XAML** MainWindow.xaml 视图中，将代码替换为下面的代码。</span><span class="sxs-lookup"><span data-stu-id="4b748-141">In the **XAML** view of MainWindow.xaml, replace the code with the following code.</span></span>  
  
    ```vb  
    <Window  
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008" xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006" mc:Ignorable="d" x:Class="MainWindow"  
        Title="Control Flow Trace" Height="350" Width="525">  
        <Grid>  
            <Button x:Name="StartButton" Content="Start" HorizontalAlignment="Left" Margin="221,10,0,0" VerticalAlignment="Top" Width="75"/>  
            <TextBox x:Name="ResultsTextBox" HorizontalAlignment="Left" TextWrapping="Wrap" VerticalAlignment="Bottom" Width="510" Height="265" FontFamily="Lucida Console" FontSize="10" VerticalScrollBarVisibility="Visible" d:LayoutOverrides="HorizontalMargin"/>  
  
        </Grid>  
    </Window>  
  
    ```  
  
     <span data-ttu-id="4b748-142">一个简单的窗口，其中包含一个文本框和一个按钮将出现在**设计**MainWindow.xaml 的视图。</span><span class="sxs-lookup"><span data-stu-id="4b748-142">A simple window that contains a text box and a button appears in the **Design** view of MainWindow.xaml.</span></span>  
  
7.  <span data-ttu-id="4b748-143">添加<xref:System.Net.Http>。</xref:System.Net.Http>的引用</span><span class="sxs-lookup"><span data-stu-id="4b748-143">Add a reference for <xref:System.Net.Http>.</span></span>  
  
8.  <span data-ttu-id="4b748-144">在**解决方案资源管理器**，MainWindow.xaml.vb，打开快捷菜单，然后选择**查看代码**。</span><span class="sxs-lookup"><span data-stu-id="4b748-144">In **Solution Explorer**, open the shortcut menu for MainWindow.xaml.vb, and then choose **View Code**.</span></span>  
  
9. <span data-ttu-id="4b748-145">MainWindow.xaml.vb，下面的代码替换该代码。</span><span class="sxs-lookup"><span data-stu-id="4b748-145">In MainWindow.xaml.vb , replace the code with the following code.</span></span>  
  
    ```vb  
    ' Add an Imports statement and a reference for System.Net.Http.  
    Imports System.Net.Http  
  
    Class MainWindow  
  
        Private Async Sub StartButton_Click(sender As Object, e As RoutedEventArgs) Handles StartButton.Click  
  
            ' The display lines in the example lead you through the control shifts.  
            ResultsTextBox.Text &= "ONE:   Entering StartButton_Click." & vbCrLf &  
                "           Calling AccessTheWebAsync." & vbCrLf  
  
            Dim getLengthTask As Task(Of Integer) = AccessTheWebAsync()  
  
            ResultsTextBox.Text &= vbCrLf & "FOUR:  Back in StartButton_Click." & vbCrLf &  
                "           Task getLengthTask is started." & vbCrLf &  
                "           About to await getLengthTask -- no caller to return to." & vbCrLf  
  
            Dim contentLength As Integer = Await getLengthTask  
  
            ResultsTextBox.Text &= vbCrLf & "SIX:   Back in StartButton_Click." & vbCrLf &  
                "           Task getLengthTask is finished." & vbCrLf &  
                "           Result from AccessTheWebAsync is stored in contentLength." & vbCrLf &  
                "           About to display contentLength and exit." & vbCrLf  
  
            ResultsTextBox.Text &=  
                String.Format(vbCrLf & "Length of the downloaded string: {0}." & vbCrLf, contentLength)  
        End Sub  
  
        Async Function AccessTheWebAsync() As Task(Of Integer)  
  
            ResultsTextBox.Text &= vbCrLf & "TWO:   Entering AccessTheWebAsync."  
  
            ' Declare an HttpClient object.  
            Dim client As HttpClient = New HttpClient()  
  
            ResultsTextBox.Text &= vbCrLf & "           Calling HttpClient.GetStringAsync." & vbCrLf  
  
            ' GetStringAsync returns a Task(Of String).   
            Dim getStringTask As Task(Of String) = client.GetStringAsync("http://msdn.microsoft.com")  
  
            ResultsTextBox.Text &= vbCrLf & "THREE: Back in AccessTheWebAsync." & vbCrLf &  
                "           Task getStringTask is started."  
  
            ' AccessTheWebAsync can continue to work until getStringTask is awaited.  
  
            ResultsTextBox.Text &=  
                vbCrLf & "           About to await getStringTask & return a Task(Of Integer) to StartButton_Click." & vbCrLf  
  
            ' Retrieve the website contents when task is complete.  
            Dim urlContents As String = Await getStringTask  
  
            ResultsTextBox.Text &= vbCrLf & "FIVE:  Back in AccessTheWebAsync." &  
                vbCrLf & "           Task getStringTask is complete." &  
                vbCrLf & "           Processing the return statement." &  
                vbCrLf & "           Exiting from AccessTheWebAsync." & vbCrLf  
  
            Return urlContents.Length  
        End Function  
  
    End Class  
    ```  
  
10. <span data-ttu-id="4b748-146">按 F5 键以运行程序，然后选择 **“启动”** 按钮。</span><span class="sxs-lookup"><span data-stu-id="4b748-146">Choose the F5 key to run the program, and then choose the **Start** button.</span></span>  
  
     <span data-ttu-id="4b748-147">应出现以下输出。</span><span class="sxs-lookup"><span data-stu-id="4b748-147">The following output should appear.</span></span>  
  
    ```  
    ONE:   Entering startButton_Click.  
               Calling AccessTheWebAsync.  
  
    TWO:   Entering AccessTheWebAsync.  
               Calling HttpClient.GetStringAsync.  
  
    THREE: Back in AccessTheWebAsync.  
               Task getStringTask is started.  
               About to await getStringTask & return a Task<int> to startButton_Click.  
  
    FOUR:  Back in startButton_Click.  
               Task getLengthTask is started.  
               About to await getLengthTask -- no caller to return to.  
  
    FIVE:  Back in AccessTheWebAsync.  
               Task getStringTask is complete.  
               Processing the return statement.  
               Exiting from AccessTheWebAsync.  
  
    SIX:   Back in startButton_Click.  
               Task getLengthTask is finished.  
               Result from AccessTheWebAsync is stored in contentLength.  
               About to display contentLength and exit.  
  
    Length of the downloaded string: 33946.  
    ```  
  
## <a name="trace-the-program"></a><span data-ttu-id="4b748-148">跟踪程序</span><span class="sxs-lookup"><span data-stu-id="4b748-148">Trace the Program</span></span>  
  
### <a name="steps-one-and-two"></a><span data-ttu-id="4b748-149">步骤&1; 和步骤&2;</span><span class="sxs-lookup"><span data-stu-id="4b748-149">Steps ONE and TWO</span></span>  
 <span data-ttu-id="4b748-150">前两个显示线追踪的路径作为`startButton_Click`调用`AccessTheWebAsync`，和`AccessTheWebAsync`调用异步<xref:System.Net.Http.HttpClient>方法<xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>。</xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29> </xref:System.Net.Http.HttpClient></span><span class="sxs-lookup"><span data-stu-id="4b748-150">The first two display lines trace the path as `startButton_Click` calls `AccessTheWebAsync`, and `AccessTheWebAsync` calls the asynchronous <xref:System.Net.Http.HttpClient> method <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>.</span></span> <span data-ttu-id="4b748-151">下图概述了在调用方法方法。</span><span class="sxs-lookup"><span data-stu-id="4b748-151">The following image outlines the calls from method to method.</span></span>  
  
 <span data-ttu-id="4b748-152">![两个步骤](../../../../csharp/programming-guide/concepts/async/media/asynctrace-onetwo.png "AsyncTrace ONETWO")</span><span class="sxs-lookup"><span data-stu-id="4b748-152">![Steps ONE and TWO](../../../../csharp/programming-guide/concepts/async/media/asynctrace-onetwo.png "AsyncTrace-ONETWO")</span></span>  
  
 <span data-ttu-id="4b748-153">两者的返回类型`AccessTheWebAsync`和`client.GetStringAsync`是<xref:System.Threading.Tasks.Task%601>。</xref:System.Threading.Tasks.Task%601></span><span class="sxs-lookup"><span data-stu-id="4b748-153">The return type of both `AccessTheWebAsync` and `client.GetStringAsync` is <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="4b748-154">有关`AccessTheWebAsync`，TResult 是一个整数。</span><span class="sxs-lookup"><span data-stu-id="4b748-154">For `AccessTheWebAsync`, TResult is an integer.</span></span> <span data-ttu-id="4b748-155">有关`GetStringAsync`，TResult 为字符串。</span><span class="sxs-lookup"><span data-stu-id="4b748-155">For `GetStringAsync`, TResult is a string.</span></span> <span data-ttu-id="4b748-156">有关异步方法的返回类型的详细信息，请参阅[异步返回类型 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md)。</span><span class="sxs-lookup"><span data-stu-id="4b748-156">For more information about async method return types, see [Async Return Types (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span></span>  
  
 <span data-ttu-id="4b748-157">在控制切换回调用方时，返回任务的异步方法返回一个任务实例。</span><span class="sxs-lookup"><span data-stu-id="4b748-157">A task-returning async method returns a task instance when control shifts back to the caller.</span></span> <span data-ttu-id="4b748-158">控制从异步方法返回其调用方时`Await`运算符时遇到的调用的方法或调用的方法结束时。</span><span class="sxs-lookup"><span data-stu-id="4b748-158">Control returns from an async method to its caller either when an `Await` operator is encountered in the called method or when the called method ends.</span></span> <span data-ttu-id="4b748-159">标记为"3"到"6"的显示行跟踪过程的这一部分。</span><span class="sxs-lookup"><span data-stu-id="4b748-159">The display lines that are labeled "THREE" through "SIX" trace this part of the process.</span></span>  
  
### <a name="step-three"></a><span data-ttu-id="4b748-160">步骤&3;</span><span class="sxs-lookup"><span data-stu-id="4b748-160">Step THREE</span></span>  
 <span data-ttu-id="4b748-161">在`AccessTheWebAsync`，异步方法<xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>调用以下载目标网页的内容。</xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29></span><span class="sxs-lookup"><span data-stu-id="4b748-161">In `AccessTheWebAsync`, the asynchronous method <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29> is called to download the contents of the target webpage.</span></span> <span data-ttu-id="4b748-162">控制将返回从`client.GetStringAsync`到`AccessTheWebAsync`时`client.GetStringAsync`返回。</span><span class="sxs-lookup"><span data-stu-id="4b748-162">Control returns from `client.GetStringAsync` to `AccessTheWebAsync` when `client.GetStringAsync` returns.</span></span>  
  
 <span data-ttu-id="4b748-163">`client.GetStringAsync`方法返回的字符串分配给一个 task`getStringTask`变量中`AccessTheWebAsync`。</span><span class="sxs-lookup"><span data-stu-id="4b748-163">The `client.GetStringAsync` method returns a task of string that’s assigned to the `getStringTask` variable in `AccessTheWebAsync`.</span></span> <span data-ttu-id="4b748-164">该示例程序中的以下行说明如何调用`client.GetStringAsync`和分配。</span><span class="sxs-lookup"><span data-stu-id="4b748-164">The following line in the example program shows the call to `client.GetStringAsync` and the assignment.</span></span>  
  
<span data-ttu-id="4b748-165"><CodeContentPlaceHolder>5</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="4b748-165"><CodeContentPlaceHolder>5</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="4b748-166">您可以将任务视为由一个承诺`client.GetStringAsync`以最终产生实际字符串。</span><span class="sxs-lookup"><span data-stu-id="4b748-166">You can think of the task as a promise by `client.GetStringAsync` to produce an actual string eventually.</span></span> <span data-ttu-id="4b748-167">在此期间，如果`AccessTheWebAsync`有工作要做的承诺字符串并不依赖于`client.GetStringAsync`，可以继续的处理而`client.GetStringAsync`等待。</span><span class="sxs-lookup"><span data-stu-id="4b748-167">In the meantime, if `AccessTheWebAsync` has work to do that doesn't depend on the promised string from `client.GetStringAsync`, that work can continue while  `client.GetStringAsync` waits.</span></span> <span data-ttu-id="4b748-168">在示例中，以下行的输出，分别标记为"3"，表示执行独立工作的机会</span><span class="sxs-lookup"><span data-stu-id="4b748-168">In the example, the following lines of output, which are labeled "THREE,” represent the opportunity to do independent work</span></span>  
  
<span data-ttu-id="4b748-169"><CodeContentPlaceHolder>6</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="4b748-169"><CodeContentPlaceHolder>6</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="4b748-170">下面的语句中止进度`AccessTheWebAsync`时`getStringTask`等待。</span><span class="sxs-lookup"><span data-stu-id="4b748-170">The following statement suspends progress in `AccessTheWebAsync` when `getStringTask` is awaited.</span></span>  
  
<span data-ttu-id="4b748-171"><CodeContentPlaceHolder>7</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="4b748-171"><CodeContentPlaceHolder>7</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="4b748-172">下图显示了从控制流`client.GetStringAsync`到分配给`getStringTask`和从创建`getStringTask`到 Await 运算符的应用程序。</span><span class="sxs-lookup"><span data-stu-id="4b748-172">The following image shows the flow of control from `client.GetStringAsync` to the assignment to `getStringTask` and from the creation of `getStringTask` to the application of an Await operator.</span></span>  
  
 <span data-ttu-id="4b748-173">![第三步](../../../../csharp/programming-guide/concepts/async/media/asynctrace-three.png "AsyncTrace 三")</span><span class="sxs-lookup"><span data-stu-id="4b748-173">![Step THREE](../../../../csharp/programming-guide/concepts/async/media/asynctrace-three.png "AsyncTrace-Three")</span></span>  
  
 <span data-ttu-id="4b748-174">Await 表达式挂起`AccessTheWebAsync`直到`client.GetStringAsync`返回。</span><span class="sxs-lookup"><span data-stu-id="4b748-174">The await expression suspends `AccessTheWebAsync` until `client.GetStringAsync` returns.</span></span> <span data-ttu-id="4b748-175">同时，控件返回到调用方`AccessTheWebAsync`， `startButton_Click`。</span><span class="sxs-lookup"><span data-stu-id="4b748-175">In the meantime, control returns to the caller of `AccessTheWebAsync`, `startButton_Click`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4b748-176">通常情况下，您应当立即 await 为异步方法调用。</span><span class="sxs-lookup"><span data-stu-id="4b748-176">Typically, you await the call to an asynchronous method immediately.</span></span> <span data-ttu-id="4b748-177">例如，以下赋值可以将替换为前面的代码中创建，然后等待`getStringTask`:`Dim urlContents As String = Await client.GetStringAsync("http://msdn.microsoft.com")`</span><span class="sxs-lookup"><span data-stu-id="4b748-177">For example, the following assignment could replace the previous code that creates and then awaits `getStringTask`: `Dim urlContents As String = Await client.GetStringAsync("http://msdn.microsoft.com")`</span></span>  
>   
>  <span data-ttu-id="4b748-178">在本主题中，await 运算符应用更高版本以容纳标记通过计划的控制流的输出行。</span><span class="sxs-lookup"><span data-stu-id="4b748-178">In this topic, the await operator is applied later to accommodate the output lines that mark the flow of control through the program.</span></span>  
  
### <a name="step-four"></a><span data-ttu-id="4b748-179">步骤&4;</span><span class="sxs-lookup"><span data-stu-id="4b748-179">Step FOUR</span></span>  
 <span data-ttu-id="4b748-180">已声明返回类型的`AccessTheWebAsync`是`Task(Of Integer)`。</span><span class="sxs-lookup"><span data-stu-id="4b748-180">The declared return type of `AccessTheWebAsync` is `Task(Of Integer)`.</span></span> <span data-ttu-id="4b748-181">因此，当`AccessTheWebAsync`被挂起，它将返回到整数的任务`startButton_Click`。</span><span class="sxs-lookup"><span data-stu-id="4b748-181">Therefore, when `AccessTheWebAsync` is suspended, it returns a task of integer to `startButton_Click`.</span></span> <span data-ttu-id="4b748-182">您应该了解，则返回的任务不是`getStringTask`。</span><span class="sxs-lookup"><span data-stu-id="4b748-182">You should understand that the returned task isn’t `getStringTask`.</span></span> <span data-ttu-id="4b748-183">返回的任务是一项新任务的整数，它表示要在挂起的方法中，完成的剩余`AccessTheWebAsync`。</span><span class="sxs-lookup"><span data-stu-id="4b748-183">The returned task is a new task of integer that represents what remains to be done in the suspended method, `AccessTheWebAsync`.</span></span> <span data-ttu-id="4b748-184">该任务是从一个承诺`AccessTheWebAsync`可以在该任务已完成时生成一个整数。</span><span class="sxs-lookup"><span data-stu-id="4b748-184">The task is a promise from `AccessTheWebAsync` to produce an integer when the task is complete.</span></span>  
  
 <span data-ttu-id="4b748-185">下列语句将赋给此任务`getLengthTask`变量。</span><span class="sxs-lookup"><span data-stu-id="4b748-185">The following statement assigns this task to the `getLengthTask` variable.</span></span>  
  
<span data-ttu-id="4b748-186"><CodeContentPlaceHolder>8</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="4b748-186"><CodeContentPlaceHolder>8</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="4b748-187">如下所示`AccessTheWebAsync`，`startButton_Click`可以继续工作并不取决于异步任务的结果 (`getLengthTask`) 之前等待的 task。</span><span class="sxs-lookup"><span data-stu-id="4b748-187">As in `AccessTheWebAsync`, `startButton_Click` can continue with work that doesn’t depend on the results of the asynchronous task (`getLengthTask`) until the task is awaited.</span></span> <span data-ttu-id="4b748-188">下面的输出行表示该工作。</span><span class="sxs-lookup"><span data-stu-id="4b748-188">The following output lines represent that work.</span></span>  
  
<span data-ttu-id="4b748-189"><CodeContentPlaceHolder>9</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="4b748-189"><CodeContentPlaceHolder>9</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="4b748-190">在进度`startButton_Click`时挂起`getLengthTask`等待。</span><span class="sxs-lookup"><span data-stu-id="4b748-190">Progress in `startButton_Click` is suspended when `getLengthTask` is awaited.</span></span> <span data-ttu-id="4b748-191">下面的赋值语句将挂起`startButton_Click`直到`AccessTheWebAsync`已完成。</span><span class="sxs-lookup"><span data-stu-id="4b748-191">The following assignment statement suspends `startButton_Click` until `AccessTheWebAsync` is complete.</span></span>  
  
<span data-ttu-id="4b748-192"><CodeContentPlaceHolder>10</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="4b748-192"><CodeContentPlaceHolder>10</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="4b748-193">下图中箭头显示从中的 await 表达式的控制流`AccessTheWebAsync`对分配到的值`getLengthTask`后, 跟在正常处理`startButton_Click`直到`getLengthTask`等待。</span><span class="sxs-lookup"><span data-stu-id="4b748-193">In the following illustration, the arrows show the flow of control from the await expression in `AccessTheWebAsync` to the assignment of a value to `getLengthTask`, followed by normal processing in `startButton_Click` until `getLengthTask` is awaited.</span></span>  
  
 <span data-ttu-id="4b748-194">![第四步](../../../../csharp/programming-guide/concepts/async/media/asynctrace-four.png "AsyncTrace 四")</span><span class="sxs-lookup"><span data-stu-id="4b748-194">![Step FOUR](../../../../csharp/programming-guide/concepts/async/media/asynctrace-four.png "AsyncTrace-FOUR")</span></span>  
  
### <a name="step-five"></a><span data-ttu-id="4b748-195">步骤&5;</span><span class="sxs-lookup"><span data-stu-id="4b748-195">Step FIVE</span></span>  
 <span data-ttu-id="4b748-196">当`client.GetStringAsync`表明它已完成，以处理`AccessTheWebAsync`发布从挂起，可以继续通过 await 语句。</span><span class="sxs-lookup"><span data-stu-id="4b748-196">When `client.GetStringAsync` signals that it’s complete, processing in `AccessTheWebAsync` is released from suspension and can continue past the await statement.</span></span> <span data-ttu-id="4b748-197">下面的输出行表示继续处理。</span><span class="sxs-lookup"><span data-stu-id="4b748-197">The following lines of output represent the resumption of processing.</span></span>  
  
<span data-ttu-id="4b748-198"><CodeContentPlaceHolder>11</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="4b748-198"><CodeContentPlaceHolder>11</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="4b748-199">操作数的 return 语句`urlContents.Length`，存储在任务的`AccessTheWebAsync`返回。</span><span class="sxs-lookup"><span data-stu-id="4b748-199">The operand of the return statement, `urlContents.Length`, is stored in the task that  `AccessTheWebAsync` returns.</span></span> <span data-ttu-id="4b748-200">Await 表达式检索该值从`getLengthTask`中`startButton_Click`。</span><span class="sxs-lookup"><span data-stu-id="4b748-200">The await expression retrieves that value from `getLengthTask` in `startButton_Click`.</span></span>  
  
 <span data-ttu-id="4b748-201">下图显示了后控制的转移`client.GetStringAsync`(和`getStringTask`) 都已完成。</span><span class="sxs-lookup"><span data-stu-id="4b748-201">The following image shows the transfer of control after `client.GetStringAsync` (and `getStringTask`) are complete.</span></span>  
  
 <span data-ttu-id="4b748-202">![第五步](../../../../csharp/programming-guide/concepts/async/media/asynctrace-five.png "AsyncTrace 五个")</span><span class="sxs-lookup"><span data-stu-id="4b748-202">![Step FIVE](../../../../csharp/programming-guide/concepts/async/media/asynctrace-five.png "AsyncTrace-FIVE")</span></span>  
  
 <span data-ttu-id="4b748-203">`AccessTheWebAsync`运行到完成，并且控件返回到`startButton_Click`，它正在等待完成。</span><span class="sxs-lookup"><span data-stu-id="4b748-203">`AccessTheWebAsync` runs to completion, and control returns to `startButton_Click`, which is awaiting the completion.</span></span>  
  
### <a name="step-six"></a><span data-ttu-id="4b748-204">步骤&6;</span><span class="sxs-lookup"><span data-stu-id="4b748-204">Step SIX</span></span>  
 <span data-ttu-id="4b748-205">当`AccessTheWebAsync`发出信号表示它已完成，处理可以继续通过中的 await 语句`startButton_Async`。</span><span class="sxs-lookup"><span data-stu-id="4b748-205">When `AccessTheWebAsync` signals that it’s complete, processing can continue past the await statement in `startButton_Async`.</span></span> <span data-ttu-id="4b748-206">事实上，该程序没有更多。</span><span class="sxs-lookup"><span data-stu-id="4b748-206">In fact, the program has nothing more to do.</span></span>  
  
 <span data-ttu-id="4b748-207">下面的输出行表示在处理恢复`startButton_Async`:</span><span class="sxs-lookup"><span data-stu-id="4b748-207">The following lines of output represent the resumption of processing in `startButton_Async`:</span></span>  
  
<span data-ttu-id="4b748-208"><CodeContentPlaceHolder>12</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="4b748-208"><CodeContentPlaceHolder>12</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="4b748-209">Await 表达式从检索`getLengthTask`return 语句中的操作数的整数值`AccessTheWebAsync`。</span><span class="sxs-lookup"><span data-stu-id="4b748-209">The await expression retrieves from `getLengthTask` the integer value that’s the operand of the return statement in `AccessTheWebAsync`.</span></span> <span data-ttu-id="4b748-210">下面的语句将该值赋予`contentLength`变量。</span><span class="sxs-lookup"><span data-stu-id="4b748-210">The following statement assigns that value to the `contentLength` variable.</span></span>  
  
<span data-ttu-id="4b748-211"><CodeContentPlaceHolder>13</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="4b748-211"><CodeContentPlaceHolder>13</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="4b748-212">下图显示从控件返回`AccessTheWebAsync`到`startButton_Click`。</span><span class="sxs-lookup"><span data-stu-id="4b748-212">The following image shows the return of control from `AccessTheWebAsync` to `startButton_Click`.</span></span>  
  
 <span data-ttu-id="4b748-213">![第六步](../../../../csharp/programming-guide/concepts/async/media/asynctrace-six.png "AsyncTrace 六个")</span><span class="sxs-lookup"><span data-stu-id="4b748-213">![Step SIX](../../../../csharp/programming-guide/concepts/async/media/asynctrace-six.png "AsyncTrace-SIX")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b748-214">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4b748-214">See Also</span></span>  
 <span data-ttu-id="4b748-215">[异步编程使用 Async 和 Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md) </span><span class="sxs-lookup"><span data-stu-id="4b748-215">[Asynchronous Programming with Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md) </span></span>  
<span data-ttu-id="4b748-216"> [异步返回类型 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md) </span><span class="sxs-lookup"><span data-stu-id="4b748-216"> [Async Return Types (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md) </span></span>  
<span data-ttu-id="4b748-217"> [演练︰ 访问 Web 使用 Async 和 Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md) </span><span class="sxs-lookup"><span data-stu-id="4b748-217"> [Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md) </span></span>  
<span data-ttu-id="4b748-218"> [异步示例︰ 异步程序 （C# 和 Visual Basic） 中的控制流](http://go.microsoft.com/fwlink/?LinkId=255285)</span><span class="sxs-lookup"><span data-stu-id="4b748-218"> [Async Sample: Control Flow in Async Programs (C# and Visual Basic)](http://go.microsoft.com/fwlink/?LinkId=255285)</span></span>
