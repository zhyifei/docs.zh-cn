---
title: 在异步任务完成时对其进行处理
ms.date: 09/12/2018
ms.assetid: 25331850-35a7-43b3-ab76-3908e4346b9d
ms.openlocfilehash: 335eb5dce74a7f0a2b8af550250105d460212b6a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59304852"
---
# <a name="start-multiple-async-tasks-and-process-them-as-they-complete-c"></a><span data-ttu-id="b16e4-102">启动多个异步任务并在其完成时进行处理 (C#)</span><span class="sxs-lookup"><span data-stu-id="b16e4-102">Start Multiple Async Tasks and Process Them As They Complete (C#)</span></span>

<span data-ttu-id="b16e4-103">通过使用 <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>，可以同时启动多个任务，并在它们完成时逐个对它们进行处理，而不是按照它们的启动顺序进行处理。</span><span class="sxs-lookup"><span data-stu-id="b16e4-103">By using <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>, you can start multiple tasks at the same time and process them one by one as they’re completed rather than process them in the order in which they're started.</span></span>

<span data-ttu-id="b16e4-104">下面的示例使用查询来创建一组任务。</span><span class="sxs-lookup"><span data-stu-id="b16e4-104">The following example uses a query to create a collection of tasks.</span></span> <span data-ttu-id="b16e4-105">每个任务都下载指定网站的内容。</span><span class="sxs-lookup"><span data-stu-id="b16e4-105">Each task downloads the contents of a specified website.</span></span> <span data-ttu-id="b16e4-106">在对 while 循环的每次迭代中，对 `WhenAny` 的等待调用返回任务集合中首先完成下载的任务。</span><span class="sxs-lookup"><span data-stu-id="b16e4-106">In each iteration of a while loop, an awaited call to `WhenAny` returns the task in the collection of tasks that finishes its download first.</span></span> <span data-ttu-id="b16e4-107">此任务从集合中删除并进行处理。</span><span class="sxs-lookup"><span data-stu-id="b16e4-107">That task is removed from the collection and processed.</span></span> <span data-ttu-id="b16e4-108">循环重复进行，直到集合中不包含任何任务。</span><span class="sxs-lookup"><span data-stu-id="b16e4-108">The loop repeats until the collection contains no more tasks.</span></span>

> [!NOTE]
> <span data-ttu-id="b16e4-109">若要运行示例，计算机上必须安装有 Visual Studio（2012 或更高版本）和 .NET Framework 4.5 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="b16e4-109">To run the examples, you must have Visual Studio (2012 or newer) and the .NET Framework 4.5 or newer installed on your computer.</span></span>

## <a name="download-an-example-solution"></a><span data-ttu-id="b16e4-110">下载示例解决方案</span><span class="sxs-lookup"><span data-stu-id="b16e4-110">Download an example solution</span></span>

<span data-ttu-id="b16e4-111">若要下载完整的 Windows Presentation Foundation (WPF) 项目，请参阅 [Async Sample:Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea)（异步示例：微调应用程序）。</span><span class="sxs-lookup"><span data-stu-id="b16e4-111">You can download the complete Windows Presentation Foundation (WPF) project from [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) and then follow these steps.</span></span>

> [!TIP]
> <span data-ttu-id="b16e4-112">如果不想下载项目，可在本主题末尾处查看 MainWindow.xaml.cs 文件。</span><span class="sxs-lookup"><span data-stu-id="b16e4-112">If you don't want to download the project, you can review the MainWindow.xaml.cs file at the end of this topic instead.</span></span>

1. <span data-ttu-id="b16e4-113">从 .zip 文件中提取已下载的文件，然后启动 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="b16e4-113">Extract the files that you downloaded from the .zip file, and then start Visual Studio.</span></span>

2. <span data-ttu-id="b16e4-114">在菜单栏上，依次选择“文件” > “打开” > “项目/解决方案”。</span><span class="sxs-lookup"><span data-stu-id="b16e4-114">On the menu bar, choose **File** > **Open** > **Project/Solution**.</span></span>

3. <span data-ttu-id="b16e4-115">在“打开项目”对话框中，打开保存已下载的示例代码的文件夹，然后打开 AsyncFineTuningCS 的解决方案 (.sln) 文件。</span><span class="sxs-lookup"><span data-stu-id="b16e4-115">In the **Open Project** dialog box, open the folder that holds the sample code you downloaded, and then open the solution (.sln) file for AsyncFineTuningCS.</span></span>

4. <span data-ttu-id="b16e4-116">在“解决方案资源管理器”中，打开“ProcessTasksAsTheyFinish”项目的快捷菜单，选择“设为启动项目”。</span><span class="sxs-lookup"><span data-stu-id="b16e4-116">In **Solution Explorer**, open the shortcut menu for the **ProcessTasksAsTheyFinish** project, and then choose **Set as StartUp Project**.</span></span>

5. <span data-ttu-id="b16e4-117">选择 F5 键以运行此程序（或按 Ctrl+F5 键以运行此程序，而不对其进行调试）。</span><span class="sxs-lookup"><span data-stu-id="b16e4-117">Choose the **F5** key to run the program (or, press **Ctrl**+**F5** keys to run the program without debugging it).</span></span>

6. <span data-ttu-id="b16e4-118">多次运行此项目以验证并不总是以相同顺序显示已下载的长度。</span><span class="sxs-lookup"><span data-stu-id="b16e4-118">Run the project several times to verify that the downloaded lengths don't always appear in the same order.</span></span>

## <a name="create-the-program-yourself"></a><span data-ttu-id="b16e4-119">自行创建程序</span><span class="sxs-lookup"><span data-stu-id="b16e4-119">Create the program yourself</span></span>

<span data-ttu-id="b16e4-120">本示例对[在一个任务完成后取消剩余异步任务 (C#)](../../../../csharp/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md) 中开发的代码进行了补充，并使用了相同的 UI。</span><span class="sxs-lookup"><span data-stu-id="b16e4-120">This example adds to the code that’s developed in [Cancel Remaining Async Tasks after One Is Complete (C#)](../../../../csharp/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md), and it uses the same UI.</span></span>

<span data-ttu-id="b16e4-121">若要自行生成示例，请按[下载示例](../../../../csharp/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md#downloading-the-example)部分的说明逐步操作，但将“CancelAfterOneTask”设置为“启动项目”。</span><span class="sxs-lookup"><span data-stu-id="b16e4-121">To build the example yourself, step by step, follow the instructions in the [Downloading the Example](../../../../csharp/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md#downloading-the-example) section, but set **CancelAfterOneTask** as the startup project.</span></span> <span data-ttu-id="b16e4-122">将此主题中的更改添加到项目中的 `AccessTheWebAsync` 方法。</span><span class="sxs-lookup"><span data-stu-id="b16e4-122">Add the changes in this topic to the `AccessTheWebAsync` method in that project.</span></span> <span data-ttu-id="b16e4-123">这些更改标有星号。</span><span class="sxs-lookup"><span data-stu-id="b16e4-123">The changes are marked with asterisks.</span></span>

<span data-ttu-id="b16e4-124">**CancelAfterOneTask** 项目已包含一个查询，执行此查询时，将创建任务集合。</span><span class="sxs-lookup"><span data-stu-id="b16e4-124">The **CancelAfterOneTask** project already includes a query that, when executed, creates a collection of tasks.</span></span> <span data-ttu-id="b16e4-125">每次对以下代码中的 `ProcessURLAsync` 进行调用都会返回 <xref:System.Threading.Tasks.Task%601>，其中 `TResult` 是一个整数：</span><span class="sxs-lookup"><span data-stu-id="b16e4-125">Each call to `ProcessURLAsync` in the following code returns a <xref:System.Threading.Tasks.Task%601>, where `TResult` is an integer:</span></span>

```csharp
IEnumerable<Task<int>> downloadTasksQuery = from url in urlList select ProcessURL(url, client, ct);
```

<span data-ttu-id="b16e4-126">在项目的 MainWindow.xaml.cs 文件中，对 `AccessTheWebAsync` 方法进行以下更改。</span><span class="sxs-lookup"><span data-stu-id="b16e4-126">In the MainWindow.xaml.cs file of the project, make the following changes to the `AccessTheWebAsync` method.</span></span>

-   <span data-ttu-id="b16e4-127">通过应用 <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> 而非 <xref:System.Linq.Enumerable.ToArray%2A> 执行查询。</span><span class="sxs-lookup"><span data-stu-id="b16e4-127">Execute the query by applying <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> instead of <xref:System.Linq.Enumerable.ToArray%2A>.</span></span>

    ```csharp
    List<Task<int>> downloadTasks = downloadTasksQuery.ToList();
    ```

-   <span data-ttu-id="b16e4-128">添加 `while` 循环，针对集合中的每个任务执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="b16e4-128">Add a `while` loop that performs the following steps for each task in the collection:</span></span>

    1.  <span data-ttu-id="b16e4-129">等待调用 `WhenAny`，以标识集合中首个完成下载的任务。</span><span class="sxs-lookup"><span data-stu-id="b16e4-129">Awaits a call to `WhenAny` to identify the first task in the collection to finish its download.</span></span>

        ```csharp
        Task<int> firstFinishedTask = await Task.WhenAny(downloadTasks);
        ```

    2.  <span data-ttu-id="b16e4-130">从集合中移除任务。</span><span class="sxs-lookup"><span data-stu-id="b16e4-130">Removes that task from the collection.</span></span>

        ```csharp
        downloadTasks.Remove(firstFinishedTask);
        ```

    3.  <span data-ttu-id="b16e4-131">等待 `firstFinishedTask`，由对 `ProcessURLAsync` 的调用返回。</span><span class="sxs-lookup"><span data-stu-id="b16e4-131">Awaits `firstFinishedTask`, which is returned by a call to `ProcessURLAsync`.</span></span> <span data-ttu-id="b16e4-132">`firstFinishedTask` 变量是 <xref:System.Threading.Tasks.Task%601>，其中 `TReturn` 是整数。</span><span class="sxs-lookup"><span data-stu-id="b16e4-132">The `firstFinishedTask` variable is a <xref:System.Threading.Tasks.Task%601> where `TReturn` is an integer.</span></span> <span data-ttu-id="b16e4-133">任务已完成，但需等待它检索已下载网站的长度，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="b16e4-133">The task is already complete, but you await it to retrieve the length of the downloaded website, as the following example shows.</span></span>

        ```csharp
        int length = await firstFinishedTask;
        resultsTextBox.Text += $"\r\nLength of the download:  {length}";
        ```

<span data-ttu-id="b16e4-134">多次运行此程序以验证并不总是以相同顺序显示已下载的长度。</span><span class="sxs-lookup"><span data-stu-id="b16e4-134">Run the program several times to verify that the downloaded lengths don't always appear in the same order.</span></span>

> [!CAUTION]
> <span data-ttu-id="b16e4-135">如示例所示，可以在循环中使用 `WhenAny` 来解决涉及少量任务的问题。</span><span class="sxs-lookup"><span data-stu-id="b16e4-135">You can use `WhenAny` in a loop, as described in the example, to solve problems that involve a small number of tasks.</span></span> <span data-ttu-id="b16e4-136">但是，如果要处理大量任务，可以采用其他更高效的方法。</span><span class="sxs-lookup"><span data-stu-id="b16e4-136">However, other approaches are more efficient if you have a large number of tasks to process.</span></span> <span data-ttu-id="b16e4-137">有关详细信息和示例，请参阅 [Processing tasks as they complete](https://blogs.msdn.microsoft.com/pfxteam/2012/08/02/processing-tasks-as-they-complete/)（在任务完成时处理它们）。</span><span class="sxs-lookup"><span data-stu-id="b16e4-137">For more information and examples, see [Processing tasks as they complete](https://blogs.msdn.microsoft.com/pfxteam/2012/08/02/processing-tasks-as-they-complete/).</span></span>

## <a name="complete-example"></a><span data-ttu-id="b16e4-138">完整示例</span><span class="sxs-lookup"><span data-stu-id="b16e4-138">Complete example</span></span>

<span data-ttu-id="b16e4-139">下列代码是示例的 MainWindow.xaml.cs 文件的完整文本。</span><span class="sxs-lookup"><span data-stu-id="b16e4-139">The following code is the complete text of the MainWindow.xaml.cs file for the example.</span></span> <span data-ttu-id="b16e4-140">对添加到此示例的元素进行了星号标记。</span><span class="sxs-lookup"><span data-stu-id="b16e4-140">Asterisks mark the elements that were added for this example.</span></span> <span data-ttu-id="b16e4-141">另请注意，必须为 <xref:System.Net.Http> 添加引用。</span><span class="sxs-lookup"><span data-stu-id="b16e4-141">Also, take note that you must add a reference for <xref:System.Net.Http>.</span></span>

<span data-ttu-id="b16e4-142">可以从 [Async Sample:Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea)（异步示例：微调应用程序）下载这些项目。</span><span class="sxs-lookup"><span data-stu-id="b16e4-142">You can download the project from [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea).</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Windows;
using System.Windows.Controls;
using System.Windows.Data;
using System.Windows.Documents;
using System.Windows.Input;
using System.Windows.Media;
using System.Windows.Media.Imaging;
using System.Windows.Navigation;
using System.Windows.Shapes;

// Add a using directive and a reference for System.Net.Http.
using System.Net.Http;

// Add the following using directive.
using System.Threading;

namespace ProcessTasksAsTheyFinish
{
    public partial class MainWindow : Window
    {
        // Declare a System.Threading.CancellationTokenSource.
        CancellationTokenSource cts;

        public MainWindow()
        {
            InitializeComponent();
        }

        private async void startButton_Click(object sender, RoutedEventArgs e)
        {
            resultsTextBox.Clear();

            // Instantiate the CancellationTokenSource.
            cts = new CancellationTokenSource();

            try
            {
                await AccessTheWebAsync(cts.Token);
                resultsTextBox.Text += "\r\nDownloads complete.";
            }
            catch (OperationCanceledException)
            {
                resultsTextBox.Text += "\r\nDownloads canceled.\r\n";
            }
            catch (Exception)
            {
                resultsTextBox.Text += "\r\nDownloads failed.\r\n";
            }

            cts = null;
        }

        private void cancelButton_Click(object sender, RoutedEventArgs e)
        {
            if (cts != null)
            {
                cts.Cancel();
            }
        }

        async Task AccessTheWebAsync(CancellationToken ct)
        {
            HttpClient client = new HttpClient();

            // Make a list of web addresses.
            List<string> urlList = SetUpURLList();

            // ***Create a query that, when executed, returns a collection of tasks.
            IEnumerable<Task<int>> downloadTasksQuery =
                from url in urlList select ProcessURL(url, client, ct);

            // ***Use ToList to execute the query and start the tasks.
            List<Task<int>> downloadTasks = downloadTasksQuery.ToList();

            // ***Add a loop to process the tasks one at a time until none remain.
            while (downloadTasks.Count > 0)
            {
                    // Identify the first task that completes.
                    Task<int> firstFinishedTask = await Task.WhenAny(downloadTasks);

                    // ***Remove the selected task from the list so that you don't
                    // process it more than once.
                    downloadTasks.Remove(firstFinishedTask);

                    // Await the completed task.
                    int length = await firstFinishedTask;
                    resultsTextBox.Text += $"\r\nLength of the download:  {length}";
            }
        }

        private List<string> SetUpURLList()
        {
            List<string> urls = new List<string>
            {
                "https://msdn.microsoft.com",
                "https://msdn.microsoft.com/library/windows/apps/br211380.aspx",
                "https://msdn.microsoft.com/library/hh290136.aspx",
                "https://msdn.microsoft.com/library/dd470362.aspx",
                "https://msdn.microsoft.com/library/aa578028.aspx",
                "https://msdn.microsoft.com/library/ms404677.aspx",
                "https://msdn.microsoft.com/library/ff730837.aspx"
            };
            return urls;
        }

        async Task<int> ProcessURL(string url, HttpClient client, CancellationToken ct)
        {
            // GetAsync returns a Task<HttpResponseMessage>.
            HttpResponseMessage response = await client.GetAsync(url, ct);

            // Retrieve the website contents from the HttpResponseMessage.
            byte[] urlContents = await response.Content.ReadAsByteArrayAsync();

            return urlContents.Length;
        }
    }
}

// Sample Output:

// Length of the download:  226093
// Length of the download:  412588
// Length of the download:  175490
// Length of the download:  204890
// Length of the download:  158855
// Length of the download:  145790
// Length of the download:  44908
// Downloads complete.
```

## <a name="see-also"></a><span data-ttu-id="b16e4-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="b16e4-143">See also</span></span>

- <xref:System.Threading.Tasks.Task.WhenAny%2A>
- [<span data-ttu-id="b16e4-144">微调异步应用程序 (C#)</span><span class="sxs-lookup"><span data-stu-id="b16e4-144">Fine-Tuning Your Async Application (C#)</span></span>](../../../../csharp/programming-guide/concepts/async/fine-tuning-your-async-application.md)
- [<span data-ttu-id="b16e4-145">使用 Async 和 Await 的异步编程 (C#)</span><span class="sxs-lookup"><span data-stu-id="b16e4-145">Asynchronous Programming with async and await (C#)</span></span>](../../../../csharp/programming-guide/concepts/async/index.md)
- [<span data-ttu-id="b16e4-146">异步示例：微调应用程序</span><span class="sxs-lookup"><span data-stu-id="b16e4-146">Async Sample: Fine Tuning Your Application</span></span>](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea)