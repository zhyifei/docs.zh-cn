---
title: '要开始使用 Azure Blob 存储使用 F #'
description: 在云中，而 Azure Blob 存储中存储非结构化的数据。
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: 3ab08154bd374896fce777c7c373204c9048b65c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="get-started-with-azure-blob-storage-using-f"></a>要开始使用 Azure Blob 存储使用 F # #

Azure Blob 存储是将非结构化数据作为对象/blob 存储在云中的服务。 Blob 存储可以存储任何类型的文本或二进制数据（如文档、媒体文件或应用程序安装程序）。 Blob 存储也称为对象存储。

这篇文章演示了如何使用 Blob 存储执行常见任务。 相关示例是使用 F # 使用 Azure Storage Client Library for.NET。 涉及的任务包括如何上载、 列出、 下载和删除 blob。

有关 blob 存储的概念概述，请参阅[blob 存储的.NET 指南](/azure/storage/storage-dotnet-how-to-use-blobs)。

## <a name="prerequisites"></a>系统必备

若要使用本指南，你必须首先[创建 Azure 存储帐户](/azure/storage/storage-create-storage-account)。 你还需要为此帐户的存储访问密钥。

## <a name="create-an-f-script-and-start-f-interactive"></a>创建的 F # 脚本并开始 F # 交互

这篇文章中的示例可在 F # 应用程序或 F # 脚本。 若要创建的 F # 脚本，创建具有的文件`.fsx`扩展，例如`blobs.fsx`，F # 开发环境中。

接下来，使用[程序包管理器](package-management.md)如[Paket](https://fsprojects.github.io/Paket/)或[NuGet](https://www.nuget.org/)安装`WindowsAzure.Storage`和`Microsoft.WindowsAzure.ConfigurationManager`包和引用`WindowsAzure.Storage.dll`和`Microsoft.WindowsAzure.Configuration.dll`中你的脚本使用`#r`指令。

### <a name="add-namespace-declarations"></a>添加命名空间声明

添加以下`open`到顶部的语句`blobs.fsx`文件：

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a>获取连接字符串

对于本教程需要 Azure 存储连接字符串。 有关连接字符串的详细信息，请参阅[配置存储连接字符串](/azure/storage/storage-configure-connection-string)。

对于本教程中，您可以在脚本中，如下输入连接字符串：

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L11-L11)]

但是，这是**不建议**的实际项目。 你的存储帐户密钥是类似于你的存储帐户的根密码。 始终必须小心地保护你的存储帐户密钥。 避免将其分发给其他用户，硬编码，或将其保存在其他人可以访问的纯文本格式的文件。 你可以重新生成你使用 Azure 门户，如果你认为可能已泄露的密钥。

为实际的应用程序，维护存储连接字符串的最佳方法是在配置文件中。 若要从配置文件中提取的连接字符串，您可以执行此操作：

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L13-L15)]

使用 Azure 配置管理器是可选的。 你还可以使用 API，如.NET Framework 的`ConfigurationManager`类型。

### <a name="parse-the-connection-string"></a>分析连接字符串

若要分析的连接字符串，请使用：

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L21-L22)]

这将返回`CloudStorageAccount`。

### <a name="create-some-local-dummy-data"></a>创建一些本地虚拟数据

在开始之前，我们的脚本的目录中创建一些虚拟的本地数据。 更高版本，你将上载此数据。

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L28-L30)]

### <a name="create-the-blob-service-client"></a>创建 Blob 服务客户端

`CloudBlobClient`类型可让你检索存储在 Blob 存储容器和 blob。 下面是创建服务客户端的一种方法：

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L36-L36)]

现在你已准备好编写代码，从读取数据并将数据写入 Blob 存储。

## <a name="create-a-container"></a>创建容器

此示例演示如何创建容器，如果不存在：

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L42-L46)]

默认情况下，新容器是私有的这意味着，你必须指定存储访问密钥才能从该容器下载 blob。 如果你想要让容器中的文件可供所有人，则可以将容器设置为公共使用下面的代码：

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L48-L49)]

在 Internet 上的任何人都可以看到公共容器中的 blob，但您可以修改或删除它们，只有具有相应的帐户访问密钥或共享的访问签名。

## <a name="upload-a-blob-into-a-container"></a>将 blob 上载到容器

Azure Blob 存储支持块 blob 和页 blob。 在大多数情况下，块 blob 是要使用的建议的类型。

若要将文件上载到块 blob，获取容器引用，使用它来获取块 blob 引用。 Blob 引用后，你可以将任何数据流上载的数据到它通过调用`UploadFromFile`方法。 如果它以前不存在，或者覆盖它，如果它存在，此操作将创建 blob。

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L55-L59)]

## <a name="list-the-blobs-in-a-container"></a>列出容器中的 blob

若要列出容器中的 blob，首先获取容器引用。 然后，可以使用容器的`ListBlobs`方法来检索其中的 blob 和/或目录。 若要访问的丰富属性和方法返回的`IListBlobItem`，你必须将它转换到`CloudBlockBlob`， `CloudPageBlob`，或`CloudBlobDirectory`对象。 如果类型未知，你可以使用类型检查来确定要将其转换为哪。 下面的代码演示如何检索和输出中的每个项的 URI`mydata`容器：

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L67-L80)]

你还可以使用在其名称中的路径信息的名称 blob。 这将创建的虚拟目录结构，您可以组织和遍历像传统文件系统一样。 请注意，目录结构才虚拟-可以在 Blob 存储的唯一资源是容器和 blob。 但是，存储客户端库提供`CloudBlobDirectory`对象来引用虚拟目录，并简化使用以这种方式组织的 blob 的过程。

例如，考虑下面的一组名为的容器中的块 blob `photos`:

*photo1.jpg*
*2015/architecture/description.txt*
*2015/architecture/photo3.jpg*
*2015/architecture/photo4.jpg*
*2016/architecture/photo5.jpg*
*2016/architecture/photo6.jpg*
*2016/architecture/description.txt*
*2016/photo7.jpg*

当调用`ListBlobs`（如上面的示例中） 的容器上, 返回一个层次结构列表。 如果它包含`CloudBlobDirectory`和`CloudBlockBlob`对象，分别表示的目录和 blob 容器中的，然后生成的输出看起来类似于此：

```console
Directory: https://<accountname>.blob.core.windows.net/photos/2015/
Directory: https://<accountname>.blob.core.windows.net/photos/2016/
Block blob of length 505623: https://<accountname>.blob.core.windows.net/photos/photo1.jpg
```

（可选） 你可以设置`UseFlatBlobListing`参数`ListBlobs`方法`true`。 在这种情况下，容器中的每个 blob 返回作为`CloudBlockBlob`对象。 调用`ListBlobs`返回一个平面列表如下所示：

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L82-L89)]

而且，具体取决于你的容器的当前内容，结果如下所示：

```console
Block blob of length 4: https://<accountname>.blob.core.windows.net/photos/2015/architecture/description.txt
Block blob of length 314618: https://<accountname>.blob.core.windows.net/photos/2015/architecture/photo3.jpg
Block blob of length 522713: https://<accountname>.blob.core.windows.net/photos/2015/architecture/photo4.jpg
Block blob of length 4: https://<accountname>.blob.core.windows.net/photos/2016/architecture/description.txt
Block blob of length 419048: https://<accountname>.blob.core.windows.net/photos/2016/architecture/photo5.jpg
Block blob of length 506388: https://<accountname>.blob.core.windows.net/photos/2016/architecture/photo6.jpg
Block blob of length 399751: https://<accountname>.blob.core.windows.net/photos/2016/photo7.jpg
Block blob of length 505623: https://<accountname>.blob.core.windows.net/photos/photo1.jpg
```

## <a name="download-blobs"></a>下载 blob

若要下载 blob，首先检索 blob 引用，然后调用`DownloadToStream`方法。 下面的示例使用`DownloadToStream`方法将 blob 内容传输到稍后可以保存到本地文件的流对象。

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L95-L101)]

你还可以使用`DownloadToStream`方法以文本字符串形式的 blob 的内容下载。

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L103-L106)]

## <a name="delete-blobs"></a>删除 blob

若要删除 blob，首先需要获取 blob 引用，然后调用`Delete`方法。

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L112-L116)]

## <a name="list-blobs-in-pages-asynchronously"></a>以异步方式列出页中的 blob

如果正在列出大量 blob，或者你想要控制一个列表操作中返回的结果数，则可以列出的结果页中的 blob。 此示例演示如何以异步方式，在页中返回结果，以便执行不会被阻止时等待返回大量结果。

此示例演示平面 blob 列表，但你也可以执行分层列表，通过设置`useFlatBlobListing`参数`ListBlobsSegmentedAsync`方法`false`。

此示例定义一个异步方法，使用`async`块。 ``let!``关键字将挂起示例方法的执行，直至列表任务完成。

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L122-L160)]

我们现在可以使用此异步例程，如下所示。 首先，你将上载一些 dummy 数据 （使用在本教程前面创建的本地文件）。

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L162-L166)]

现在，调用例程。 你使用``Async.RunSynchronously``以强制执行异步操作。

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L168-L168)]

## <a name="writing-to-an-append-blob"></a>写入追加 blob

追加 blob 针对追加操作，例如日志记录进行了优化。 类似于块 blob，追加 blob 由块组成，但当你将新的块添加到追加 blob，始终追加到 blob 的末尾。 无法更新或删除追加 blob 中的现有块。 追加 blob 的块 Id 不公开，因为它们适用于块 blob。

追加 blob 中的每个块可以是不同的大小，最大为 4 MB，并且追加 blob 可以包括最多 50000 个块。 因此，追加 blob 的最大大小是稍微大于 195 GB （4 MB X 50000 块）。

下面的示例创建新的追加 blob，并将一些数据追加到它，模拟一个简单的日志记录操作。

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L174-L203)]

请参阅[了解块 Blob、 页 Blob 和追加 Blob](https://msdn.microsoft.com/library/azure/ee691964.aspx)有关三种 blob 之间的差异的详细信息。

## <a name="concurrent-access"></a>并发访问

若要允许从多个客户端或多个进程实例并发访问到某一 blob，可以使用**Etag**或**租约**。

* **Etag** -提供一种方法，用于检测 blob 或容器是否被另一个进程修改

* **租约**-使您能够获取独占式可续订写入或删除一段时间内对 blob 的访问

有关详细信息，请参阅[管理在 Microsoft Azure 存储空间的并发](https://azure.microsoft.com/blog/managing-concurrency-in-microsoft-azure-storage-2/)。

## <a name="naming-containers"></a>命名容器

Azure 存储空间中的每个 blob 必须驻留在一个容器。 该容器构成 blob 名称的一部分。 例如，`mydata`是这些示例 blob Uri 中的容器的名称：

    https://storagesample.blob.core.windows.net/mydata/blob1.txt
    https://storagesample.blob.core.windows.net/mydata/photos/myphoto.jpg

容器名称必须是有效的 DNS 名称，符合以下命名规则：

1. 容器名称必须以字母或数字开头，并且只能包含字母、 数字和短划线 （-） 字符。
1. 必须立即前面并且后跟字母或数字; 每个短划线 （-） 字符容器名称中不允许使用连续划线。
1. 容器名称中的所有字母必须都为小写。
1. 容器名称必须是 3 到 63 个字符。

请注意，容器的名称必须始终为小写。 如果你在容器名称，包括大写字母-或其他方式违反了容器命名规则，你可能会收到 400 错误 （错误请求）。

## <a name="managing-security-for-blobs"></a>管理 blob 的安全性

默认情况下，Azure 存储空间保留你的数据安全通过限制对帐户的所有者，拥有帐户访问密钥的访问。 当你需要进行共享你的存储帐户中的 blob 数据时，务必这样做不会影响你的帐户访问密钥的安全性。 此外，你可以加密 blob 数据，以确保其安全将通过电缆和 Azure 存储中。

### <a name="controlling-access-to-blob-data"></a>控制对 blob 数据的访问

默认情况下，你的存储帐户中的 blob 数据是只有存储帐户所有者访问。 默认情况下，针对 Blob 存储的请求进行身份验证需要帐户访问密钥。 但是，你可能想要向其他用户提供某些 blob 数据。

有关如何控制对 blob 存储的访问的详细信息，请参阅[上访问控制的 blob 存储部分.NET 指南](/azure/storage/storage-dotnet-how-to-use-blobs#controlling-access-to-blob-data)。


### <a name="encrypting-blob-data"></a>加密的 blob 数据

Azure 存储空间支持在客户端和服务器上的 blob 数据进行加密。

有关加密的 blob 数据的详细信息，请参阅[上加密的 blob 存储部分.NET 指南](/azure/storage/storage-dotnet-how-to-use-blobs#encrypting-blob-data)。

## <a name="next-steps"></a>后续步骤

现在，你已了解 Blob 存储的基础知识，单击下面的链接以了解详细信息。

### <a name="tools"></a>工具
- [F # AzureStorageTypeProvider](https://fsprojects.github.io/AzureStorageTypeProvider/) F # 类型提供程序可以用于浏览 Blob、 表和队列 Azure 存储空间资产并轻松地将应用在其上的 CRUD 操作。
- [FSharp.Azure.Storage](https://github.com/fsprojects/FSharp.Azure.Storage) F # API 使用 Microsoft Azure 表存储服务
- [Microsoft Azure 存储资源管理器 (MASE)](/azure/vs-azure-tools-storage-manage-with-storage-explorer)使您能够以可视方式使用 Azure 存储空间数据在 Windows、 OS X 和 Linux 上的 Microsoft 从一个免费的独立应用程序。

### <a name="blob-storage-reference"></a>Blob 存储参考

- [用于.NET 的 azure 存储 Api](/dotnet/api/overview/azure/storage)
- [Azure 存储服务 REST API 参考](/rest/api/storageservices/Azure-Storage-Services-REST-API-Reference)

### <a name="related-guides"></a>相关参考线

- [在 C# 中的 Azure Blob 存储入门](https://azure.microsoft.com/resources/samples/storage-blob-dotnet-getting-started/)
- [在 Windows 上传输数据的 AzCopy 命令行实用程序](/azure/storage/common/storage-use-azcopy)
- [在 Linux 上传输数据的 AzCopy 命令行实用程序](/azure/storage/common/storage-use-azcopy-linux)
- [配置 Azure 存储连接字符串](/azure/storage/common/storage-configure-connection-string)
- [Azure 存储团队博客](https://blogs.msdn.microsoft.com/windowsazurestorage/)
