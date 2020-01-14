---
title: 通过 F# 实现 Azure 队列存储入门
description: Azure 队列用于在应用程序组件之间进行可靠的异步消息传送。 应用程序组件可以利用云消息传送进行独立缩放。
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: 841068ac91aecc53811359e27d984907569a2c6d
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/14/2020
ms.locfileid: "75935497"
---
# <a name="get-started-with-azure-queue-storage-using-f"></a>使用 F\# 开始使用 Azure 队列存储

Azure 队列存储用于在应用程序组件之间进行云消息传送。 在设计应用程序以实现可伸缩性时，通常要将各个应用程序组件分离，使其可以独立地进行伸缩。 队列存储提供的异步消息传送适用于在应用程序组件之间进行通信，无论这些应用程序组件是运行在云中、桌面上、本地服务器上还是移动设备上。 队列存储还支持管理异步任务以及构建过程工作流。

### <a name="about-this-tutorial"></a>关于本教程

本教程演示如何使用 Azure F#队列存储为某些常见任务编写代码。 涉及的任务包括创建和删除队列、添加、读取和删除队列消息。

有关队列存储的概念性概述，请参阅[队列存储的 .net 指南](/azure/storage/storage-dotnet-how-to-use-queues)。

## <a name="prerequisites"></a>先决条件

若要使用本指南，必须先[创建 Azure 存储帐户](/azure/storage/storage-create-storage-account)。
还需要此帐户的存储访问密钥。

## <a name="create-an-f-script-and-start-f-interactive"></a>创建F#脚本并开始F#交互式

本文中的示例可用于F#应用程序或F#脚本。 若要创建F#脚本，请在F#开发环境中创建一个具有 `.fsx` 扩展名的文件，例如 `queues.fsx`。

接下来，使用[程序包管理器](package-management.md)（如[Paket](https://fsprojects.github.io/Paket/)或[NuGet](https://www.nuget.org/) ）通过 `#r` 指令在脚本中安装 `WindowsAzure.Storage` 包和引用 `WindowsAzure.Storage.dll`。

### <a name="add-namespace-declarations"></a>添加命名空间声明

将下列 `open` 语句添加到 `queues.fsx` 文件顶部：

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L1-L3)]

### <a name="get-your-connection-string"></a>获取连接字符串

本教程需要 Azure 存储连接字符串。 有关连接字符串的详细信息，请参阅[配置存储连接字符串](/azure/storage/storage-configure-connection-string)。

对于本教程，您将在脚本中输入连接字符串，如下所示：

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L9-L9)]

但对于实际项目，**不建议这样做**。 您的存储帐户密钥类似于您的存储帐户的根密码。 始终要小心保护存储帐户密钥。 避免将其分发给其他用户、对其进行硬编码或将其保存在其他人可以访问的纯文本文件中。 如果你认为密钥可能已泄漏，你可以使用 Azure 门户重新生成密钥。

对于实际应用程序，维护存储连接字符串的最佳方式是在配置文件中。 若要从配置文件中提取连接字符串，可以执行以下操作：

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L11-L13)]

不一定要使用 Azure Configuration Manager。 你还可以使用 API，例如 .NET Framework 的 `ConfigurationManager` 类型。

### <a name="parse-the-connection-string"></a>解析连接字符串

若要分析连接字符串，请使用：

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L19-L20)]

这会返回 `CloudStorageAccount`。

### <a name="create-the-queue-service-client"></a>创建队列服务客户端

`CloudQueueClient` 类使你能够检索存储在队列存储中的队列。 下面是创建服务客户端的一种方法：

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L26-L26)]

现在，已准备好编写从队列存储读取数据并将数据写入队列存储的代码。

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

您可以在队列中就地更改检索到的消息的内容。 如果消息表示工作任务，则你可以使用此功能来更新该工作任务的状态。 以下代码使用新内容更新队列消息，并将可见性超时设置为再延长 60 秒。 这将保存与消息关联的工作的状态，并额外为客户端提供一分钟的时间来继续处理消息。 可使用此方法跟踪队列消息上的多步骤工作流，即使处理步骤因硬件或软件故障而失败，也无需从头开始操作。 通常，还可以保留重试计数，如果消息重试次数超过若干次，则会将其删除。 这可避免每次处理某条消息时都触发应用程序错误。

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L65-L69)]

## <a name="de-queue-the-next-message"></a>取消对下一条消息的排队

你的代码通过两个步骤来取消对队列中某条消息的排队。 调用 `GetMessage`时，将获取队列中的下一条消息。 从 `GetMessage` 返回的消息对于从此队列读取消息的任何其他代码都是不可见的。 默认情况下，此消息将持续 30 秒不可见。 若要完成从队列中删除消息，还必须调用 `DeleteMessage`。 此删除消息的两步过程可确保当您的代码因硬件或软件故障而无法处理消息时，您的其他代码实例可以获取同一消息并重试。 代码在处理消息后 `DeleteMessage` 立即调用。

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L75-L76)]

## <a name="use-async-workflows-with-common-queue-storage-apis"></a>将异步工作流用于常见的队列存储 Api

此示例演示如何将异步工作流与公共队列存储 Api 一起使用。

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L82-L91)]

## <a name="additional-options-for-de-queuing-messages"></a>用于取消对消息进行排队的其他选项

你可以通过两种方式自定义队列中的消息检索。
首先，你可以获取一批消息（最多 32 个）。 其次，你可以设置更长或更短的不可见超时时间，从而允许你的代码使用更多或更少时间来完全处理每个消息。 下面的代码示例使用 `GetMessages` 在一次调用中获取20条消息，然后处理每条消息。 它还将每条消息的不可见超时时间设置为 5 分钟。 请注意，5分钟会同时为所有消息启动，因此，在调用 `GetMessages`之后5分钟后，任何尚未删除的消息都将再次变得可见。

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L97-L99)]

## <a name="get-the-queue-length"></a>获取队列长度

你可以获取队列中消息的估计数。 `FetchAttributes` 方法要求队列服务检索队列属性，包括消息计数。 `ApproximateMessageCount` 属性返回 `FetchAttributes` 方法检索到的最后一个值，而无需调用队列服务。

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L105-L106)]

## <a name="delete-a-queue"></a>删除队列

若要删除队列及其中包含的所有消息，请对队列对象调用 `Delete` 方法。

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L112-L113)]

## <a name="next-steps"></a>后续步骤

现在，您已了解有关队列存储的基础知识，可单击下面的链接来了解更复杂的存储任务。

- [用于 .NET 的 Azure 存储 API](/dotnet/api/overview/azure/storage)
- [Azure 存储类型提供程序](https://github.com/fsprojects/AzureStorageTypeProvider)
- [Azure 存储团队博客](https://docs.microsoft.com/archive/blogs/windowsazurestorage/)
- [Configure Azure Storage connection strings](/azure/storage/common/storage-configure-connection-string)（配置 Azure 存储连接字符串）
- [Azure 存储服务 REST API 参考](/rest/api/storageservices/Azure-Storage-Services-REST-API-Reference)
