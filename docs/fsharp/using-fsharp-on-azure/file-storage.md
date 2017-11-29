---
title: "要开始使用 Azure 文件存储使用 F #"
description: "在云中，而 Azure 文件存储中存储文件数据和从 Azure 虚拟机 (VM) 装载云文件共享或从本地应用程序运行 Windows。"
keywords: "visual f #、 f # 中，函数编程，.NET，.NET 核心，Azure"
author: sylvanc
ms.author: phcart
ms.date: 09/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 5c26a0aa-186e-476c-9f87-e0191754579e
ms.openlocfilehash: 66b2503744e9024deac3d6dabea57da4fd393bd8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="get-started-with-azure-file-storage-using-f"></a><span data-ttu-id="35a4c-104">要开始使用 Azure 文件存储使用 F #</span><span class="sxs-lookup"><span data-stu-id="35a4c-104">Get started with Azure File storage using F#</span></span> #

<span data-ttu-id="35a4c-105">Azure 文件存储区都提供在云中使用标准的文件共享的服务[服务器消息块 (SMB) 协议](https://msdn.microsoft.com/library/windows/desktop/aa365233.aspx)。</span><span class="sxs-lookup"><span data-stu-id="35a4c-105">Azure File storage is a service that offers file shares in the cloud using the standard [Server Message Block (SMB) Protocol](https://msdn.microsoft.com/library/windows/desktop/aa365233.aspx).</span></span> <span data-ttu-id="35a4c-106">支持 SMB 2.1 和 SMB 3.0。</span><span class="sxs-lookup"><span data-stu-id="35a4c-106">Both SMB 2.1 and SMB 3.0 are supported.</span></span> <span data-ttu-id="35a4c-107">使用 Azure 文件存储，你可以迁移的旧版应用程序快速且无成本高昂的重写依赖到 Azure 的文件共享。</span><span class="sxs-lookup"><span data-stu-id="35a4c-107">With Azure File storage, you can migrate legacy applications that rely on file shares to Azure quickly and without costly rewrites.</span></span> <span data-ttu-id="35a4c-108">运行在 Azure 虚拟机或云服务或从本地客户端的应用程序可以装载文件共享在云中，就像桌面应用程序装载典型 SMB 共享一样。</span><span class="sxs-lookup"><span data-stu-id="35a4c-108">Applications running in Azure virtual machines or cloud services or from on-premises clients can mount a file share in the cloud, just as a desktop application mounts a typical SMB share.</span></span> <span data-ttu-id="35a4c-109">然后，任意数量的应用程序组件可以装载并同时访问文件存储共享。</span><span class="sxs-lookup"><span data-stu-id="35a4c-109">Any number of application components can then mount and access the File storage share simultaneously.</span></span>

<span data-ttu-id="35a4c-110">有关文件存储的概念概述，请参阅[文件存储的.NET 指南](/azure/storage/storage-dotnet-how-to-use-files)。</span><span class="sxs-lookup"><span data-stu-id="35a4c-110">For a conceptual overview of file storage, please see [the .NET guide for file storage](/azure/storage/storage-dotnet-how-to-use-files).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="35a4c-111">先决条件</span><span class="sxs-lookup"><span data-stu-id="35a4c-111">Prerequisites</span></span>

<span data-ttu-id="35a4c-112">若要使用本指南，你必须首先[创建 Azure 存储帐户](/azure/storage/storage-create-storage-account)。</span><span class="sxs-lookup"><span data-stu-id="35a4c-112">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account).</span></span>
<span data-ttu-id="35a4c-113">此外需要为此帐户存储访问密钥。</span><span class="sxs-lookup"><span data-stu-id="35a4c-113">You'll also need your storage access key for this account.</span></span>

## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="35a4c-114">创建的 F # 脚本并开始 F # 交互</span><span class="sxs-lookup"><span data-stu-id="35a4c-114">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="35a4c-115">这篇文章中的示例可在 F # 应用程序或 F # 脚本。</span><span class="sxs-lookup"><span data-stu-id="35a4c-115">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="35a4c-116">若要创建的 F # 脚本，创建具有的文件`.fsx`扩展，例如`files.fsx`，F # 开发环境中。</span><span class="sxs-lookup"><span data-stu-id="35a4c-116">To create an F# script, create a file with the `.fsx` extension, for example `files.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="35a4c-117">接下来，使用[程序包管理器](package-management.md)如[Paket](https://fsprojects.github.io/Paket/)或[NuGet](https://www.nuget.org/)安装`WindowsAzure.Storage`包和引用`WindowsAzure.Storage.dll`在脚本中使用`#r`指令。</span><span class="sxs-lookup"><span data-stu-id="35a4c-117">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` package and reference `WindowsAzure.Storage.dll` in your script using a `#r` directive.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="35a4c-118">添加命名空间声明</span><span class="sxs-lookup"><span data-stu-id="35a4c-118">Add namespace declarations</span></span>

<span data-ttu-id="35a4c-119">添加以下`open`到顶部的语句`files.fsx`文件：</span><span class="sxs-lookup"><span data-stu-id="35a4c-119">Add the following `open` statements to the top of the `files.fsx` file:</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a><span data-ttu-id="35a4c-120">获取连接字符串</span><span class="sxs-lookup"><span data-stu-id="35a4c-120">Get your connection string</span></span>

<span data-ttu-id="35a4c-121">对于本教程，你将需要一个 Azure 存储连接字符串。</span><span class="sxs-lookup"><span data-stu-id="35a4c-121">You'll need an Azure Storage connection string for this tutorial.</span></span> <span data-ttu-id="35a4c-122">有关连接字符串的详细信息，请参阅[配置存储连接字符串](/azure/storage/storage-configure-connection-string)。</span><span class="sxs-lookup"><span data-stu-id="35a4c-122">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

<span data-ttu-id="35a4c-123">对于本教程中，您将在脚本中，如下输入你的连接字符串：</span><span class="sxs-lookup"><span data-stu-id="35a4c-123">For the tutorial, you'll enter your connection string in your script, like this:</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L11-L11)]

<span data-ttu-id="35a4c-124">但是，这是**不建议**的实际项目。</span><span class="sxs-lookup"><span data-stu-id="35a4c-124">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="35a4c-125">你的存储帐户密钥是类似于你的存储帐户的根密码。</span><span class="sxs-lookup"><span data-stu-id="35a4c-125">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="35a4c-126">始终必须小心地保护你的存储帐户密钥。</span><span class="sxs-lookup"><span data-stu-id="35a4c-126">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="35a4c-127">避免将其分发给其他用户，硬编码，或将其保存在其他人可以访问的纯文本格式的文件。</span><span class="sxs-lookup"><span data-stu-id="35a4c-127">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="35a4c-128">你可以重新生成你使用 Azure 门户，如果你认为可能已泄露的密钥。</span><span class="sxs-lookup"><span data-stu-id="35a4c-128">You can regenerate your key using the Azure Portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="35a4c-129">为实际的应用程序，维护存储连接字符串的最佳方法是在配置文件中。</span><span class="sxs-lookup"><span data-stu-id="35a4c-129">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="35a4c-130">若要从配置文件中提取的连接字符串，您可以执行此操作：</span><span class="sxs-lookup"><span data-stu-id="35a4c-130">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L13-L15)]

<span data-ttu-id="35a4c-131">使用 Azure 配置管理器是可选的。</span><span class="sxs-lookup"><span data-stu-id="35a4c-131">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="35a4c-132">你还可以使用 API，如.NET Framework 的`ConfigurationManager`类型。</span><span class="sxs-lookup"><span data-stu-id="35a4c-132">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="35a4c-133">分析连接字符串</span><span class="sxs-lookup"><span data-stu-id="35a4c-133">Parse the connection string</span></span>

<span data-ttu-id="35a4c-134">若要分析的连接字符串，请使用：</span><span class="sxs-lookup"><span data-stu-id="35a4c-134">To parse the connection string, use:</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L21-L22)]

<span data-ttu-id="35a4c-135">这将返回`CloudStorageAccount`。</span><span class="sxs-lookup"><span data-stu-id="35a4c-135">This will return a `CloudStorageAccount`.</span></span>

### <a name="create-the-file-service-client"></a><span data-ttu-id="35a4c-136">创建文件服务客户端</span><span class="sxs-lookup"><span data-stu-id="35a4c-136">Create the File service client</span></span>

<span data-ttu-id="35a4c-137">`CloudFileClient`类型可让你以编程方式使用文件存储中存储的文件。</span><span class="sxs-lookup"><span data-stu-id="35a4c-137">The `CloudFileClient` type enables you to programmatically use files stored in File storage.</span></span> <span data-ttu-id="35a4c-138">下面是创建服务客户端的一种方法：</span><span class="sxs-lookup"><span data-stu-id="35a4c-138">Here's one way to create the service client:</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L28-L28)]

<span data-ttu-id="35a4c-139">现在，你就可以编写代码，从读取数据并将数据写入文件存储了。</span><span class="sxs-lookup"><span data-stu-id="35a4c-139">Now you are ready to write code that reads data from and writes data to File storage.</span></span>

## <a name="create-a-file-share"></a><span data-ttu-id="35a4c-140">创建文件共享</span><span class="sxs-lookup"><span data-stu-id="35a4c-140">Create a file share</span></span>

<span data-ttu-id="35a4c-141">此示例演示如何创建文件共享，如果不存在：</span><span class="sxs-lookup"><span data-stu-id="35a4c-141">This example shows how to create a file share if it does not already exist:</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L34-L35)]

## <a name="create-a-root-directory-and-a-subdirectory"></a><span data-ttu-id="35a4c-142">创建一个子目录和根目录的目录</span><span class="sxs-lookup"><span data-stu-id="35a4c-142">Create a root directory and a subdirectory</span></span>

<span data-ttu-id="35a4c-143">在此，你将获取根目录并获取子目录的根目录。</span><span class="sxs-lookup"><span data-stu-id="35a4c-143">Here, you get the root directory and get a sub-directory of the root.</span></span> <span data-ttu-id="35a4c-144">如果它们尚不存在，则创建两者。</span><span class="sxs-lookup"><span data-stu-id="35a4c-144">You create both if they don't already exist.</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L41-L43)]

## <a name="upload-text-as-a-file"></a><span data-ttu-id="35a4c-145">将文本上载为文件</span><span class="sxs-lookup"><span data-stu-id="35a4c-145">Upload text as a file</span></span>

<span data-ttu-id="35a4c-146">此示例演示如何将文本作为文件上载。</span><span class="sxs-lookup"><span data-stu-id="35a4c-146">This example shows how to upload text as a file.</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L49-L50)]

### <a name="download-a-file-to-a-local-copy-of-the-file"></a><span data-ttu-id="35a4c-147">将文件下载到文件的本地副本</span><span class="sxs-lookup"><span data-stu-id="35a4c-147">Download a file to a local copy of the file</span></span>

<span data-ttu-id="35a4c-148">此处你下载刚创建的文件附加到本地文件的内容。</span><span class="sxs-lookup"><span data-stu-id="35a4c-148">Here you download the file just created, appending the contents to a local file.</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L56-L56)]

### <a name="set-the-maximum-size-for-a-file-share"></a><span data-ttu-id="35a4c-149">设置文件共享的最大大小</span><span class="sxs-lookup"><span data-stu-id="35a4c-149">Set the maximum size for a file share</span></span>

<span data-ttu-id="35a4c-150">下面的示例演示如何检查共享的当前使用情况以及如何设置共享的配额。</span><span class="sxs-lookup"><span data-stu-id="35a4c-150">The example below shows how to check the current usage for a share and how to set the quota for the share.</span></span> <span data-ttu-id="35a4c-151">`FetchAttributes`必须调用来填充的共享`Properties`，和`SetProperties`传播到 Azure 文件存储的本地更改。</span><span class="sxs-lookup"><span data-stu-id="35a4c-151">`FetchAttributes` must be called to populate a share's `Properties`, and `SetProperties` to propagate local changes to Azure File storage.</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L62-L72)]

### <a name="generate-a-shared-access-signature-for-a-file-or-file-share"></a><span data-ttu-id="35a4c-152">生成的文件或文件共享的共享的访问签名</span><span class="sxs-lookup"><span data-stu-id="35a4c-152">Generate a shared access signature for a file or file share</span></span>

<span data-ttu-id="35a4c-153">你可以生成共享的访问签名 (SAS) 文件共享或单个文件。</span><span class="sxs-lookup"><span data-stu-id="35a4c-153">You can generate a shared access signature (SAS) for a file share or for an individual file.</span></span> <span data-ttu-id="35a4c-154">你还可以在用于管理共享的访问签名的文件共享上创建共享的访问策略。</span><span class="sxs-lookup"><span data-stu-id="35a4c-154">You can also create a shared access policy on a file share to manage shared access signatures.</span></span> <span data-ttu-id="35a4c-155">创建共享的访问策略建议，因为它提供了一种它在受到威胁时撤消 SAS。</span><span class="sxs-lookup"><span data-stu-id="35a4c-155">Creating a shared access policy is recommended, as it provides a means of revoking the SAS if it should be compromised.</span></span>

<span data-ttu-id="35a4c-156">在这里，你创建共享访问共享上的策略，然后使用该策略的共享中文件 SAS 提供约束。</span><span class="sxs-lookup"><span data-stu-id="35a4c-156">Here, you create a shared access policy on a share, and then use that policy to provide the constraints for a SAS on a file in the share.</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L78-L94)]

<span data-ttu-id="35a4c-157">有关创建和使用共享的访问签名的详细信息，请参阅[使用共享访问签名 (SAS)](/azure/storage/storage-dotnet-shared-access-signature-part-1)和[创建并将 SAS 用于 Blob 存储](/azure/storage/storage-dotnet-shared-access-signature-part-2)。</span><span class="sxs-lookup"><span data-stu-id="35a4c-157">For more information about creating and using shared access signatures, see [Using Shared Access Signatures (SAS)](/azure/storage/storage-dotnet-shared-access-signature-part-1) and [Create and use a SAS with Blob storage](/azure/storage/storage-dotnet-shared-access-signature-part-2).</span></span>

### <a name="copy-files"></a><span data-ttu-id="35a4c-158">将文件复制</span><span class="sxs-lookup"><span data-stu-id="35a4c-158">Copy files</span></span>

<span data-ttu-id="35a4c-159">你可以将文件复制到另一个文件或 blob 或将一个 blob 到文件。</span><span class="sxs-lookup"><span data-stu-id="35a4c-159">You can copy a file to another file or to a blob, or a blob to a file.</span></span> <span data-ttu-id="35a4c-160">如果要将 blob 复制到一个文件或文件中的 blob，你*必须*使用共享的访问签名 (SAS) 进行身份验证的源对象，即使在同一存储帐户内复制。</span><span class="sxs-lookup"><span data-stu-id="35a4c-160">If you are copying a blob to a file, or a file to a blob, you *must* use a shared access signature (SAS) to authenticate the source object, even if you are copying within the same storage account.</span></span>

### <a name="copy-a-file-to-another-file"></a><span data-ttu-id="35a4c-161">将文件复制到另一个文件</span><span class="sxs-lookup"><span data-stu-id="35a4c-161">Copy a file to another file</span></span>

<span data-ttu-id="35a4c-162">在这里，你将文件复制到同一共享中的另一个文件。</span><span class="sxs-lookup"><span data-stu-id="35a4c-162">Here, you copy a file to another file in the same share.</span></span> <span data-ttu-id="35a4c-163">因为此复制操作相同的存储帐户中的文件之间进行复制，可以使用共享密钥身份验证来进行复制。</span><span class="sxs-lookup"><span data-stu-id="35a4c-163">Because this copy operation copies between files in the same storage account, you can use Shared Key authentication to perform the copy.</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L100-L101)]

### <a name="copy-a-file-to-a-blob"></a><span data-ttu-id="35a4c-164">将文件复制到 blob</span><span class="sxs-lookup"><span data-stu-id="35a4c-164">Copy a file to a blob</span></span>

<span data-ttu-id="35a4c-165">在这里，您创建一个文件并将其复制到同一存储帐户内的 blob。</span><span class="sxs-lookup"><span data-stu-id="35a4c-165">Here, you create a file and copy it to a blob within the same storage account.</span></span> <span data-ttu-id="35a4c-166">创建源文件，服务用于在复制操作期间验证到源代码文件的访问权限的 SAS。</span><span class="sxs-lookup"><span data-stu-id="35a4c-166">You create a SAS for the source file, which the service uses to authenticate access to the source file during the copy operation.</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L107-L120)]

<span data-ttu-id="35a4c-167">相同的方式，可以将 blob 复制到一个文件。</span><span class="sxs-lookup"><span data-stu-id="35a4c-167">You can copy a blob to a file in the same way.</span></span> <span data-ttu-id="35a4c-168">如果源对象是一个 blob，然后创建一个 SAS 以复制操作期间验证对该 blob 的访问。</span><span class="sxs-lookup"><span data-stu-id="35a4c-168">If the source object is a blob, then create a SAS to authenticate access to that blob during the copy operation.</span></span>

## <a name="troubleshooting-file-storage-using-metrics"></a><span data-ttu-id="35a4c-169">故障排除的文件存储使用度量值</span><span class="sxs-lookup"><span data-stu-id="35a4c-169">Troubleshooting File storage using metrics</span></span>

<span data-ttu-id="35a4c-170">Azure 存储分析支持文件存储的度量值。</span><span class="sxs-lookup"><span data-stu-id="35a4c-170">Azure Storage Analytics supports metrics for File storage.</span></span> <span data-ttu-id="35a4c-171">使用指标数据，你可以跟踪请求和诊断问题。</span><span class="sxs-lookup"><span data-stu-id="35a4c-171">With metrics data, you can trace requests and diagnose issues.</span></span>

<span data-ttu-id="35a4c-172">你可以为存储启用指标文件从[Azure 门户](https://portal.azure.com)，也可以执行从 F # 如下：</span><span class="sxs-lookup"><span data-stu-id="35a4c-172">You can enable metrics for File storage from the [Azure Portal](https://portal.azure.com), or you can do it from F# like this:</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L126-L140)]

## <a name="next-steps"></a><span data-ttu-id="35a4c-173">后续步骤</span><span class="sxs-lookup"><span data-stu-id="35a4c-173">Next steps</span></span>

<span data-ttu-id="35a4c-174">请参阅以下链接以获取有关 Azure 文件存储的详细信息。</span><span class="sxs-lookup"><span data-stu-id="35a4c-174">See these links for more information about Azure File storage.</span></span>

### <a name="conceptual-articles-and-videos"></a><span data-ttu-id="35a4c-175">概念性文章和视频</span><span class="sxs-lookup"><span data-stu-id="35a4c-175">Conceptual articles and videos</span></span>

- [<span data-ttu-id="35a4c-176">Azure 文件存储： 顺畅云 SMB 文件系统的 Windows 和 Linux</span><span class="sxs-lookup"><span data-stu-id="35a4c-176">Azure Files Storage: a frictionless cloud SMB file system for Windows and Linux</span></span>](https://azure.microsoft.com/resources/videos/azurecon-2015-azure-files-storage-a-frictionless-cloud-smb-file-system-for-windows-and-linux/)
- [<span data-ttu-id="35a4c-177">如何通过 Linux 使用 Azure 文件存储</span><span class="sxs-lookup"><span data-stu-id="35a4c-177">How to use Azure File Storage with Linux</span></span>](/azure/storage/storage-how-to-use-files-linux)

### <a name="tooling-support-for-file-storage"></a><span data-ttu-id="35a4c-178">文件存储的工具支持</span><span class="sxs-lookup"><span data-stu-id="35a4c-178">Tooling support for File storage</span></span>

- [<span data-ttu-id="35a4c-179">对 Azure 存储空间使用 Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="35a4c-179">Using Azure PowerShell with Azure Storage</span></span>](/azure/storage/storage-powershell-guide-full)
- [<span data-ttu-id="35a4c-180">如何对 Microsoft Azure 存储空间使用 AzCopy</span><span class="sxs-lookup"><span data-stu-id="35a4c-180">How to use AzCopy with Microsoft Azure Storage</span></span>](/azure/storage/storage-use-azcopy)
- [<span data-ttu-id="35a4c-181">对 Azure 存储空间使用 Azure CLI</span><span class="sxs-lookup"><span data-stu-id="35a4c-181">Using the Azure CLI with Azure Storage</span></span>](/azure/storage/storage-azure-cli#create-and-manage-file-shares)

### <a name="reference"></a><span data-ttu-id="35a4c-182">参考</span><span class="sxs-lookup"><span data-stu-id="35a4c-182">Reference</span></span>

- [<span data-ttu-id="35a4c-183">存储客户端库.NET 参考</span><span class="sxs-lookup"><span data-stu-id="35a4c-183">Storage Client Library for .NET reference</span></span>](https://msdn.microsoft.com/library/azure/mt347887.aspx)
- [<span data-ttu-id="35a4c-184">文件服务 REST API 参考</span><span class="sxs-lookup"><span data-stu-id="35a4c-184">File Service REST API reference</span></span>](/rest/api/storageservices/fileservices/File-Service-REST-API)

### <a name="blog-posts"></a><span data-ttu-id="35a4c-185">博客文章</span><span class="sxs-lookup"><span data-stu-id="35a4c-185">Blog posts</span></span>

- [<span data-ttu-id="35a4c-186">Azure 文件存储现已正式发布</span><span class="sxs-lookup"><span data-stu-id="35a4c-186">Azure File storage is now generally available</span></span>](https://azure.microsoft.com/blog/azure-file-storage-now-generally-available/)
- [<span data-ttu-id="35a4c-187">内的 Azure 文件存储</span><span class="sxs-lookup"><span data-stu-id="35a4c-187">Inside Azure File Storage</span></span>](https://azure.microsoft.com/blog/inside-azure-file-storage/) 
- [<span data-ttu-id="35a4c-188">Microsoft Azure 文件服务简介</span><span class="sxs-lookup"><span data-stu-id="35a4c-188">Introducing Microsoft Azure File Service</span></span>](http://blogs.msdn.com/b/windowsazurestorage/archive/2014/05/12/introducing-microsoft-azure-file-service.aspx)
- [<span data-ttu-id="35a4c-189">将连接保存到 Microsoft Azure 文件</span><span class="sxs-lookup"><span data-stu-id="35a4c-189">Persisting connections to Microsoft Azure Files</span></span>](http://blogs.msdn.com/b/windowsazurestorage/archive/2014/05/27/persisting-connections-to-microsoft-azure-files.aspx)
