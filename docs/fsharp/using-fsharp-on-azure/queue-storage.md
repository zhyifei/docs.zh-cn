---
title: 使用 F# Azure 队列存储入门
description: Azure 队列提供可靠、 异步消息传送应用程序组件之间。 云消息传送使应用程序组件可单独缩放。
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: 14bbc657f965fc262d2a83b1fdf982fe5e75d55e
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "33569408"
---
# <a name="get-started-with-azure-queue-storage-using-f"></a><span data-ttu-id="12b51-104">使用 F# Azure 队列存储入门</span><span class="sxs-lookup"><span data-stu-id="12b51-104">Get started with Azure Queue storage using F#</span></span> #

<span data-ttu-id="12b51-105">Azure 队列存储提供了云应用程序组件之间的消息传送。</span><span class="sxs-lookup"><span data-stu-id="12b51-105">Azure Queue storage provides cloud messaging between application components.</span></span> <span data-ttu-id="12b51-106">在设计时缩放的应用程序，应用程序组件通常被分离，以便它们可以独立缩放。</span><span class="sxs-lookup"><span data-stu-id="12b51-106">In designing applications for scale, application components are often decoupled, so that they can scale independently.</span></span> <span data-ttu-id="12b51-107">队列存储可实现异步消息传送应用程序组件之间的通信是否在云中、 在桌面上、 在本地服务器上，或在移动设备上运行。</span><span class="sxs-lookup"><span data-stu-id="12b51-107">Queue storage delivers asynchronous messaging for communication between application components, whether they are running in the cloud, on the desktop, on an on-premises server, or on a mobile device.</span></span> <span data-ttu-id="12b51-108">队列存储还支持管理异步任务以及构建过程工作流。</span><span class="sxs-lookup"><span data-stu-id="12b51-108">Queue storage also supports managing asynchronous tasks and building process work flows.</span></span>

### <a name="about-this-tutorial"></a><span data-ttu-id="12b51-109">有关本教程</span><span class="sxs-lookup"><span data-stu-id="12b51-109">About this tutorial</span></span>

<span data-ttu-id="12b51-110">本教程演示如何编写F#使用 Azure 队列存储一些常见任务的代码。</span><span class="sxs-lookup"><span data-stu-id="12b51-110">This tutorial shows how to write F# code for some common tasks using Azure Queue storage.</span></span> <span data-ttu-id="12b51-111">涉及的任务包括创建和删除队列以及添加、 读取和删除队列消息。</span><span class="sxs-lookup"><span data-stu-id="12b51-111">Tasks covered include creating and deleting queues and adding, reading, and deleting queue messages.</span></span>

<span data-ttu-id="12b51-112">有关队列存储的概念性概述，请参阅[队列存储.NET 指南](/azure/storage/storage-dotnet-how-to-use-queues)。</span><span class="sxs-lookup"><span data-stu-id="12b51-112">For a conceptual overview of queue storage, please see [the .NET guide for queue storage](/azure/storage/storage-dotnet-how-to-use-queues).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="12b51-113">系统必备</span><span class="sxs-lookup"><span data-stu-id="12b51-113">Prerequisites</span></span>

<span data-ttu-id="12b51-114">若要使用本指南，您必须首先[创建 Azure 存储帐户](/azure/storage/storage-create-storage-account)。</span><span class="sxs-lookup"><span data-stu-id="12b51-114">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account).</span></span>
<span data-ttu-id="12b51-115">此外需要为此帐户存储访问密钥。</span><span class="sxs-lookup"><span data-stu-id="12b51-115">You'll also need your storage access key for this account.</span></span>

## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="12b51-116">创建 F# 脚本，并开始将 F# Interactive</span><span class="sxs-lookup"><span data-stu-id="12b51-116">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="12b51-117">这篇文章中的示例可以在 F# 应用程序或 F# 脚本中使用。</span><span class="sxs-lookup"><span data-stu-id="12b51-117">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="12b51-118">若要创建 F# 脚本，创建的文件`.fsx`扩展，例如`queues.fsx`，在 F# 开发环境中。</span><span class="sxs-lookup"><span data-stu-id="12b51-118">To create an F# script, create a file with the `.fsx` extension, for example `queues.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="12b51-119">接下来，使用[程序包管理器](package-management.md)如[paket 依存](https://fsprojects.github.io/Paket/)或[NuGet](https://www.nuget.org/)安装`WindowsAzure.Storage`程序包和引用`WindowsAzure.Storage.dll`使用在脚本中`#r`指令。</span><span class="sxs-lookup"><span data-stu-id="12b51-119">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` package and reference `WindowsAzure.Storage.dll` in your script using a `#r` directive.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="12b51-120">添加命名空间声明</span><span class="sxs-lookup"><span data-stu-id="12b51-120">Add namespace declarations</span></span>

<span data-ttu-id="12b51-121">添加以下`open`顶部的语句`queues.fsx`文件：</span><span class="sxs-lookup"><span data-stu-id="12b51-121">Add the following `open` statements to the top of the `queues.fsx` file:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L1-L3)]

### <a name="get-your-connection-string"></a><span data-ttu-id="12b51-122">获取连接字符串</span><span class="sxs-lookup"><span data-stu-id="12b51-122">Get your connection string</span></span>

<span data-ttu-id="12b51-123">对于本教程需要 Azure 存储连接字符串。</span><span class="sxs-lookup"><span data-stu-id="12b51-123">You'll need an Azure Storage connection string for this tutorial.</span></span> <span data-ttu-id="12b51-124">有关连接字符串的详细信息，请参阅[配置存储连接字符串](/azure/storage/storage-configure-connection-string)。</span><span class="sxs-lookup"><span data-stu-id="12b51-124">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

<span data-ttu-id="12b51-125">本教程中，将在脚本中，此类输入你的连接字符串：</span><span class="sxs-lookup"><span data-stu-id="12b51-125">For the tutorial, you'll enter your connection string in your script, like this:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L9-L9)]

<span data-ttu-id="12b51-126">但是，这是**不建议这样做**为实际项目。</span><span class="sxs-lookup"><span data-stu-id="12b51-126">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="12b51-127">你的存储帐户密钥是类似于你的存储帐户的根密码。</span><span class="sxs-lookup"><span data-stu-id="12b51-127">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="12b51-128">始终要小心保护存储帐户密钥。</span><span class="sxs-lookup"><span data-stu-id="12b51-128">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="12b51-129">避免将其分发给其他用户，硬编码，或将其保存在其他人可以访问的纯文本格式的文件。</span><span class="sxs-lookup"><span data-stu-id="12b51-129">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="12b51-130">您可以重新生成你使用 Azure 门户，如果你认为可能已泄露的密钥。</span><span class="sxs-lookup"><span data-stu-id="12b51-130">You can regenerate your key using the Azure Portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="12b51-131">为实际的应用程序，维护存储连接字符串的最佳方法是在配置文件中。</span><span class="sxs-lookup"><span data-stu-id="12b51-131">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="12b51-132">若要从配置文件中提取的连接字符串，可以执行此操作：</span><span class="sxs-lookup"><span data-stu-id="12b51-132">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L11-L13)]

<span data-ttu-id="12b51-133">使用 Azure 配置管理器是可选的。</span><span class="sxs-lookup"><span data-stu-id="12b51-133">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="12b51-134">此外可以使用诸如.NET Framework 的 API`ConfigurationManager`类型。</span><span class="sxs-lookup"><span data-stu-id="12b51-134">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="12b51-135">分析连接字符串</span><span class="sxs-lookup"><span data-stu-id="12b51-135">Parse the connection string</span></span>

<span data-ttu-id="12b51-136">若要分析的连接字符串，请使用：</span><span class="sxs-lookup"><span data-stu-id="12b51-136">To parse the connection string, use:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L19-L20)]

<span data-ttu-id="12b51-137">这将返回`CloudStorageAccount`。</span><span class="sxs-lookup"><span data-stu-id="12b51-137">This will return a `CloudStorageAccount`.</span></span>

### <a name="create-the-queue-service-client"></a><span data-ttu-id="12b51-138">创建队列服务客户端</span><span class="sxs-lookup"><span data-stu-id="12b51-138">Create the Queue service client</span></span>

<span data-ttu-id="12b51-139">`CloudQueueClient`类使您能够检索存储在队列中的队列存储。</span><span class="sxs-lookup"><span data-stu-id="12b51-139">The `CloudQueueClient` class enables you to retrieve queues stored in Queue storage.</span></span> <span data-ttu-id="12b51-140">下面是创建服务客户端的一种方法：</span><span class="sxs-lookup"><span data-stu-id="12b51-140">Here's one way to create the service client:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L26-L26)]

<span data-ttu-id="12b51-141">现在已准备好编写代码，读取数据并将数据写入到队列存储。</span><span class="sxs-lookup"><span data-stu-id="12b51-141">Now you are ready to write code that reads data from and writes data to Queue storage.</span></span>

## <a name="create-a-queue"></a><span data-ttu-id="12b51-142">创建队列</span><span class="sxs-lookup"><span data-stu-id="12b51-142">Create a queue</span></span>

<span data-ttu-id="12b51-143">此示例演示如何创建队列，如果它尚不存在：</span><span class="sxs-lookup"><span data-stu-id="12b51-143">This example shows how to create a queue if it doesn't already exist:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L32-L36)]

## <a name="insert-a-message-into-a-queue"></a><span data-ttu-id="12b51-144">队列中插入一条消息</span><span class="sxs-lookup"><span data-stu-id="12b51-144">Insert a message into a queue</span></span>

<span data-ttu-id="12b51-145">若要将消息插入现有队列，先创建一个新`CloudQueueMessage`。</span><span class="sxs-lookup"><span data-stu-id="12b51-145">To insert a message into an existing queue, first create a new `CloudQueueMessage`.</span></span> <span data-ttu-id="12b51-146">接下来，调用`AddMessage`方法。</span><span class="sxs-lookup"><span data-stu-id="12b51-146">Next, call the `AddMessage` method.</span></span> <span data-ttu-id="12b51-147">一个`CloudQueueMessage`可以创建从字符串 （utf-8 格式） 或`byte`数组，如下：</span><span class="sxs-lookup"><span data-stu-id="12b51-147">A `CloudQueueMessage` can be created from either a string (in UTF-8 format) or a `byte` array, like this:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L42-L44)]

## <a name="peek-at-the-next-message"></a><span data-ttu-id="12b51-148">扫视下一条消息</span><span class="sxs-lookup"><span data-stu-id="12b51-148">Peek at the next message</span></span>

<span data-ttu-id="12b51-149">可以扫视队列前面的消息，但不从队列中移除它通过调用`PeekMessage`方法。</span><span class="sxs-lookup"><span data-stu-id="12b51-149">You can peek at the message in the front of a queue, without removing it from the queue, by calling the `PeekMessage` method.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L50-L52)]

## <a name="get-the-next-message-for-processing"></a><span data-ttu-id="12b51-150">获取下一条消息的处理</span><span class="sxs-lookup"><span data-stu-id="12b51-150">Get the next message for processing</span></span>

<span data-ttu-id="12b51-151">可以通过调用来检索消息的处理队列的前部`GetMessage`方法。</span><span class="sxs-lookup"><span data-stu-id="12b51-151">You can retrieve the message at the front of a queue for processing by calling the `GetMessage` method.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L58-L59)]

<span data-ttu-id="12b51-152">更高版本通过使用指示成功处理了消息的`DeleteMessage`。</span><span class="sxs-lookup"><span data-stu-id="12b51-152">You later indicate successful processing of the message by using `DeleteMessage`.</span></span>

## <a name="change-the-contents-of-a-queued-message"></a><span data-ttu-id="12b51-153">更改已排队消息的内容</span><span class="sxs-lookup"><span data-stu-id="12b51-153">Change the contents of a queued message</span></span>

<span data-ttu-id="12b51-154">你可以检索的消息中现有的队列中的内容。</span><span class="sxs-lookup"><span data-stu-id="12b51-154">You can change the contents of a retrieved message in-place in the queue.</span></span> <span data-ttu-id="12b51-155">如果消息表示工作任务，可以使用此功能来更新该工作任务的状态。</span><span class="sxs-lookup"><span data-stu-id="12b51-155">If the message represents a work task, you could use this feature to update the status of the work task.</span></span> <span data-ttu-id="12b51-156">以下代码使用新内容更新队列消息，并设置可见性超时延长 60 秒。</span><span class="sxs-lookup"><span data-stu-id="12b51-156">The following code updates the queue message with new contents, and sets the visibility timeout to extend another 60 seconds.</span></span> <span data-ttu-id="12b51-157">这会保存与消息关联的工作状态并为客户端提供了一分钟的时间来继续处理该消息。</span><span class="sxs-lookup"><span data-stu-id="12b51-157">This saves the state of work associated with the message, and gives the client another minute to continue working on the message.</span></span> <span data-ttu-id="12b51-158">可以使用此方法在队列消息中，跟踪多步骤工作流，而无需从头开始，如果一个处理步骤因硬件或软件故障而失败。</span><span class="sxs-lookup"><span data-stu-id="12b51-158">You could use this technique to track multi-step workflows on queue messages, without having to start over from the beginning if a processing step fails due to hardware or software failure.</span></span> <span data-ttu-id="12b51-159">通常，你还可以保留重试计数，并且如果消息重试次数超过几次，则会将其删除。</span><span class="sxs-lookup"><span data-stu-id="12b51-159">Typically, you would keep a retry count as well, and if the message is retried more than some number of times, you would delete it.</span></span> <span data-ttu-id="12b51-160">这可避免每次处理它时将触发应用程序错误的消息。</span><span class="sxs-lookup"><span data-stu-id="12b51-160">This protects against a message that triggers an application error each time it is processed.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L65-L69)]

## <a name="de-queue-the-next-message"></a><span data-ttu-id="12b51-161">取消下一条消息的排队</span><span class="sxs-lookup"><span data-stu-id="12b51-161">De-queue the next message</span></span>

<span data-ttu-id="12b51-162">你的代码来取消队列的消息从队列中两个步骤。</span><span class="sxs-lookup"><span data-stu-id="12b51-162">Your code de-queues a message from a queue in two steps.</span></span> <span data-ttu-id="12b51-163">当您调用`GetMessage`，您将获得队列中下一条消息。</span><span class="sxs-lookup"><span data-stu-id="12b51-163">When you call `GetMessage`, you get the next message in a queue.</span></span> <span data-ttu-id="12b51-164">从返回的消息`GetMessage`变得对从此队列读取消息的任何其他代码不可见。</span><span class="sxs-lookup"><span data-stu-id="12b51-164">A message returned from `GetMessage` becomes invisible to any other code reading messages from this queue.</span></span> <span data-ttu-id="12b51-165">默认情况下，此消息将保持不可见 30 秒。</span><span class="sxs-lookup"><span data-stu-id="12b51-165">By default, this message stays invisible for 30 seconds.</span></span> <span data-ttu-id="12b51-166">若要完成从队列中删除消息，还必须调用`DeleteMessage`。</span><span class="sxs-lookup"><span data-stu-id="12b51-166">To finish removing the message from the queue, you must also call `DeleteMessage`.</span></span> <span data-ttu-id="12b51-167">删除消息的此两步过程可确保你的代码无法处理消息，因为硬件或软件故障，如果你的代码的另一个实例可以获取同一消息并重试。</span><span class="sxs-lookup"><span data-stu-id="12b51-167">This two-step process of removing a message assures that if your code fails to process a message due to hardware or software failure, another instance of your code can get the same message and try again.</span></span> <span data-ttu-id="12b51-168">你的代码调用`DeleteMessage`处理消息后。</span><span class="sxs-lookup"><span data-stu-id="12b51-168">Your code calls `DeleteMessage` right after the message has been processed.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L75-L76)]

## <a name="use-async-workflows-with-common-queue-storage-apis"></a><span data-ttu-id="12b51-169">使用具有公用队列存储 Api 的异步工作流</span><span class="sxs-lookup"><span data-stu-id="12b51-169">Use Async workflows with common Queue storage APIs</span></span>

<span data-ttu-id="12b51-170">此示例演示如何使用公用队列存储 Api 的异步工作流。</span><span class="sxs-lookup"><span data-stu-id="12b51-170">This example shows how to use an async workflow with common Queue storage APIs.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L82-L91)]

## <a name="additional-options-for-de-queuing-messages"></a><span data-ttu-id="12b51-171">其他方法取消排队消息</span><span class="sxs-lookup"><span data-stu-id="12b51-171">Additional options for de-queuing messages</span></span>

<span data-ttu-id="12b51-172">有两种方法可以自定义队列中的消息检索。</span><span class="sxs-lookup"><span data-stu-id="12b51-172">There are two ways you can customize message retrieval from a queue.</span></span>
<span data-ttu-id="12b51-173">首先，您可以获取一批消息 （最多 32)。</span><span class="sxs-lookup"><span data-stu-id="12b51-173">First, you can get a batch of messages (up to 32).</span></span> <span data-ttu-id="12b51-174">其次，您可以设置更长或更短的不可见超时，从而允许代码使用更多或更少的时间来彻底处理每条消息。</span><span class="sxs-lookup"><span data-stu-id="12b51-174">Second, you can set a longer or shorter invisibility timeout, allowing your code more or less time to fully process each message.</span></span> <span data-ttu-id="12b51-175">下面的代码示例使用`GetMessages`获取 20 中其中一个的消息调用，然后再处理每条消息。</span><span class="sxs-lookup"><span data-stu-id="12b51-175">The following code example uses `GetMessages` to get 20 messages in one call and then processes each message.</span></span> <span data-ttu-id="12b51-176">它还设置为 5 分钟内为每个消息的不可见超时时间。</span><span class="sxs-lookup"><span data-stu-id="12b51-176">It also sets the invisibility timeout to five minutes for each message.</span></span> <span data-ttu-id="12b51-177">请注意，对于所有消息在 5 分钟内开始在同一时间，因此 5 分钟后传递自调用`GetMessages`，尚未删除的任何消息将再次变得可见。</span><span class="sxs-lookup"><span data-stu-id="12b51-177">Note that the 5 minutes starts for all messages at the same time, so after 5 minutes have passed since the call to `GetMessages`, any messages which have not been deleted will become visible again.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L97-L99)]

## <a name="get-the-queue-length"></a><span data-ttu-id="12b51-178">获取队列长度</span><span class="sxs-lookup"><span data-stu-id="12b51-178">Get the queue length</span></span>

<span data-ttu-id="12b51-179">您可以获得队列中的消息数的估计值。</span><span class="sxs-lookup"><span data-stu-id="12b51-179">You can get an estimate of the number of messages in a queue.</span></span> <span data-ttu-id="12b51-180">`FetchAttributes`方法要求队列服务检索队列属性，包括消息计数。</span><span class="sxs-lookup"><span data-stu-id="12b51-180">The `FetchAttributes` method asks the Queue service to retrieve the queue attributes, including the message count.</span></span> <span data-ttu-id="12b51-181">`ApproximateMessageCount`属性返回检索到的最后一个值`FetchAttributes`方法，而不会调用队列服务。</span><span class="sxs-lookup"><span data-stu-id="12b51-181">The `ApproximateMessageCount` property returns the last value retrieved by the `FetchAttributes` method, without calling the Queue service.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L105-L106)]

## <a name="delete-a-queue"></a><span data-ttu-id="12b51-182">删除队列</span><span class="sxs-lookup"><span data-stu-id="12b51-182">Delete a queue</span></span>

<span data-ttu-id="12b51-183">若要删除队列及其包含的所有消息，调用`Delete`对队列对象的方法。</span><span class="sxs-lookup"><span data-stu-id="12b51-183">To delete a queue and all the messages contained in it, call the `Delete` method on the queue object.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L112-L113)]

## <a name="next-steps"></a><span data-ttu-id="12b51-184">后续步骤</span><span class="sxs-lookup"><span data-stu-id="12b51-184">Next steps</span></span>

<span data-ttu-id="12b51-185">现在，你已了解队列存储的基础知识，单击下面的链接可了解更复杂的存储任务。</span><span class="sxs-lookup"><span data-stu-id="12b51-185">Now that you've learned the basics of Queue storage, follow these links to learn about more complex storage tasks.</span></span>

- [<span data-ttu-id="12b51-186">用于.NET 的 azure 存储 Api</span><span class="sxs-lookup"><span data-stu-id="12b51-186">Azure Storage APIs for .NET</span></span>](/dotnet/api/overview/azure/storage)
- [<span data-ttu-id="12b51-187">Azure 存储类型提供程序</span><span class="sxs-lookup"><span data-stu-id="12b51-187">Azure Storage Type Provider</span></span>](https://github.com/fsprojects/AzureStorageTypeProvider)
- [<span data-ttu-id="12b51-188">Azure 存储团队博客</span><span class="sxs-lookup"><span data-stu-id="12b51-188">Azure Storage Team Blog</span></span>](https://blogs.msdn.microsoft.com/windowsazurestorage/)
- [<span data-ttu-id="12b51-189">配置 Azure 存储连接字符串</span><span class="sxs-lookup"><span data-stu-id="12b51-189">Configure Azure Storage connection strings</span></span>](/azure/storage/common/storage-configure-connection-string)
- [<span data-ttu-id="12b51-190">Azure 存储服务 REST API 参考</span><span class="sxs-lookup"><span data-stu-id="12b51-190">Azure Storage Services REST API Reference</span></span>](/rest/api/storageservices/Azure-Storage-Services-REST-API-Reference)
