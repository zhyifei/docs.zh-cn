---
title: "使用 F # 的 Azure 队列存储入门"
description: "Azure 队列提供可靠、 异步消息传送应用程序组件之间。 云消息传送启用应用程序组件进行独立扩展。"
keywords: "visual f #、 f # 中，函数编程，.NET，.NET 核心，Azure"
author: sylvanc
ms.author: phcart
ms.date: 09/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 70dc554c-8f4d-42a7-8e2a-6438657d012a
ms.openlocfilehash: 50b2d69a1753add688aa14c3314a0ca2df9f03a4
ms.sourcegitcommit: 655fd4f78741967f80c409cef98347fdcf77857d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2018
---
# <a name="get-started-with-azure-queue-storage-using-f"></a><span data-ttu-id="547c1-105">使用 F # 的 Azure 队列存储入门</span><span class="sxs-lookup"><span data-stu-id="547c1-105">Get started with Azure Queue storage using F#</span></span> #

<span data-ttu-id="547c1-106">Azure 队列存储提供了云应用程序组件之间的消息传递。</span><span class="sxs-lookup"><span data-stu-id="547c1-106">Azure Queue storage provides cloud messaging between application components.</span></span> <span data-ttu-id="547c1-107">在设计时缩放的应用程序，应用程序组件之间是通常分离，以便它们可以独立地扩展。</span><span class="sxs-lookup"><span data-stu-id="547c1-107">In designing applications for scale, application components are often decoupled, so that they can scale independently.</span></span> <span data-ttu-id="547c1-108">队列存储提供了应用程序组件之间的通信的异步消息传送是否在云中、 在桌面上、 在本地服务器上，或在移动设备上运行。</span><span class="sxs-lookup"><span data-stu-id="547c1-108">Queue storage delivers asynchronous messaging for communication between application components, whether they are running in the cloud, on the desktop, on an on-premises server, or on a mobile device.</span></span> <span data-ttu-id="547c1-109">队列存储还支持管理异步任务以及构建过程工作流。</span><span class="sxs-lookup"><span data-stu-id="547c1-109">Queue storage also supports managing asynchronous tasks and building process work flows.</span></span>

### <a name="about-this-tutorial"></a><span data-ttu-id="547c1-110">关于本教程</span><span class="sxs-lookup"><span data-stu-id="547c1-110">About this tutorial</span></span>

<span data-ttu-id="547c1-111">本教程演示如何编写为使用 Azure 队列存储的一些常见任务的 F # 代码。</span><span class="sxs-lookup"><span data-stu-id="547c1-111">This tutorial shows how to write F# code for some common tasks using Azure Queue storage.</span></span> <span data-ttu-id="547c1-112">涉及的任务包括创建和删除队列和添加、 读取和删除队列消息。</span><span class="sxs-lookup"><span data-stu-id="547c1-112">Tasks covered include creating and deleting queues and adding, reading, and deleting queue messages.</span></span>

<span data-ttu-id="547c1-113">有关队列存储的概念概述，请参阅[队列存储.NET 指南](/azure/storage/storage-dotnet-how-to-use-queues)。</span><span class="sxs-lookup"><span data-stu-id="547c1-113">For a conceptual overview of queue storage, please see [the .NET guide for queue storage](/azure/storage/storage-dotnet-how-to-use-queues).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="547c1-114">系统必备</span><span class="sxs-lookup"><span data-stu-id="547c1-114">Prerequisites</span></span>

<span data-ttu-id="547c1-115">若要使用本指南，你必须首先[创建 Azure 存储帐户](/azure/storage/storage-create-storage-account)。</span><span class="sxs-lookup"><span data-stu-id="547c1-115">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account).</span></span>
<span data-ttu-id="547c1-116">此外需要为此帐户存储访问密钥。</span><span class="sxs-lookup"><span data-stu-id="547c1-116">You'll also need your storage access key for this account.</span></span>

## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="547c1-117">创建的 F # 脚本并开始 F # 交互</span><span class="sxs-lookup"><span data-stu-id="547c1-117">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="547c1-118">这篇文章中的示例可在 F # 应用程序或 F # 脚本。</span><span class="sxs-lookup"><span data-stu-id="547c1-118">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="547c1-119">若要创建的 F # 脚本，创建具有的文件`.fsx`扩展，例如`queues.fsx`，F # 开发环境中。</span><span class="sxs-lookup"><span data-stu-id="547c1-119">To create an F# script, create a file with the `.fsx` extension, for example `queues.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="547c1-120">接下来，使用[程序包管理器](package-management.md)如[Paket](https://fsprojects.github.io/Paket/)或[NuGet](https://www.nuget.org/)安装`WindowsAzure.Storage`包和引用`WindowsAzure.Storage.dll`在脚本中使用`#r`指令。</span><span class="sxs-lookup"><span data-stu-id="547c1-120">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` package and reference `WindowsAzure.Storage.dll` in your script using a `#r` directive.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="547c1-121">添加命名空间声明</span><span class="sxs-lookup"><span data-stu-id="547c1-121">Add namespace declarations</span></span>

<span data-ttu-id="547c1-122">添加以下`open`到顶部的语句`queues.fsx`文件：</span><span class="sxs-lookup"><span data-stu-id="547c1-122">Add the following `open` statements to the top of the `queues.fsx` file:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L1-L3)]

### <a name="get-your-connection-string"></a><span data-ttu-id="547c1-123">获取连接字符串</span><span class="sxs-lookup"><span data-stu-id="547c1-123">Get your connection string</span></span>

<span data-ttu-id="547c1-124">对于本教程，你将需要一个 Azure 存储连接字符串。</span><span class="sxs-lookup"><span data-stu-id="547c1-124">You'll need an Azure Storage connection string for this tutorial.</span></span> <span data-ttu-id="547c1-125">有关连接字符串的详细信息，请参阅[配置存储连接字符串](/azure/storage/storage-configure-connection-string)。</span><span class="sxs-lookup"><span data-stu-id="547c1-125">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

<span data-ttu-id="547c1-126">对于本教程中，您将在脚本中，如下输入你的连接字符串：</span><span class="sxs-lookup"><span data-stu-id="547c1-126">For the tutorial, you'll enter your connection string in your script, like this:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L9-L9)]

<span data-ttu-id="547c1-127">但是，这是**不建议**的实际项目。</span><span class="sxs-lookup"><span data-stu-id="547c1-127">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="547c1-128">你的存储帐户密钥是类似于你的存储帐户的根密码。</span><span class="sxs-lookup"><span data-stu-id="547c1-128">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="547c1-129">始终必须小心地保护你的存储帐户密钥。</span><span class="sxs-lookup"><span data-stu-id="547c1-129">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="547c1-130">避免将其分发给其他用户，硬编码，或将其保存在其他人可以访问的纯文本格式的文件。</span><span class="sxs-lookup"><span data-stu-id="547c1-130">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="547c1-131">你可以重新生成你使用 Azure 门户，如果你认为可能已泄露的密钥。</span><span class="sxs-lookup"><span data-stu-id="547c1-131">You can regenerate your key using the Azure Portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="547c1-132">为实际的应用程序，维护存储连接字符串的最佳方法是在配置文件中。</span><span class="sxs-lookup"><span data-stu-id="547c1-132">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="547c1-133">若要从配置文件中提取的连接字符串，您可以执行此操作：</span><span class="sxs-lookup"><span data-stu-id="547c1-133">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L11-L13)]

<span data-ttu-id="547c1-134">使用 Azure 配置管理器是可选的。</span><span class="sxs-lookup"><span data-stu-id="547c1-134">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="547c1-135">你还可以使用 API，如.NET Framework 的`ConfigurationManager`类型。</span><span class="sxs-lookup"><span data-stu-id="547c1-135">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="547c1-136">分析连接字符串</span><span class="sxs-lookup"><span data-stu-id="547c1-136">Parse the connection string</span></span>

<span data-ttu-id="547c1-137">若要分析的连接字符串，请使用：</span><span class="sxs-lookup"><span data-stu-id="547c1-137">To parse the connection string, use:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L19-L20)]

<span data-ttu-id="547c1-138">这将返回`CloudStorageAccount`。</span><span class="sxs-lookup"><span data-stu-id="547c1-138">This will return a `CloudStorageAccount`.</span></span>

### <a name="create-the-queue-service-client"></a><span data-ttu-id="547c1-139">创建队列服务客户端</span><span class="sxs-lookup"><span data-stu-id="547c1-139">Create the Queue service client</span></span>

<span data-ttu-id="547c1-140">`CloudQueueClient`类使你能够检索存储在队列存储中的队列。</span><span class="sxs-lookup"><span data-stu-id="547c1-140">The `CloudQueueClient` class enables you to retrieve queues stored in Queue storage.</span></span> <span data-ttu-id="547c1-141">下面是创建服务客户端的一种方法：</span><span class="sxs-lookup"><span data-stu-id="547c1-141">Here's one way to create the service client:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L26-L26)]

<span data-ttu-id="547c1-142">现在，你就可以编写代码，从读取数据并将数据写入队列存储了。</span><span class="sxs-lookup"><span data-stu-id="547c1-142">Now you are ready to write code that reads data from and writes data to Queue storage.</span></span>

## <a name="create-a-queue"></a><span data-ttu-id="547c1-143">创建队列</span><span class="sxs-lookup"><span data-stu-id="547c1-143">Create a queue</span></span>

<span data-ttu-id="547c1-144">此示例演示如何创建队列，如果它尚不存在：</span><span class="sxs-lookup"><span data-stu-id="547c1-144">This example shows how to create a queue if it doesn't already exist:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L32-L36)]

## <a name="insert-a-message-into-a-queue"></a><span data-ttu-id="547c1-145">队列中插入一条消息</span><span class="sxs-lookup"><span data-stu-id="547c1-145">Insert a message into a queue</span></span>

<span data-ttu-id="547c1-146">若要将消息插入现有队列，首先创建一个新`CloudQueueMessage`。</span><span class="sxs-lookup"><span data-stu-id="547c1-146">To insert a message into an existing queue, first create a new `CloudQueueMessage`.</span></span> <span data-ttu-id="547c1-147">接下来，调用`AddMessage`方法。</span><span class="sxs-lookup"><span data-stu-id="547c1-147">Next, call the `AddMessage` method.</span></span> <span data-ttu-id="547c1-148">A`CloudQueueMessage`可以创建从字符串 （utf-8 格式） 或`byte`数组，如下：</span><span class="sxs-lookup"><span data-stu-id="547c1-148">A `CloudQueueMessage` can be created from either a string (in UTF-8 format) or a `byte` array, like this:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L42-L44)]

## <a name="peek-at-the-next-message"></a><span data-ttu-id="547c1-149">扫视下一条消息</span><span class="sxs-lookup"><span data-stu-id="547c1-149">Peek at the next message</span></span>

<span data-ttu-id="547c1-150">你可以扫视队列前面的消息而不删除它从队列中，通过调用`PeekMessage`方法。</span><span class="sxs-lookup"><span data-stu-id="547c1-150">You can peek at the message in the front of a queue, without removing it from the queue, by calling the `PeekMessage` method.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L50-L52)]

## <a name="get-the-next-message-for-processing"></a><span data-ttu-id="547c1-151">获取下一条消息进行处理</span><span class="sxs-lookup"><span data-stu-id="547c1-151">Get the next message for processing</span></span>

<span data-ttu-id="547c1-152">你可以通过调用检索处理队列的靠前的消息`GetMessage`方法。</span><span class="sxs-lookup"><span data-stu-id="547c1-152">You can retrieve the message at the front of a queue for processing by calling the `GetMessage` method.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L58-L59)]

<span data-ttu-id="547c1-153">更高版本通过使用指示成功处理的消息`DeleteMessage`。</span><span class="sxs-lookup"><span data-stu-id="547c1-153">You later indicate successful processing of the message by using `DeleteMessage`.</span></span>

## <a name="change-the-contents-of-a-queued-message"></a><span data-ttu-id="547c1-154">更改已排队消息的内容</span><span class="sxs-lookup"><span data-stu-id="547c1-154">Change the contents of a queued message</span></span>

<span data-ttu-id="547c1-155">你可以更改检索到的消息中现有的队列中的内容。</span><span class="sxs-lookup"><span data-stu-id="547c1-155">You can change the contents of a retrieved message in-place in the queue.</span></span> <span data-ttu-id="547c1-156">如果消息表示工作任务，你可以使用此功能来更新该工作任务的状态。</span><span class="sxs-lookup"><span data-stu-id="547c1-156">If the message represents a work task, you could use this feature to update the status of the work task.</span></span> <span data-ttu-id="547c1-157">以下代码使用新内容更新队列消息，并将设置为再延长 60 秒的可见性超时。</span><span class="sxs-lookup"><span data-stu-id="547c1-157">The following code updates the queue message with new contents, and sets the visibility timeout to extend another 60 seconds.</span></span> <span data-ttu-id="547c1-158">这将保存与消息关联的工作的状态，并提供一分钟的时间来继续处理消息的客户端。</span><span class="sxs-lookup"><span data-stu-id="547c1-158">This saves the state of work associated with the message, and gives the client another minute to continue working on the message.</span></span> <span data-ttu-id="547c1-159">无法使用此方法跟踪对队列消息的多步骤工作流，而无需从头开始如果一个处理步骤因硬件或软件故障而失败。</span><span class="sxs-lookup"><span data-stu-id="547c1-159">You could use this technique to track multi-step workflows on queue messages, without having to start over from the beginning if a processing step fails due to hardware or software failure.</span></span> <span data-ttu-id="547c1-160">通常，你还可以保留重试计数，并且如果多个几次重试消息，你将删除它。</span><span class="sxs-lookup"><span data-stu-id="547c1-160">Typically, you would keep a retry count as well, and if the message is retried more than some number of times, you would delete it.</span></span> <span data-ttu-id="547c1-161">这可避免每次处理它时将触发应用程序错误的消息。</span><span class="sxs-lookup"><span data-stu-id="547c1-161">This protects against a message that triggers an application error each time it is processed.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L65-L69)]

## <a name="de-queue-the-next-message"></a><span data-ttu-id="547c1-162">取消下一条消息的排队</span><span class="sxs-lookup"><span data-stu-id="547c1-162">De-queue the next message</span></span>

<span data-ttu-id="547c1-163">你的代码取消排队的消息从队列中两个步骤。</span><span class="sxs-lookup"><span data-stu-id="547c1-163">Your code de-queues a message from a queue in two steps.</span></span> <span data-ttu-id="547c1-164">当调用`GetMessage`，你将获得队列中下一条消息。</span><span class="sxs-lookup"><span data-stu-id="547c1-164">When you call `GetMessage`, you get the next message in a queue.</span></span> <span data-ttu-id="547c1-165">从返回的消息`GetMessage`变得对从此队列读取消息的任何其他代码不可见。</span><span class="sxs-lookup"><span data-stu-id="547c1-165">A message returned from `GetMessage` becomes invisible to any other code reading messages from this queue.</span></span> <span data-ttu-id="547c1-166">默认情况下，此消息将在 30 秒内持续不可见。</span><span class="sxs-lookup"><span data-stu-id="547c1-166">By default, this message stays invisible for 30 seconds.</span></span> <span data-ttu-id="547c1-167">若要完成从队列中删除消息，还必须调用`DeleteMessage`。</span><span class="sxs-lookup"><span data-stu-id="547c1-167">To finish removing the message from the queue, you must also call `DeleteMessage`.</span></span> <span data-ttu-id="547c1-168">删除消息的此两步过程可确保你的代码无法处理因硬件或软件故障而一条消息，如果你的代码的另一个实例可以获取同一消息并重试。</span><span class="sxs-lookup"><span data-stu-id="547c1-168">This two-step process of removing a message assures that if your code fails to process a message due to hardware or software failure, another instance of your code can get the same message and try again.</span></span> <span data-ttu-id="547c1-169">你的代码调用`DeleteMessage`处理消息后。</span><span class="sxs-lookup"><span data-stu-id="547c1-169">Your code calls `DeleteMessage` right after the message has been processed.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L75-L76)]

## <a name="use-async-workflows-with-common-queue-storage-apis"></a><span data-ttu-id="547c1-170">异步工作流使用公用队列存储 Api</span><span class="sxs-lookup"><span data-stu-id="547c1-170">Use Async workflows with common Queue storage APIs</span></span>

<span data-ttu-id="547c1-171">此示例演示如何通过公用队列存储 Api 使用的异步工作流。</span><span class="sxs-lookup"><span data-stu-id="547c1-171">This example shows how to use an async workflow with common Queue storage APIs.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L82-L91)]

## <a name="additional-options-for-de-queuing-messages"></a><span data-ttu-id="547c1-172">消息的取消排队的其他选项</span><span class="sxs-lookup"><span data-stu-id="547c1-172">Additional options for de-queuing messages</span></span>

<span data-ttu-id="547c1-173">有两种方法可以自定义队列的消息检索。</span><span class="sxs-lookup"><span data-stu-id="547c1-173">There are two ways you can customize message retrieval from a queue.</span></span>
<span data-ttu-id="547c1-174">首先，你可以获取一批消息 （最多 32 条)。</span><span class="sxs-lookup"><span data-stu-id="547c1-174">First, you can get a batch of messages (up to 32).</span></span> <span data-ttu-id="547c1-175">其次，你可以设置更长或更短的不可见性超时，允许你的代码更多或更少的时间来彻底处理每条消息。</span><span class="sxs-lookup"><span data-stu-id="547c1-175">Second, you can set a longer or shorter invisibility timeout, allowing your code more or less time to fully process each message.</span></span> <span data-ttu-id="547c1-176">下面的代码示例使用`GetMessages`获取 20 之一中的消息调用，然后再处理每条消息。</span><span class="sxs-lookup"><span data-stu-id="547c1-176">The following code example uses `GetMessages` to get 20 messages in one call and then processes each message.</span></span> <span data-ttu-id="547c1-177">它还将不可见性超时设置为 5 分钟时间，每条消息。</span><span class="sxs-lookup"><span data-stu-id="547c1-177">It also sets the invisibility timeout to five minutes for each message.</span></span> <span data-ttu-id="547c1-178">请注意，5 分钟一次启动的所有消息因此 5 分钟后传递到在调用`GetMessages`，尚未删除的任何消息将再次变得可见。</span><span class="sxs-lookup"><span data-stu-id="547c1-178">Note that the 5 minutes starts for all messages at the same time, so after 5 minutes have passed since the call to `GetMessages`, any messages which have not been deleted will become visible again.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L97-L99)]

## <a name="get-the-queue-length"></a><span data-ttu-id="547c1-179">获取队列长度</span><span class="sxs-lookup"><span data-stu-id="547c1-179">Get the queue length</span></span>

<span data-ttu-id="547c1-180">你可以获取队列中的估计值的消息数。</span><span class="sxs-lookup"><span data-stu-id="547c1-180">You can get an estimate of the number of messages in a queue.</span></span> <span data-ttu-id="547c1-181">`FetchAttributes`方法要求队列服务检索队列属性，包括消息计数。</span><span class="sxs-lookup"><span data-stu-id="547c1-181">The `FetchAttributes` method asks the Queue service to retrieve the queue attributes, including the message count.</span></span> <span data-ttu-id="547c1-182">`ApproximateMessageCount`属性返回的最后一个值，通过检索`FetchAttributes`方法，而不会调用队列服务。</span><span class="sxs-lookup"><span data-stu-id="547c1-182">The `ApproximateMessageCount` property returns the last value retrieved by the `FetchAttributes` method, without calling the Queue service.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L105-L106)]

## <a name="delete-a-queue"></a><span data-ttu-id="547c1-183">删除队列</span><span class="sxs-lookup"><span data-stu-id="547c1-183">Delete a queue</span></span>

<span data-ttu-id="547c1-184">若要删除队列及其包含的所有消息，调用`Delete`对队列对象的方法。</span><span class="sxs-lookup"><span data-stu-id="547c1-184">To delete a queue and all the messages contained in it, call the `Delete` method on the queue object.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L112-L113)]

## <a name="next-steps"></a><span data-ttu-id="547c1-185">后续步骤</span><span class="sxs-lookup"><span data-stu-id="547c1-185">Next steps</span></span>

<span data-ttu-id="547c1-186">现在，你已了解队列存储的基础知识，单击下面的链接以了解更复杂的存储任务。</span><span class="sxs-lookup"><span data-stu-id="547c1-186">Now that you've learned the basics of Queue storage, follow these links to learn about more complex storage tasks.</span></span>

- [<span data-ttu-id="547c1-187">用于.NET 的 azure 存储 Api</span><span class="sxs-lookup"><span data-stu-id="547c1-187">Azure Storage APIs for .NET</span></span>](/dotnet/api/overview/azure/storage)
- [<span data-ttu-id="547c1-188">Azure 存储类型提供程序</span><span class="sxs-lookup"><span data-stu-id="547c1-188">Azure Storage Type Provider</span></span>](https://github.com/fsprojects/AzureStorageTypeProvider)
- [<span data-ttu-id="547c1-189">Azure 存储团队博客</span><span class="sxs-lookup"><span data-stu-id="547c1-189">Azure Storage Team Blog</span></span>](https://blogs.msdn.microsoft.com/windowsazurestorage/)
- [<span data-ttu-id="547c1-190">配置 Azure 存储连接字符串</span><span class="sxs-lookup"><span data-stu-id="547c1-190">Configure Azure Storage connection strings</span></span>](/azure/storage/common/storage-configure-connection-string)
- [<span data-ttu-id="547c1-191">Azure 存储服务 REST API 参考</span><span class="sxs-lookup"><span data-stu-id="547c1-191">Azure Storage Services REST API Reference</span></span>](/rest/api/storageservices/Azure-Storage-Services-REST-API-Reference)
