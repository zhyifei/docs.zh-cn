---
title: 通过 F# 实现 Azure 队列存储入门
description: Azure 队列在应用程序组件之间提供可靠的异步消息传送。 通过云消息传递，你的应用程序组件可以独立缩放。
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: a09cbdd4b995e34177c110ce91b02162bb19dfa8
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2019
ms.locfileid: "73423842"
---
# <a name="get-started-with-azure-queue-storage-using-f"></a>使用 F\# 开始使用 Azure 队列存储

Azure 队列存储在应用程序组件之间提供云消息传送。 在设计规模应用程序时，应用程序组件通常是分离的，以便它们可以独立缩放。 队列存储提供了异步消息传送，以便在应用程序组件之间进行通信，无论它们是在云中、在桌面上、在本地服务器上运行还是在移动设备上运行。 队列存储还支持管理异步任务以及构建过程工作流。

### <a name="about-this-tutorial"></a>关于本教程

本教程演示如何使用 Azure F#队列存储为某些常见任务编写代码。 涉及的任务包括创建和删除队列、添加、读取和删除队列消息。

有关队列存储的概念性概述，请参阅[队列存储的 .net 指南](/azure/storage/storage-dotnet-how-to-use-queues)。

## <a name="prerequisites"></a>Prerequisites

若要使用本指南，必须先[创建 Azure 存储帐户](/azure/storage/storage-create-storage-account)。
还需要此帐户的存储访问密钥。

## <a name="create-an-f-script-and-start-f-interactive"></a>创建F#脚本并开始F#交互式

本文中的示例可用于F#应用程序或F#脚本。 若要创建F#脚本，请在F#开发环境中创建一个具有 `.fsx` 扩展名的文件，例如 `queues.fsx`。

接下来，使用[程序包管理器](package-management.md)（如[Paket](https://fsprojects.github.io/Paket/)或[NuGet](https://www.nuget.org/) ）通过 `#r` 指令在脚本中安装 `WindowsAzure.Storage` 包和引用 `WindowsAzure.Storage.dll`。

### <a name="add-namespace-declarations"></a>添加命名空间声明

将以下 `open` 语句添加到 `queues.fsx` 文件的顶部：

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L1-L3)]

### <a name="get-your-connection-string"></a>获取连接字符串

本教程需要 Azure 存储连接字符串。 有关连接字符串的详细信息，请参阅[配置存储连接字符串](/azure/storage/storage-configure-connection-string)。

对于本教程，您将在脚本中输入连接字符串，如下所示：

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L9-L9)]

但对于实际项目，**不建议这样做**。 存储帐户密钥类似于存储帐户的根密码。 务必小心保护存储帐户密钥。 避免将其分发给其他用户、对其进行硬编码或将其保存在其他人可以访问的纯文本文件中。 如果你认为密钥可能已泄漏，你可以使用 Azure 门户重新生成密钥。

对于实际应用程序，维护存储连接字符串的最佳方式是在配置文件中。 若要从配置文件中提取连接字符串，可以执行以下操作：

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L11-L13)]

使用 Azure Configuration Manager 是可选的。 你还可以使用 API，例如 .NET Framework 的 `ConfigurationManager` 类型。

### <a name="parse-the-connection-string"></a>分析连接字符串

若要分析连接字符串，请使用：

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L19-L20)]

这会返回 `CloudStorageAccount`。

### <a name="create-the-queue-service-client"></a>创建队列服务客户端

`CloudQueueClient` 类使你能够检索存储在队列存储中的队列。 下面是创建服务客户端的一种方法：

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L26-L26)]

现在，你已准备好编写从队列存储读取数据并将数据写入队列存储的代码。

## <a name="create-a-queue"></a>创建队列

此示例演示如何创建队列（如果该队列尚不存在）：

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L32-L36)]

## <a name="insert-a-message-into-a-queue"></a>在队列中插入消息

若要将消息插入现有队列，请先创建一个新的 `CloudQueueMessage`。 接下来，调用 `AddMessage` 方法。 可从字符串（UTF-8 格式）或 `byte` 数组创建 `CloudQueueMessage`，如下所示：

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L42-L44)]

## <a name="peek-at-the-next-message"></a>扫视下一条消息

通过调用 `PeekMessage` 方法，你可以扫视队列前面的消息，而不必从队列中将其删除。

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L50-L52)]

## <a name="get-the-next-message-for-processing"></a>获取要处理的下一条消息

可以通过调用 `GetMessage` 方法，检索队列前面的消息，以便进行处理。

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L58-L59)]

稍后使用 `DeleteMessage`指示消息处理是否成功。

## <a name="change-the-contents-of-a-queued-message"></a>更改已排队消息的内容

您可以在队列中就地更改检索到的消息的内容。 如果消息表示工作任务，则可以使用此功能来更新工作任务的状态。 下面的代码用新内容更新队列消息，并将可见性超时设置为再延长60秒。 这会保存与消息关联的工作的状态，并为客户端提供另一分钟的时间来继续处理该消息。 您可以使用此方法跟踪队列消息上的多步骤工作流，而无需在处理步骤因硬件或软件故障而失败时从头开始重新开始。 通常，还可以保留重试计数，如果消息重试次数超过若干次，则会将其删除。 这可以防止消息在每次处理时触发应用程序错误。

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L65-L69)]

## <a name="de-queue-the-next-message"></a>取消对下一条消息的排队

你的代码通过两个步骤将消息从队列中取消排队。 调用 `GetMessage`时，将获取队列中的下一条消息。 从 `GetMessage` 返回的消息变得对从此队列读取消息的任何其他代码不可见。 默认情况下，此消息将持续30秒不可见。 若要完成从队列中删除消息，还必须调用 `DeleteMessage`。 此删除消息的两步过程可确保，如果代码因硬件或软件故障而无法处理消息，则代码的其他实例可以获取相同消息并重试。 代码在处理消息后 `DeleteMessage` 立即调用。

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L75-L76)]

## <a name="use-async-workflows-with-common-queue-storage-apis"></a>将异步工作流用于常见的队列存储 Api

此示例演示如何将异步工作流与公共队列存储 Api 一起使用。

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L82-L91)]

## <a name="additional-options-for-de-queuing-messages"></a>用于取消对消息进行排队的其他选项

可以通过两种方式自定义队列中的消息检索。
首先，你可以获取一批消息（最多32）。 其次，你可以设置更长或更短的不可见超时时间，从而允许你的代码使用更多或更少的时间来完全处理每个消息。 下面的代码示例使用 `GetMessages` 在一次调用中获取20条消息，然后处理每条消息。 它还将每条消息的不可见超时时间设置为5分钟。 请注意，5分钟会同时为所有消息启动，因此，在调用 `GetMessages`之后5分钟后，任何尚未删除的消息都将再次变得可见。

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L97-L99)]

## <a name="get-the-queue-length"></a>获取队列长度

可以估计队列中的消息数。 `FetchAttributes` 方法要求队列服务检索队列属性，包括消息计数。 `ApproximateMessageCount` 属性返回 `FetchAttributes` 方法检索到的最后一个值，而无需调用队列服务。

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L105-L106)]

## <a name="delete-a-queue"></a>删除队列

若要删除队列及其中包含的所有消息，请对队列对象调用 `Delete` 方法。

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L112-L113)]

## <a name="next-steps"></a>后续步骤

现在，你已了解有关队列存储的基础知识，请单击下面的链接了解更复杂的存储任务。

- [适用于 .NET 的 Azure 存储 Api](/dotnet/api/overview/azure/storage)
- [Azure 存储类型提供程序](https://github.com/fsprojects/AzureStorageTypeProvider)
- [Azure 存储团队博客](https://blogs.msdn.microsoft.com/windowsazurestorage/)
- [配置 Azure 存储连接字符串](/azure/storage/common/storage-configure-connection-string)
- [Azure 存储服务 REST API 参考](/rest/api/storageservices/Azure-Storage-Services-REST-API-Reference)
