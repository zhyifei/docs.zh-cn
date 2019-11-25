---
title: 演练：使用 Async 和 Await 访问 Web
ms.date: 07/20/2015
ms.assetid: 84fd047f-fab8-4d89-8ced-104fb7310a91
ms.openlocfilehash: c13e592eb155d14c2e7cb2388a96925a7f1fa413
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349097"
---
# <a name="walkthrough-accessing-the-web-by-using-async-and-await-visual-basic"></a>演练：使用 Async 和 Await 访问 Web (Visual Basic)

使用 async/await 功能可以更轻松直观地编写异步程序。 你可以编写类似于同步代码的异步代码，并让编译器处理异步代码通常需要的疑难回调函数和延续。

For more information about the Async feature, see [Asynchronous Programming with Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md).

本演练从对网站列表中的字节数进行求和的同步 Windows Presentation Foundation (WPF) 应用程序入手， 然后使用新功能将该应用程序转换为异步解决方案。

如果不想自行生成应用程序，可以从[开发人员代码示例](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f)下载“Async 示例：访问 Web 演练（C# 和 Visual Basic）”。

在本演练中，你将完成下列任务：

> [!div class="checklist"]
>
> - [Create a WPF application](#create-a-wpf-application)
> - [Design a simple WPF MainWindow](#design-a-simple-wpf-mainwindow)
> - [Add a reference](#add-a-reference)
> - [Add necessary Imports statements](#add-necessary-imports-statements)
> - [Create a synchronous application](#create-a-synchronous-application)
> - [Test the synchronous solution](#test-the-synchronous-solution)
> - [Convert GetURLContents to an asynchronous method](#convert-geturlcontents-to-an-asynchronous-method)
> - [Convert SumPageSizes to an asynchronous method](#convert-sumpagesizes-to-an-asynchronous-method)
> - [Convert startButton_Click to an asynchronous method](#convert-startbutton_click-to-an-asynchronous-method)
> - [Test the asynchronous solution](#test-the-asynchronous-solution)
> - [Replace the GetURLContentsAsync method with a .NET Framework method](#replace-the-geturlcontentsasync-method-with-a-net-framework-method)

See the [Example](#example) section for the complete asynchronous example.

## <a name="prerequisites"></a>Prerequisites

计算机上必须安装 Visual Studio 2012 或更高版本。 For more information, see the Visual Studio [Downloads](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) page.

## <a name="create-a-wpf-application"></a>创建 WPF 应用程序

1. 启动 Visual Studio。

2. 在菜单栏上，依次选择 **“文件”** 、 **“新建”** 、 **“项目”** 。

    **“新建项目”** 对话框随即打开。

3. In the **Installed Templates** pane, choose Visual Basic, and then choose **WPF Application** from the list of project types.

4. 在“名称”文本框中，输入 `AsyncExampleWPF`，然后选择“确定”按钮。

    新项目将出现在“解决方案资源管理器”中。

## <a name="design-a-simple-wpf-mainwindow"></a>设计简单的 WPF MainWindow

1. 在 Visual Studio 代码编辑器中，选择 **“MainWindow.xaml”** 选项卡。

2. 如果“工具箱”窗口不可见，则打开“视图”菜单，然后选择“工具箱”。

3. 向“MainWindow”窗口添加一个“Button”控件和一个“TextBox”控件。

4. 突出显示“TextBox”控件，在“属性”窗口中，设置下列值：

    - 将“名称”属性设置为 `resultsTextBox`。

    - 将“高度”属性设置为 250。

    - 将“宽度”属性设置为 500。

    - 在“文本”选项卡中，指定等宽字体，例如 Lucida Console 或 Global Monospace。

5. 突出显示“Button”控件，在“属性”窗口中，设置下列值：

    - 将“名称”属性设置为 `startButton`。

    - 将“内容”属性的值从“Button”更改为“Start”。

6. 确定文本框和按钮的位置，以便它们都在“MainWindow”窗口中显示。

    有关 WPF XAML 设计器的详细信息，请参阅[使用 XAML 设计器创建 UI](/visualstudio/xaml-tools/creating-a-ui-by-using-xaml-designer-in-visual-studio)。

## <a name="add-a-reference"></a>添加引用

1. 在“解决方案资源管理器”中，突出显示项目的名称。

2. 在菜单栏上，依次选择“项目”、“添加引用”。

    此时将显示“引用管理器”对话框。

3. 在对话框顶部，验证项目是否以 .NET Framework 4.5 或更高版本为目标。

4. 在“程序集”区域，选择“Framework”（如果尚未选择它）。

5. 在名称列表中，选中“System.Net.Http”复选框。

6. 选择“确定”按钮关闭对话框。

## <a name="add-necessary-imports-statements"></a>Add necessary Imports statements

1. In **Solution Explorer**, open the shortcut menu for MainWindow.xaml.vb, and then choose **View Code**.

2. Add the following `Imports` statements at the top of the code file if they’re not already present.

    ```vb
    Imports System.Net.Http
    Imports System.Net
    Imports System.IO
    ```

## <a name="create-a-synchronous-application"></a>Create a synchronous application

1. In the design window, MainWindow.xaml, double-click the **Start** button to create the `startButton_Click` event handler in MainWindow.xaml.vb.

2. In MainWindow.xaml.vb, copy the following code into the body of `startButton_Click`:

    ```vb
    resultsTextBox.Clear()
    SumPageSizes()
    resultsTextBox.Text &= vbCrLf & "Control returned to startButton_Click."
    ```

    代码调用驱动应用程序 `SumPageSizes` 的方法，并在控件返回到 `startButton_Click` 时显示一条消息。

3. 该同步解决方案的代码包含以下四个方法：

    - `SumPageSizes`，从 `SetUpURLList` 获取网页 URL 列表并随后调用 `GetURLContents` 和 `DisplayResults` 以处理每个 URL。

    - `SetUpURLList`，生成并返回 Web 地址列表。

    - `GetURLContents`，下载每个网站的内容并将内容作为字节数组返回。

    - `DisplayResults`，显示每个 URL 的字节数组中的字节数。

    Copy the following four methods, and then paste them under the `startButton_Click` event handler in MainWindow.xaml.vb:

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
                "https://msdn.microsoft.com/library/windows/apps/br211380.aspx",
                "https://msdn.microsoft.com",
                "https://msdn.microsoft.com/library/hh290136.aspx",
                "https://msdn.microsoft.com/library/ee256749.aspx",
                "https://msdn.microsoft.com/library/hh290138.aspx",
                "https://msdn.microsoft.com/library/hh290140.aspx",
                "https://msdn.microsoft.com/library/dd470362.aspx",
                "https://msdn.microsoft.com/library/aa578028.aspx",
                "https://msdn.microsoft.com/library/ms404677.aspx",
                "https://msdn.microsoft.com/library/ff730837.aspx"
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
        ' Strip off the "https://".
        Dim displayURL = url.Replace("https://", "")
        resultsTextBox.Text &= String.Format(vbCrLf & "{0,-58} {1,8}", displayURL, bytes)
    End Sub
    ```

## <a name="test-the-synchronous-solution"></a>测试同步解决方案

1. 按 F5 键以运行程序，然后选择 **“启动”** 按钮。

    此时应显示类似于以下列表的输出：

    ```console
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

    请注意，显示计数需要几秒钟时间。 与此同时，在等待请求的资源下载时，UI 线程处于被阻止状态。 因此，选择“启动”按钮后，将无法移动、最大化、最小化显示窗口，甚至也无法关闭显示窗口。 在字节计数开始显示之前，这些操作都会失败。 如果网站没有响应，将不会指示哪个网站失败。 甚至停止等待和关闭程序也会很困难。

## <a name="convert-geturlcontents-to-an-asynchronous-method"></a>将 GetURLContents 转换为异步方法

1. To convert the synchronous solution to an asynchronous solution, the best place to start is in `GetURLContents` because the calls to the <xref:System.Net.HttpWebRequest.GetResponse%2A?displayProperty=nameWithType> method and to the <xref:System.IO.Stream.CopyTo%2A?displayProperty=nameWithType> method are where the application accesses the web. .NET Framework 提供两种方法的异步版本，这让转换变得轻松。

    有关 `GetURLContents` 中使用的方法的详细信息，请参阅 <xref:System.Net.WebRequest>。

    > [!NOTE]
    > 在你按照本演练中的步骤进行操作的过程中，将出现多个编译器错误。 你可以忽略这些错误并继续演练。

    将在 `GetURLContents` 的第三行中调用的方法从 `GetResponse` 更改为基于任务的异步 <xref:System.Net.WebRequest.GetResponseAsync%2A> 方法。

    ```vb
    Using response As WebResponse = webReq.GetResponseAsync()
    ```

2. `GetResponseAsync` 返回 <xref:System.Threading.Tasks.Task%601>。 在这种情况下，任务返回变量`TResult` 具有类型 <xref:System.Net.WebResponse>。 该任务是在请求的任务已下载且任务已完成运行后，生成实际 `WebResponse` 对象的承诺。

    To retrieve the `WebResponse` value from the task, apply an [Await](../../../../visual-basic/language-reference/operators/await-operator.md) operator to the call to `GetResponseAsync`, as the following code shows.

    ```vb
    Using response As WebResponse = Await webReq.GetResponseAsync()
    ```

    `Await` 运算符将当前方法 `GetURLContents` 的执行挂起，直到完成等待的任务为止。 同时，控制权返回给当前方法的调用方。 在此示例中，当前方法是 `GetURLContents`，调用方是 `SumPageSizes`。 任务完成时，承诺的 `WebResponse` 对象作为等待的任务的值生成，并分配给变量 `response`。

    上一条语句可以分为以下两条语句，以阐明所发生的情况。

    ```vb
    Dim responseTask As Task(Of WebResponse) = webReq.GetResponseAsync()
    Using response As WebResponse = Await responseTask
    ```

    对 `webReq.GetResponseAsync` 的调用返回 `Task(Of WebResponse)` 或 `Task<WebResponse>`。 Then an `Await` operator is applied to the task to retrieve the `WebResponse` value.

    如果你的异步方法需要完成不依赖于任务的完成的工作，则在调用异步方法之后及应用 await 运算符之前的这段时间，该方法可以在这两个语句之间继续完成该工作。 For examples, see [How to: Make Multiple Web Requests in Parallel by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md) and [How to: Extend the Async Walkthrough by Using Task.WhenAll (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md).

3. 因为在上一步中添加了 `Await` 运算符，所以会发生编译器错误。 The operator can be used only in methods that are marked with the [Async](../../../../visual-basic/language-reference/modifiers/async.md) modifier. 当你重复转换步骤以使用对 `CopyToAsync` 的调用替换对 `CopyTo` 的调用时，请忽略该错误。

    - 更改被调用到 <xref:System.IO.Stream.CopyToAsync%2A> 的方法的名称。

    - `CopyTo` 或 `CopyToAsync` 方法复制字节到其参数 `content`，并且不返回有意义的值。 在同步版本中，对 `CopyTo` 的调用是不返回值的简单语句。 异步版本 `CopyToAsync` 返回 <xref:System.Threading.Tasks.Task>。 任务函数类似“Task(void)”，并让该方法能够等待。 应用 `Await` 或 `await` 到对 `CopyToAsync` 的调用，如下列代码所示。

        ```vb
        Await responseStream.CopyToAsync(content)
        ```

         上一条语句缩写以下两行代码。

        ```vb
        ' CopyToAsync returns a Task, not a Task<T>.
        Dim copyTask As Task = responseStream.CopyToAsync(content)

        ' When copyTask is completed, content contains a copy of
        ' responseStream.
        Await copyTask
        ```

4. `GetURLContents` 中仍需要完成的操作是调整方法签名。 You can use the `Await` operator only in methods that are marked with the [Async](../../../../visual-basic/language-reference/modifiers/async.md) modifier. 添加修饰符以将方法标记为*异步方法*，如下列代码所示。

    ```vb
    Private Async Function GetURLContents(url As String) As Byte()
    ```

5. The return type of an async method can only be <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601>. 在 Visual Basic 中，方法必须为返回 `Task` 或 `Task(Of T)` 的 `Function`，或方法必须为 `Sub`。 Typically, a `Sub` method  is used only in an async event handler, where `Sub` is required. In other cases, you use `Task(T)` if the completed method has a [Return](../../../../visual-basic/language-reference/statements/return-statement.md) statement that returns a value of type T, and you use `Task` if the completed method doesn’t return a meaningful value.

    For more information, see [Async Return Types (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md).

    方法 `GetURLContents` 具有 return 语句，且该语句返回字节数组。 因此，异步版本的返回类型为 Task(T)，其中 T 为字节数组。 在方法签名中进行下列更改：

    - 将返回类型更改为 `Task(Of Byte())`。

    - 按照约定，异步方法的名称以“Async”结尾，因此，请重命名方法 `GetURLContentsAsync`。

    下列代码显示这些更改。

    ```vb
    Private Async Function GetURLContentsAsync(url As String) As Task(Of Byte())
    ```

    进行这几处更改后，`GetURLContents` 到异步方法的转换完成。

## <a name="convert-sumpagesizes-to-an-asynchronous-method"></a>将 SumPageSizes 转换为异步方法

1. 为 `SumPageSizes` 重复之前过程中的步骤。 首先，将对 `GetURLContents` 的调用更改为异步调用。

    - 将调用的方法的名称从 `GetURLContents` 更改为 `GetURLContentsAsync`（如果尚未执行此操作）。

    - 将 `Await` 应用到 `GetURLContentsAsync` 返回的任务，以便获取字节数组值。

    下列代码显示这些更改。

    ```vb
    Dim urlContents As Byte() = Await GetURLContentsAsync(url)
    ```

    上一个分配缩写以下两行代码。

    ```vb
    ' GetURLContentsAsync returns a task. At completion, the task
    ' produces a byte array.
    Dim getContentsTask As Task(Of Byte()) = GetURLContentsAsync(url)
    Dim urlContents As Byte() = Await getContentsTask
    ```

2. 在方法签名中进行下列更改：

    - 使用 `Async` 修饰符标记方法。

    - 将“Async”添加到方法名称。

    - There is no task return variable, T, this time because `SumPageSizesAsync` doesn’t return a value for T. (The method has no `Return` statement.) However, the method must return a `Task` to be awaitable. Therefore, change the method type from `Sub` to `Function`. 函数的返回类型为 `Task`。

    下列代码显示这些更改。

    ```vb
    Private Async Function SumPageSizesAsync() As Task
    ```

    从 `SumPageSizes` 到 `SumPageSizesAsync` 的转换完成。

## <a name="convert-startbutton_click-to-an-asynchronous-method"></a>将 startButton_Click 转换为异步方法

1. 在事件处理程序中，将调用的方法的名称从 `SumPageSizes` 更改为 `SumPageSizesAsync`（如果尚未执行此操作）。

2. 由于 `SumPageSizesAsync` 是异步方法，请更改事件处理程序中的代码以等待结果。

    对 `SumPageSizesAsync` 的调用反射对 `GetURLContentsAsync` 中的 `CopyToAsync` 的调用。 调用返回的是 `Task`，而不是 `Task(T)`。

    与之前的过程一样，你可以使用一条语句或两条语句转换调用。 下列代码显示这些更改。

    ```vb
    ' One-step async call.
    Await SumPageSizesAsync()

    ' Two-step async call.
    Dim sumTask As Task = SumPageSizesAsync()
    Await sumTask
    ```

3. 要防止意外重新进入操作，请在 `startButton_Click` 顶部添加下列语句，以禁用“启动”按钮。

    ```vb
    ' Disable the button until the operation is complete.
    startButton.IsEnabled = False
    ```

    可以重新启用事件处理程序末尾的按钮。

    ```vb
    ' Reenable the button in case you want to run the operation again.
    startButton.IsEnabled = True
    ```

    For more information about reentrancy, see [Handling Reentrancy in Async Apps (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/handling-reentrancy-in-async-apps.md).

4. 最后，将 `Async` 修饰符添加到声明，以便事件处理程序可以等待 `SumPagSizesAsync`。

    ```vb
    Async Sub startButton_Click(sender As Object, e As RoutedEventArgs) Handles startButton.Click
    ```

    通常情况下，事件处理程序的名称不会更改。 The return type isn’t changed to `Task` because event handlers must be `Sub` procedures in Visual Basic.

    项目从同步处理到异步处理的转换完成。

## <a name="test-the-asynchronous-solution"></a>测试异步解决方案

1. 按 F5 键以运行程序，然后选择 **“启动”** 按钮。

2. 此时应显示类似于同步解决方案的输出的输出。 但是，请注意下列差异。

    - 处理完成后，所有结果不会同时出现。 例如，两个程序都在 `startButton_Click` 中包含一行可以清除文本框的代码。 目的在于，在一组结果显示后，第二次选择“启动”按钮时，可以清除运行之间的文本框。 在同步版本中，下载完成且 UI 线程可以自由完成其他工作时，文本框在计数第二次显示之前即被清除。 在异步版本中，选择“启动”按钮后立即清除文本框。

    - 最重要的是，UI 线程在下载过程中未被阻止。 在 Web 资源下载、计数和显示期间，可以移动窗口或调整窗口大小。 如果其中一个网站速度缓慢或没有响应，则可以通过选择“关闭”按钮取消操作（右上角红色字段中的 x）。

## <a name="replace-the-geturlcontentsasync-method-with-a-net-framework-method"></a>Replace the GetURLContentsAsync method with a .NET Framework method

1. The .NET Framework provides many async methods that you can use. One of them, the <xref:System.Net.Http.HttpClient.GetByteArrayAsync%28System.String%29?displayProperty=nameWithType> method, does just what you need for this walkthrough. 你可以使用它来替代你在早前过程中创建的 `GetURLContentsAsync` 方法。

    The first step is to create an <xref:System.Net.Http.HttpClient> object in the `SumPageSizesAsync` method. 在方法的开头添加下列声明。

    ```vb
    ' Declare an HttpClient object and increase the buffer size. The
    ' default buffer size is 65,536.
    Dim client As HttpClient =
        New HttpClient() With {.MaxResponseContentBufferSize = 1000000}
    ```

2. 在 `SumPageSizesAsync,` 中，使用对 `HttpClient` 方法的调用替换对 `GetURLContentsAsync` 方法的调用。

    ```vb
    Dim urlContents As Byte() = Await client.GetByteArrayAsync(url)
    ```

3. 删除或注释禁用你编写的 `GetURLContentsAsync` 方法。

4. 按 F5 键以运行程序，然后选择 **“启动”** 按钮。

    此版本的项目的行为应与“测试异步解决方案”过程描述的行为匹配，且你的工作量应该更少。

## <a name="example"></a>示例

The following is the full example of the converted asynchronous solution that uses the asynchronous `GetURLContentsAsync` method. 请注意，它与原始同步解决方案十分类似。

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
                "https://msdn.microsoft.com/library/windows/apps/br211380.aspx",
                "https://msdn.microsoft.com",
                "https://msdn.microsoft.com/library/hh290136.aspx",
                "https://msdn.microsoft.com/library/ee256749.aspx",
                "https://msdn.microsoft.com/library/hh290138.aspx",
                "https://msdn.microsoft.com/library/hh290140.aspx",
                "https://msdn.microsoft.com/library/dd470362.aspx",
                "https://msdn.microsoft.com/library/aa578028.aspx",
                "https://msdn.microsoft.com/library/ms404677.aspx",
                "https://msdn.microsoft.com/library/ff730837.aspx"
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
        ' Strip off the "https://".
        Dim displayURL = url.Replace("https://", "")
        resultsTextBox.Text &= String.Format(vbCrLf & "{0,-58} {1,8}", displayURL, bytes)
    End Sub

End Class
```

下列代码包含使用 `HttpClient` 方法 `GetByteArrayAsync` 的解决方案的完整示例。

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

        ' Two-step async call.
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
                "https://msdn.microsoft.com/library/windows/apps/br211380.aspx",
                "https://msdn.microsoft.com",
                "https://msdn.microsoft.com/library/hh290136.aspx",
                "https://msdn.microsoft.com/library/ee256749.aspx",
                "https://msdn.microsoft.com/library/hh290138.aspx",
                "https://msdn.microsoft.com/library/hh290140.aspx",
                "https://msdn.microsoft.com/library/dd470362.aspx",
                "https://msdn.microsoft.com/library/aa578028.aspx",
                "https://msdn.microsoft.com/library/ms404677.aspx",
                "https://msdn.microsoft.com/library/ff730837.aspx"
            }
        Return urls
    End Function

    Private Sub DisplayResults(url As String, content As Byte())

        ' Display the length of each website. The string format
        ' is designed to be used with a monospaced font, such as
        ' Lucida Console or Global Monospace.
        Dim bytes = content.Length
        ' Strip off the "https://".
        Dim displayURL = url.Replace("https://", "")
        resultsTextBox.Text &= String.Format(vbCrLf & "{0,-58} {1,8}", displayURL, bytes)
    End Sub

End Class
```

## <a name="see-also"></a>请参阅

- [异步示例：访问 Web 演练（C# 和 Visual Basic）](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f)
- [Await 运算符](../../../../visual-basic/language-reference/operators/await-operator.md)
- [Async](../../../../visual-basic/language-reference/modifiers/async.md)
- [使用 Async 和 Await 的异步编程 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md)
- [异步返回类型 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md)
- [基于任务的异步编程 (TAP)](https://go.microsoft.com/fwlink/?LinkId=204847)
- [如何：使用 Task.WhenAll 扩展异步演练 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md)
- [如何：使用 Async 和 Await 并行发出多个 Web 请求 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md)
