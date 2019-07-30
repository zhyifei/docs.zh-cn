---
title: 通过 F# 实现 Azure 队列存储入门
description: Azure 队列在应用程序组件之间提供可靠的异步消息传送。 通过云消息传递, 你的应用程序组件可以独立缩放。
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: 65af98fb88e91d709eb0e35907cbc2dc097634d0
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630482"
---
# <a name="get-started-with-azure-queue-storage-using-f"></a><span data-ttu-id="f84bb-104">使用 F 开始使用 Azure 队列存储\#</span><span class="sxs-lookup"><span data-stu-id="f84bb-104">Get started with Azure Queue storage using F\#</span></span>

<span data-ttu-id="f84bb-105">Azure 队列存储在应用程序组件之间提供云消息传送。</span><span class="sxs-lookup"><span data-stu-id="f84bb-105">Azure Queue storage provides cloud messaging between application components.</span></span> <span data-ttu-id="f84bb-106">在设计规模应用程序时, 应用程序组件通常是分离的, 以便它们可以独立缩放。</span><span class="sxs-lookup"><span data-stu-id="f84bb-106">In designing applications for scale, application components are often decoupled, so that they can scale independently.</span></span> <span data-ttu-id="f84bb-107">队列存储提供了异步消息传送, 以便在应用程序组件之间进行通信, 无论它们是在云中、在桌面上、在本地服务器上运行还是在移动设备上运行。</span><span class="sxs-lookup"><span data-stu-id="f84bb-107">Queue storage delivers asynchronous messaging for communication between application components, whether they are running in the cloud, on the desktop, on an on-premises server, or on a mobile device.</span></span> <span data-ttu-id="f84bb-108">队列存储还支持管理异步任务以及构建过程工作流。</span><span class="sxs-lookup"><span data-stu-id="f84bb-108">Queue storage also supports managing asynchronous tasks and building process work flows.</span></span>

### <a name="about-this-tutorial"></a><span data-ttu-id="f84bb-109">关于本教程</span><span class="sxs-lookup"><span data-stu-id="f84bb-109">About this tutorial</span></span>

<span data-ttu-id="f84bb-110">本教程演示如何使用 Azure F#队列存储为某些常见任务编写代码。</span><span class="sxs-lookup"><span data-stu-id="f84bb-110">This tutorial shows how to write F# code for some common tasks using Azure Queue storage.</span></span> <span data-ttu-id="f84bb-111">涉及的任务包括创建和删除队列、添加、读取和删除队列消息。</span><span class="sxs-lookup"><span data-stu-id="f84bb-111">Tasks covered include creating and deleting queues and adding, reading, and deleting queue messages.</span></span>

<span data-ttu-id="f84bb-112">有关队列存储的概念性概述, 请参阅[队列存储的 .net 指南](/azure/storage/storage-dotnet-how-to-use-queues)。</span><span class="sxs-lookup"><span data-stu-id="f84bb-112">For a conceptual overview of queue storage, please see [the .NET guide for queue storage](/azure/storage/storage-dotnet-how-to-use-queues).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f84bb-113">系统必备</span><span class="sxs-lookup"><span data-stu-id="f84bb-113">Prerequisites</span></span>

<span data-ttu-id="f84bb-114">若要使用本指南, 必须先[创建 Azure 存储帐户](/azure/storage/storage-create-storage-account)。</span><span class="sxs-lookup"><span data-stu-id="f84bb-114">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account).</span></span>
<span data-ttu-id="f84bb-115">还需要此帐户的存储访问密钥。</span><span class="sxs-lookup"><span data-stu-id="f84bb-115">You'll also need your storage access key for this account.</span></span>

## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="f84bb-116">创建F#脚本并开始F#交互式</span><span class="sxs-lookup"><span data-stu-id="f84bb-116">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="f84bb-117">本文中的示例可用于F#应用程序或F#脚本。</span><span class="sxs-lookup"><span data-stu-id="f84bb-117">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="f84bb-118">若要创建F#脚本, 请在`.fsx` F#开发环境中创建`queues.fsx`扩展名为的文件。</span><span class="sxs-lookup"><span data-stu-id="f84bb-118">To create an F# script, create a file with the `.fsx` extension, for example `queues.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="f84bb-119">接下来, 使用[包管理器](package-management.md)(如`#r` [Paket](https://fsprojects.github.io/Paket/)或`WindowsAzure.Storage` [NuGet](https://www.nuget.org/) ) 通过指令在脚本`WindowsAzure.Storage.dll`中安装包和引用。</span><span class="sxs-lookup"><span data-stu-id="f84bb-119">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` package and reference `WindowsAzure.Storage.dll` in your script using a `#r` directive.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="f84bb-120">添加命名空间声明</span><span class="sxs-lookup"><span data-stu-id="f84bb-120">Add namespace declarations</span></span>

<span data-ttu-id="f84bb-121">将以下`open`语句添加到`queues.fsx`文件顶部:</span><span class="sxs-lookup"><span data-stu-id="f84bb-121">Add the following `open` statements to the top of the `queues.fsx` file:</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L1-L3)]

### <a name="get-your-connection-string"></a><span data-ttu-id="f84bb-122">获取连接字符串</span><span class="sxs-lookup"><span data-stu-id="f84bb-122">Get your connection string</span></span>

<span data-ttu-id="f84bb-123">本教程需要 Azure 存储连接字符串。</span><span class="sxs-lookup"><span data-stu-id="f84bb-123">You'll need an Azure Storage connection string for this tutorial.</span></span> <span data-ttu-id="f84bb-124">有关连接字符串的详细信息, 请参阅[配置存储连接字符串](/azure/storage/storage-configure-connection-string)。</span><span class="sxs-lookup"><span data-stu-id="f84bb-124">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

<span data-ttu-id="f84bb-125">对于本教程, 您将在脚本中输入连接字符串, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="f84bb-125">For the tutorial, you'll enter your connection string in your script, like this:</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L9-L9)]

<span data-ttu-id="f84bb-126">但对于实际项目,**不建议这样做**。</span><span class="sxs-lookup"><span data-stu-id="f84bb-126">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="f84bb-127">存储帐户密钥类似于存储帐户的根密码。</span><span class="sxs-lookup"><span data-stu-id="f84bb-127">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="f84bb-128">务必小心保护存储帐户密钥。</span><span class="sxs-lookup"><span data-stu-id="f84bb-128">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="f84bb-129">避免将其分发给其他用户、对其进行硬编码或将其保存在其他人可以访问的纯文本文件中。</span><span class="sxs-lookup"><span data-stu-id="f84bb-129">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="f84bb-130">如果你认为密钥可能已泄漏, 你可以使用 Azure 门户重新生成密钥。</span><span class="sxs-lookup"><span data-stu-id="f84bb-130">You can regenerate your key using the Azure Portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="f84bb-131">对于实际应用程序, 维护存储连接字符串的最佳方式是在配置文件中。</span><span class="sxs-lookup"><span data-stu-id="f84bb-131">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="f84bb-132">若要从配置文件中提取连接字符串, 可以执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="f84bb-132">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L11-L13)]

<span data-ttu-id="f84bb-133">使用 Azure Configuration Manager 是可选的。</span><span class="sxs-lookup"><span data-stu-id="f84bb-133">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="f84bb-134">你还可以使用 API, 例如 .NET Framework 的`ConfigurationManager`类型。</span><span class="sxs-lookup"><span data-stu-id="f84bb-134">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="f84bb-135">分析连接字符串</span><span class="sxs-lookup"><span data-stu-id="f84bb-135">Parse the connection string</span></span>

<span data-ttu-id="f84bb-136">若要分析连接字符串, 请使用:</span><span class="sxs-lookup"><span data-stu-id="f84bb-136">To parse the connection string, use:</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L19-L20)]

<span data-ttu-id="f84bb-137">这将返回`CloudStorageAccount`。</span><span class="sxs-lookup"><span data-stu-id="f84bb-137">This will return a `CloudStorageAccount`.</span></span>

### <a name="create-the-queue-service-client"></a><span data-ttu-id="f84bb-138">创建队列服务客户端</span><span class="sxs-lookup"><span data-stu-id="f84bb-138">Create the Queue service client</span></span>

<span data-ttu-id="f84bb-139">`CloudQueueClient`类使你能够检索存储在队列存储中的队列。</span><span class="sxs-lookup"><span data-stu-id="f84bb-139">The `CloudQueueClient` class enables you to retrieve queues stored in Queue storage.</span></span> <span data-ttu-id="f84bb-140">下面是创建服务客户端的一种方法:</span><span class="sxs-lookup"><span data-stu-id="f84bb-140">Here's one way to create the service client:</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L26-L26)]

<span data-ttu-id="f84bb-141">现在, 你已准备好编写从队列存储读取数据并将数据写入队列存储的代码。</span><span class="sxs-lookup"><span data-stu-id="f84bb-141">Now you are ready to write code that reads data from and writes data to Queue storage.</span></span>

## <a name="create-a-queue"></a><span data-ttu-id="f84bb-142">创建队列</span><span class="sxs-lookup"><span data-stu-id="f84bb-142">Create a queue</span></span>

<span data-ttu-id="f84bb-143">此示例演示如何创建队列 (如果该队列尚不存在):</span><span class="sxs-lookup"><span data-stu-id="f84bb-143">This example shows how to create a queue if it doesn't already exist:</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L32-L36)]

## <a name="insert-a-message-into-a-queue"></a><span data-ttu-id="f84bb-144">在队列中插入消息</span><span class="sxs-lookup"><span data-stu-id="f84bb-144">Insert a message into a queue</span></span>

<span data-ttu-id="f84bb-145">若要将消息插入现有队列, 请先创建一个新`CloudQueueMessage`的。</span><span class="sxs-lookup"><span data-stu-id="f84bb-145">To insert a message into an existing queue, first create a new `CloudQueueMessage`.</span></span> <span data-ttu-id="f84bb-146">接下来, 调用`AddMessage`方法。</span><span class="sxs-lookup"><span data-stu-id="f84bb-146">Next, call the `AddMessage` method.</span></span> <span data-ttu-id="f84bb-147">可从字符串 (utf-8 格式) `byte`或数组创建, 如下所示: `CloudQueueMessage`</span><span class="sxs-lookup"><span data-stu-id="f84bb-147">A `CloudQueueMessage` can be created from either a string (in UTF-8 format) or a `byte` array, like this:</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L42-L44)]

## <a name="peek-at-the-next-message"></a><span data-ttu-id="f84bb-148">扫视下一条消息</span><span class="sxs-lookup"><span data-stu-id="f84bb-148">Peek at the next message</span></span>

<span data-ttu-id="f84bb-149">通过调用`PeekMessage`方法, 可以查看队列前面的消息, 而不必从队列中将其删除。</span><span class="sxs-lookup"><span data-stu-id="f84bb-149">You can peek at the message in the front of a queue, without removing it from the queue, by calling the `PeekMessage` method.</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L50-L52)]

## <a name="get-the-next-message-for-processing"></a><span data-ttu-id="f84bb-150">获取要处理的下一条消息</span><span class="sxs-lookup"><span data-stu-id="f84bb-150">Get the next message for processing</span></span>

<span data-ttu-id="f84bb-151">可以通过调用`GetMessage`方法来检索队列前面的消息, 以便进行处理。</span><span class="sxs-lookup"><span data-stu-id="f84bb-151">You can retrieve the message at the front of a queue for processing by calling the `GetMessage` method.</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L58-L59)]

<span data-ttu-id="f84bb-152">稍后, 您可以使用`DeleteMessage`来指示成功处理消息。</span><span class="sxs-lookup"><span data-stu-id="f84bb-152">You later indicate successful processing of the message by using `DeleteMessage`.</span></span>

## <a name="change-the-contents-of-a-queued-message"></a><span data-ttu-id="f84bb-153">更改已排队消息的内容</span><span class="sxs-lookup"><span data-stu-id="f84bb-153">Change the contents of a queued message</span></span>

<span data-ttu-id="f84bb-154">您可以在队列中就地更改检索到的消息的内容。</span><span class="sxs-lookup"><span data-stu-id="f84bb-154">You can change the contents of a retrieved message in-place in the queue.</span></span> <span data-ttu-id="f84bb-155">如果消息表示工作任务, 则可以使用此功能来更新工作任务的状态。</span><span class="sxs-lookup"><span data-stu-id="f84bb-155">If the message represents a work task, you could use this feature to update the status of the work task.</span></span> <span data-ttu-id="f84bb-156">下面的代码用新内容更新队列消息, 并将可见性超时设置为再延长60秒。</span><span class="sxs-lookup"><span data-stu-id="f84bb-156">The following code updates the queue message with new contents, and sets the visibility timeout to extend another 60 seconds.</span></span> <span data-ttu-id="f84bb-157">这会保存与消息关联的工作的状态, 并为客户端提供另一分钟的时间来继续处理该消息。</span><span class="sxs-lookup"><span data-stu-id="f84bb-157">This saves the state of work associated with the message, and gives the client another minute to continue working on the message.</span></span> <span data-ttu-id="f84bb-158">您可以使用此方法跟踪队列消息上的多步骤工作流, 而无需在处理步骤因硬件或软件故障而失败时从头开始重新开始。</span><span class="sxs-lookup"><span data-stu-id="f84bb-158">You could use this technique to track multi-step workflows on queue messages, without having to start over from the beginning if a processing step fails due to hardware or software failure.</span></span> <span data-ttu-id="f84bb-159">通常, 还可以保留重试计数, 如果消息重试次数超过若干次, 则会将其删除。</span><span class="sxs-lookup"><span data-stu-id="f84bb-159">Typically, you would keep a retry count as well, and if the message is retried more than some number of times, you would delete it.</span></span> <span data-ttu-id="f84bb-160">这可以防止消息在每次处理时触发应用程序错误。</span><span class="sxs-lookup"><span data-stu-id="f84bb-160">This protects against a message that triggers an application error each time it is processed.</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L65-L69)]

## <a name="de-queue-the-next-message"></a><span data-ttu-id="f84bb-161">取消对下一条消息的排队</span><span class="sxs-lookup"><span data-stu-id="f84bb-161">De-queue the next message</span></span>

<span data-ttu-id="f84bb-162">你的代码通过两个步骤将消息从队列中取消排队。</span><span class="sxs-lookup"><span data-stu-id="f84bb-162">Your code de-queues a message from a queue in two steps.</span></span> <span data-ttu-id="f84bb-163">调用`GetMessage`时, 将获取队列中的下一条消息。</span><span class="sxs-lookup"><span data-stu-id="f84bb-163">When you call `GetMessage`, you get the next message in a queue.</span></span> <span data-ttu-id="f84bb-164">返回`GetMessage`的消息对从此队列读取消息的任何其他代码不可见。</span><span class="sxs-lookup"><span data-stu-id="f84bb-164">A message returned from `GetMessage` becomes invisible to any other code reading messages from this queue.</span></span> <span data-ttu-id="f84bb-165">默认情况下, 此消息将持续30秒不可见。</span><span class="sxs-lookup"><span data-stu-id="f84bb-165">By default, this message stays invisible for 30 seconds.</span></span> <span data-ttu-id="f84bb-166">若要完成从队列中删除消息, 还必须调用`DeleteMessage`。</span><span class="sxs-lookup"><span data-stu-id="f84bb-166">To finish removing the message from the queue, you must also call `DeleteMessage`.</span></span> <span data-ttu-id="f84bb-167">此删除消息的两步过程可确保, 如果代码因硬件或软件故障而无法处理消息, 则代码的其他实例可以获取相同消息并重试。</span><span class="sxs-lookup"><span data-stu-id="f84bb-167">This two-step process of removing a message assures that if your code fails to process a message due to hardware or software failure, another instance of your code can get the same message and try again.</span></span> <span data-ttu-id="f84bb-168">代码在处理`DeleteMessage`消息后立即调用。</span><span class="sxs-lookup"><span data-stu-id="f84bb-168">Your code calls `DeleteMessage` right after the message has been processed.</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L75-L76)]

## <a name="use-async-workflows-with-common-queue-storage-apis"></a><span data-ttu-id="f84bb-169">将异步工作流用于常见的队列存储 Api</span><span class="sxs-lookup"><span data-stu-id="f84bb-169">Use Async workflows with common Queue storage APIs</span></span>

<span data-ttu-id="f84bb-170">此示例演示如何将异步工作流与公共队列存储 Api 一起使用。</span><span class="sxs-lookup"><span data-stu-id="f84bb-170">This example shows how to use an async workflow with common Queue storage APIs.</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L82-L91)]

## <a name="additional-options-for-de-queuing-messages"></a><span data-ttu-id="f84bb-171">用于取消对消息进行排队的其他选项</span><span class="sxs-lookup"><span data-stu-id="f84bb-171">Additional options for de-queuing messages</span></span>

<span data-ttu-id="f84bb-172">可以通过两种方式自定义队列中的消息检索。</span><span class="sxs-lookup"><span data-stu-id="f84bb-172">There are two ways you can customize message retrieval from a queue.</span></span>
<span data-ttu-id="f84bb-173">首先, 你可以获取一批消息 (最多 32)。</span><span class="sxs-lookup"><span data-stu-id="f84bb-173">First, you can get a batch of messages (up to 32).</span></span> <span data-ttu-id="f84bb-174">其次, 你可以设置更长或更短的不可见超时时间, 从而允许你的代码使用更多或更少的时间来完全处理每个消息。</span><span class="sxs-lookup"><span data-stu-id="f84bb-174">Second, you can set a longer or shorter invisibility timeout, allowing your code more or less time to fully process each message.</span></span> <span data-ttu-id="f84bb-175">下面的代码示例使用`GetMessages`在一个调用中获取20条消息, 然后处理每条消息。</span><span class="sxs-lookup"><span data-stu-id="f84bb-175">The following code example uses `GetMessages` to get 20 messages in one call and then processes each message.</span></span> <span data-ttu-id="f84bb-176">它还将每条消息的不可见超时时间设置为5分钟。</span><span class="sxs-lookup"><span data-stu-id="f84bb-176">It also sets the invisibility timeout to five minutes for each message.</span></span> <span data-ttu-id="f84bb-177">请注意, 5 分钟会同时为所有消息启动, 因此, 在调用`GetMessages`后5分钟后, 任何尚未删除的消息都将再次变得可见。</span><span class="sxs-lookup"><span data-stu-id="f84bb-177">Note that the 5 minutes starts for all messages at the same time, so after 5 minutes have passed since the call to `GetMessages`, any messages which have not been deleted will become visible again.</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L97-L99)]

## <a name="get-the-queue-length"></a><span data-ttu-id="f84bb-178">获取队列长度</span><span class="sxs-lookup"><span data-stu-id="f84bb-178">Get the queue length</span></span>

<span data-ttu-id="f84bb-179">可以估计队列中的消息数。</span><span class="sxs-lookup"><span data-stu-id="f84bb-179">You can get an estimate of the number of messages in a queue.</span></span> <span data-ttu-id="f84bb-180">`FetchAttributes`方法要求队列服务检索队列属性, 包括消息计数。</span><span class="sxs-lookup"><span data-stu-id="f84bb-180">The `FetchAttributes` method asks the Queue service to retrieve the queue attributes, including the message count.</span></span> <span data-ttu-id="f84bb-181">属性返回`FetchAttributes`方法检索到的最后一个值, 而不会调用队列服务。 `ApproximateMessageCount`</span><span class="sxs-lookup"><span data-stu-id="f84bb-181">The `ApproximateMessageCount` property returns the last value retrieved by the `FetchAttributes` method, without calling the Queue service.</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L105-L106)]

## <a name="delete-a-queue"></a><span data-ttu-id="f84bb-182">删除队列</span><span class="sxs-lookup"><span data-stu-id="f84bb-182">Delete a queue</span></span>

<span data-ttu-id="f84bb-183">若要删除队列及其中包含的所有消息, 请对队列`Delete`对象调用方法。</span><span class="sxs-lookup"><span data-stu-id="f84bb-183">To delete a queue and all the messages contained in it, call the `Delete` method on the queue object.</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L112-L113)]

## <a name="next-steps"></a><span data-ttu-id="f84bb-184">后续步骤</span><span class="sxs-lookup"><span data-stu-id="f84bb-184">Next steps</span></span>

<span data-ttu-id="f84bb-185">现在, 你已了解有关队列存储的基础知识, 请单击下面的链接了解更复杂的存储任务。</span><span class="sxs-lookup"><span data-stu-id="f84bb-185">Now that you've learned the basics of Queue storage, follow these links to learn about more complex storage tasks.</span></span>

- [<span data-ttu-id="f84bb-186">适用于 .NET 的 Azure 存储 Api</span><span class="sxs-lookup"><span data-stu-id="f84bb-186">Azure Storage APIs for .NET</span></span>](/dotnet/api/overview/azure/storage)
- [<span data-ttu-id="f84bb-187">Azure 存储类型提供程序</span><span class="sxs-lookup"><span data-stu-id="f84bb-187">Azure Storage Type Provider</span></span>](https://github.com/fsprojects/AzureStorageTypeProvider)
- [<span data-ttu-id="f84bb-188">Azure 存储团队博客</span><span class="sxs-lookup"><span data-stu-id="f84bb-188">Azure Storage Team Blog</span></span>](https://blogs.msdn.microsoft.com/windowsazurestorage/)
- [<span data-ttu-id="f84bb-189">配置 Azure 存储连接字符串</span><span class="sxs-lookup"><span data-stu-id="f84bb-189">Configure Azure Storage connection strings</span></span>](/azure/storage/common/storage-configure-connection-string)
- [<span data-ttu-id="f84bb-190">Azure 存储服务 REST API 参考</span><span class="sxs-lookup"><span data-stu-id="f84bb-190">Azure Storage Services REST API Reference</span></span>](/rest/api/storageservices/Azure-Storage-Services-REST-API-Reference)
