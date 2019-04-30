---
title: 开始使用 Azure 文件存储使用F#
description: 使用 Azure 文件存储在云中存储文件数据和从 Azure 虚拟机 (VM) 装载云文件共享或从本地应用程序运行 Windows。
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: fa6dadc863bb9116cfac5afd7cd22a724bc7afe2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62031221"
---
# <a name="get-started-with-azure-file-storage-using-f"></a><span data-ttu-id="b17e9-103">Azure 文件存储使用 F 入门\#</span><span class="sxs-lookup"><span data-stu-id="b17e9-103">Get started with Azure File storage using F\#</span></span>

<span data-ttu-id="b17e9-104">Azure 文件存储是一种服务，提供在云中使用标准文件共享[服务器消息块 (SMB) 协议](https://msdn.microsoft.com/library/windows/desktop/aa365233.aspx)。</span><span class="sxs-lookup"><span data-stu-id="b17e9-104">Azure File storage is a service that offers file shares in the cloud using the standard [Server Message Block (SMB) Protocol](https://msdn.microsoft.com/library/windows/desktop/aa365233.aspx).</span></span> <span data-ttu-id="b17e9-105">支持 SMB 2.1 和 SMB 3.0。</span><span class="sxs-lookup"><span data-stu-id="b17e9-105">Both SMB 2.1 and SMB 3.0 are supported.</span></span> <span data-ttu-id="b17e9-106">使用 Azure 文件存储，你可以迁移依赖文件共享到 Azure，快速且无成本高昂的重写的旧版应用程序。</span><span class="sxs-lookup"><span data-stu-id="b17e9-106">With Azure File storage, you can migrate legacy applications that rely on file shares to Azure quickly and without costly rewrites.</span></span> <span data-ttu-id="b17e9-107">在 Azure 虚拟机或云服务或从本地客户端运行的应用程序可以装载文件共享在云中，就像桌面应用程序装载典型 SMB 共享一样。</span><span class="sxs-lookup"><span data-stu-id="b17e9-107">Applications running in Azure virtual machines or cloud services or from on-premises clients can mount a file share in the cloud, just as a desktop application mounts a typical SMB share.</span></span> <span data-ttu-id="b17e9-108">任意数量的应用程序组件可以然后装载并同时访问文件存储共享。</span><span class="sxs-lookup"><span data-stu-id="b17e9-108">Any number of application components can then mount and access the File storage share simultaneously.</span></span>

<span data-ttu-id="b17e9-109">有关文件存储的概念概述，请参阅[文件存储的.NET 指南](/azure/storage/storage-dotnet-how-to-use-files)。</span><span class="sxs-lookup"><span data-stu-id="b17e9-109">For a conceptual overview of file storage, please see [the .NET guide for file storage](/azure/storage/storage-dotnet-how-to-use-files).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b17e9-110">系统必备</span><span class="sxs-lookup"><span data-stu-id="b17e9-110">Prerequisites</span></span>

<span data-ttu-id="b17e9-111">若要使用本指南，您必须首先[创建 Azure 存储帐户](/azure/storage/storage-create-storage-account)。</span><span class="sxs-lookup"><span data-stu-id="b17e9-111">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account).</span></span>
<span data-ttu-id="b17e9-112">此外需要为此帐户存储访问密钥。</span><span class="sxs-lookup"><span data-stu-id="b17e9-112">You'll also need your storage access key for this account.</span></span>

## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="b17e9-113">创建F#脚本并启动F#交互式</span><span class="sxs-lookup"><span data-stu-id="b17e9-113">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="b17e9-114">这篇文章中的示例可在F#应用程序或F#脚本。</span><span class="sxs-lookup"><span data-stu-id="b17e9-114">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="b17e9-115">若要创建F#脚本，创建的文件`.fsx`扩展，例如`files.fsx`，在你F#开发环境。</span><span class="sxs-lookup"><span data-stu-id="b17e9-115">To create an F# script, create a file with the `.fsx` extension, for example `files.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="b17e9-116">接下来，使用[程序包管理器](package-management.md)如[paket 依存](https://fsprojects.github.io/Paket/)或[NuGet](https://www.nuget.org/)安装`WindowsAzure.Storage`程序包和引用`WindowsAzure.Storage.dll`使用在脚本中`#r`指令。</span><span class="sxs-lookup"><span data-stu-id="b17e9-116">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` package and reference `WindowsAzure.Storage.dll` in your script using a `#r` directive.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="b17e9-117">添加命名空间声明</span><span class="sxs-lookup"><span data-stu-id="b17e9-117">Add namespace declarations</span></span>

<span data-ttu-id="b17e9-118">添加以下`open`顶部的语句`files.fsx`文件：</span><span class="sxs-lookup"><span data-stu-id="b17e9-118">Add the following `open` statements to the top of the `files.fsx` file:</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a><span data-ttu-id="b17e9-119">获取连接字符串</span><span class="sxs-lookup"><span data-stu-id="b17e9-119">Get your connection string</span></span>

<span data-ttu-id="b17e9-120">对于本教程需要 Azure 存储连接字符串。</span><span class="sxs-lookup"><span data-stu-id="b17e9-120">You'll need an Azure Storage connection string for this tutorial.</span></span> <span data-ttu-id="b17e9-121">有关连接字符串的详细信息，请参阅[配置存储连接字符串](/azure/storage/storage-configure-connection-string)。</span><span class="sxs-lookup"><span data-stu-id="b17e9-121">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

<span data-ttu-id="b17e9-122">本教程中，将在脚本中，此类输入你的连接字符串：</span><span class="sxs-lookup"><span data-stu-id="b17e9-122">For the tutorial, you'll enter your connection string in your script, like this:</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L11-L11)]

<span data-ttu-id="b17e9-123">但是，这是**不建议这样做**为实际项目。</span><span class="sxs-lookup"><span data-stu-id="b17e9-123">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="b17e9-124">你的存储帐户密钥是类似于你的存储帐户的根密码。</span><span class="sxs-lookup"><span data-stu-id="b17e9-124">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="b17e9-125">始终要小心保护存储帐户密钥。</span><span class="sxs-lookup"><span data-stu-id="b17e9-125">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="b17e9-126">避免将其分发给其他用户，硬编码，或将其保存在其他人可以访问的纯文本格式的文件。</span><span class="sxs-lookup"><span data-stu-id="b17e9-126">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="b17e9-127">您可以重新生成你使用 Azure 门户，如果你认为可能已泄露的密钥。</span><span class="sxs-lookup"><span data-stu-id="b17e9-127">You can regenerate your key using the Azure Portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="b17e9-128">为实际的应用程序，维护存储连接字符串的最佳方法是在配置文件中。</span><span class="sxs-lookup"><span data-stu-id="b17e9-128">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="b17e9-129">若要从配置文件中提取的连接字符串，可以执行此操作：</span><span class="sxs-lookup"><span data-stu-id="b17e9-129">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L13-L15)]

<span data-ttu-id="b17e9-130">使用 Azure 配置管理器是可选的。</span><span class="sxs-lookup"><span data-stu-id="b17e9-130">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="b17e9-131">此外可以使用诸如.NET Framework 的 API`ConfigurationManager`类型。</span><span class="sxs-lookup"><span data-stu-id="b17e9-131">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="b17e9-132">分析连接字符串</span><span class="sxs-lookup"><span data-stu-id="b17e9-132">Parse the connection string</span></span>

<span data-ttu-id="b17e9-133">若要分析的连接字符串，请使用：</span><span class="sxs-lookup"><span data-stu-id="b17e9-133">To parse the connection string, use:</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L21-L22)]

<span data-ttu-id="b17e9-134">这将返回`CloudStorageAccount`。</span><span class="sxs-lookup"><span data-stu-id="b17e9-134">This will return a `CloudStorageAccount`.</span></span>

### <a name="create-the-file-service-client"></a><span data-ttu-id="b17e9-135">创建文件服务客户端</span><span class="sxs-lookup"><span data-stu-id="b17e9-135">Create the File service client</span></span>

<span data-ttu-id="b17e9-136">`CloudFileClient`类型可让你以编程方式使用文件存储中存储的文件。</span><span class="sxs-lookup"><span data-stu-id="b17e9-136">The `CloudFileClient` type enables you to programmatically use files stored in File storage.</span></span> <span data-ttu-id="b17e9-137">下面是创建服务客户端的一种方法：</span><span class="sxs-lookup"><span data-stu-id="b17e9-137">Here's one way to create the service client:</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L28-L28)]

<span data-ttu-id="b17e9-138">现在已准备好编写代码，读取数据并将数据写入到文件存储。</span><span class="sxs-lookup"><span data-stu-id="b17e9-138">Now you are ready to write code that reads data from and writes data to File storage.</span></span>

## <a name="create-a-file-share"></a><span data-ttu-id="b17e9-139">创建文件共享</span><span class="sxs-lookup"><span data-stu-id="b17e9-139">Create a file share</span></span>

<span data-ttu-id="b17e9-140">此示例演示如何创建文件共享，如果尚不存在：</span><span class="sxs-lookup"><span data-stu-id="b17e9-140">This example shows how to create a file share if it does not already exist:</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L34-L35)]

## <a name="create-a-root-directory-and-a-subdirectory"></a><span data-ttu-id="b17e9-141">创建根目录和子目录</span><span class="sxs-lookup"><span data-stu-id="b17e9-141">Create a root directory and a subdirectory</span></span>

<span data-ttu-id="b17e9-142">在此，您将获取的根目录，并获取根目录的子目录。</span><span class="sxs-lookup"><span data-stu-id="b17e9-142">Here, you get the root directory and get a sub-directory of the root.</span></span> <span data-ttu-id="b17e9-143">如果它们尚不存在，则创建两者。</span><span class="sxs-lookup"><span data-stu-id="b17e9-143">You create both if they don't already exist.</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L41-L43)]

## <a name="upload-text-as-a-file"></a><span data-ttu-id="b17e9-144">将文本作为一个文件上传</span><span class="sxs-lookup"><span data-stu-id="b17e9-144">Upload text as a file</span></span>

<span data-ttu-id="b17e9-145">此示例演示如何将文本作为一个文件上传。</span><span class="sxs-lookup"><span data-stu-id="b17e9-145">This example shows how to upload text as a file.</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L49-L50)]

### <a name="download-a-file-to-a-local-copy-of-the-file"></a><span data-ttu-id="b17e9-146">将文件下载到文件的本地副本</span><span class="sxs-lookup"><span data-stu-id="b17e9-146">Download a file to a local copy of the file</span></span>

<span data-ttu-id="b17e9-147">此处您下载刚创建的文件将内容追加到本地文件。</span><span class="sxs-lookup"><span data-stu-id="b17e9-147">Here you download the file just created, appending the contents to a local file.</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L56-L56)]

### <a name="set-the-maximum-size-for-a-file-share"></a><span data-ttu-id="b17e9-148">设置文件共享的最大大小</span><span class="sxs-lookup"><span data-stu-id="b17e9-148">Set the maximum size for a file share</span></span>

<span data-ttu-id="b17e9-149">以下示例演示如何检查共享当前使用情况以及如何设置共享的配额。</span><span class="sxs-lookup"><span data-stu-id="b17e9-149">The example below shows how to check the current usage for a share and how to set the quota for the share.</span></span> <span data-ttu-id="b17e9-150">`FetchAttributes` 必须调用来填充的共享`Properties`，和`SetProperties`传播到 Azure 文件存储的本地更改。</span><span class="sxs-lookup"><span data-stu-id="b17e9-150">`FetchAttributes` must be called to populate a share's `Properties`, and `SetProperties` to propagate local changes to Azure File storage.</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L62-L72)]

### <a name="generate-a-shared-access-signature-for-a-file-or-file-share"></a><span data-ttu-id="b17e9-151">生成共享的访问签名的文件或文件共享</span><span class="sxs-lookup"><span data-stu-id="b17e9-151">Generate a shared access signature for a file or file share</span></span>

<span data-ttu-id="b17e9-152">可以生成共享的访问签名 (SAS) 文件共享或单个文件。</span><span class="sxs-lookup"><span data-stu-id="b17e9-152">You can generate a shared access signature (SAS) for a file share or for an individual file.</span></span> <span data-ttu-id="b17e9-153">此外可以用于管理共享的访问签名的文件共享上创建共享的访问策略。</span><span class="sxs-lookup"><span data-stu-id="b17e9-153">You can also create a shared access policy on a file share to manage shared access signatures.</span></span> <span data-ttu-id="b17e9-154">创建共享的访问策略建议，因为它提供了它在受到威胁时撤消 SAS 的一种方式。</span><span class="sxs-lookup"><span data-stu-id="b17e9-154">Creating a shared access policy is recommended, as it provides a means of revoking the SAS if it should be compromised.</span></span>

<span data-ttu-id="b17e9-155">在这里，创建共享访问策略在共享上，并将该策略以便提供对共享中文件的 SAS 的约束。</span><span class="sxs-lookup"><span data-stu-id="b17e9-155">Here, you create a shared access policy on a share, and then use that policy to provide the constraints for a SAS on a file in the share.</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L78-L94)]

<span data-ttu-id="b17e9-156">有关创建和使用共享的访问签名的详细信息，请参阅[使用共享访问签名 (SAS)](/azure/storage/storage-dotnet-shared-access-signature-part-1)并[创建并将 SAS 用于 Blob 存储](/azure/storage/storage-dotnet-shared-access-signature-part-2)。</span><span class="sxs-lookup"><span data-stu-id="b17e9-156">For more information about creating and using shared access signatures, see [Using Shared Access Signatures (SAS)](/azure/storage/storage-dotnet-shared-access-signature-part-1) and [Create and use a SAS with Blob storage](/azure/storage/storage-dotnet-shared-access-signature-part-2).</span></span>

### <a name="copy-files"></a><span data-ttu-id="b17e9-157">将文件复制</span><span class="sxs-lookup"><span data-stu-id="b17e9-157">Copy files</span></span>

<span data-ttu-id="b17e9-158">您可以将文件复制到另一个文件或 blob 或将一个 blob 到文件。</span><span class="sxs-lookup"><span data-stu-id="b17e9-158">You can copy a file to another file or to a blob, or a blob to a file.</span></span> <span data-ttu-id="b17e9-159">如果要将 blob 复制到一个文件或某个文件到一个 blob，你*必须*使用共享的访问签名 (SAS) 进行身份验证的源对象，即使相同的存储帐户内进行复制。</span><span class="sxs-lookup"><span data-stu-id="b17e9-159">If you are copying a blob to a file, or a file to a blob, you *must* use a shared access signature (SAS) to authenticate the source object, even if you are copying within the same storage account.</span></span>

### <a name="copy-a-file-to-another-file"></a><span data-ttu-id="b17e9-160">将文件复制到另一个文件</span><span class="sxs-lookup"><span data-stu-id="b17e9-160">Copy a file to another file</span></span>

<span data-ttu-id="b17e9-161">在这里，您将文件复制到同一共享中的另一个文件。</span><span class="sxs-lookup"><span data-stu-id="b17e9-161">Here, you copy a file to another file in the same share.</span></span> <span data-ttu-id="b17e9-162">因为此复制操作在相同的存储帐户中的文件之间进行复制，可以使用共享密钥身份验证来执行复制。</span><span class="sxs-lookup"><span data-stu-id="b17e9-162">Because this copy operation copies between files in the same storage account, you can use Shared Key authentication to perform the copy.</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L100-L101)]

### <a name="copy-a-file-to-a-blob"></a><span data-ttu-id="b17e9-163">将文件复制到 blob</span><span class="sxs-lookup"><span data-stu-id="b17e9-163">Copy a file to a blob</span></span>

<span data-ttu-id="b17e9-164">在这里，创建一个文件并将其复制到同一存储帐户内的 blob。</span><span class="sxs-lookup"><span data-stu-id="b17e9-164">Here, you create a file and copy it to a blob within the same storage account.</span></span> <span data-ttu-id="b17e9-165">创建源文件，该服务用于在复制操作期间验证源文件的访问权限的 SAS。</span><span class="sxs-lookup"><span data-stu-id="b17e9-165">You create a SAS for the source file, which the service uses to authenticate access to the source file during the copy operation.</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L107-L120)]

<span data-ttu-id="b17e9-166">相同的方式，可以将 blob 复制到一个文件。</span><span class="sxs-lookup"><span data-stu-id="b17e9-166">You can copy a blob to a file in the same way.</span></span> <span data-ttu-id="b17e9-167">如果源对象是一个 blob，然后创建一个 SAS 以复制操作期间对该 blob 的访问进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="b17e9-167">If the source object is a blob, then create a SAS to authenticate access to that blob during the copy operation.</span></span>

## <a name="troubleshooting-file-storage-using-metrics"></a><span data-ttu-id="b17e9-168">故障排除的文件存储使用指标</span><span class="sxs-lookup"><span data-stu-id="b17e9-168">Troubleshooting File storage using metrics</span></span>

<span data-ttu-id="b17e9-169">Azure 存储分析针对文件存储支持的指标。</span><span class="sxs-lookup"><span data-stu-id="b17e9-169">Azure Storage Analytics supports metrics for File storage.</span></span> <span data-ttu-id="b17e9-170">使用指标数据，可以跟踪请求和诊断问题。</span><span class="sxs-lookup"><span data-stu-id="b17e9-170">With metrics data, you can trace requests and diagnose issues.</span></span>

<span data-ttu-id="b17e9-171">可以启用对从文件存储的指标[Azure 门户](https://portal.azure.com)，也可以从F#如下所示：</span><span class="sxs-lookup"><span data-stu-id="b17e9-171">You can enable metrics for File storage from the [Azure Portal](https://portal.azure.com), or you can do it from F# like this:</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L126-L140)]

## <a name="next-steps"></a><span data-ttu-id="b17e9-172">后续步骤</span><span class="sxs-lookup"><span data-stu-id="b17e9-172">Next steps</span></span>

<span data-ttu-id="b17e9-173">请参阅以下链接详细了解 Azure 文件存储。</span><span class="sxs-lookup"><span data-stu-id="b17e9-173">See these links for more information about Azure File storage.</span></span>

### <a name="conceptual-articles-and-videos"></a><span data-ttu-id="b17e9-174">概念性文章和视频</span><span class="sxs-lookup"><span data-stu-id="b17e9-174">Conceptual articles and videos</span></span>

- [<span data-ttu-id="b17e9-175">Azure 文件存储： 顺畅的云 SMB 文件系统适用于 Windows 和 Linux</span><span class="sxs-lookup"><span data-stu-id="b17e9-175">Azure Files Storage: a frictionless cloud SMB file system for Windows and Linux</span></span>](https://azure.microsoft.com/resources/videos/azurecon-2015-azure-files-storage-a-frictionless-cloud-smb-file-system-for-windows-and-linux/)
- [<span data-ttu-id="b17e9-176">如何通过 Linux 使用 Azure 文件存储</span><span class="sxs-lookup"><span data-stu-id="b17e9-176">How to use Azure File Storage with Linux</span></span>](/azure/storage/storage-how-to-use-files-linux)

### <a name="tooling-support-for-file-storage"></a><span data-ttu-id="b17e9-177">文件存储的工具支持</span><span class="sxs-lookup"><span data-stu-id="b17e9-177">Tooling support for File storage</span></span>

- [<span data-ttu-id="b17e9-178">对 Azure 存储使用 Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="b17e9-178">Using Azure PowerShell with Azure Storage</span></span>](/azure/storage/storage-powershell-guide-full)
- [<span data-ttu-id="b17e9-179">如何使用 Microsoft Azure 存储 AzCopy</span><span class="sxs-lookup"><span data-stu-id="b17e9-179">How to use AzCopy with Microsoft Azure Storage</span></span>](/azure/storage/storage-use-azcopy)
- [<span data-ttu-id="b17e9-180">使用 Azure CLI 与 Azure 存储</span><span class="sxs-lookup"><span data-stu-id="b17e9-180">Using the Azure CLI with Azure Storage</span></span>](/azure/storage/storage-azure-cli#create-and-manage-file-shares)

### <a name="reference"></a><span data-ttu-id="b17e9-181">参考</span><span class="sxs-lookup"><span data-stu-id="b17e9-181">Reference</span></span>

- [<span data-ttu-id="b17e9-182">存储客户端库.NET 参考</span><span class="sxs-lookup"><span data-stu-id="b17e9-182">Storage Client Library for .NET reference</span></span>](https://msdn.microsoft.com/library/azure/mt347887.aspx)
- [<span data-ttu-id="b17e9-183">文件服务 REST API 参考</span><span class="sxs-lookup"><span data-stu-id="b17e9-183">File Service REST API reference</span></span>](/rest/api/storageservices/fileservices/File-Service-REST-API)

### <a name="blog-posts"></a><span data-ttu-id="b17e9-184">博客文章</span><span class="sxs-lookup"><span data-stu-id="b17e9-184">Blog posts</span></span>

- [<span data-ttu-id="b17e9-185">Azure 文件存储现已公开发布</span><span class="sxs-lookup"><span data-stu-id="b17e9-185">Azure File storage is now generally available</span></span>](https://azure.microsoft.com/blog/azure-file-storage-now-generally-available/)
- [<span data-ttu-id="b17e9-186">Azure 文件存储内部</span><span class="sxs-lookup"><span data-stu-id="b17e9-186">Inside Azure File Storage</span></span>](https://azure.microsoft.com/blog/inside-azure-file-storage/) 
- [<span data-ttu-id="b17e9-187">Microsoft Azure 文件服务简介</span><span class="sxs-lookup"><span data-stu-id="b17e9-187">Introducing Microsoft Azure File Service</span></span>](https://blogs.msdn.microsoft.com/windowsazurestorage/2014/05/12/introducing-microsoft-azure-file-service/)
- [<span data-ttu-id="b17e9-188">将连接保存到 Microsoft Azure 文件</span><span class="sxs-lookup"><span data-stu-id="b17e9-188">Persisting connections to Microsoft Azure Files</span></span>](https://blogs.msdn.microsoft.com/windowsazurestorage/2014/05/26/persisting-connections-to-microsoft-azure-files/)
