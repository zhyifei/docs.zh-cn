---
title: "访问 Web 以 Async 和 Await (Visual Basic 中) |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs:
- VB
ms.assetid: 84fd047f-fab8-4d89-8ced-104fb7310a91
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
ms.openlocfilehash: 643fff648336c664961ad7956308acbaea262f61
ms.contentlocale: zh-cn
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-accessing-the-web-by-using-async-and-await-visual-basic"></a><span data-ttu-id="fd93f-102">演练：使用 Async 和 Await 访问 Web (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fd93f-102">Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)</span></span>
<span data-ttu-id="fd93f-103">您可以编写异步程序更轻松、 更直观地通过使用中引入的功能[!INCLUDE[vs_dev11_long](../../../../csharp/includes/vs_dev11_long_md.md)]。</span><span class="sxs-lookup"><span data-stu-id="fd93f-103">You can write asynchronous programs more easily and intuitively by using features that were introduced in [!INCLUDE[vs_dev11_long](../../../../csharp/includes/vs_dev11_long_md.md)].</span></span> <span data-ttu-id="fd93f-104">你可以编写类似于同步代码的异步代码，并让编译器处理异步代码通常需要的疑难回调函数和延续。</span><span class="sxs-lookup"><span data-stu-id="fd93f-104">You can write asynchronous code that looks like synchronous code and let the compiler handle the difficult callback functions and continuations that asynchronous code usually entails.</span></span>  
  
 <span data-ttu-id="fd93f-105">有关异步功能的详细信息，请参阅[使用 Async 和 Await (Visual Basic 中) 的异步编程](../../../../visual-basic/programming-guide/concepts/async/index.md)。</span><span class="sxs-lookup"><span data-stu-id="fd93f-105">For more information about the Async feature, see [Asynchronous Programming with Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md).</span></span>  
  
 <span data-ttu-id="fd93f-106">本演练从对网站列表中的字节数进行求和的同步 Windows Presentation Foundation (WPF) 应用程序入手，</span><span class="sxs-lookup"><span data-stu-id="fd93f-106">This walkthrough starts with a synchronous Windows Presentation Foundation (WPF) application that sums the number of bytes in a list of websites.</span></span> <span data-ttu-id="fd93f-107">然后使用新功能将该应用程序转换为异步解决方案。</span><span class="sxs-lookup"><span data-stu-id="fd93f-107">The walkthrough then converts the application to an asynchronous solution by using the new features.</span></span>  
  
 <span data-ttu-id="fd93f-108">如果您不想自己生成应用程序，您可以下载"异步示例︰ 访问 Web 演练 （C# 和 Visual Basic）"从[开发人员代码示例](http://go.microsoft.com/fwlink/?LinkId=255191)。</span><span class="sxs-lookup"><span data-stu-id="fd93f-108">If you don't want to build the applications yourself, you can download "Async Sample: Accessing the Web Walkthrough (C# and Visual Basic)" from [Developer Code Samples](http://go.microsoft.com/fwlink/?LinkId=255191).</span></span>  
  
 <span data-ttu-id="fd93f-109">在本演练中，你将完成下列任务：</span><span class="sxs-lookup"><span data-stu-id="fd93f-109">In this walkthrough, you complete the following tasks:</span></span>  
  
-   [<span data-ttu-id="fd93f-110">若要创建一个 WPF 应用程序</span><span class="sxs-lookup"><span data-stu-id="fd93f-110">To create a WPF application</span></span>](#CreateWPFApp)  
  
-   [<span data-ttu-id="fd93f-111">若要设计简单的 WPF MainWindow</span><span class="sxs-lookup"><span data-stu-id="fd93f-111">To design a simple WPF MainWindow</span></span>](#MainWindow)  
  
-   [<span data-ttu-id="fd93f-112">若要添加的引用</span><span class="sxs-lookup"><span data-stu-id="fd93f-112">To add a reference</span></span>](#AddRef)  
  
-   [<span data-ttu-id="fd93f-113">若要添加必要的 Imports 语句</span><span class="sxs-lookup"><span data-stu-id="fd93f-113">To add necessary Imports statements</span></span>](#ImportsState)  
  
-   [<span data-ttu-id="fd93f-114">若要创建同步应用程序</span><span class="sxs-lookup"><span data-stu-id="fd93f-114">To create a synchronous application</span></span>](#synchronous)  
  
-   [<span data-ttu-id="fd93f-115">若要测试同步解决方案</span><span class="sxs-lookup"><span data-stu-id="fd93f-115">To test the synchronous solution</span></span>](#testSynch)  
  
-   [<span data-ttu-id="fd93f-116">将 geturlcontents 转换为异步方法</span><span class="sxs-lookup"><span data-stu-id="fd93f-116">To convert GetURLContents to an asynchronous method</span></span>](#GetURLContents)  
  
-   [<span data-ttu-id="fd93f-117">将 sumpagesizes 转换为异步方法</span><span class="sxs-lookup"><span data-stu-id="fd93f-117">To convert SumPageSizes to an asynchronous method</span></span>](#SumPageSizes)  
  
-   [<span data-ttu-id="fd93f-118">将 startbutton_click 转换为异步方法</span><span class="sxs-lookup"><span data-stu-id="fd93f-118">To convert startButton_Click to an asynchronous method</span></span>](#startButton)  
  
-   [<span data-ttu-id="fd93f-119">若要测试异步解决方案</span><span class="sxs-lookup"><span data-stu-id="fd93f-119">To test the asynchronous solution</span></span>](#testAsynch)  
  
-   [<span data-ttu-id="fd93f-120">若要使用.NET Framework 方法替换方法 GetURLContentsAsync</span><span class="sxs-lookup"><span data-stu-id="fd93f-120">To replace method GetURLContentsAsync with a .NET Framework method</span></span>](#GetURLContentsAsync)  
  
-   [<span data-ttu-id="fd93f-121">示例</span><span class="sxs-lookup"><span data-stu-id="fd93f-121">Example</span></span>](#BKMK_CompleteCodeExamples)  
  
## <a name="prerequisites"></a><span data-ttu-id="fd93f-122">先决条件</span><span class="sxs-lookup"><span data-stu-id="fd93f-122">Prerequisites</span></span>  
 <span data-ttu-id="fd93f-123">必须在您的计算机上安装 visual Studio 2012 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="fd93f-123">Visual Studio 2012 or later must be installed on your computer.</span></span> <span data-ttu-id="fd93f-124">有关详细信息，请参阅[Microsoft 网站](http://go.microsoft.com/fwlink/?LinkId=235233)。</span><span class="sxs-lookup"><span data-stu-id="fd93f-124">For more information, see the [Microsoft website](http://go.microsoft.com/fwlink/?LinkId=235233).</span></span>  
  
###  <span data-ttu-id="fd93f-125"><a name="CreateWPFApp"></a>若要创建一个 WPF 应用程序</span><span class="sxs-lookup"><span data-stu-id="fd93f-125"><a name="CreateWPFApp"></a> To create a WPF application</span></span>  
  
1.  <span data-ttu-id="fd93f-126">启动 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="fd93f-126">Start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="fd93f-127">在菜单栏上，依次选择“文件” ****、“新建” ****、“项目” ****。</span><span class="sxs-lookup"><span data-stu-id="fd93f-127">On the menu bar, choose **File**, **New**, **Project**.</span></span>  
  
     <span data-ttu-id="fd93f-128">**“新建项目”** 对话框随即打开。</span><span class="sxs-lookup"><span data-stu-id="fd93f-128">The **New Project** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="fd93f-129">在**已安装的模板**窗格中，选择 Visual Basic，然后选择**WPF 应用程序**从项目类型列表。</span><span class="sxs-lookup"><span data-stu-id="fd93f-129">In the **Installed Templates** pane, choose Visual Basic, and then choose **WPF Application** from the list of project types.</span></span>  
  
4.  <span data-ttu-id="fd93f-130">在**名称**文字框中，输入`AsyncExampleWPF`，然后选择**确定**按钮。</span><span class="sxs-lookup"><span data-stu-id="fd93f-130">In the **Name** text box, enter `AsyncExampleWPF`, and then choose the **OK** button.</span></span>  
  
     <span data-ttu-id="fd93f-131">新项目将出现在**解决方案资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="fd93f-131">The new project appears in **Solution Explorer**.</span></span>  
  
##  <a name="BKMK_DesignWPFMainWin"></a>   
###  <span data-ttu-id="fd93f-132"><a name="MainWindow"></a>若要设计简单的 WPF MainWindow</span><span class="sxs-lookup"><span data-stu-id="fd93f-132"><a name="MainWindow"></a> To design a simple WPF MainWindow</span></span>  
  
1.  <span data-ttu-id="fd93f-133">在 Visual Studio 代码编辑器中，选择 **“MainWindow.xaml”** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="fd93f-133">In the Visual Studio Code Editor, choose the **MainWindow.xaml** tab.</span></span>  
  
2.  <span data-ttu-id="fd93f-134">如果**工具箱**窗口不可见，请打开**视图**菜单上，然后选择**工具箱**。</span><span class="sxs-lookup"><span data-stu-id="fd93f-134">If the **Toolbox** window isn’t visible, open the **View** menu, and then choose **Toolbox**.</span></span>  
  
3.  <span data-ttu-id="fd93f-135">添加**按钮**控件和一个**TextBox**控制转移到**MainWindow**窗口。</span><span class="sxs-lookup"><span data-stu-id="fd93f-135">Add a **Button** control and a **TextBox** control to the **MainWindow** window.</span></span>  
  
4.  <span data-ttu-id="fd93f-136">突出显示**TextBox**控件，然后在**属性**窗口中，设置以下值︰</span><span class="sxs-lookup"><span data-stu-id="fd93f-136">Highlight the **TextBox** control and, in the **Properties** window, set the following values:</span></span>  
  
    -   <span data-ttu-id="fd93f-137">设置**名称**属性设置为`resultsTextBox`。</span><span class="sxs-lookup"><span data-stu-id="fd93f-137">Set the **Name** property to `resultsTextBox`.</span></span>  
  
    -   <span data-ttu-id="fd93f-138">设置**高度**属性设置为 250。</span><span class="sxs-lookup"><span data-stu-id="fd93f-138">Set the **Height** property to 250.</span></span>  
  
    -   <span data-ttu-id="fd93f-139">设置**宽度**属性设置为 500。</span><span class="sxs-lookup"><span data-stu-id="fd93f-139">Set the **Width** property to 500.</span></span>  
  
    -   <span data-ttu-id="fd93f-140">在**文本**选项卡上，指定等宽字体，例如黑控制台或全局等宽字体。</span><span class="sxs-lookup"><span data-stu-id="fd93f-140">On the **Text** tab, specify a monospaced font, such as Lucida Console or Global Monospace.</span></span>  
  
5.  <span data-ttu-id="fd93f-141">突出显示**按钮**控件，然后在**属性**窗口中，设置以下值︰</span><span class="sxs-lookup"><span data-stu-id="fd93f-141">Highlight the **Button** control and, in the **Properties** window, set the following values:</span></span>  
  
    -   <span data-ttu-id="fd93f-142">设置**名称**属性设置为`startButton`。</span><span class="sxs-lookup"><span data-stu-id="fd93f-142">Set the **Name** property to `startButton`.</span></span>  
  
    -   <span data-ttu-id="fd93f-143">值更改**内容**属性从**按钮**到**启动**。</span><span class="sxs-lookup"><span data-stu-id="fd93f-143">Change the value of the **Content** property from **Button** to **Start**.</span></span>  
  
6.  <span data-ttu-id="fd93f-144">定位文本框和按钮，以便这两项出现在**MainWindow**窗口。</span><span class="sxs-lookup"><span data-stu-id="fd93f-144">Position the text box and the button so that both appear in the **MainWindow** window.</span></span>  
  
     <span data-ttu-id="fd93f-145">有关 WPF XAML 设计器的详细信息，请参阅[使用 XAML 设计器创建 UI](https://docs.microsoft.com/visualstudio/designers/creating-a-ui-by-using-xaml-designer-in-visual-studio)。</span><span class="sxs-lookup"><span data-stu-id="fd93f-145">For more information about the WPF XAML Designer, see [Creating a UI by using XAML Designer](https://docs.microsoft.com/visualstudio/designers/creating-a-ui-by-using-xaml-designer-in-visual-studio).</span></span>  
  
##  <a name="BKMK_AddReference"></a>   
###  <span data-ttu-id="fd93f-146"><a name="AddRef"></a>若要添加的引用</span><span class="sxs-lookup"><span data-stu-id="fd93f-146"><a name="AddRef"></a> To add a reference</span></span>  
  
1.  <span data-ttu-id="fd93f-147">在**解决方案资源管理器**，突出显示您的项目的名称。</span><span class="sxs-lookup"><span data-stu-id="fd93f-147">In **Solution Explorer**, highlight your project's name.</span></span>  
  
2.  <span data-ttu-id="fd93f-148">在菜单栏上依次选择**项目**，**添加引用**。</span><span class="sxs-lookup"><span data-stu-id="fd93f-148">On the menu bar, choose **Project**, **Add Reference**.</span></span>  
  
     <span data-ttu-id="fd93f-149">**引用管理器**对话框随即出现。</span><span class="sxs-lookup"><span data-stu-id="fd93f-149">The **Reference Manager** dialog box appears.</span></span>  
  
3.  <span data-ttu-id="fd93f-150">在对话框中的顶部，请验证您的项目针对.NET Framework 4.5 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="fd93f-150">At the top of the dialog box, verify that your project is targeting the .NET Framework 4.5 or higher.</span></span>  
  
4.  <span data-ttu-id="fd93f-151">在**程序集**区域中，选择**Framework**如果不已经选择。</span><span class="sxs-lookup"><span data-stu-id="fd93f-151">In the **Assemblies** area, choose **Framework** if it isn’t already chosen.</span></span>  
  
5.  <span data-ttu-id="fd93f-152">在名称的列表，选择**System.Net.Http**复选框。</span><span class="sxs-lookup"><span data-stu-id="fd93f-152">In the list of names, select the **System.Net.Http** check box.</span></span>  
  
6.  <span data-ttu-id="fd93f-153">选择**确定**按钮以关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="fd93f-153">Choose the **OK** button to close the dialog box.</span></span>  
  
##  <a name="BKMK_AddStatesandDirs"></a>   
###  <span data-ttu-id="fd93f-154"><a name="ImportsState"></a>若要添加必要的 Imports 语句</span><span class="sxs-lookup"><span data-stu-id="fd93f-154"><a name="ImportsState"></a> To add necessary Imports statements</span></span>  
  
1.  <span data-ttu-id="fd93f-155">在**解决方案资源管理器**，MainWindow.xaml.vb，打开快捷菜单，然后选择**查看代码**。</span><span class="sxs-lookup"><span data-stu-id="fd93f-155">In **Solution Explorer**, open the shortcut menu for MainWindow.xaml.vb, and then choose **View Code**.</span></span>  
  
2.  <span data-ttu-id="fd93f-156">将以下代码添加`Imports`语句如果它们尚不存在的代码文件的顶部。</span><span class="sxs-lookup"><span data-stu-id="fd93f-156">Add the following `Imports` statements at the top of the code file if they’re not already present.</span></span>  
  
    ```vb  
    Imports System.Net.Http  
    Imports System.Net  
    Imports System.IO  
    ```  
  
##  <a name="BKMK_CreatSynchApp"></a>   
###  <span data-ttu-id="fd93f-157"><a name="synchronous"></a>若要创建同步应用程序</span><span class="sxs-lookup"><span data-stu-id="fd93f-157"><a name="synchronous"></a> To create a synchronous application</span></span>  
  
1.  <span data-ttu-id="fd93f-158">在设计窗口中，MainWindow.xaml，双击**启动**按钮以创建`startButton_Click`MainWindow.xaml.vb 中的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="fd93f-158">In the design window, MainWindow.xaml, double-click the **Start** button to create the `startButton_Click` event handler in MainWindow.xaml.vb.</span></span>  
  
2.  <span data-ttu-id="fd93f-159">在 MainWindow.xaml.vb，将下面的代码复制到的正文`startButton_Click`:</span><span class="sxs-lookup"><span data-stu-id="fd93f-159">In MainWindow.xaml.vb, copy the following code into the body of `startButton_Click`:</span></span>  
  
    ```vb  
    resultsTextBox.Clear()  
    SumPageSizes()  
    resultsTextBox.Text &= vbCrLf & "Control returned to startButton_Click."  
    ```  
  
     <span data-ttu-id="fd93f-160">代码调用驱动应用程序 `SumPageSizes` 的方法，并在控件返回到 `startButton_Click` 时显示一条消息。</span><span class="sxs-lookup"><span data-stu-id="fd93f-160">The code calls the method that drives the application, `SumPageSizes`, and displays a message when control returns to `startButton_Click`.</span></span>  
  
3.  <span data-ttu-id="fd93f-161">该同步解决方案的代码包含以下四个方法：</span><span class="sxs-lookup"><span data-stu-id="fd93f-161">The code for the synchronous solution contains the following four methods:</span></span>  
  
    -   <span data-ttu-id="fd93f-162">`SumPageSizes`，从 `SetUpURLList` 获取网页 URL 列表并随后调用 `GetURLContents` 和 `DisplayResults` 以处理每个 URL。</span><span class="sxs-lookup"><span data-stu-id="fd93f-162">`SumPageSizes`, which gets a list of webpage URLs from `SetUpURLList` and then calls `GetURLContents` and `DisplayResults` to process each URL.</span></span>  
  
    -   <span data-ttu-id="fd93f-163">`SetUpURLList`，生成并返回 Web 地址列表。</span><span class="sxs-lookup"><span data-stu-id="fd93f-163">`SetUpURLList`, which makes and returns a list of web addresses.</span></span>  
  
    -   <span data-ttu-id="fd93f-164">`GetURLContents`，下载每个网站的内容并将内容作为字节数组返回。</span><span class="sxs-lookup"><span data-stu-id="fd93f-164">`GetURLContents`, which downloads the contents of each website and returns the contents as a byte array.</span></span>  
  
    -   <span data-ttu-id="fd93f-165">`DisplayResults`，显示每个 URL 的字节数组中的字节数。</span><span class="sxs-lookup"><span data-stu-id="fd93f-165">`DisplayResults`, which displays  the number of bytes in the byte array for each URL.</span></span>  
  
     <span data-ttu-id="fd93f-166">复制以下四种方法，然后再粘贴它们下`startButton_Click`MainWindow.xaml.vb 中的事件处理程序︰</span><span class="sxs-lookup"><span data-stu-id="fd93f-166">Copy the following four methods, and then paste them under the `startButton_Click` event handler in MainWindow.xaml.vb:</span></span>  
  
    ```vb  
    Private Sub SumPageSizes()  
  
        ' Make a list of web addresses.  
        Dim urlList As List(Of String) = SetUpURLList()  
  
        Dim total = 0  
        For Each url In urlList  
            ' GetURLContents returns the contents of url as a byte array.  
            Dim urlContents As Byte() = GetURLContents(url)  
  
            DisplayResults(url, urlContents)  
  
            ' Update the total.  
            total += urlContents.Length  
        Next  
  
        ' Display the total count for all of the web addresses.  
        resultsTextBox.Text &= String.Format(vbCrLf & vbCrLf & "Total bytes returned:  {0}" & vbCrLf, total)  
    End Sub  
  
    Private Function SetUpURLList() As List(Of String)  
  
        Dim urls = New List(Of String) From  
            {  
                "http://msdn.microsoft.com/library/windows/apps/br211380.aspx",  
                "http://msdn.microsoft.com",  
                "http://msdn.microsoft.com/library/hh290136.aspx",  
                "http://msdn.microsoft.com/library/ee256749.aspx",  
                "http://msdn.microsoft.com/library/hh290138.aspx",  
                "http://msdn.microsoft.com/library/hh290140.aspx",  
                "http://msdn.microsoft.com/library/dd470362.aspx",  
                "http://msdn.microsoft.com/library/aa578028.aspx",  
                "http://msdn.microsoft.com/library/ms404677.aspx",  
                "http://msdn.microsoft.com/library/ff730837.aspx"  
            }  
        Return urls  
    End Function  
  
    Private Function GetURLContents(url As String) As Byte()  
  
        ' The downloaded resource ends up in the variable named content.  
        Dim content = New MemoryStream()  
  
        ' Initialize an HttpWebRequest for the current URL.  
        Dim webReq = CType(WebRequest.Create(url), HttpWebRequest)  
  
        ' Send the request to the Internet resource and wait for  
        ' the response.  
        ' Note: you can't use HttpWebRequest.GetResponse in a Windows Store app.  
        Using response As WebResponse = webReq.GetResponse()  
            ' Get the data stream that is associated with the specified URL.  
            Using responseStream As Stream = response.GetResponseStream()  
                ' Read the bytes in responseStream and copy them to content.    
                responseStream.CopyTo(content)  
            End Using  
        End Using  
  
        ' Return the result as a byte array.  
        Return content.ToArray()  
    End Function  
  
    Private Sub DisplayResults(url As String, content As Byte())  
  
        ' Display the length of each website. The string format   
        ' is designed to be used with a monospaced font, such as  
        ' Lucida Console or Global Monospace.  
        Dim bytes = content.Length  
        ' Strip off the "http://".  
        Dim displayURL = url.Replace("http://", "")  
        resultsTextBox.Text &= String.Format(vbCrLf & "{0,-58} {1,8}", displayURL, bytes)  
    End Sub  
    ```  
  
##  <a name="BKMK_TestSynchSol"></a>   
###  <span data-ttu-id="fd93f-167"><a name="testSynch"></a>若要测试同步解决方案</span><span class="sxs-lookup"><span data-stu-id="fd93f-167"><a name="testSynch"></a> To test the synchronous solution</span></span>  
  
1.  <span data-ttu-id="fd93f-168">按 F5 键以运行程序，然后选择 **“启动”** 按钮。</span><span class="sxs-lookup"><span data-stu-id="fd93f-168">Choose the F5 key to run the program, and then choose the **Start** button.</span></span>  
  
     <span data-ttu-id="fd93f-169">此时应显示类似于下列列表的输出。</span><span class="sxs-lookup"><span data-stu-id="fd93f-169">Output that resembles the following list should appear.</span></span>  
  
    ```  
  
    msdn.microsoft.com/library/windows/apps/br211380.aspx        383832  
    msdn.microsoft.com                                            33964  
    msdn.microsoft.com/library/hh290136.aspx               225793  
    msdn.microsoft.com/library/ee256749.aspx               143577  
    msdn.microsoft.com/library/hh290138.aspx               237372  
    msdn.microsoft.com/library/hh290140.aspx               128279  
    msdn.microsoft.com/library/dd470362.aspx               157649  
    msdn.microsoft.com/library/aa578028.aspx               204457  
    msdn.microsoft.com/library/ms404677.aspx               176405  
    msdn.microsoft.com/library/ff730837.aspx               143474  
  
    Total bytes returned:  1834802  
  
    Control returned to startButton_Click.  
  
    ```  
  
     <span data-ttu-id="fd93f-170">请注意，显示计数需要几秒钟时间。</span><span class="sxs-lookup"><span data-stu-id="fd93f-170">Notice that it takes a few seconds to display the counts.</span></span> <span data-ttu-id="fd93f-171">与此同时，在等待请求的资源下载时，UI 线程处于被阻止状态。</span><span class="sxs-lookup"><span data-stu-id="fd93f-171">During that time, the UI thread is blocked while it waits for requested resources to download.</span></span> <span data-ttu-id="fd93f-172">结果是，您不能移动、 最大化、 最小化，或甚至在您选择后关闭显示窗口**启动**按钮。</span><span class="sxs-lookup"><span data-stu-id="fd93f-172">As a result, you can't move, maximize, minimize, or even close the display window after you choose the  **Start** button.</span></span> <span data-ttu-id="fd93f-173">在字节计数开始显示之前，这些操作都会失败。</span><span class="sxs-lookup"><span data-stu-id="fd93f-173">These efforts fail until the byte counts start to appear.</span></span> <span data-ttu-id="fd93f-174">如果网站没有响应，将不会指示哪个网站失败。</span><span class="sxs-lookup"><span data-stu-id="fd93f-174">If a website isn’t responding, you have no indication of which site failed.</span></span> <span data-ttu-id="fd93f-175">甚至停止等待和关闭程序也会很困难。</span><span class="sxs-lookup"><span data-stu-id="fd93f-175">It is difficult even to stop waiting and close the program.</span></span>  
  
##  <a name="BKMK_ConvertGtBtArr"></a>   
###  <span data-ttu-id="fd93f-176"><a name="GetURLContents"></a>将 geturlcontents 转换为异步方法</span><span class="sxs-lookup"><span data-stu-id="fd93f-176"><a name="GetURLContents"></a> To convert GetURLContents to an asynchronous method</span></span>  
  
1.  <span data-ttu-id="fd93f-177">若要转换成一个异步解决方案的同步解决方案，以启动的最佳位置，是在`GetURLContents`因为对调用<xref:System.Net.HttpWebRequest>方法<xref:System.Net.HttpWebRequest.GetResponse%2A>和<xref:System.IO.Stream>方法<xref:System.IO.Stream.CopyTo%2A>是应用程序用来访问 web。</xref:System.IO.Stream.CopyTo%2A> </xref:System.IO.Stream> </xref:System.Net.HttpWebRequest.GetResponse%2A> </xref:System.Net.HttpWebRequest></span><span class="sxs-lookup"><span data-stu-id="fd93f-177">To convert the synchronous solution to an asynchronous solution, the best place to start is in `GetURLContents` because the calls to the <xref:System.Net.HttpWebRequest> method <xref:System.Net.HttpWebRequest.GetResponse%2A> and to the <xref:System.IO.Stream> method <xref:System.IO.Stream.CopyTo%2A> are where the application accesses the web.</span></span> <span data-ttu-id="fd93f-178">.NET Framework 提供两种方法的异步版本，这让转换变得轻松。</span><span class="sxs-lookup"><span data-stu-id="fd93f-178">The .NET Framework makes the conversion easy by supplying asynchronous versions of both methods.</span></span>  
  
     <span data-ttu-id="fd93f-179">有关详细信息的方法中使用的`GetURLContents`，请参阅<xref:System.Net.WebRequest>。</xref:System.Net.WebRequest></span><span class="sxs-lookup"><span data-stu-id="fd93f-179">For more information about the methods that are used in `GetURLContents`, see <xref:System.Net.WebRequest>.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fd93f-180">在你按照本演练中的步骤进行操作的过程中，将出现多个编译器错误。</span><span class="sxs-lookup"><span data-stu-id="fd93f-180">As you follow the steps in this walkthrough, several compiler errors appear.</span></span> <span data-ttu-id="fd93f-181">你可以忽略这些错误并继续演练。</span><span class="sxs-lookup"><span data-stu-id="fd93f-181">You can ignore them and continue with the walkthrough.</span></span>  
  
     <span data-ttu-id="fd93f-182">更改中的第三行调用的方法`GetURLContents`从`GetResponse`对异步的基于任务的<xref:System.Net.WebRequest.GetResponseAsync%2A>方法。</xref:System.Net.WebRequest.GetResponseAsync%2A></span><span class="sxs-lookup"><span data-stu-id="fd93f-182">Change the method that's called in the third line of `GetURLContents` from `GetResponse` to the asynchronous, task-based <xref:System.Net.WebRequest.GetResponseAsync%2A> method.</span></span>  
  
    ```vb  
    Using response As WebResponse = webReq.GetResponseAsync()  
    ```  
  
2.  <span data-ttu-id="fd93f-183">`GetResponseAsync`返回一种<xref:System.Threading.Tasks.Task%601>。</xref:System.Threading.Tasks.Task%601></span><span class="sxs-lookup"><span data-stu-id="fd93f-183">`GetResponseAsync` returns a <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="fd93f-184">在这种情况下，*任务返回变量*， `TResult`，具有类型<xref:System.Net.WebResponse>。</xref:System.Net.WebResponse></span><span class="sxs-lookup"><span data-stu-id="fd93f-184">In this case, the *task return variable*, `TResult`, has type <xref:System.Net.WebResponse>.</span></span> <span data-ttu-id="fd93f-185">该任务是在请求的任务已下载且任务已完成运行后，生成实际 `WebResponse` 对象的承诺。</span><span class="sxs-lookup"><span data-stu-id="fd93f-185">The task is a promise to produce an actual `WebResponse` object after the requested data has been downloaded and the task has run to completion.</span></span>  
  
     <span data-ttu-id="fd93f-186">若要检索`WebResponse`值从任务时，请将应用[Await](../../../../visual-basic/language-reference/operators/await-operator.md)运算符以对调用`GetResponseAsync`，如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="fd93f-186">To retrieve the `WebResponse` value from the task, apply an [Await](../../../../visual-basic/language-reference/operators/await-operator.md) operator to the call to `GetResponseAsync`, as the following code shows.</span></span>  
  
<span data-ttu-id="fd93f-187"><CodeContentPlaceHolder>5</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="fd93f-187"><CodeContentPlaceHolder>5</CodeContentPlaceHolder></span></span>  
     <span data-ttu-id="fd93f-188">`Await`运算符将暂停当前方法的执行`GetURLContents`，直到所等待的任务已完成。</span><span class="sxs-lookup"><span data-stu-id="fd93f-188">The `Await` operator suspends the execution of the current method, `GetURLContents`, until the awaited task is complete.</span></span> <span data-ttu-id="fd93f-189">同时，控制权返回给当前方法的调用方。</span><span class="sxs-lookup"><span data-stu-id="fd93f-189">In the meantime, control returns to the caller of the current method.</span></span> <span data-ttu-id="fd93f-190">在此示例中，当前方法是 `GetURLContents`，调用方是 `SumPageSizes`。</span><span class="sxs-lookup"><span data-stu-id="fd93f-190">In this example, the current method is `GetURLContents`, and the caller is `SumPageSizes`.</span></span> <span data-ttu-id="fd93f-191">任务完成时，承诺的 `WebResponse` 对象作为等待的任务的值生成，并分配给变量 `response`。</span><span class="sxs-lookup"><span data-stu-id="fd93f-191">When the task is finished, the promised `WebResponse` object is produced as the value of the awaited task and assigned to the variable `response`.</span></span>  
  
     The previous statement can be separated into the following two statements to clarify what happens.  
  
<span data-ttu-id="fd93f-192"><CodeContentPlaceHolder>6</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="fd93f-192"><CodeContentPlaceHolder>6</CodeContentPlaceHolder></span></span>  
     <span data-ttu-id="fd93f-193">对 `webReq.GetResponseAsync` 的调用返回 `Task(Of WebResponse)` 或 `Task<WebResponse>`。</span><span class="sxs-lookup"><span data-stu-id="fd93f-193">The call to `webReq.GetResponseAsync` returns a `Task(Of WebResponse)` or `Task<WebResponse>`.</span></span> <span data-ttu-id="fd93f-194">则`Await`运算符应用于要检索的任务`WebResponse`值。</span><span class="sxs-lookup"><span data-stu-id="fd93f-194">Then an `Await` operator is applied to the task to retrieve the `WebResponse` value.</span></span>  
  
     If your async method has work to do that doesn’t depend on the completion of the task, the method can continue with that work between these two statements, after the call to the async method and before the await operator is applied. For examples, see [How to: Make Multiple Web Requests in Parallel by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md) and [How to: Extend the Async Walkthrough by Using Task.WhenAll (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md).  
  
3.  <span data-ttu-id="fd93f-195">由于你添加了`Await`上一步中的运算符，则编译器将发生错误。</span><span class="sxs-lookup"><span data-stu-id="fd93f-195">Because you added the `Await` operator in the previous step, a compiler error occurs.</span></span> <span data-ttu-id="fd93f-196">可以仅在使用标记的方法中使用运算符[异步](../../../../visual-basic/language-reference/modifiers/async.md)修饰符。</span><span class="sxs-lookup"><span data-stu-id="fd93f-196">The operator can be used only in methods that are marked with the [Async](../../../../visual-basic/language-reference/modifiers/async.md) modifier.</span></span> <span data-ttu-id="fd93f-197">当你重复转换步骤以使用对 `CopyToAsync` 的调用替换对 `CopyTo` 的调用时，请忽略该错误。</span><span class="sxs-lookup"><span data-stu-id="fd93f-197">Ignore the error while you repeat the conversion steps to replace the call to `CopyTo` with a call to `CopyToAsync`.</span></span>  
  
    -   <span data-ttu-id="fd93f-198">更改到<xref:System.IO.Stream.CopyToAsync%2A>。</xref:System.IO.Stream.CopyToAsync%2A>调用的方法的名称</span><span class="sxs-lookup"><span data-stu-id="fd93f-198">Change the name of the method that’s called to <xref:System.IO.Stream.CopyToAsync%2A>.</span></span>  
  
    -   <span data-ttu-id="fd93f-199">`CopyTo` 或 `CopyToAsync` 方法复制字节到其参数 `content`，并且不返回有意义的值。</span><span class="sxs-lookup"><span data-stu-id="fd93f-199">The `CopyTo` or `CopyToAsync` method copies bytes to its argument, `content`, and doesn’t return a meaningful value.</span></span> <span data-ttu-id="fd93f-200">在同步版本中，对 `CopyTo` 的调用是不返回值的简单语句。</span><span class="sxs-lookup"><span data-stu-id="fd93f-200">In the synchronous version, the call to `CopyTo` is a simple statement that doesn't return a value.</span></span> <span data-ttu-id="fd93f-201">异步版本`CopyToAsync`，返回一种<xref:System.Threading.Tasks.Task>。</xref:System.Threading.Tasks.Task></span><span class="sxs-lookup"><span data-stu-id="fd93f-201">The asynchronous version, `CopyToAsync`, returns a <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="fd93f-202">任务函数类似“Task(void)”，并让该方法能够等待。</span><span class="sxs-lookup"><span data-stu-id="fd93f-202">The task functions like "Task(void)" and enables the method to be awaited.</span></span> <span data-ttu-id="fd93f-203">应用 `Await` 或 `await` 到对 `CopyToAsync` 的调用，如下列代码所示。</span><span class="sxs-lookup"><span data-stu-id="fd93f-203">Apply `Await` or `await` to the call to `CopyToAsync`, as the following code shows.</span></span>  
  
<span data-ttu-id="fd93f-204"><CodeContentPlaceHolder>7</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="fd93f-204"><CodeContentPlaceHolder>7</CodeContentPlaceHolder></span></span>  
         <span data-ttu-id="fd93f-205">上一条语句缩写以下两行代码。</span><span class="sxs-lookup"><span data-stu-id="fd93f-205">The previous statement abbreviates the following two lines of code.</span></span>  
  
<span data-ttu-id="fd93f-206"><CodeContentPlaceHolder>8</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="fd93f-206"><CodeContentPlaceHolder>8</CodeContentPlaceHolder></span></span>  
4.  <span data-ttu-id="fd93f-207">`GetURLContents` 中仍需要完成的操作是调整方法签名。</span><span class="sxs-lookup"><span data-stu-id="fd93f-207">All that remains to be done in `GetURLContents` is to adjust the method signature.</span></span> <span data-ttu-id="fd93f-208">您可以使用`Await`仅在使用标记的方法中的运算符[异步](../../../../visual-basic/language-reference/modifiers/async.md)修饰符。</span><span class="sxs-lookup"><span data-stu-id="fd93f-208">You can use the `Await` operator only in methods that are marked with the [Async](../../../../visual-basic/language-reference/modifiers/async.md) modifier.</span></span> <span data-ttu-id="fd93f-209">添加修饰符来标记该方法为*async 方法*，如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="fd93f-209">Add the modifier to mark the method as an *async method*, as the following code shows.</span></span>  
  
<span data-ttu-id="fd93f-210"><CodeContentPlaceHolder>9</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="fd93f-210"><CodeContentPlaceHolder>9</CodeContentPlaceHolder></span></span>  
5.  <span data-ttu-id="fd93f-211">异步方法的返回类型也只能<xref:System.Threading.Tasks.Task>、 <xref:System.Threading.Tasks.Task%601>。</xref:System.Threading.Tasks.Task%601> </xref:System.Threading.Tasks.Task></span><span class="sxs-lookup"><span data-stu-id="fd93f-211">The return type of an async method can only be <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="fd93f-212">在 Visual Basic 中，方法必须为返回 `Task` 或 `Task(Of T)` 的 `Function`，或方法必须为 `Sub`。</span><span class="sxs-lookup"><span data-stu-id="fd93f-212">In Visual Basic, the method must be a `Function` that returns a `Task` or a `Task(Of T)`, or the method must be a `Sub`.</span></span> <span data-ttu-id="fd93f-213">通常情况下，`Sub`方法仅用于异步事件处理程序，其中`Sub`是必需的。</span><span class="sxs-lookup"><span data-stu-id="fd93f-213">Typically, a `Sub` method  is used only in an async event handler, where `Sub` is required.</span></span> <span data-ttu-id="fd93f-214">在其他情况下，您将使用`Task(T)`如果已完成的方法有[返回](../../../../visual-basic/language-reference/statements/return-statement.md)语句返回值的类型 T，并且你使用`Task`如果已完成的方法不返回有意义的值。</span><span class="sxs-lookup"><span data-stu-id="fd93f-214">In other cases, you use `Task(T)` if the completed method has a [Return](../../../../visual-basic/language-reference/statements/return-statement.md) statement that returns a value of type T, and you use `Task` if the completed method doesn’t return a meaningful value.</span></span>  
  
     <span data-ttu-id="fd93f-215">有关详细信息，请参阅[异步返回类型 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md)。</span><span class="sxs-lookup"><span data-stu-id="fd93f-215">For more information, see [Async Return Types (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span></span>  
  
     <span data-ttu-id="fd93f-216">方法 `GetURLContents` 具有 return 语句，且该语句返回字节数组。</span><span class="sxs-lookup"><span data-stu-id="fd93f-216">Method `GetURLContents` has a return statement, and the statement returns a byte array.</span></span> <span data-ttu-id="fd93f-217">因此，异步版本的返回类型为 Task(T)，其中 T 为字节数组。</span><span class="sxs-lookup"><span data-stu-id="fd93f-217">Therefore, the return type of the async version is Task(T), where T is a byte array.</span></span> <span data-ttu-id="fd93f-218">在方法签名中进行下列更改：</span><span class="sxs-lookup"><span data-stu-id="fd93f-218">Make the following changes in the method signature:</span></span>  
  
    -   <span data-ttu-id="fd93f-219">更改返回类型设置为`Task(Of Byte())`。</span><span class="sxs-lookup"><span data-stu-id="fd93f-219">Change the return type to `Task(Of Byte())`.</span></span>  
  
    -   <span data-ttu-id="fd93f-220">按照约定，异步方法的名称以“Async”结尾，因此，请重命名方法 `GetURLContentsAsync`。</span><span class="sxs-lookup"><span data-stu-id="fd93f-220">By convention, asynchronous methods have names that end in "Async," so rename the method `GetURLContentsAsync`.</span></span>  
  
     <span data-ttu-id="fd93f-221">下列代码显示这些更改。</span><span class="sxs-lookup"><span data-stu-id="fd93f-221">The following code shows these changes.</span></span>  
  
    ```vb  
    Private Async Function GetURLContentsAsync(url As String) As Task(Of Byte())  
    ```  
  
     <span data-ttu-id="fd93f-222">进行这几处更改后，`GetURLContents` 到异步方法的转换完成。</span><span class="sxs-lookup"><span data-stu-id="fd93f-222">With those few changes, the conversion of `GetURLContents` to an asynchronous method is complete.</span></span>  
  
##  <a name="BKMK_ConvertSumPagSzs"></a>   
###  <span data-ttu-id="fd93f-223"><a name="SumPageSizes"></a>将 sumpagesizes 转换为异步方法</span><span class="sxs-lookup"><span data-stu-id="fd93f-223"><a name="SumPageSizes"></a> To convert SumPageSizes to an asynchronous method</span></span>  
  
1.  <span data-ttu-id="fd93f-224">为 `SumPageSizes` 重复之前过程中的步骤。</span><span class="sxs-lookup"><span data-stu-id="fd93f-224">Repeat the steps from the previous procedure for `SumPageSizes`.</span></span> <span data-ttu-id="fd93f-225">首先，将对 `GetURLContents` 的调用更改为异步调用。</span><span class="sxs-lookup"><span data-stu-id="fd93f-225">First, change the call to `GetURLContents` to an asynchronous call.</span></span>  
  
    -   <span data-ttu-id="fd93f-226">将调用的方法的名称从 `GetURLContents` 更改为 `GetURLContentsAsync`（如果尚未执行此操作）。</span><span class="sxs-lookup"><span data-stu-id="fd93f-226">Change the name of the method that’s called from `GetURLContents` to `GetURLContentsAsync`, if you haven't already done so.</span></span>  
  
    -   <span data-ttu-id="fd93f-227">应用`Await`给任务的`GetURLContentsAsync`返回以获取字节数组值。</span><span class="sxs-lookup"><span data-stu-id="fd93f-227">Apply `Await` to the task that `GetURLContentsAsync` returns to obtain the byte array value.</span></span>  
  
     <span data-ttu-id="fd93f-228">下列代码显示这些更改。</span><span class="sxs-lookup"><span data-stu-id="fd93f-228">The following code shows these changes.</span></span>  
  
    ```vb  
    Dim urlContents As Byte() = Await GetURLContentsAsync(url)  
    ```  
  
     <span data-ttu-id="fd93f-229">上一个分配缩写以下两行代码。</span><span class="sxs-lookup"><span data-stu-id="fd93f-229">The previous assignment abbreviates the following two lines of code.</span></span>  
  
    ```vb  
    ' GetURLContentsAsync returns a task. At completion, the task   
    ' produces a byte array.   
    'Dim getContentsTask As Task(Of Byte()) = GetURLContentsAsync(url)   
    'Dim urlContents As Byte() = Await getContentsTask  
  
    ```  
  
2.  <span data-ttu-id="fd93f-230">在方法签名中进行下列更改：</span><span class="sxs-lookup"><span data-stu-id="fd93f-230">Make the following changes in the method's signature:</span></span>  
  
    -   <span data-ttu-id="fd93f-231">此方法标记`Async`修饰符。</span><span class="sxs-lookup"><span data-stu-id="fd93f-231">Mark the method with the `Async` modifier.</span></span>  
  
    -   <span data-ttu-id="fd93f-232">将“Async”添加到方法名称。</span><span class="sxs-lookup"><span data-stu-id="fd93f-232">Add "Async" to the method name.</span></span>  
  
    -   <span data-ttu-id="fd93f-233">这一次没有任务返回变量 T，因为 `SumPageSizesAsync` 不返回 T 的值。(该方法没有`Return`语句。)但是，该方法必须返回 `Task` 才能进行等待。</span><span class="sxs-lookup"><span data-stu-id="fd93f-233">There is no task return variable, T, this time because `SumPageSizesAsync` doesn’t return a value for T. (The method has no `Return` statement.) However, the method must return a `Task` to be awaitable.</span></span> <span data-ttu-id="fd93f-234">因此，更改中的方法类型`Sub`到`Function`。</span><span class="sxs-lookup"><span data-stu-id="fd93f-234">Therefore, change the method type from `Sub` to `Function`.</span></span> <span data-ttu-id="fd93f-235">函数的返回类型为 `Task`。</span><span class="sxs-lookup"><span data-stu-id="fd93f-235">The return type of the function is `Task`.</span></span>  
  
     <span data-ttu-id="fd93f-236">下列代码显示这些更改。</span><span class="sxs-lookup"><span data-stu-id="fd93f-236">The following code shows these changes.</span></span>  
  
    ```vb  
    Private Async Function SumPageSizesAsync() As Task  
    ```  
  
     <span data-ttu-id="fd93f-237">从 `SumPageSizes` 到 `SumPageSizesAsync` 的转换完成。</span><span class="sxs-lookup"><span data-stu-id="fd93f-237">The conversion of `SumPageSizes` to `SumPageSizesAsync` is complete.</span></span>  
  
##  <a name="BKMK_Cnvrtbttn1"></a>   
###  <span data-ttu-id="fd93f-238"><a name="startButton"></a>将 startbutton_click 转换为异步方法</span><span class="sxs-lookup"><span data-stu-id="fd93f-238"><a name="startButton"></a> To convert startButton_Click to an asynchronous method</span></span>  
  
1.  <span data-ttu-id="fd93f-239">在事件处理程序中，将调用的方法的名称从 `SumPageSizes` 更改为 `SumPageSizesAsync`（如果尚未执行此操作）。</span><span class="sxs-lookup"><span data-stu-id="fd93f-239">In the event handler, change the name of the called method from `SumPageSizes` to `SumPageSizesAsync`, if you haven’t already done so.</span></span>  
  
2.  <span data-ttu-id="fd93f-240">由于 `SumPageSizesAsync` 是异步方法，请更改事件处理程序中的代码以等待结果。</span><span class="sxs-lookup"><span data-stu-id="fd93f-240">Because `SumPageSizesAsync` is an async method, change the code in the event handler to await the result.</span></span>  
  
     <span data-ttu-id="fd93f-241">对 `SumPageSizesAsync` 的调用反射对 `GetURLContentsAsync` 中的 `CopyToAsync` 的调用。</span><span class="sxs-lookup"><span data-stu-id="fd93f-241">The call to `SumPageSizesAsync` mirrors the call to `CopyToAsync` in `GetURLContentsAsync`.</span></span> <span data-ttu-id="fd93f-242">调用返回的是 `Task`，而不是 `Task(T)`。</span><span class="sxs-lookup"><span data-stu-id="fd93f-242">The call returns a `Task`, not a `Task(T)`.</span></span>  
  
     <span data-ttu-id="fd93f-243">与之前的过程一样，你可以使用一条语句或两条语句转换调用。</span><span class="sxs-lookup"><span data-stu-id="fd93f-243">As in previous procedures, you can convert the call by using one statement or two statements.</span></span> <span data-ttu-id="fd93f-244">下列代码显示这些更改。</span><span class="sxs-lookup"><span data-stu-id="fd93f-244">The following code shows these changes.</span></span>  
  
    ```vb  
    '' One-step async call.  
    Await SumPageSizesAsync()  
  
    ' Two-step async call.  
    'Dim sumTask As Task = SumPageSizesAsync()  
    'Await sumTask  
    ```  
  
3.  <span data-ttu-id="fd93f-245">若要防止意外重新输入该操作，在顶部添加以下语句`startButton_Click`禁用**启动**按钮。</span><span class="sxs-lookup"><span data-stu-id="fd93f-245">To prevent accidentally reentering the operation, add the following statement at the top of `startButton_Click` to disable the **Start** button.</span></span>  
  
    ```vb  
    ' Disable the button until the operation is complete.  
    startButton.IsEnabled = False  
    ```  
  
     <span data-ttu-id="fd93f-246">可以重新启用事件处理程序末尾的按钮。</span><span class="sxs-lookup"><span data-stu-id="fd93f-246">You can reenable the button at the end of the event handler.</span></span>  
  
    ```vb  
    ' Reenable the button in case you want to run the operation again.  
    startButton.IsEnabled = True  
    ```  
  
     <span data-ttu-id="fd93f-247">有关重入的详细信息，请参阅[处理异步应用程序 (Visual Basic 中) 中的重入](../../../../visual-basic/programming-guide/concepts/async/handling-reentrancy-in-async-apps.md)。</span><span class="sxs-lookup"><span data-stu-id="fd93f-247">For more information about reentrancy, see [Handling Reentrancy in Async Apps (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/handling-reentrancy-in-async-apps.md).</span></span>  
  
4.  <span data-ttu-id="fd93f-248">最后，添加`Async`修饰符声明，以便事件处理程序可以等待`SumPagSizesAsync`。</span><span class="sxs-lookup"><span data-stu-id="fd93f-248">Finally, add the `Async` modifier to the declaration so that the event handler can await `SumPagSizesAsync`.</span></span>  
  
    ```vb  
    Async Sub startButton_Click(sender As Object, e As RoutedEventArgs) Handles startButton.Click  
    ```  
  
     <span data-ttu-id="fd93f-249">通常情况下，事件处理程序的名称不会更改。</span><span class="sxs-lookup"><span data-stu-id="fd93f-249">Typically, the names of event handlers aren’t changed.</span></span> <span data-ttu-id="fd93f-250">返回类型不更改为`Task`因为事件处理程序必须是`Sub`Visual Basic 中的过程。</span><span class="sxs-lookup"><span data-stu-id="fd93f-250">The return type isn’t changed to `Task` because event handlers must be `Sub` procedures in Visual Basic.</span></span>  
  
     <span data-ttu-id="fd93f-251">项目从同步处理到异步处理的转换完成。</span><span class="sxs-lookup"><span data-stu-id="fd93f-251">The conversion of the project from synchronous to asynchronous processing is complete.</span></span>  
  
##  <a name="BKMK_testAsynchSolution"></a>   
###  <span data-ttu-id="fd93f-252"><a name="testAsynch"></a>若要测试异步解决方案</span><span class="sxs-lookup"><span data-stu-id="fd93f-252"><a name="testAsynch"></a> To test the asynchronous solution</span></span>  
  
1.  <span data-ttu-id="fd93f-253">按 F5 键以运行程序，然后选择 **“启动”** 按钮。</span><span class="sxs-lookup"><span data-stu-id="fd93f-253">Choose the F5 key to run the program, and then choose the **Start** button.</span></span>  
  
2.  <span data-ttu-id="fd93f-254">此时应显示类似于同步解决方案的输出的输出。</span><span class="sxs-lookup"><span data-stu-id="fd93f-254">Output that resembles the output of the synchronous solution should appear.</span></span> <span data-ttu-id="fd93f-255">但是，请注意下列差异。</span><span class="sxs-lookup"><span data-stu-id="fd93f-255">However, notice the following differences.</span></span>  
  
    -   <span data-ttu-id="fd93f-256">处理完成后，所有结果不会同时出现。</span><span class="sxs-lookup"><span data-stu-id="fd93f-256">The results don’t all occur at the same time, after the processing is complete.</span></span> <span data-ttu-id="fd93f-257">例如，两个程序都在 `startButton_Click` 中包含一行可以清除文本框的代码。</span><span class="sxs-lookup"><span data-stu-id="fd93f-257">For example, both programs contain a line in `startButton_Click` that clears the text box.</span></span> <span data-ttu-id="fd93f-258">其目的是为了清除运行间隔文本框中，如果您选择**启动**后个结果集已显示的第二个时间的按钮。</span><span class="sxs-lookup"><span data-stu-id="fd93f-258">The intent is to clear the text box between runs if you choose the **Start** button for a second time, after one set of results has appeared.</span></span> <span data-ttu-id="fd93f-259">在同步版本中，下载完成且 UI 线程可以自由完成其他工作时，文本框在计数第二次显示之前即被清除。</span><span class="sxs-lookup"><span data-stu-id="fd93f-259">In the synchronous version, the text box is cleared just before the counts appear for the second time, when the downloads are completed and the UI thread is free to do other work.</span></span> <span data-ttu-id="fd93f-260">在异步版本中，文本框中之后立即清除您选择**启动**按钮。</span><span class="sxs-lookup"><span data-stu-id="fd93f-260">In the asynchronous version, the text box clears immediately after you choose the **Start** button.</span></span>  
  
    -   <span data-ttu-id="fd93f-261">最重要的是，UI 线程在下载过程中未被阻止。</span><span class="sxs-lookup"><span data-stu-id="fd93f-261">Most importantly, the UI thread isn’t blocked during the downloads.</span></span> <span data-ttu-id="fd93f-262">在 Web 资源下载、计数和显示期间，可以移动窗口或调整窗口大小。</span><span class="sxs-lookup"><span data-stu-id="fd93f-262">You can move or resize the window while the web resources are being downloaded, counted, and displayed.</span></span> <span data-ttu-id="fd93f-263">如果其中一个网站运行缓慢或没有响应，您可以通过选择取消该操作**关闭**按钮 (在右上角的红色字段中 x)。</span><span class="sxs-lookup"><span data-stu-id="fd93f-263">If one of the websites is slow or not responding, you can cancel the operation by choosing the **Close** button (the x in the red field in the upper-right corner).</span></span>  
  
##  <a name="BKMK_ReplaceGetByteArrayAsync"></a>   
###  <span data-ttu-id="fd93f-264"><a name="GetURLContentsAsync"></a>若要使用.NET Framework 方法替换方法 GetURLContentsAsync</span><span class="sxs-lookup"><span data-stu-id="fd93f-264"><a name="GetURLContentsAsync"></a> To replace method GetURLContentsAsync with a .NET Framework method</span></span>  
  
1.  <span data-ttu-id="fd93f-265">.NET Framework 4.5 提供可供你使用的许多异步方法。</span><span class="sxs-lookup"><span data-stu-id="fd93f-265">The .NET Framework 4.5 provides many async methods that you can use.</span></span> <span data-ttu-id="fd93f-266">其中之一，<xref:System.Net.Http.HttpClient>方法<xref:System.Net.Http.HttpClient.GetByteArrayAsync%28System.String%29>，没有正是您所需要对于本演练。</xref:System.Net.Http.HttpClient.GetByteArrayAsync%28System.String%29> </xref:System.Net.Http.HttpClient></span><span class="sxs-lookup"><span data-stu-id="fd93f-266">One of them, the <xref:System.Net.Http.HttpClient> method <xref:System.Net.Http.HttpClient.GetByteArrayAsync%28System.String%29>, does just what you need for this walkthrough.</span></span> <span data-ttu-id="fd93f-267">你可以使用它来替代你在早前过程中创建的 `GetURLContentsAsync` 方法。</span><span class="sxs-lookup"><span data-stu-id="fd93f-267">You can use it instead of the `GetURLContentsAsync` method that you created in an earlier procedure.</span></span>  
  
     <span data-ttu-id="fd93f-268">第一步是在方法 `SumPageSizesAsync` 中创建 `HttpClient` 对象。</span><span class="sxs-lookup"><span data-stu-id="fd93f-268">The first step is to create an `HttpClient` object in method `SumPageSizesAsync`.</span></span> <span data-ttu-id="fd93f-269">在方法的开头添加下列声明。</span><span class="sxs-lookup"><span data-stu-id="fd93f-269">Add the following declaration at the start of the method.</span></span>  
  
    ```vb  
    ' Declare an HttpClient object and increase the buffer size. The  
    ' default buffer size is 65,536.  
    Dim client As HttpClient =  
        New HttpClient() With {.MaxResponseContentBufferSize = 1000000}  
    ```  
  
2.  <span data-ttu-id="fd93f-270">在 `SumPageSizesAsync,` 中，使用对 `HttpClient` 方法的调用替换对 `GetURLContentsAsync` 方法的调用。</span><span class="sxs-lookup"><span data-stu-id="fd93f-270">In `SumPageSizesAsync,` replace the call to your `GetURLContentsAsync` method with a call to the `HttpClient` method.</span></span>  
  
    ```vb  
    Dim urlContents As Byte() = Await client.GetByteArrayAsync(url)  
    ```  
  
3.  <span data-ttu-id="fd93f-271">删除或注释禁用你编写的 `GetURLContentsAsync` 方法。</span><span class="sxs-lookup"><span data-stu-id="fd93f-271">Remove or comment out the `GetURLContentsAsync` method that you wrote.</span></span>  
  
4.  <span data-ttu-id="fd93f-272">按 F5 键以运行程序，然后选择 **“启动”** 按钮。</span><span class="sxs-lookup"><span data-stu-id="fd93f-272">Choose the F5 key to run the program, and then choose the **Start** button.</span></span>  
  
     <span data-ttu-id="fd93f-273">此版本的项目的行为应与“测试异步解决方案”过程描述的行为匹配，且你的工作量应该更少。</span><span class="sxs-lookup"><span data-stu-id="fd93f-273">The behavior of this version of the project should match the behavior that the "To test the asynchronous solution" procedure describes but with even less effort from you.</span></span>  
  
##  <span data-ttu-id="fd93f-274"><a name="BKMK_CompleteCodeExamples"></a>示例</span><span class="sxs-lookup"><span data-stu-id="fd93f-274"><a name="BKMK_CompleteCodeExamples"></a> Example</span></span>  
 <span data-ttu-id="fd93f-275">下列代码包含使用你编写的异步 `GetURLContentsAsync` 方法从同步解决方案转换为异步解决方案的完整示例。</span><span class="sxs-lookup"><span data-stu-id="fd93f-275">The following code contains the full example of the conversion from a synchronous to an asynchronous solution by using the asynchronous `GetURLContentsAsync` method that you wrote.</span></span> <span data-ttu-id="fd93f-276">请注意，它与原始同步解决方案十分类似。</span><span class="sxs-lookup"><span data-stu-id="fd93f-276">Notice that it strongly resembles the original, synchronous solution.</span></span>  
  
```vb  
' Add the following Imports statements, and add a reference for System.Net.Http.  
Imports System.Net.Http  
Imports System.Net  
Imports System.IO  
  
Class MainWindow  
  
    Async Sub startButton_Click(sender As Object, e As RoutedEventArgs) Handles startButton.Click  
  
        ' Disable the button until the operation is complete.  
        startButton.IsEnabled = False  
  
        resultsTextBox.Clear()  
  
        '' One-step async call.  
        Await SumPageSizesAsync()  
  
        ' Two-step async call.  
        'Dim sumTask As Task = SumPageSizesAsync()  
        'Await sumTask  
  
        resultsTextBox.Text &= vbCrLf & "Control returned to button1_Click."  
  
        ' Reenable the button in case you want to run the operation again.  
        startButton.IsEnabled = True  
    End Sub  
  
    Private Async Function SumPageSizesAsync() As Task  
  
        ' Make a list of web addresses.  
        Dim urlList As List(Of String) = SetUpURLList()  
  
        Dim total = 0  
        For Each url In urlList  
            Dim urlContents As Byte() = Await GetURLContentsAsync(url)  
  
            ' The previous line abbreviates the following two assignment statements.  
  
            '//<snippet21>  
            ' GetURLContentsAsync returns a task. At completion, the task  
            ' produces a byte array.  
            'Dim getContentsTask As Task(Of Byte()) = GetURLContentsAsync(url)  
            'Dim urlContents As Byte() = Await getContentsTask  
  
            DisplayResults(url, urlContents)  
  
            ' Update the total.  
            total += urlContents.Length  
        Next  
  
        ' Display the total count for all of the websites.  
        resultsTextBox.Text &= String.Format(vbCrLf & vbCrLf &  
                                             "Total bytes returned:  {0}" & vbCrLf, total)  
    End Function  
  
    Private Function SetUpURLList() As List(Of String)  
  
        Dim urls = New List(Of String) From  
            {  
                "http://msdn.microsoft.com/library/windows/apps/br211380.aspx",  
                "http://msdn.microsoft.com",  
                "http://msdn.microsoft.com/library/hh290136.aspx",  
                "http://msdn.microsoft.com/library/ee256749.aspx",  
                "http://msdn.microsoft.com/library/hh290138.aspx",  
                "http://msdn.microsoft.com/library/hh290140.aspx",  
                "http://msdn.microsoft.com/library/dd470362.aspx",  
                "http://msdn.microsoft.com/library/aa578028.aspx",  
                "http://msdn.microsoft.com/library/ms404677.aspx",  
                "http://msdn.microsoft.com/library/ff730837.aspx"  
            }  
        Return urls  
    End Function  
  
    Private Async Function GetURLContentsAsync(url As String) As Task(Of Byte())  
  
        ' The downloaded resource ends up in the variable named content.  
        Dim content = New MemoryStream()  
  
        ' Initialize an HttpWebRequest for the current URL.  
        Dim webReq = CType(WebRequest.Create(url), HttpWebRequest)  
  
        ' Send the request to the Internet resource and wait for  
        ' the response.  
        Using response As WebResponse = Await webReq.GetResponseAsync()  
  
            ' The previous statement abbreviates the following two statements.  
  
            'Dim responseTask As Task(Of WebResponse) = webReq.GetResponseAsync()  
            'Using response As WebResponse = Await responseTask  
  
            ' Get the data stream that is associated with the specified URL.  
            Using responseStream As Stream = response.GetResponseStream()  
                ' Read the bytes in responseStream and copy them to content.    
                Await responseStream.CopyToAsync(content)  
  
                ' The previous statement abbreviates the following two statements.  
  
                ' CopyToAsync returns a Task, not a Task<T>.  
                'Dim copyTask As Task = responseStream.CopyToAsync(content)  
  
                ' When copyTask is completed, content contains a copy of  
                ' responseStream.  
                'Await copyTask  
            End Using  
        End Using  
  
        ' Return the result as a byte array.  
        Return content.ToArray()  
    End Function  
  
    Private Sub DisplayResults(url As String, content As Byte())  
  
        ' Display the length of each website. The string format   
        ' is designed to be used with a monospaced font, such as  
        ' Lucida Console or Global Monospace.  
        Dim bytes = content.Length  
        ' Strip off the "http://".  
        Dim displayURL = url.Replace("http://", "")  
        resultsTextBox.Text &= String.Format(vbCrLf & "{0,-58} {1,8}", displayURL, bytes)  
    End Sub  
  
End Class  
```  
  
 <span data-ttu-id="fd93f-277">下列代码包含使用 `HttpClient` 方法 `GetByteArrayAsync` 的解决方案的完整示例。</span><span class="sxs-lookup"><span data-stu-id="fd93f-277">The following code contains the full example of the solution that uses the `HttpClient` method, `GetByteArrayAsync`.</span></span>  
  
```vb  
' Add the following Imports statements, and add a reference for System.Net.Http.  
Imports System.Net.Http  
Imports System.Net  
Imports System.IO  
  
Class MainWindow  
  
    Async Sub startButton_Click(sender As Object, e As RoutedEventArgs) Handles startButton.Click  
  
        resultsTextBox.Clear()  
  
        ' Disable the button until the operation is complete.  
        startButton.IsEnabled = False  
  
        ' One-step async call.  
        Await SumPageSizesAsync()  
  
        '' Two-step async call.  
        'Dim sumTask As Task = SumPageSizesAsync()  
        'Await sumTask  
  
        resultsTextBox.Text &= vbCrLf & "Control returned to button1_Click."  
  
        ' Reenable the button in case you want to run the operation again.  
        startButton.IsEnabled = True  
    End Sub  
  
    Private Async Function SumPageSizesAsync() As Task  
  
        ' Declare an HttpClient object and increase the buffer size. The  
        ' default buffer size is 65,536.  
        Dim client As HttpClient =  
            New HttpClient() With {.MaxResponseContentBufferSize = 1000000}  
  
        ' Make a list of web addresses.  
        Dim urlList As List(Of String) = SetUpURLList()  
  
        Dim total = 0  
        For Each url In urlList  
            ' GetByteArrayAsync returns a task. At completion, the task  
            ' produces a byte array.  
            Dim urlContents As Byte() = Await client.GetByteArrayAsync(url)  
  
            ' The following two lines can replace the previous assignment statement.  
            'Dim getContentsTask As Task(Of Byte()) = client.GetByteArrayAsync(url)  
            'Dim urlContents As Byte() = Await getContentsTask  
  
            DisplayResults(url, urlContents)  
  
            ' Update the total.  
            total += urlContents.Length  
        Next  
  
        ' Display the total count for all of the websites.  
        resultsTextBox.Text &= String.Format(vbCrLf & vbCrLf &  
                                             "Total bytes returned:  {0}" & vbCrLf, total)  
    End Function  
  
    Private Function SetUpURLList() As List(Of String)  
  
        Dim urls = New List(Of String) From  
            {  
                "http://msdn.microsoft.com/library/windows/apps/br211380.aspx",  
                "http://msdn.microsoft.com",  
                "http://msdn.microsoft.com/library/hh290136.aspx",  
                "http://msdn.microsoft.com/library/ee256749.aspx",  
                "http://msdn.microsoft.com/library/hh290138.aspx",  
                "http://msdn.microsoft.com/library/hh290140.aspx",  
                "http://msdn.microsoft.com/library/dd470362.aspx",  
                "http://msdn.microsoft.com/library/aa578028.aspx",  
                "http://msdn.microsoft.com/library/ms404677.aspx",  
                "http://msdn.microsoft.com/library/ff730837.aspx"  
            }  
        Return urls  
    End Function  
  
    Private Sub DisplayResults(url As String, content As Byte())  
  
        ' Display the length of each website. The string format   
        ' is designed to be used with a monospaced font, such as  
        ' Lucida Console or Global Monospace.  
        Dim bytes = content.Length  
        ' Strip off the "http://".  
        Dim displayURL = url.Replace("http://", "")  
        resultsTextBox.Text &= String.Format(vbCrLf & "{0,-58} {1,8}", displayURL, bytes)  
    End Sub  
  
End Class  
```  
  
## <a name="see-also"></a><span data-ttu-id="fd93f-278">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fd93f-278">See Also</span></span>  
 <span data-ttu-id="fd93f-279">[异步示例︰ 访问 Web 演练 （C# 和 Visual Basic）](http://go.microsoft.com/fwlink/?LinkId=255191) </span><span class="sxs-lookup"><span data-stu-id="fd93f-279">[Async Sample: Accessing the Web Walkthrough (C# and Visual Basic)](http://go.microsoft.com/fwlink/?LinkId=255191) </span></span>  
<span data-ttu-id="fd93f-280"> [Await 运算符](../../../../visual-basic/language-reference/operators/await-operator.md) </span><span class="sxs-lookup"><span data-stu-id="fd93f-280"> [Await Operator](../../../../visual-basic/language-reference/operators/await-operator.md) </span></span>  
<span data-ttu-id="fd93f-281"> [异步](../../../../visual-basic/language-reference/modifiers/async.md) </span><span class="sxs-lookup"><span data-stu-id="fd93f-281"> [Async](../../../../visual-basic/language-reference/modifiers/async.md) </span></span>  
<span data-ttu-id="fd93f-282"> [异步编程使用 Async 和 Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md) </span><span class="sxs-lookup"><span data-stu-id="fd93f-282"> [Asynchronous Programming with Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md) </span></span>  
<span data-ttu-id="fd93f-283"> [异步返回类型 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md) </span><span class="sxs-lookup"><span data-stu-id="fd93f-283"> [Async Return Types (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md) </span></span>  
<span data-ttu-id="fd93f-284"> [基于任务的异步编程 (TAP)](http://go.microsoft.com/fwlink/?LinkId=204847) </span><span class="sxs-lookup"><span data-stu-id="fd93f-284"> [Task-based Asynchronous Programming (TAP)](http://go.microsoft.com/fwlink/?LinkId=204847) </span></span>  
<span data-ttu-id="fd93f-285"> [如何︰ 使用 Task.WhenAll (Visual Basic 中) 扩展异步演练](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md) </span><span class="sxs-lookup"><span data-stu-id="fd93f-285"> [How to: Extend the Async Walkthrough by Using Task.WhenAll (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md) </span></span>  
<span data-ttu-id="fd93f-286"> [如何︰ 并行发起多个 Web 请求，使用 Async 和 Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md)</span><span class="sxs-lookup"><span data-stu-id="fd93f-286"> [How to: Make Multiple Web Requests in Parallel by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md)</span></span>
