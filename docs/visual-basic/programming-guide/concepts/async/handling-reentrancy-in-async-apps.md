---
title: 处理异步应用程序中的可重入性
ms.date: 07/20/2015
ms.assetid: ef3dc73d-13fb-4c5f-a686-6b84148bbffe
ms.openlocfilehash: 110298a2ca937dbf39c94cfe9df29afb2e76a91c
ms.sourcegitcommit: 348bb052d5cef109a61a3d5253faa5d7167d55ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2020
ms.locfileid: "82021493"
---
# <a name="handling-reentrancy-in-async-apps-visual-basic"></a><span data-ttu-id="a9172-102">在异步应用程序中处理重入 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a9172-102">Handling Reentrancy in Async Apps (Visual Basic)</span></span>

<span data-ttu-id="a9172-103">在应用中包含异步代码时，应考虑并且可以阻止重新进入（指在异步操作完成之前重新进入它）。</span><span class="sxs-lookup"><span data-stu-id="a9172-103">When you include asynchronous code in your app, you should consider and possibly prevent reentrancy, which refers to reentering an asynchronous operation before it has completed.</span></span> <span data-ttu-id="a9172-104">如果不识别并处理重新进入的可能性，则它可能会导致意外结果。</span><span class="sxs-lookup"><span data-stu-id="a9172-104">If you don't identify and handle possibilities for reentrancy, it can cause unexpected results.</span></span>

> [!NOTE]
> <span data-ttu-id="a9172-105">若要运行该示例，计算机上必须安装 Visual Studio 2012 或更高版本和 .NET Framework 4.5 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="a9172-105">To run the example, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>

> [!NOTE]
> <span data-ttu-id="a9172-106">传输层安全性 (TLS) 版本 1.2 现在是在应用开发中使用的最低版本。</span><span class="sxs-lookup"><span data-stu-id="a9172-106">Transport Layer Security (TLS) version 1.2 is now the minimum version to use in your app development.</span></span> <span data-ttu-id="a9172-107">如果应用的目标早于 4.7 的 .NET 框架版本，请参阅以下有关[传输层安全性 （TLS） 最佳实践的文章](../../../../framework/network-programming/tls.md)。</span><span class="sxs-lookup"><span data-stu-id="a9172-107">If your app targets a .NET Framework version earlier than 4.7, refer to the following article for [Transport Layer Security (TLS) best practices with the .NET Framework](../../../../framework/network-programming/tls.md).</span></span>

## <a name="recognizing-reentrancy"></a><a name="BKMK_RecognizingReentrancy"></a><span data-ttu-id="a9172-108">识别重新进入</span><span class="sxs-lookup"><span data-stu-id="a9172-108">Recognizing Reentrancy</span></span>

<span data-ttu-id="a9172-109">在本主题中的示例中，用户选择“开始”\*\*\*\* 按钮以启动一个异步应用，该应用下载一系列网站并计算下载的总字节数。</span><span class="sxs-lookup"><span data-stu-id="a9172-109">In the example in this topic, users choose a **Start** button to initiate an asynchronous app that downloads a series of websites and calculates the total number of bytes that are downloaded.</span></span> <span data-ttu-id="a9172-110">该示例的同步版本以相同方式进行响应（无论用户选择该按钮多少次），因为在第一次选择之后，UI 线程会忽略这些事件，直到应用完成运行。</span><span class="sxs-lookup"><span data-stu-id="a9172-110">A synchronous version of the example would respond the same way regardless of how many times a user chooses the button because, after the first time, the UI thread ignores those events until the app finishes running.</span></span> <span data-ttu-id="a9172-111">但是，在异步应用中，UI 线程会继续响应，你可能会在它完成之前重新进入异步操作。</span><span class="sxs-lookup"><span data-stu-id="a9172-111">In an asynchronous app, however, the UI thread continues to respond, and you might reenter the asynchronous operation before it has completed.</span></span>

<span data-ttu-id="a9172-112">下面的示例显示用户仅选择“开始”\*\*\*\* 按钮一次时的预期输出。</span><span class="sxs-lookup"><span data-stu-id="a9172-112">The following example shows the expected output if the user chooses the **Start** button only once.</span></span> <span data-ttu-id="a9172-113">下载网站的列表会出现，其中包含每个站点的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="a9172-113">A list of the downloaded websites appears with the size, in bytes, of each site.</span></span> <span data-ttu-id="a9172-114">总字节数会在结尾处显示。</span><span class="sxs-lookup"><span data-stu-id="a9172-114">The total number of bytes appears at the end.</span></span>

```console
1. msdn.microsoft.com/library/hh191443.aspx                83732
2. msdn.microsoft.com/library/aa578028.aspx               205273
3. msdn.microsoft.com/library/jj155761.aspx                29019
4. msdn.microsoft.com/library/hh290140.aspx               117152
5. msdn.microsoft.com/library/hh524395.aspx                68959
6. msdn.microsoft.com/library/ms404677.aspx               197325
7. msdn.microsoft.com                                            42972
8. msdn.microsoft.com/library/ff730837.aspx               146159

TOTAL bytes returned:  890591
```

<span data-ttu-id="a9172-115">但是，如果用户多次选择按钮，则会反复调用事件处理程序，并且每次都会重新进入下载进程。</span><span class="sxs-lookup"><span data-stu-id="a9172-115">However, if the user chooses the button more than once, the event handler is invoked repeatedly, and the download process is reentered each time.</span></span> <span data-ttu-id="a9172-116">因此，会有多个异步操作同时运行，输出会使结果交错，而总字节数令人困惑。</span><span class="sxs-lookup"><span data-stu-id="a9172-116">As a result, several asynchronous operations are running at the same time, the output interleaves the results, and the total number of bytes is confusing.</span></span>

```console
1. msdn.microsoft.com/library/hh191443.aspx                83732
2. msdn.microsoft.com/library/aa578028.aspx               205273
3. msdn.microsoft.com/library/jj155761.aspx                29019
4. msdn.microsoft.com/library/hh290140.aspx               117152
5. msdn.microsoft.com/library/hh524395.aspx                68959
1. msdn.microsoft.com/library/hh191443.aspx                83732
2. msdn.microsoft.com/library/aa578028.aspx               205273
6. msdn.microsoft.com/library/ms404677.aspx               197325
3. msdn.microsoft.com/library/jj155761.aspx                29019
7. msdn.microsoft.com                                            42972
4. msdn.microsoft.com/library/hh290140.aspx               117152
8. msdn.microsoft.com/library/ff730837.aspx               146159

TOTAL bytes returned:  890591

5. msdn.microsoft.com/library/hh524395.aspx                68959
1. msdn.microsoft.com/library/hh191443.aspx                83732
2. msdn.microsoft.com/library/aa578028.aspx               205273
6. msdn.microsoft.com/library/ms404677.aspx               197325
3. msdn.microsoft.com/library/jj155761.aspx                29019
4. msdn.microsoft.com/library/hh290140.aspx               117152
7. msdn.microsoft.com                                            42972
5. msdn.microsoft.com/library/hh524395.aspx                68959
8. msdn.microsoft.com/library/ff730837.aspx               146159

TOTAL bytes returned:  890591

6. msdn.microsoft.com/library/ms404677.aspx               197325
7. msdn.microsoft.com                                            42972
8. msdn.microsoft.com/library/ff730837.aspx               146159

TOTAL bytes returned:  890591
```

<span data-ttu-id="a9172-117">可以滚动到本主题末尾来评审生成此输出的代码。</span><span class="sxs-lookup"><span data-stu-id="a9172-117">You can review the code that produces this output by scrolling to the end of this topic.</span></span> <span data-ttu-id="a9172-118">可以通过将解决方案下载到本地计算机，然后运行 WebsiteDownload 项目，或是通过使用本主题末尾的代码创建自己的项目，来体验该代码。有关详细信息和说明，请参阅[检查并运行示例应用](#BKMD_SettingUpTheExample)。</span><span class="sxs-lookup"><span data-stu-id="a9172-118">You can experiment with the code by downloading the solution to your local computer and then running the WebsiteDownload project or by using the code at the end of this topic to create your own project For more information and instructions, see [Reviewing and Running the Example App](#BKMD_SettingUpTheExample).</span></span>

## <a name="handling-reentrancy"></a><a name="BKMK_HandlingReentrancy"></a><span data-ttu-id="a9172-119">处理重化</span><span class="sxs-lookup"><span data-stu-id="a9172-119">Handling Reentrancy</span></span>

<span data-ttu-id="a9172-120">可以采用各种方式处理重新进入，具体取决于希望应用执行的操作。</span><span class="sxs-lookup"><span data-stu-id="a9172-120">You can handle reentrancy in a variety of ways, depending on what you want your app to do.</span></span> <span data-ttu-id="a9172-121">本主题展示了以下示例：</span><span class="sxs-lookup"><span data-stu-id="a9172-121">This topic presents the following examples:</span></span>

- [<span data-ttu-id="a9172-122">禁用“开始”按钮</span><span class="sxs-lookup"><span data-stu-id="a9172-122">Disable the Start Button</span></span>](#BKMK_DisableTheStartButton)

  <span data-ttu-id="a9172-123">在操作运行期间禁用“开始”\*\*\*\* 按钮，以便用户无法中断它。</span><span class="sxs-lookup"><span data-stu-id="a9172-123">Disable the **Start** button while the operation is running so that the user can't interrupt it.</span></span>

- [<span data-ttu-id="a9172-124">取消并重新启动操作</span><span class="sxs-lookup"><span data-stu-id="a9172-124">Cancel and Restart the Operation</span></span>](#BKMK_CancelAndRestart)

  <span data-ttu-id="a9172-125">当用户再次选择“开始”\*\*\*\* 按钮时取消仍在运行的任何操作，然后让最近请求的操作继续运行。</span><span class="sxs-lookup"><span data-stu-id="a9172-125">Cancel any operation that is still running when the user chooses the **Start** button again, and then let the most recently requested operation continue.</span></span>

- [<span data-ttu-id="a9172-126">运行多个操作并将输出排入队列</span><span class="sxs-lookup"><span data-stu-id="a9172-126">Run Multiple Operations and Queue the Output</span></span>](#BKMK_RunMultipleOperations)

  <span data-ttu-id="a9172-127">允许所有请求的操作异步运行，但是会协调输出的显示，以便每个操作的结果按顺序一起显示。</span><span class="sxs-lookup"><span data-stu-id="a9172-127">Allow all requested operations to run asynchronously, but coordinate the display of output so that the results from each operation appear together and in order.</span></span>

### <a name="disable-the-start-button"></a><a name="BKMK_DisableTheStartButton"></a><span data-ttu-id="a9172-128">禁用"开始"按钮</span><span class="sxs-lookup"><span data-stu-id="a9172-128">Disable the Start Button</span></span>

<span data-ttu-id="a9172-129">可以通过在 `StartButton_Click` 事件处理程序顶部禁用“开始”\*\*\*\* 按钮，在操作运行期间阻止该按钮。</span><span class="sxs-lookup"><span data-stu-id="a9172-129">You can block the **Start** button while an operation is running by disabling the button at the top of the `StartButton_Click` event handler.</span></span> <span data-ttu-id="a9172-130">随后可以在操作完成时从 `Finally` 块中重新启用中该按钮，以便用户可以再次运行应用。</span><span class="sxs-lookup"><span data-stu-id="a9172-130">You can then reenable the button from within a  `Finally` block when the operation finishes so that users can run the app again.</span></span>

<span data-ttu-id="a9172-131">下面的代码演示了这些更改（使用星号标记）。</span><span class="sxs-lookup"><span data-stu-id="a9172-131">The following code shows these changes, which are marked with asterisks.</span></span> <span data-ttu-id="a9172-132">可以将更改添加到本主题末尾的代码中，或从[异步示例：.NET 桌面应用中的重新进入](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06)下载已完成的应用。</span><span class="sxs-lookup"><span data-stu-id="a9172-132">You can add the changes to the code at the end of this topic, or you can download the finished app from [Async Samples: Reentrancy in .NET Desktop Apps](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06).</span></span> <span data-ttu-id="a9172-133">项目名是 DisableStartButton。</span><span class="sxs-lookup"><span data-stu-id="a9172-133">The project name is DisableStartButton.</span></span>

```vb
Private Async Sub StartButton_Click(sender As Object, e As RoutedEventArgs)
    ' This line is commented out to make the results clearer in the output.
    'ResultsTextBox.Text = ""

    ' ***Disable the Start button until the downloads are complete.
    StartButton.IsEnabled = False

    Try
        Await AccessTheWebAsync()

    Catch ex As Exception
        ResultsTextBox.Text &= vbCrLf & "Downloads failed."
    ' ***Enable the Start button in case you want to run the program again.
    Finally
        StartButton.IsEnabled = True

    End Try
End Sub
```

<span data-ttu-id="a9172-134">由于进行了这些更改，所以该按钮在 `AccessTheWebAsync` 下载网站期间不会进行响应，因此无法重新进入该进程。</span><span class="sxs-lookup"><span data-stu-id="a9172-134">As a result of the changes, the button doesn't respond while `AccessTheWebAsync` is downloading the websites, so the process can’t be reentered.</span></span>

### <a name="cancel-and-restart-the-operation"></a><a name="BKMK_CancelAndRestart"></a><span data-ttu-id="a9172-135">取消和重启操作</span><span class="sxs-lookup"><span data-stu-id="a9172-135">Cancel and Restart the Operation</span></span>

<span data-ttu-id="a9172-136">可以使“开始”\*\*\*\* 按钮保持活动状态而不是禁用该按钮，但是如果用户再次选择该按钮，则取消已在运行的操作，让最近开始的操作继续运行。</span><span class="sxs-lookup"><span data-stu-id="a9172-136">Instead of disabling the **Start** button, you can keep the button active but, if the user chooses that button again, cancel the operation that's already running and let the most recently started operation continue.</span></span>

<span data-ttu-id="a9172-137">有关取消的详细信息，请参阅[微调您的异步应用程序（可视化基本）。](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md)</span><span class="sxs-lookup"><span data-stu-id="a9172-137">For more information about cancellation, see [Fine-Tuning Your Async Application (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md).</span></span>

<span data-ttu-id="a9172-138">若要设置此方案，请对[检查并运行示例应用](#BKMD_SettingUpTheExample)中提供的基本代码进行以下更改。</span><span class="sxs-lookup"><span data-stu-id="a9172-138">To set up this scenario, make the following changes to the basic code that is provided in [Reviewing and Running the Example App](#BKMD_SettingUpTheExample).</span></span> <span data-ttu-id="a9172-139">您还可以从 Async 示例下载已完成的应用程序[：在 .NET 桌面应用程序中的重新转换](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06)。</span><span class="sxs-lookup"><span data-stu-id="a9172-139">You can also download the finished app from [Async Samples: Reentrancy in .NET Desktop Apps](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06).</span></span> <span data-ttu-id="a9172-140">此项目的名称是 CancelAndRestart。</span><span class="sxs-lookup"><span data-stu-id="a9172-140">The name of this project is CancelAndRestart.</span></span>

1. <span data-ttu-id="a9172-141">声明 <xref:System.Threading.CancellationTokenSource> 变量 `cts`，它处于所有方法的范围内。</span><span class="sxs-lookup"><span data-stu-id="a9172-141">Declare a <xref:System.Threading.CancellationTokenSource> variable, `cts`, that’s in scope for all methods.</span></span>

    ```vb
    Class MainWindow // Or Class MainPage

        ' *** Declare a System.Threading.CancellationTokenSource.
        Dim cts As CancellationTokenSource
    ```

2. <span data-ttu-id="a9172-142">在 `StartButton_Click` 中，确定操作是否已在进行。</span><span class="sxs-lookup"><span data-stu-id="a9172-142">In `StartButton_Click`, determine whether an operation is already underway.</span></span> <span data-ttu-id="a9172-143">如果 值`cts`为`Nothing`，则没有操作已处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="a9172-143">If the value of `cts` is `Nothing`, no operation is already active.</span></span> <span data-ttu-id="a9172-144">如果值不是`Nothing`，则已运行的操作将被取消。</span><span class="sxs-lookup"><span data-stu-id="a9172-144">If the value isn't `Nothing`, the operation that is already running is canceled.</span></span>

    ```vb
    ' *** If a download process is already underway, cancel it.
    If cts IsNot Nothing Then
        cts.Cancel()
    End If
    ```

3. <span data-ttu-id="a9172-145">将 `cts` 设置为表示当前进程的不同值。</span><span class="sxs-lookup"><span data-stu-id="a9172-145">Set `cts` to a different value that represents the current process.</span></span>

    ```vb
    ' *** Now set cts to cancel the current process if the button is chosen again.
    Dim newCTS As CancellationTokenSource = New CancellationTokenSource()
    cts = newCTS
    ```

4. <span data-ttu-id="a9172-146">在`StartButton_Click`的末尾，当前过程已完成，因此将 值`cts`设置为`Nothing`返回 。</span><span class="sxs-lookup"><span data-stu-id="a9172-146">At the end of `StartButton_Click`, the current process is complete, so set the value of `cts` back to `Nothing`.</span></span>

    ```vb
    ' *** When the process completes, signal that another process can proceed.
    If cts Is newCTS Then
        cts = Nothing
    End If
    ```

<span data-ttu-id="a9172-147">以下代码显示了 `StartButton_Click` 中的所有更改。</span><span class="sxs-lookup"><span data-stu-id="a9172-147">The following code shows all the changes in `StartButton_Click`.</span></span> <span data-ttu-id="a9172-148">新增内容标有星号。</span><span class="sxs-lookup"><span data-stu-id="a9172-148">The additions are marked with asterisks.</span></span>

```vb
Private Async Sub StartButton_Click(sender As Object, e As RoutedEventArgs)

    ' This line is commented out to make the results clearer.
    'ResultsTextBox.Text = ""

    ' *** If a download process is underway, cancel it.
    If cts IsNot Nothing Then
        cts.Cancel()
    End If

    ' *** Now set cts to cancel the current process if the button is chosen again.
    Dim newCTS As CancellationTokenSource = New CancellationTokenSource()
    cts = newCTS

    Try
        ' *** Send a token to carry the message if the operation is canceled.
        Await AccessTheWebAsync(cts.Token)

    Catch ex As OperationCanceledException
        ResultsTextBox.Text &= vbCrLf & "Download canceled." & vbCrLf

    Catch ex As Exception
        ResultsTextBox.Text &= vbCrLf & "Downloads failed."
    End Try

    ' *** When the process is complete, signal that another process can proceed.
    If cts Is newCTS Then
        cts = Nothing
    End If
End Sub
```

<span data-ttu-id="a9172-149">在 `AccessTheWebAsync` 中，进行下列更改。</span><span class="sxs-lookup"><span data-stu-id="a9172-149">In `AccessTheWebAsync`, make the following changes.</span></span>

- <span data-ttu-id="a9172-150">添加参数以从 `StartButton_Click` 接受取消标记。</span><span class="sxs-lookup"><span data-stu-id="a9172-150">Add a parameter to accept the cancellation token from `StartButton_Click`.</span></span>

- <span data-ttu-id="a9172-151">使用 <xref:System.Net.Http.HttpClient.GetAsync%2A> 方法下载网站，因为 `GetAsync` 接受 <xref:System.Threading.CancellationToken> 参数。</span><span class="sxs-lookup"><span data-stu-id="a9172-151">Use the <xref:System.Net.Http.HttpClient.GetAsync%2A> method to download the websites because `GetAsync` accepts a <xref:System.Threading.CancellationToken> argument.</span></span>

- <span data-ttu-id="a9172-152">调用 `DisplayResults` 以显示下载的每个网站的结果之前，检查 `ct` 以验证当前操作是否未取消。</span><span class="sxs-lookup"><span data-stu-id="a9172-152">Before calling `DisplayResults` to display the results for each downloaded website, check `ct` to verify that the current operation hasn’t been canceled.</span></span>

 <span data-ttu-id="a9172-153">下面的代码演示了这些更改（使用星号标记）。</span><span class="sxs-lookup"><span data-stu-id="a9172-153">The following code shows these changes, which are marked with asterisks.</span></span>

```vb
' *** Provide a parameter for the CancellationToken from StartButton_Click.
Private Async Function AccessTheWebAsync(ct As CancellationToken) As Task

    ' Declare an HttpClient object.
    Dim client = New HttpClient()

    ' Make a list of web addresses.
    Dim urlList As List(Of String) = SetUpURLList()

    Dim total = 0
    Dim position = 0

    For Each url In urlList
        ' *** Use the HttpClient.GetAsync method because it accepts a
        ' cancellation token.
        Dim response As HttpResponseMessage = Await client.GetAsync(url, ct)

        ' *** Retrieve the website contents from the HttpResponseMessage.
        Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()

        ' *** Check for cancellations before displaying information about the
        ' latest site.
        ct.ThrowIfCancellationRequested()

        position += 1
        DisplayResults(url, urlContents, position)

        ' Update the total.
        total += urlContents.Length
    Next

    ' Display the total count for all of the websites.
    ResultsTextBox.Text &=
        String.Format(vbCrLf & vbCrLf & "TOTAL bytes returned:  " & total & vbCrLf)
End Function
```

<span data-ttu-id="a9172-154">如果在运行此应用时多次选择 **"开始"** 按钮，则应生成类似于以下输出的结果：</span><span class="sxs-lookup"><span data-stu-id="a9172-154">If you choose the **Start** button several times while this app is running, it should produce results that resemble the following output:</span></span>

```console
1. msdn.microsoft.com/library/hh191443.aspx                83732
2. msdn.microsoft.com/library/aa578028.aspx               205273
3. msdn.microsoft.com/library/jj155761.aspx                29019
4. msdn.microsoft.com/library/hh290140.aspx               122505
5. msdn.microsoft.com/library/hh524395.aspx                68959
6. msdn.microsoft.com/library/ms404677.aspx               197325
Download canceled.

1. msdn.microsoft.com/library/hh191443.aspx                83732
2. msdn.microsoft.com/library/aa578028.aspx               205273
3. msdn.microsoft.com/library/jj155761.aspx                29019
Download canceled.

1. msdn.microsoft.com/library/hh191443.aspx                83732
2. msdn.microsoft.com/library/aa578028.aspx               205273
3. msdn.microsoft.com/library/jj155761.aspx                29019
4. msdn.microsoft.com/library/hh290140.aspx               117152
5. msdn.microsoft.com/library/hh524395.aspx                68959
6. msdn.microsoft.com/library/ms404677.aspx               197325
7. msdn.microsoft.com                                            42972
8. msdn.microsoft.com/library/ff730837.aspx               146159

TOTAL bytes returned:  890591
```

<span data-ttu-id="a9172-155">若要消除部分列表，请对 `StartButton_Click` 中的第一行代码取消注释以在用户每次重新启动操作时清除文本框。</span><span class="sxs-lookup"><span data-stu-id="a9172-155">To eliminate the partial lists, uncomment the first line of code in `StartButton_Click` to clear the text box each time the user restarts the operation.</span></span>

### <a name="run-multiple-operations-and-queue-the-output"></a><a name="BKMK_RunMultipleOperations"></a><span data-ttu-id="a9172-156">运行多个操作并排队输出</span><span class="sxs-lookup"><span data-stu-id="a9172-156">Run Multiple Operations and Queue the Output</span></span>

<span data-ttu-id="a9172-157">此第三个示例最复杂，因为应用会在用户每次选择“开始”\*\*\*\* 按钮时启动另一个异步操作，并且所有操作都会运行到完成。</span><span class="sxs-lookup"><span data-stu-id="a9172-157">This third example is the most complicated in that the app starts another asynchronous operation each time that the user chooses the **Start** button, and all the operations run to completion.</span></span> <span data-ttu-id="a9172-158">所有请求的操作以异步方式从列表中下载网站，但是操作的输出会按顺序呈现。</span><span class="sxs-lookup"><span data-stu-id="a9172-158">All the requested operations download websites from the list asynchronously, but the output from the operations is presented sequentially.</span></span> <span data-ttu-id="a9172-159">也就是说，实际下载活动是交错进行的（如[识别重新进入](#BKMK_RecognizingReentrancy)中的输出所示），但是每个组的结果列表会分开呈现。</span><span class="sxs-lookup"><span data-stu-id="a9172-159">That is, the actual downloading activity is interleaved, as the output in [Recognizing Reentrancy](#BKMK_RecognizingReentrancy) shows, but the list of results for each group is presented separately.</span></span>

<span data-ttu-id="a9172-160">操作会共享一个全局 <xref:System.Threading.Tasks.Task> (`pendingWork`)，它用作显示进程的守卫。</span><span class="sxs-lookup"><span data-stu-id="a9172-160">The operations share a global <xref:System.Threading.Tasks.Task>, `pendingWork`, which serves as a gatekeeper for the display process.</span></span>

<span data-ttu-id="a9172-161">可以通过将更改粘贴到[生成应用](#BKMK_BuildingTheApp)中的代码来运行此示例，也可以按照[下载应用](#BKMK_DownloadingTheApp)中的说明下载示例，然后运行 QueueResults 项目。</span><span class="sxs-lookup"><span data-stu-id="a9172-161">You can run this example by pasting the changes into the code in [Building the App](#BKMK_BuildingTheApp), or you can follow the instructions in [Downloading the App](#BKMK_DownloadingTheApp) to download the sample and then run the QueueResults project.</span></span>

<span data-ttu-id="a9172-162">下面的输出显示用户仅选择“开始”\*\*\*\* 按钮一次时的结果。</span><span class="sxs-lookup"><span data-stu-id="a9172-162">The following output shows the result if the user chooses the **Start** button only once.</span></span> <span data-ttu-id="a9172-163">字母标签 A 指示结果来自首次选择“开始”\*\*\*\* 按钮。</span><span class="sxs-lookup"><span data-stu-id="a9172-163">The letter label, A, indicates that the result is from the first time the **Start** button is chosen.</span></span> <span data-ttu-id="a9172-164">编号显示下载目标列表中 URL 的顺序。</span><span class="sxs-lookup"><span data-stu-id="a9172-164">The numbers show the order of the URLs in the list of download targets.</span></span>

```console
#Starting group A.
#Task assigned for group A.

A-1. msdn.microsoft.com/library/hh191443.aspx                87389
A-2. msdn.microsoft.com/library/aa578028.aspx               209858
A-3. msdn.microsoft.com/library/jj155761.aspx                30870
A-4. msdn.microsoft.com/library/hh290140.aspx               119027
A-5. msdn.microsoft.com/library/hh524395.aspx                71260
A-6. msdn.microsoft.com/library/ms404677.aspx               199186
A-7. msdn.microsoft.com                                            53266
A-8. msdn.microsoft.com/library/ff730837.aspx               148020

TOTAL bytes returned:  918876

#Group A is complete.
```

<span data-ttu-id="a9172-165">如果用户选择“开始”\*\*\*\* 按钮三次，则应用会生成类似于以下各行的输出。</span><span class="sxs-lookup"><span data-stu-id="a9172-165">If the user chooses the **Start** button three times, the app produces output that resembles the following lines.</span></span> <span data-ttu-id="a9172-166">以井号 (#) 开头的信息行会跟踪应用程序的进度。</span><span class="sxs-lookup"><span data-stu-id="a9172-166">The information lines that start with a pound sign (#) trace the progress of the application.</span></span>

```console
#Starting group A.
#Task assigned for group A.

A-1. msdn.microsoft.com/library/hh191443.aspx                87389
A-2. msdn.microsoft.com/library/aa578028.aspx               207089
A-3. msdn.microsoft.com/library/jj155761.aspx                30870
A-4. msdn.microsoft.com/library/hh290140.aspx               119027
A-5. msdn.microsoft.com/library/hh524395.aspx                71259
A-6. msdn.microsoft.com/library/ms404677.aspx               199185

#Starting group B.
#Task assigned for group B.

A-7. msdn.microsoft.com                                            53266

#Starting group C.
#Task assigned for group C.

A-8. msdn.microsoft.com/library/ff730837.aspx               148010

TOTAL bytes returned:  916095

B-1. msdn.microsoft.com/library/hh191443.aspx                87389
B-2. msdn.microsoft.com/library/aa578028.aspx               207089
B-3. msdn.microsoft.com/library/jj155761.aspx                30870
B-4. msdn.microsoft.com/library/hh290140.aspx               119027
B-5. msdn.microsoft.com/library/hh524395.aspx                71260
B-6. msdn.microsoft.com/library/ms404677.aspx               199186

#Group A is complete.

B-7. msdn.microsoft.com                                            53266
B-8. msdn.microsoft.com/library/ff730837.aspx               148010

TOTAL bytes returned:  916097

C-1. msdn.microsoft.com/library/hh191443.aspx                87389
C-2. msdn.microsoft.com/library/aa578028.aspx               207089

#Group B is complete.

C-3. msdn.microsoft.com/library/jj155761.aspx                30870
C-4. msdn.microsoft.com/library/hh290140.aspx               119027
C-5. msdn.microsoft.com/library/hh524395.aspx                72765
C-6. msdn.microsoft.com/library/ms404677.aspx               199186
C-7. msdn.microsoft.com                                            56190
C-8. msdn.microsoft.com/library/ff730837.aspx               148010

TOTAL bytes returned:  920526

#Group C is complete.
```

<span data-ttu-id="a9172-167">组 B 和 C 会在组 A 完成之前开始，但是每个组的输出会分开显示。</span><span class="sxs-lookup"><span data-stu-id="a9172-167">Groups B and C start before group A has finished, but the output for the each group appears separately.</span></span> <span data-ttu-id="a9172-168">组 A 的所有输出会首先显示，后跟组 B 的所有输出，再然后是组 C 的所有输出。应用会始终按顺序显示组，并且对于每个组，始终按 URL 在 URL 列表中的显示顺序来显示有关各个网站的信息。</span><span class="sxs-lookup"><span data-stu-id="a9172-168">All the output for group A appears first, followed by all the output for group B, and then all the output for group C. The app always displays the groups in order and, for each group, always displays the information about the individual websites in the order that the URLs appear in the list of URLs.</span></span>

<span data-ttu-id="a9172-169">但是，无法预测下载实际发生的顺序。</span><span class="sxs-lookup"><span data-stu-id="a9172-169">However, you can't predict the order in which the downloads actually happen.</span></span> <span data-ttu-id="a9172-170">在多个组启动之后，它们生成的下载任务都处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="a9172-170">After multiple groups have been started, the download tasks that they generate are all active.</span></span> <span data-ttu-id="a9172-171">无法假定 A-1 会在 B-1 之前下载，并且无法假定 A-1 会在 A-2 之前下载。</span><span class="sxs-lookup"><span data-stu-id="a9172-171">You can't assume that A-1 will be downloaded before B-1, and you can't assume that A-1 will be downloaded before A-2.</span></span>

#### <a name="global-definitions"></a><span data-ttu-id="a9172-172">全局定义</span><span class="sxs-lookup"><span data-stu-id="a9172-172">Global Definitions</span></span>

<span data-ttu-id="a9172-173">示例代码包含所有方法都可见的以下两个全局声明。</span><span class="sxs-lookup"><span data-stu-id="a9172-173">The sample code contains the following two global declarations that are visible from all methods.</span></span>

```vb
Class MainWindow    ' Class MainPage in Windows Store app.

    ' ***Declare the following variables where all methods can access them.
    Private pendingWork As Task = Nothing
    Private group As Char = ChrW(AscW("A") - 1)
```

<span data-ttu-id="a9172-174">`Task` 变量 `pendingWork` 会监视显示进程并防止任何组中断另一个组的显示操作。</span><span class="sxs-lookup"><span data-stu-id="a9172-174">The `Task` variable, `pendingWork`, oversees the display process and prevents any group from interrupting another group's display operation.</span></span> <span data-ttu-id="a9172-175">字符变量 `group` 标记来自不同组的输出以验证结果是否按预期顺序出现。</span><span class="sxs-lookup"><span data-stu-id="a9172-175">The character variable, `group`, labels the output from different groups to verify that results appear in the expected order.</span></span>

#### <a name="the-click-event-handler"></a><span data-ttu-id="a9172-176">单击事件处理程序</span><span class="sxs-lookup"><span data-stu-id="a9172-176">The Click Event Handler</span></span>

<span data-ttu-id="a9172-177">事件处理程序 `StartButton_Click` 会在用户每次选择“开始”\*\*\*\* 按钮时增加组号。</span><span class="sxs-lookup"><span data-stu-id="a9172-177">The event handler, `StartButton_Click`, increments the group letter each time the user chooses the **Start** button.</span></span> <span data-ttu-id="a9172-178">随后处理程序会调用 `AccessTheWebAsync` 以运行下载操作。</span><span class="sxs-lookup"><span data-stu-id="a9172-178">Then the handler calls `AccessTheWebAsync` to run the downloading operation.</span></span>

```vb
Private Async Sub StartButton_Click(sender As Object, e As RoutedEventArgs)
    ' ***Verify that each group's results are displayed together, and that
    ' the groups display in order, by marking each group with a letter.
    group = ChrW(AscW(group) + 1)
    ResultsTextBox.Text &= String.Format(vbCrLf & vbCrLf & "#Starting group {0}.", group)

    Try
        ' *** Pass the group value to AccessTheWebAsync.
        Dim finishedGroup As Char = Await AccessTheWebAsync(group)

        ' The following line verifies a successful return from the download and
        ' display procedures.
        ResultsTextBox.Text &= String.Format(vbCrLf & vbCrLf & "#Group {0} is complete." & vbCrLf, finishedGroup)

    Catch ex As Exception
        ResultsTextBox.Text &= vbCrLf & "Downloads failed."

    End Try
End Sub
```

#### <a name="the-accessthewebasync-method"></a><span data-ttu-id="a9172-179">AccessTheWebAsync 方法</span><span class="sxs-lookup"><span data-stu-id="a9172-179">The AccessTheWebAsync Method</span></span>

<span data-ttu-id="a9172-180">此示例将 `AccessTheWebAsync` 拆分为两个方法。</span><span class="sxs-lookup"><span data-stu-id="a9172-180">This example splits `AccessTheWebAsync` into two methods.</span></span> <span data-ttu-id="a9172-181">第一个方法 `AccessTheWebAsync` 会为组启动所有下载任务并设置 `pendingWork` 以控制显示进程。</span><span class="sxs-lookup"><span data-stu-id="a9172-181">The first method, `AccessTheWebAsync`, starts all the download tasks for a group and sets up `pendingWork` to control the display process.</span></span> <span data-ttu-id="a9172-182">该方法使用语言集成查询（LINQ 查询）和 <xref:System.Linq.Enumerable.ToArray%2A> 同时启动所有下载任务。</span><span class="sxs-lookup"><span data-stu-id="a9172-182">The method uses a Language Integrated Query (LINQ query) and <xref:System.Linq.Enumerable.ToArray%2A> to start all the download tasks at the same time.</span></span>

<span data-ttu-id="a9172-183">`AccessTheWebAsync` 随后调用 `FinishOneGroupAsync` 以等待每个下载完成并显示其长度。</span><span class="sxs-lookup"><span data-stu-id="a9172-183">`AccessTheWebAsync` then calls `FinishOneGroupAsync` to await the completion of each download and display its length.</span></span>

<span data-ttu-id="a9172-184">`FinishOneGroupAsync` 会返回在 `AccessTheWebAsync` 中分配给 `pendingWork` 的任务。</span><span class="sxs-lookup"><span data-stu-id="a9172-184">`FinishOneGroupAsync` returns a task that's assigned to `pendingWork` in `AccessTheWebAsync`.</span></span> <span data-ttu-id="a9172-185">该值会在任务完成之前阻止另一个操作进行中断。</span><span class="sxs-lookup"><span data-stu-id="a9172-185">That value prevents interruption by another operation before the task is complete.</span></span>

```vb
Private Async Function AccessTheWebAsync(grp As Char) As Task(Of Char)

    Dim client = New HttpClient()

    ' Make a list of the web addresses to download.
    Dim urlList As List(Of String) = SetUpURLList()

    ' ***Kick off the downloads. The application of ToArray activates all the download tasks.
    Dim getContentTasks As Task(Of Byte())() =
        urlList.Select(Function(addr) client.GetByteArrayAsync(addr)).ToArray()

    ' ***Call the method that awaits the downloads and displays the results.
    ' Assign the Task that FinishOneGroupAsync returns to the gatekeeper task, pendingWork.
    pendingWork = FinishOneGroupAsync(urlList, getContentTasks, grp)

    ResultsTextBox.Text &=
        String.Format(vbCrLf & "#Task assigned for group {0}. Download tasks are active." & vbCrLf, grp)

    ' ***This task is complete when a group has finished downloading and displaying.
    Await pendingWork

    ' You can do other work here or just return.
    Return grp
End Function
```

#### <a name="the-finishonegroupasync-method"></a><span data-ttu-id="a9172-186">FinishOneGroupAsync 方法</span><span class="sxs-lookup"><span data-stu-id="a9172-186">The FinishOneGroupAsync Method</span></span>

<span data-ttu-id="a9172-187">此方法会循环访问组中的下载任务（等待每个任务、显示下载网站的长度并将该长度添加到总和中）。</span><span class="sxs-lookup"><span data-stu-id="a9172-187">This method cycles through the download tasks in a group, awaiting each one, displaying the length of the downloaded website, and adding the length to the total.</span></span>

<span data-ttu-id="a9172-188">`FinishOneGroupAsync` 中的第一个语句使用 `pendingWork` 确保进入方法不会干扰已在显示进程中或已在等待的操作。</span><span class="sxs-lookup"><span data-stu-id="a9172-188">The first statement in `FinishOneGroupAsync` uses `pendingWork` to make sure that entering the method doesn't interfere with an operation that is already in the display process or that's already waiting.</span></span> <span data-ttu-id="a9172-189">如果这类操作正在进行，则进入操作必须等待轮到它。</span><span class="sxs-lookup"><span data-stu-id="a9172-189">If such an operation is in progress, the entering operation must wait its turn.</span></span>

```vb
Private Async Function FinishOneGroupAsync(urls As List(Of String), contentTasks As Task(Of Byte())(), grp As Char) As Task

    ' Wait for the previous group to finish displaying results.
    If pendingWork IsNot Nothing Then
        Await pendingWork
    End If

    Dim total = 0

    ' contentTasks is the array of Tasks that was created in AccessTheWebAsync.
    For i As Integer = 0 To contentTasks.Length - 1
        ' Await the download of a particular URL, and then display the URL and
        ' its length.
        Dim content As Byte() = Await contentTasks(i)
        DisplayResults(urls(i), content, i, grp)
        total += content.Length
    Next

    ' Display the total count for all of the websites.
    ResultsTextBox.Text &=
        String.Format(vbCrLf & vbCrLf & "TOTAL bytes returned:  " & total & vbCrLf)
End Function
```

<span data-ttu-id="a9172-190">可以通过在[构建应用](#BKMK_BuildingTheApp)中将更改粘贴到代码中来运行此示例，也可以按照[下载应用](#BKMK_DownloadingTheApp)中的说明下载示例，然后运行队列结果项目。</span><span class="sxs-lookup"><span data-stu-id="a9172-190">You can run this example by pasting the changes into the code in [Building the App](#BKMK_BuildingTheApp), or you can follow the instructions in [Downloading the App](#BKMK_DownloadingTheApp) to download the sample, and then run the QueueResults project.</span></span>

#### <a name="points-of-interest"></a><span data-ttu-id="a9172-191">兴趣点</span><span class="sxs-lookup"><span data-stu-id="a9172-191">Points of Interest</span></span>

<span data-ttu-id="a9172-192">输出中以井号 (#) 开头的信息行阐明了此示例的工作原理。</span><span class="sxs-lookup"><span data-stu-id="a9172-192">The information lines that start with a pound sign (#) in the output clarify how this example works.</span></span>

<span data-ttu-id="a9172-193">输出演示以下模式。</span><span class="sxs-lookup"><span data-stu-id="a9172-193">The output shows the following patterns.</span></span>

- <span data-ttu-id="a9172-194">一个组可以上一组显示其输出期间启动，但上一组的输出显示不会中断。</span><span class="sxs-lookup"><span data-stu-id="a9172-194">A group can be started while a previous group is displaying its output, but the display of the previous group's output isn't interrupted.</span></span>

  ```console
  #Starting group A.
  #Task assigned for group A. Download tasks are active.

  A-1. msdn.microsoft.com/library/hh191443.aspx                87389
  A-2. msdn.microsoft.com/library/aa578028.aspx               207089
  A-3. msdn.microsoft.com/library/jj155761.aspx                30870
  A-4. msdn.microsoft.com/library/hh290140.aspx               119037
  A-5. msdn.microsoft.com/library/hh524395.aspx                71260

  #Starting group B.
  #Task assigned for group B. Download tasks are active.

  A-6. msdn.microsoft.com/library/ms404677.aspx               199186
  A-7. msdn.microsoft.com                                            53078
  A-8. msdn.microsoft.com/library/ff730837.aspx               148010

  TOTAL bytes returned:  915919

  B-1. msdn.microsoft.com/library/hh191443.aspx                87388
  B-2. msdn.microsoft.com/library/aa578028.aspx               207089
  B-3. msdn.microsoft.com/library/jj155761.aspx                30870

  #Group A is complete.

  B-4. msdn.microsoft.com/library/hh290140.aspx               119027
  B-5. msdn.microsoft.com/library/hh524395.aspx                71260
  B-6. msdn.microsoft.com/library/ms404677.aspx               199186
  B-7. msdn.microsoft.com                                            53078
  B-8. msdn.microsoft.com/library/ff730837.aspx               148010

  TOTAL bytes returned:  915908
  ```

- <span data-ttu-id="a9172-195">任务`pendingWork`仅`Nothing`针对首先启动的`FinishOneGroupAsync`A 组。</span><span class="sxs-lookup"><span data-stu-id="a9172-195">The `pendingWork` task is `Nothing` at the start of `FinishOneGroupAsync` only for group A, which started first.</span></span> <span data-ttu-id="a9172-196">组 A 在它到达 `FinishOneGroupAsync` 时尚未尚未完成 await 表达式。</span><span class="sxs-lookup"><span data-stu-id="a9172-196">Group A hasn’t yet completed an await expression when it reaches `FinishOneGroupAsync`.</span></span> <span data-ttu-id="a9172-197">因此，控制权未返回给 `AccessTheWebAsync`，对 `pendingWork` 的第一个分配尚未发生。</span><span class="sxs-lookup"><span data-stu-id="a9172-197">Therefore, control hasn't returned to `AccessTheWebAsync`, and the first assignment to `pendingWork` hasn't occurred.</span></span>

- <span data-ttu-id="a9172-198">下面两行始终在输出中一起显示。</span><span class="sxs-lookup"><span data-stu-id="a9172-198">The following two lines always appear together in the output.</span></span> <span data-ttu-id="a9172-199">该代码从不会在于 `StartButton_Click` 中启动组操作与将组的任务分配给 `pendingWork` 之间中断。</span><span class="sxs-lookup"><span data-stu-id="a9172-199">The code is never interrupted between starting a group's operation in `StartButton_Click` and assigning a task for the group to `pendingWork`.</span></span>

  ```console
  #Starting group B.
  #Task assigned for group B. Download tasks are active.
  ```

  <span data-ttu-id="a9172-200">组进入 `StartButton_Click` 之后，操作在操作进入 `FinishOneGroupAsync` 之前不会完成 await 表达式。</span><span class="sxs-lookup"><span data-stu-id="a9172-200">After a group enters `StartButton_Click`, the operation doesn't complete an await expression until the operation enters `FinishOneGroupAsync`.</span></span> <span data-ttu-id="a9172-201">因此，没有其他操作可以在代码段期间获得控制权。</span><span class="sxs-lookup"><span data-stu-id="a9172-201">Therefore, no other operation can gain control during that segment of code.</span></span>

## <a name="reviewing-and-running-the-example-app"></a><a name="BKMD_SettingUpTheExample"></a><span data-ttu-id="a9172-202">查看并运行示例应用</span><span class="sxs-lookup"><span data-stu-id="a9172-202">Reviewing and Running the Example App</span></span>

<span data-ttu-id="a9172-203">若要更好地了解示例应用，可以下载它，自己生成或查看本主题末尾的代码，而无需实现应用。</span><span class="sxs-lookup"><span data-stu-id="a9172-203">To better understand the example app, you can download it, build it yourself, or review the code at the end of this topic without implementing the app.</span></span>

> [!NOTE]
> <span data-ttu-id="a9172-204">若要将示例作为 Windows Presentation Foundation (WPF) 桌面应用运行，计算机上必须安装有 Visual Studio 2012 或更高版本和 .NET Framework 4.5 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="a9172-204">To run the example as a Windows Presentation Foundation (WPF) desktop app, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>

### <a name="downloading-the-app"></a><a name="BKMK_DownloadingTheApp"></a><span data-ttu-id="a9172-205">下载应用</span><span class="sxs-lookup"><span data-stu-id="a9172-205">Downloading the App</span></span>

1. <span data-ttu-id="a9172-206">从[异步示例：.NET 桌面应用中的重新进入](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06)下载压缩文件。</span><span class="sxs-lookup"><span data-stu-id="a9172-206">Download the compressed file from [Async Samples: Reentrancy in .NET Desktop Apps](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06).</span></span>

2. <span data-ttu-id="a9172-207">解压缩下载的文件，然后启动 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="a9172-207">Decompress the file that you downloaded, and then start Visual Studio.</span></span>

3. <span data-ttu-id="a9172-208">在菜单栏上，依次选择 **“文件”**、 **“打开”** 和 **“项目/解决方案”**。</span><span class="sxs-lookup"><span data-stu-id="a9172-208">On the menu bar, choose **File**, **Open**, **Project/Solution**.</span></span>

4. <span data-ttu-id="a9172-209">导航到保存解压缩的示例代码的文件夹，然后打开解决方案 (.sln) 文件。</span><span class="sxs-lookup"><span data-stu-id="a9172-209">Navigate to the folder that holds the decompressed sample code, and then open the solution (.sln) file.</span></span>

5. <span data-ttu-id="a9172-210">在“解决方案资源管理器”\*\*\*\* 中，打开要运行的项目的快捷菜单，然后选择“设置为 StartUpProject”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a9172-210">In **Solution Explorer**, open the shortcut menu for the project that you want to run, and then choose **Set as StartUpProject**.</span></span>

6. <span data-ttu-id="a9172-211">选择 CTRL+F5 键以生成并运行项目。</span><span class="sxs-lookup"><span data-stu-id="a9172-211">Choose the CTRL+F5 keys to build and run the project.</span></span>

### <a name="building-the-app"></a><a name="BKMK_BuildingTheApp"></a><span data-ttu-id="a9172-212">生成应用</span><span class="sxs-lookup"><span data-stu-id="a9172-212">Building the App</span></span>

<span data-ttu-id="a9172-213">以下部分提供用于将示例生成为 WPF 应用的代码。</span><span class="sxs-lookup"><span data-stu-id="a9172-213">The following section provides the code to build the example as a WPF app.</span></span>

##### <a name="to-build-a-wpf-app"></a><span data-ttu-id="a9172-214">生成 WPF 应用程序</span><span class="sxs-lookup"><span data-stu-id="a9172-214">To build a WPF app</span></span>

1. <span data-ttu-id="a9172-215">启动 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="a9172-215">Start Visual Studio.</span></span>

2. <span data-ttu-id="a9172-216">在菜单栏上，依次选择 **“文件”**-&gt;**“新建”**-&gt;**“项目”**。</span><span class="sxs-lookup"><span data-stu-id="a9172-216">On the menu bar, choose **File**, **New**, **Project**.</span></span>

     <span data-ttu-id="a9172-217">系统将打开“新建项目”\*\*\*\* 对话框。</span><span class="sxs-lookup"><span data-stu-id="a9172-217">The **New Project** dialog box opens.</span></span>

3. <span data-ttu-id="a9172-218">在 **"已安装模板"** 窗格中，展开**可视化基本**，然后展开**Windows**。</span><span class="sxs-lookup"><span data-stu-id="a9172-218">In the **Installed Templates** pane, expand **Visual Basic**, and then expand **Windows**.</span></span>

4. <span data-ttu-id="a9172-219">在项目类型列表中，选择“WPF 应用程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a9172-219">In the list of project types, choose **WPF Application**.</span></span>

5. <span data-ttu-id="a9172-220">将项目命名为 `WebsiteDownloadWPF`，选择 .NET Framework 版本 4.6 或更高版本，然后单击“确定”按钮\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a9172-220">Name the project `WebsiteDownloadWPF`, choose .NET Framework version of 4.6 or higher and then click the **OK** button.</span></span>

     <span data-ttu-id="a9172-221">新项目将出现在“解决方案资源管理器”\*\*\*\* 中。</span><span class="sxs-lookup"><span data-stu-id="a9172-221">The new project appears in **Solution Explorer**.</span></span>

6. <span data-ttu-id="a9172-222">在 Visual Studio 代码编辑器中，选择 **“MainWindow.xaml”** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="a9172-222">In the Visual Studio Code Editor, choose the **MainWindow.xaml** tab.</span></span>

     <span data-ttu-id="a9172-223">如果选项卡不可见，请打开**解决方案资源管理器**中 MainWindow.xaml 的快捷菜单，然后选择 **"查看代码**"。</span><span class="sxs-lookup"><span data-stu-id="a9172-223">If the tab isn’t visible, open the shortcut menu for MainWindow.xaml in **Solution Explorer**, and then choose **View Code**.</span></span>

7. <span data-ttu-id="a9172-224">在 MainWindow.xaml 的“XAML”\*\*\*\* 视图中，将代码替换为以下代码。</span><span class="sxs-lookup"><span data-stu-id="a9172-224">In the **XAML** view of MainWindow.xaml, replace the code with the following code.</span></span>

    ```xaml
    <Window x:Class="MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:local="using:WebsiteDownloadWPF"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        mc:Ignorable="d">

        <Grid Width="517" Height="360">
            <Button x:Name="StartButton" Content="Start" HorizontalAlignment="Left" Margin="-1,0,0,0" VerticalAlignment="Top" Click="StartButton_Click" Height="53" Background="#FFA89B9B" FontSize="36" Width="518"  />
            <TextBox x:Name="ResultsTextBox" HorizontalAlignment="Left" Margin="-1,53,0,-36" TextWrapping="Wrap" VerticalAlignment="Top" Height="343" FontSize="10" ScrollViewer.VerticalScrollBarVisibility="Visible" Width="518" FontFamily="Lucida Console" />
        </Grid>
    </Window>
    ```

     <span data-ttu-id="a9172-225">MainWindow.xaml 的“设计”\*\*\*\* 视图中将显示一个简单的窗口，其中包含一个文本框和一个按钮。</span><span class="sxs-lookup"><span data-stu-id="a9172-225">A simple window that contains a text box and a button appears in the **Design** view of MainWindow.xaml.</span></span>

8. <span data-ttu-id="a9172-226">在**解决方案资源管理器中**，右键单击**引用**并选择"**添加引用**"。</span><span class="sxs-lookup"><span data-stu-id="a9172-226">In **Solution Explorer**, right-click on **References** and select **Add Reference**.</span></span>

     <span data-ttu-id="a9172-227">如果尚未选择，请为 <xref:System.Net.Http> 添加引用。</span><span class="sxs-lookup"><span data-stu-id="a9172-227">Add a reference for <xref:System.Net.Http>, if it is not selected already.</span></span>

9. <span data-ttu-id="a9172-228">在**解决方案资源管理器中**，打开 MainWindow.xaml.vb 的快捷菜单，然后选择 **"查看代码**"。</span><span class="sxs-lookup"><span data-stu-id="a9172-228">In **Solution Explorer**, open the shortcut menu for MainWindow.xaml.vb, and then choose **View Code**.</span></span>

10. <span data-ttu-id="a9172-229">在 MainWindow.xaml.vb 中，将代码替换为以下代码。</span><span class="sxs-lookup"><span data-stu-id="a9172-229">In MainWindow.xaml.vb , replace the code with the following code.</span></span>

    ```vb
    ' Add the following Imports statements, and add a reference for System.Net.Http.
    Imports System.Net.Http
    Imports System.Threading

    Class MainWindow

        Private Async Sub StartButton_Click(sender As Object, e As RoutedEventArgs)
            System.Net.ServicePointManager.SecurityProtocol = System.Net.ServicePointManager.SecurityProtocol Or System.Net.SecurityProtocolType.Tls12

            ' This line is commented out to make the results clearer in the output.
            'ResultsTextBox.Text = ""

            Try
                Await AccessTheWebAsync()

            Catch ex As Exception
                ResultsTextBox.Text &= vbCrLf & "Downloads failed."

            End Try
        End Sub

        Private Async Function AccessTheWebAsync() As Task

            ' Declare an HttpClient object.
            Dim client = New HttpClient()

            ' Make a list of web addresses.
            Dim urlList As List(Of String) = SetUpURLList()

            Dim total = 0
            Dim position = 0

            For Each url In urlList
                ' GetByteArrayAsync returns a task. At completion, the task
                ' produces a byte array.
                Dim urlContents As Byte() = Await client.GetByteArrayAsync(url)

                position += 1
                DisplayResults(url, urlContents, position)

                ' Update the total.
                total += urlContents.Length
            Next

            ' Display the total count for all of the websites.
            ResultsTextBox.Text &=
                String.Format(vbCrLf & vbCrLf & "TOTAL bytes returned:  " & total & vbCrLf)
        End Function

        Private Function SetUpURLList() As List(Of String)
            Dim urls = New List(Of String) From
            {
                "https://msdn.microsoft.com/library/hh191443.aspx",
                "https://msdn.microsoft.com/library/aa578028.aspx",
                "https://msdn.microsoft.com/library/jj155761.aspx",
                "https://msdn.microsoft.com/library/hh290140.aspx",
                "https://msdn.microsoft.com/library/hh524395.aspx",
                "https://msdn.microsoft.com/library/ms404677.aspx",
                "https://msdn.microsoft.com",
                "https://msdn.microsoft.com/library/ff730837.aspx"
            }
            Return urls
        End Function

        Private Sub DisplayResults(url As String, content As Byte(), pos As Integer)
            ' Display the length of each website. The string format is designed
            ' to be used with a monospaced font, such as Lucida Console or
            ' Global Monospace.

            ' Strip off the "http:'".
            Dim displayURL = url.Replace("https://", "")
            ' Display position in the URL list, the URL, and the number of bytes.
            ResultsTextBox.Text &= String.Format(vbCrLf & "{0}. {1,-58} {2,8}", pos, displayURL, content.Length)
        End Sub
    End Class
    ```

11. <span data-ttu-id="a9172-230">选择 CTRL+F5 键以运行程序，然后多次选择“开始”\*\*\*\* 按钮。</span><span class="sxs-lookup"><span data-stu-id="a9172-230">Choose the CTRL+F5 keys to run the program, and then choose the **Start** button several times.</span></span>

12. <span data-ttu-id="a9172-231">从[禁用“开始”按钮](#BKMK_DisableTheStartButton)、[取消并重启操作](#BKMK_CancelAndRestart)或[运行多个操作并将输出排入队列](#BKMK_RunMultipleOperations)中进行更改以处理重新进入。</span><span class="sxs-lookup"><span data-stu-id="a9172-231">Make the changes from [Disable the Start Button](#BKMK_DisableTheStartButton), [Cancel and Restart the Operation](#BKMK_CancelAndRestart), or [Run Multiple Operations and Queue the Output](#BKMK_RunMultipleOperations) to handle the reentrancy.</span></span>

## <a name="see-also"></a><span data-ttu-id="a9172-232">请参阅</span><span class="sxs-lookup"><span data-stu-id="a9172-232">See also</span></span>

- [<span data-ttu-id="a9172-233">演练：使用 Async 和 Await 访问 Web (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a9172-233">Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)
- [<span data-ttu-id="a9172-234">使用 Async 和 Await 的异步编程 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a9172-234">Asynchronous Programming with Async and Await (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/index.md)
