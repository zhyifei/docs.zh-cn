---
title: 通过 F# 实现 Azure 文件存储入门
description: 使用 Azure 文件存储在云中存储文件数据和从 Azure 虚拟机 (VM) 或从运行 Windows 的本地应用程序装载云文件共享。
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: 1b38ee53f2f73f7b7f4ee12f712f487cb726d41e
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739588"
---
# <a name="get-started-with-azure-file-storage-using-f"></a>使用 F 开始使用 Azure 文件存储\#

Azure 文件存储是使用标准[服务器消息块 （SMB） 协议](https://msdn.microsoft.com/library/windows/desktop/aa365233.aspx)在云中提供文件共享的服务。 支持 SMB 2.1 和 SMB 3.0。 通过 Azure 文件存储，可以将依赖文件共享的旧版应用程序快速迁移到 Azure 且无成本高昂的重写。 在 Azure 虚拟机或云服务中或者从本地客户端运行的应用程序可以在云中装载文件共享，就像桌面应用程序装载典型的 SMB 共享一样。 之后，任意数量的应用程序组件可以装载并同时访问文件存储共享。

有关文件存储的概念概述[，请参阅文件存储的 .NET 指南](https://docs.microsoft.com/azure/storage/storage-dotnet-how-to-use-files)。

## <a name="prerequisites"></a>先决条件

要使用本指南，必须首先创建[Azure 存储帐户](https://docs.microsoft.com/azure/storage/storage-create-storage-account)。
您还需要此帐户的存储访问密钥。

## <a name="create-an-f-script-and-start-f-interactive"></a>创建 F# 脚本和开始 F# 交互式

本文中的示例可用于 F# 应用程序或 F# 脚本。 要创建 F# 脚本，请创建一个`.fsx`包含扩展名的文件`files.fsx`，例如，在 F# 开发环境中。

接下来，使用[Paket](https://fsprojects.github.io/Paket/)或[NuGet](https://www.nuget.org/)等[包管理器](package-management.md)使用`WindowsAzure.Storage``#r`指令在脚本`WindowsAzure.Storage.dll`中安装包和引用。

### <a name="add-namespace-declarations"></a>添加命名空间声明

将下列 `open` 语句添加到 `files.fsx` 文件顶部：

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a>获取连接字符串

本教程需要 Azure 存储连接字符串。 有关连接字符串的详细信息，请参阅[配置存储连接字符串](https://docs.microsoft.com/azure/storage/storage-configure-connection-string)。

在本教程中，您将在脚本中输入连接字符串，如下所示：

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L11-L11)]

但是，**不建议**对实际项目进行此类使用。 存储帐户密钥类似于存储帐户的根密码。 始终要小心保护存储帐户密钥。 避免将其分发给其他用户、对其进行硬编码或将其保存在其他人可以访问的纯文本文件中。 如果您认为密钥可能已泄露，则可以使用 Azure 门户重新生成密钥。

对于实际应用程序，维护存储连接字符串的最佳方法是在配置文件中。 要从配置文件中获取连接字符串，可以执行以下操作：

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L13-L15)]

不一定要使用 Azure Configuration Manager。 您还可以使用 API，如 .NET 框架的类型`ConfigurationManager`。

### <a name="parse-the-connection-string"></a>解析连接字符串

要分析连接字符串，请使用：

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L21-L22)]

这将返回 。 `CloudStorageAccount`

### <a name="create-the-file-service-client"></a>创建文件服务客户端

该`CloudFileClient`类型使您能够以编程方式使用存储在文件存储中的文件。 下面是创建服务客户端的一种方法：

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L28-L28)]

现在，您可以编写从文件存储读取数据并将数据写入文件存储的代码。

## <a name="create-a-file-share"></a>创建文件共享

此示例演示如何创建文件共享（如果文件共享不存在）：

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L34-L35)]

## <a name="create-a-root-directory-and-a-subdirectory"></a>创建根目录和子目录

在这里，您将获得根目录，并获得根的子目录。 如果它们不存在，则创建两者。

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L41-L43)]

## <a name="upload-text-as-a-file"></a>将文本作为文件上载

此示例演示如何将文本上载为文件。

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L49-L50)]

### <a name="download-a-file-to-a-local-copy-of-the-file"></a>将文件下载到文件的本地副本

在这里，您可以下载刚刚创建的文件，将内容追加到本地文件中。

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L56-L56)]

### <a name="set-the-maximum-size-for-a-file-share"></a>设置文件共享的最大大小

下面的示例演示如何检查共享的当前使用情况，以及如何设置共享的配额。 `FetchAttributes`必须调用 以填充共享 的`Properties`，并将`SetProperties`本地更改传播到 Azure 文件存储。

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L62-L72)]

### <a name="generate-a-shared-access-signature-for-a-file-or-file-share"></a>为文件或文件共享生成共享访问签名

可以为文件共享或单个文件生成共享访问签名 (SAS)。 还可以在文件共享上创建一个共享访问策略以管理共享访问签名。 建议创建共享访问策略，因为它提供了一种在受到威胁时撤消 SAS 的方式。

在这里，在共享上创建共享访问策略，然后使用该策略为共享中的文件上的 SAS 提供约束。

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L78-L94)]

有关创建和使用共享访问签名的更多信息，请参阅[使用共享访问签名 (SAS)](https://docs.microsoft.com/azure/storage/storage-dotnet-shared-access-signature-part-1) 和[创建 SAS 并将其与 Blob 存储结合使用](https://docs.microsoft.com/azure/storage/storage-dotnet-shared-access-signature-part-2)。

### <a name="copy-files"></a>复制文件

您可以将文件复制到其他文件或 Blob，或将 Blob 复制到文件。 如果要将 Blob 复制到文件或文件复制到 Blob，*则必须*使用共享访问签名 （SAS） 对源对象进行身份验证，即使您正在同一存储帐户中复制也是如此。

### <a name="copy-a-file-to-another-file"></a>将一个文件复制到另一个文件

在这里，您将文件复制到同一共享中的另一个文件。 因为此操作在同一存储帐户中的文件之间进行复制，可以使用共享密钥身份验证来进行复制。

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L100-L101)]

### <a name="copy-a-file-to-a-blob"></a>将文件复制到 Blob

在这里，您将创建一个文件并将其复制到同一存储帐户中的 Blob。 为源文件创建 SAS，服务用于在复制操作期间对源文件的访问进行身份验证。

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L107-L120)]

可以用相同的方式将一个 Blob 复制到一个文件。 如果源对象是一个 Blob，则创建一个 SAS 以复制操作期间验证对该 Blob 的访问。

## <a name="troubleshooting-file-storage-using-metrics"></a>使用指标对文件存储进行故障排除

Azure 存储分析支持文件存储的指标。 使用指标数据，可以跟踪请求和诊断问题。

可以从[Azure 门户](https://portal.azure.com)启用文件存储的指标，也可以从 F# 执行此操作，如下所示：

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L126-L140)]

## <a name="next-steps"></a>后续步骤

有关 Azure 文件存储的详细信息，请参阅这些链接。

### <a name="conceptual-articles-and-videos"></a>概念性文章和视频

- [Azure 文件存储：适用于 Windows 和 Linux 的顺畅的云 SMB 文件系统](https://azure.microsoft.com/resources/videos/azurecon-2015-azure-files-storage-a-frictionless-cloud-smb-file-system-for-windows-and-linux/)
- [如何通过 Linux 使用 Azure 文件存储](https://docs.microsoft.com/azure/storage/storage-how-to-use-files-linux)

### <a name="tooling-support-for-file-storage"></a>文件存储的工具支持

- [对 Azure 存储空间使用 Azure PowerShell](https://docs.microsoft.com/azure/storage/storage-powershell-guide-full)
- [如何对 Microsoft Azure 存储使用 AzCopy](https://docs.microsoft.com/azure/storage/storage-use-azcopy)
- [使用 Azure CLI 创建、下载和列出 blob](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-cli#create-and-manage-file-shares)

### <a name="reference"></a>参考

- [.NET 存储客户端库参考](https://msdn.microsoft.com/library/azure/mt347887.aspx)
- [文件服务 REST API 参考](/rest/api/storageservices/fileservices/File-Service-REST-API)

### <a name="blog-posts"></a>博客文章

- [Azure 文件存储现已正式发布](https://azure.microsoft.com/blog/azure-file-storage-now-generally-available/)
- [在 Azure 文件存储中](https://azure.microsoft.com/blog/inside-azure-file-storage/)
- [Microsoft Azure 文件服务简介](https://docs.microsoft.com/archive/blogs/windowsazurestorage/introducing-microsoft-azure-file-service)
- [将连接保存到 Microsoft Azure 文件中](https://docs.microsoft.com/archive/blogs/windowsazurestorage/persisting-connections-to-microsoft-azure-files)
