---
title: 通过 F# 实现 Azure Blob 入门
description: 使用 Azure Blob 存储在云中存储非结构化的数据。
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: 3d020c2cd9a11db1cd4b7a60113e1be03655f763
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2019
ms.locfileid: "65880038"
---
# <a name="get-started-with-azure-blob-storage-using-f"></a><span data-ttu-id="0412f-103">开始使用 Azure Blob 存储中使用 F\#</span><span class="sxs-lookup"><span data-stu-id="0412f-103">Get started with Azure Blob storage using F\#</span></span>

<span data-ttu-id="0412f-104">Azure Blob 存储是将非结构化数据作为对象/blob 存储在云中的服务。</span><span class="sxs-lookup"><span data-stu-id="0412f-104">Azure Blob storage is a service that stores unstructured data in the cloud as objects/blobs.</span></span> <span data-ttu-id="0412f-105">Blob 存储可以存储任何类型的文本或二进制数据（如文档、媒体文件或应用程序安装程序）。</span><span class="sxs-lookup"><span data-stu-id="0412f-105">Blob storage can store any type of text or binary data, such as a document, media file, or application installer.</span></span> <span data-ttu-id="0412f-106">Blob 存储也称为对象存储。</span><span class="sxs-lookup"><span data-stu-id="0412f-106">Blob storage is also referred to as object storage.</span></span>

<span data-ttu-id="0412f-107">本文介绍如何使用 Blob 存储执行常见任务。</span><span class="sxs-lookup"><span data-stu-id="0412f-107">This article shows you how to perform common tasks using Blob storage.</span></span> <span data-ttu-id="0412f-108">相关示例是使用F#使用用于.NET 的 Azure 存储客户端库。</span><span class="sxs-lookup"><span data-stu-id="0412f-108">The samples are written using F# using the Azure Storage Client Library for .NET.</span></span> <span data-ttu-id="0412f-109">涉及的任务包括如何上传、 列出、 下载和删除 blob。</span><span class="sxs-lookup"><span data-stu-id="0412f-109">The tasks covered include how to upload, list, download, and delete blobs.</span></span>

<span data-ttu-id="0412f-110">有关 blob 存储的概念概述，请参阅[适用于 blob 存储的.NET 指南](/azure/storage/storage-dotnet-how-to-use-blobs)。</span><span class="sxs-lookup"><span data-stu-id="0412f-110">For a conceptual overview of blob storage, see [the .NET guide for blob storage](/azure/storage/storage-dotnet-how-to-use-blobs).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0412f-111">系统必备</span><span class="sxs-lookup"><span data-stu-id="0412f-111">Prerequisites</span></span>

<span data-ttu-id="0412f-112">若要使用本指南，您必须首先[创建 Azure 存储帐户](/azure/storage/storage-create-storage-account)。</span><span class="sxs-lookup"><span data-stu-id="0412f-112">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account).</span></span> <span data-ttu-id="0412f-113">为此帐户还需要存储访问密钥。</span><span class="sxs-lookup"><span data-stu-id="0412f-113">You also need your storage access key for this account.</span></span>

## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="0412f-114">创建F#脚本并启动F#交互式</span><span class="sxs-lookup"><span data-stu-id="0412f-114">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="0412f-115">这篇文章中的示例可在F#应用程序或F#脚本。</span><span class="sxs-lookup"><span data-stu-id="0412f-115">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="0412f-116">若要创建F#脚本，创建的文件`.fsx`扩展，例如`blobs.fsx`，在你F#开发环境。</span><span class="sxs-lookup"><span data-stu-id="0412f-116">To create an F# script, create a file with the `.fsx` extension, for example `blobs.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="0412f-117">接下来，使用[程序包管理器](package-management.md)如[paket 依存](https://fsprojects.github.io/Paket/)或[NuGet](https://www.nuget.org/)安装`WindowsAzure.Storage`并`Microsoft.WindowsAzure.ConfigurationManager`包和引用`WindowsAzure.Storage.dll`和`Microsoft.WindowsAzure.Configuration.dll`脚本使用`#r`指令。</span><span class="sxs-lookup"><span data-stu-id="0412f-117">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` and `Microsoft.WindowsAzure.ConfigurationManager` packages and reference `WindowsAzure.Storage.dll` and `Microsoft.WindowsAzure.Configuration.dll` in your script using a `#r` directive.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="0412f-118">添加命名空间声明</span><span class="sxs-lookup"><span data-stu-id="0412f-118">Add namespace declarations</span></span>

<span data-ttu-id="0412f-119">添加以下`open`顶部的语句`blobs.fsx`文件：</span><span class="sxs-lookup"><span data-stu-id="0412f-119">Add the following `open` statements to the top of the `blobs.fsx` file:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a><span data-ttu-id="0412f-120">获取连接字符串</span><span class="sxs-lookup"><span data-stu-id="0412f-120">Get your connection string</span></span>

<span data-ttu-id="0412f-121">对于本教程需要 Azure 存储连接字符串。</span><span class="sxs-lookup"><span data-stu-id="0412f-121">You need an Azure Storage connection string for this tutorial.</span></span> <span data-ttu-id="0412f-122">有关连接字符串的详细信息，请参阅[配置存储连接字符串](/azure/storage/storage-configure-connection-string)。</span><span class="sxs-lookup"><span data-stu-id="0412f-122">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

<span data-ttu-id="0412f-123">本教程中，在脚本中，此类输入连接字符串：</span><span class="sxs-lookup"><span data-stu-id="0412f-123">For the tutorial, you enter your connection string in your script, like this:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L11-L11)]

<span data-ttu-id="0412f-124">但是，这是**不建议这样做**为实际项目。</span><span class="sxs-lookup"><span data-stu-id="0412f-124">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="0412f-125">你的存储帐户密钥是类似于你的存储帐户的根密码。</span><span class="sxs-lookup"><span data-stu-id="0412f-125">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="0412f-126">始终要小心保护存储帐户密钥。</span><span class="sxs-lookup"><span data-stu-id="0412f-126">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="0412f-127">避免将其分发给其他用户，硬编码，或将其保存在其他人可以访问的纯文本格式的文件。</span><span class="sxs-lookup"><span data-stu-id="0412f-127">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="0412f-128">您可以重新生成你使用 Azure 门户，如果你认为可能已泄露的密钥。</span><span class="sxs-lookup"><span data-stu-id="0412f-128">You can regenerate your key using the Azure Portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="0412f-129">为实际的应用程序，维护存储连接字符串的最佳方法是在配置文件中。</span><span class="sxs-lookup"><span data-stu-id="0412f-129">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="0412f-130">若要从配置文件中提取的连接字符串，可以执行此操作：</span><span class="sxs-lookup"><span data-stu-id="0412f-130">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L13-L15)]

<span data-ttu-id="0412f-131">使用 Azure 配置管理器是可选的。</span><span class="sxs-lookup"><span data-stu-id="0412f-131">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="0412f-132">此外可以使用诸如.NET Framework 的 API`ConfigurationManager`类型。</span><span class="sxs-lookup"><span data-stu-id="0412f-132">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="0412f-133">分析连接字符串</span><span class="sxs-lookup"><span data-stu-id="0412f-133">Parse the connection string</span></span>

<span data-ttu-id="0412f-134">若要分析的连接字符串，请使用：</span><span class="sxs-lookup"><span data-stu-id="0412f-134">To parse the connection string, use:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L21-L22)]

<span data-ttu-id="0412f-135">这将返回`CloudStorageAccount`。</span><span class="sxs-lookup"><span data-stu-id="0412f-135">This returns a `CloudStorageAccount`.</span></span>

### <a name="create-some-local-dummy-data"></a><span data-ttu-id="0412f-136">创建一些本地虚拟数据</span><span class="sxs-lookup"><span data-stu-id="0412f-136">Create some local dummy data</span></span>

<span data-ttu-id="0412f-137">在开始之前，请在我们的脚本的目录中创建一些虚拟的本地数据。</span><span class="sxs-lookup"><span data-stu-id="0412f-137">Before you begin, create some dummy local data in the directory of our script.</span></span> <span data-ttu-id="0412f-138">稍后您将此数据上传。</span><span class="sxs-lookup"><span data-stu-id="0412f-138">Later you upload this data.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L28-L30)]

### <a name="create-the-blob-service-client"></a><span data-ttu-id="0412f-139">创建 Blob 服务客户端</span><span class="sxs-lookup"><span data-stu-id="0412f-139">Create the Blob service client</span></span>

<span data-ttu-id="0412f-140">`CloudBlobClient`类型使你能够检索存储在 Blob 存储中容器和 blob。</span><span class="sxs-lookup"><span data-stu-id="0412f-140">The `CloudBlobClient` type enables you to retrieve containers and blobs stored in Blob storage.</span></span> <span data-ttu-id="0412f-141">下面是创建服务客户端的一种方法：</span><span class="sxs-lookup"><span data-stu-id="0412f-141">Here's one way to create the service client:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L36-L36)]

<span data-ttu-id="0412f-142">现在已准备好编写代码，读取数据并将数据写入到 Blob 存储。</span><span class="sxs-lookup"><span data-stu-id="0412f-142">Now you are ready to write code that reads data from and writes data to Blob storage.</span></span>

## <a name="create-a-container"></a><span data-ttu-id="0412f-143">创建容器</span><span class="sxs-lookup"><span data-stu-id="0412f-143">Create a container</span></span>

<span data-ttu-id="0412f-144">此示例演示如何创建一个容器，如果尚不存在：</span><span class="sxs-lookup"><span data-stu-id="0412f-144">This example shows how to create a container if it does not already exist:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L42-L46)]

<span data-ttu-id="0412f-145">默认情况下，新容器是私有的这意味着，必须指定存储访问密钥才能从该容器下载 blob。</span><span class="sxs-lookup"><span data-stu-id="0412f-145">By default, the new container is private, meaning that you must specify your storage access key to download blobs from this container.</span></span> <span data-ttu-id="0412f-146">如果你想要让容器中的文件可供所有人，你可以将容器设置为公共使用以下代码：</span><span class="sxs-lookup"><span data-stu-id="0412f-146">If you want to make the files within the container available to everyone, you can set the container to be public using the following code:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L48-L49)]

<span data-ttu-id="0412f-147">在 Internet 上的任何人都可以看到公共容器中的 blob，但您可以修改或删除它们仅在具有相应的帐户访问密钥或共享的访问签名。</span><span class="sxs-lookup"><span data-stu-id="0412f-147">Anyone on the Internet can see blobs in a public container, but you can modify or delete them only if you have the appropriate account access key or a shared access signature.</span></span>

## <a name="upload-a-blob-into-a-container"></a><span data-ttu-id="0412f-148">一个 blob 上传到容器</span><span class="sxs-lookup"><span data-stu-id="0412f-148">Upload a blob into a container</span></span>

<span data-ttu-id="0412f-149">Azure Blob 存储支持块 blob 和页 blob。</span><span class="sxs-lookup"><span data-stu-id="0412f-149">Azure Blob Storage supports block blobs and page blobs.</span></span> <span data-ttu-id="0412f-150">在大多数情况下，块 blob 是要使用的建议的类型。</span><span class="sxs-lookup"><span data-stu-id="0412f-150">In most cases, a block blob is the recommended type to use.</span></span>

<span data-ttu-id="0412f-151">若要将文件上载到块 blob，获取容器引用，并使用它获取块 blob 引用。</span><span class="sxs-lookup"><span data-stu-id="0412f-151">To upload a file to a block blob, get a container reference and use it to get a block blob reference.</span></span> <span data-ttu-id="0412f-152">Blob 引用后，您可以将任何数据流上载的数据到它通过调用`UploadFromFile`方法。</span><span class="sxs-lookup"><span data-stu-id="0412f-152">Once you have a blob reference, you can upload any stream of data to it by calling the `UploadFromFile` method.</span></span> <span data-ttu-id="0412f-153">如果以前不存在，或者覆盖它，如果存在，此操作将创建 blob。</span><span class="sxs-lookup"><span data-stu-id="0412f-153">This operation creates the blob if it didn't previously exist, or overwrite it if it does exist.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L55-L59)]

## <a name="list-the-blobs-in-a-container"></a><span data-ttu-id="0412f-154">列出容器中的 blob</span><span class="sxs-lookup"><span data-stu-id="0412f-154">List the blobs in a container</span></span>

<span data-ttu-id="0412f-155">若要列出容器中的 blob，首先获取容器引用。</span><span class="sxs-lookup"><span data-stu-id="0412f-155">To list the blobs in a container, first get a container reference.</span></span> <span data-ttu-id="0412f-156">然后，可以使用容器的`ListBlobs`方法来检索其中的 blob 和/或目录。</span><span class="sxs-lookup"><span data-stu-id="0412f-156">You can then use the container's `ListBlobs` method to retrieve the blobs and/or directories within it.</span></span> <span data-ttu-id="0412f-157">若要访问的属性和方法返回丰富`IListBlobItem`，你必须将其转换为`CloudBlockBlob`， `CloudPageBlob`，或`CloudBlobDirectory`对象。</span><span class="sxs-lookup"><span data-stu-id="0412f-157">To access the rich set of properties and methods for a returned `IListBlobItem`, you must cast it to a `CloudBlockBlob`, `CloudPageBlob`, or `CloudBlobDirectory` object.</span></span> <span data-ttu-id="0412f-158">如果类型未知，可以使用类型检查来确定要将其转换为。</span><span class="sxs-lookup"><span data-stu-id="0412f-158">If the type is unknown, you can use a type check to determine which to cast it to.</span></span> <span data-ttu-id="0412f-159">下面的代码演示如何检索和输出中的每个项的 URI`mydata`容器：</span><span class="sxs-lookup"><span data-stu-id="0412f-159">The following code demonstrates how to retrieve and output the URI of each item in the `mydata` container:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L67-L80)]

<span data-ttu-id="0412f-160">您还可以包含在其名称中的路径信息的名称 blob。</span><span class="sxs-lookup"><span data-stu-id="0412f-160">You can also name blobs with path information in their names.</span></span> <span data-ttu-id="0412f-161">这将创建一个虚拟目录结构，您可以组织和遍历像传统文件系统一样。</span><span class="sxs-lookup"><span data-stu-id="0412f-161">This creates a virtual directory structure that you can organize and traverse as you would a traditional file system.</span></span> <span data-ttu-id="0412f-162">请注意，目录结构仅仅是虚拟-可在 Blob 存储的唯一资源是容器和 blob。</span><span class="sxs-lookup"><span data-stu-id="0412f-162">Note that the directory structure is virtual only - the only resources available in Blob storage are containers and blobs.</span></span> <span data-ttu-id="0412f-163">但是，存储客户端库提供`CloudBlobDirectory`对象来引用虚拟目录，并简化过程的这种方式组织的 blob 的使用。</span><span class="sxs-lookup"><span data-stu-id="0412f-163">However, the storage client library offers a `CloudBlobDirectory` object to refer to a virtual directory and simplify the process of working with blobs that are organized in this way.</span></span>

<span data-ttu-id="0412f-164">例如，考虑名为的容器的块 blob 的下面一`photos`:</span><span class="sxs-lookup"><span data-stu-id="0412f-164">For example, consider the following set of block blobs in a container named `photos`:</span></span>

<span data-ttu-id="0412f-165">*photo1.jpg*\\</span><span class="sxs-lookup"><span data-stu-id="0412f-165">*photo1.jpg*\\</span></span>
<span data-ttu-id="0412f-166">*2015/architecture/description.txt*\\</span><span class="sxs-lookup"><span data-stu-id="0412f-166">*2015/architecture/description.txt*\\</span></span>
<span data-ttu-id="0412f-167">*2015/architecture/photo3.jpg*\\</span><span class="sxs-lookup"><span data-stu-id="0412f-167">*2015/architecture/photo3.jpg*\\</span></span>
<span data-ttu-id="0412f-168">*2015/architecture/photo4.jpg*\\</span><span class="sxs-lookup"><span data-stu-id="0412f-168">*2015/architecture/photo4.jpg*\\</span></span>
<span data-ttu-id="0412f-169">*2016/architecture/photo5.jpg*\\</span><span class="sxs-lookup"><span data-stu-id="0412f-169">*2016/architecture/photo5.jpg*\\</span></span>
<span data-ttu-id="0412f-170">*2016/architecture/photo6.jpg*\\</span><span class="sxs-lookup"><span data-stu-id="0412f-170">*2016/architecture/photo6.jpg*\\</span></span>
<span data-ttu-id="0412f-171">*2016/architecture/description.txt*\\</span><span class="sxs-lookup"><span data-stu-id="0412f-171">*2016/architecture/description.txt*\\</span></span>
<span data-ttu-id="0412f-172">*2016/photo7.jpg*\\</span><span class="sxs-lookup"><span data-stu-id="0412f-172">*2016/photo7.jpg*\\</span></span>

<span data-ttu-id="0412f-173">当您调用`ListBlobs`上 （如上面的示例中） 的容器，将返回一个层次结构列表。</span><span class="sxs-lookup"><span data-stu-id="0412f-173">When you call `ListBlobs` on a container (as in the above sample), a hierarchical listing is returned.</span></span> <span data-ttu-id="0412f-174">如果它同时包含`CloudBlobDirectory`和`CloudBlockBlob`对象，分别表示目录和 blob 容器中的，则生成的输出显示类似于下面：</span><span class="sxs-lookup"><span data-stu-id="0412f-174">If it contains both `CloudBlobDirectory` and `CloudBlockBlob` objects, representing the directories and blobs in the container, respectively, then the resulting output looks similar to this:</span></span>

```console
Directory: https://<accountname>.blob.core.windows.net/photos/2015/
Directory: https://<accountname>.blob.core.windows.net/photos/2016/
Block blob of length 505623: https://<accountname>.blob.core.windows.net/photos/photo1.jpg
```

<span data-ttu-id="0412f-175">或者，可以设置`UseFlatBlobListing`的参数`ListBlobs`方法`true`。</span><span class="sxs-lookup"><span data-stu-id="0412f-175">Optionally, you can set the `UseFlatBlobListing` parameter of the `ListBlobs` method to `true`.</span></span> <span data-ttu-id="0412f-176">在这种情况下，每个 blob 容器中的返回作为`CloudBlockBlob`对象。</span><span class="sxs-lookup"><span data-stu-id="0412f-176">In this case, every blob in the container is returned as a `CloudBlockBlob` object.</span></span> <span data-ttu-id="0412f-177">对调用`ListBlobs`返回一个平面列表如下所示：</span><span class="sxs-lookup"><span data-stu-id="0412f-177">The call to `ListBlobs` to return a flat listing looks like this:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L82-L89)]

<span data-ttu-id="0412f-178">而且，具体取决于你的容器的当前内容，结果如下所示：</span><span class="sxs-lookup"><span data-stu-id="0412f-178">and, depending on the current contents of your container, the results look like this:</span></span>

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

## <a name="download-blobs"></a><span data-ttu-id="0412f-179">下载 blob</span><span class="sxs-lookup"><span data-stu-id="0412f-179">Download blobs</span></span>

<span data-ttu-id="0412f-180">若要下载 blob，首先检索 blob 引用，然后调用`DownloadToStream`方法。</span><span class="sxs-lookup"><span data-stu-id="0412f-180">To download blobs, first retrieve a blob reference and then call the `DownloadToStream` method.</span></span> <span data-ttu-id="0412f-181">下面的示例使用`DownloadToStream`方法将 blob 内容传输到稍后可以保存到本地文件的流对象。</span><span class="sxs-lookup"><span data-stu-id="0412f-181">The following example uses the `DownloadToStream` method to transfer the blob contents to a stream object that you can then persist to a local file.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L95-L101)]

<span data-ttu-id="0412f-182">此外可以使用`DownloadToStream`方法下载文本字符串形式将 blob 的内容。</span><span class="sxs-lookup"><span data-stu-id="0412f-182">You can also use the `DownloadToStream` method to download the contents of a blob as a text string.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L103-L106)]

## <a name="delete-blobs"></a><span data-ttu-id="0412f-183">删除 blob</span><span class="sxs-lookup"><span data-stu-id="0412f-183">Delete blobs</span></span>

<span data-ttu-id="0412f-184">若要删除 blob，首先请获取 blob 引用，然后调用`Delete`方法。</span><span class="sxs-lookup"><span data-stu-id="0412f-184">To delete a blob, first get a blob reference and then call the `Delete` method on it.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L112-L116)]

## <a name="list-blobs-in-pages-asynchronously"></a><span data-ttu-id="0412f-185">以异步方式列出页中的 blob</span><span class="sxs-lookup"><span data-stu-id="0412f-185">List blobs in pages asynchronously</span></span>

<span data-ttu-id="0412f-186">如果要列出大量 blob，或者你想要控制在一个列表操作返回的结果数，可以列出页结果中的 blob。</span><span class="sxs-lookup"><span data-stu-id="0412f-186">If you are listing a large number of blobs, or you want to control the number of results you return in one listing operation, you can list blobs in pages of results.</span></span> <span data-ttu-id="0412f-187">此示例演示如何在页中以异步方式返回结果，以便等待返回大量结果时不阻止执行。</span><span class="sxs-lookup"><span data-stu-id="0412f-187">This example shows how to return results in pages asynchronously, so that execution is not blocked while waiting to return a large set of results.</span></span>

<span data-ttu-id="0412f-188">此示例演示平面 blob 列表，但还可以执行分层列表中，通过设置`useFlatBlobListing`的参数`ListBlobsSegmentedAsync`方法`false`。</span><span class="sxs-lookup"><span data-stu-id="0412f-188">This example shows a flat blob listing, but you can also perform a hierarchical listing, by setting the `useFlatBlobListing` parameter of the `ListBlobsSegmentedAsync` method to `false`.</span></span>

<span data-ttu-id="0412f-189">此示例定义一个异步方法，使用`async`块。</span><span class="sxs-lookup"><span data-stu-id="0412f-189">The sample defines an asynchronous method, using an `async` block.</span></span> <span data-ttu-id="0412f-190">``let!``关键字将挂起示例方法的执行，直至列表任务完成。</span><span class="sxs-lookup"><span data-stu-id="0412f-190">The ``let!`` keyword suspends execution of the sample method until the listing task completes.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L122-L160)]

<span data-ttu-id="0412f-191">我们现在可以使用此异步例程，如下所示。</span><span class="sxs-lookup"><span data-stu-id="0412f-191">We can now use this asynchronous routine as follows.</span></span> <span data-ttu-id="0412f-192">首先您将上传一些虚拟数据 （使用在本教程前面创建的本地文件）。</span><span class="sxs-lookup"><span data-stu-id="0412f-192">First you upload some dummy data (using the local file created earlier in this tutorial).</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L162-L166)]

<span data-ttu-id="0412f-193">现在，调用该例程。</span><span class="sxs-lookup"><span data-stu-id="0412f-193">Now, call the routine.</span></span> <span data-ttu-id="0412f-194">您使用`Async.RunSynchronously`以强制执行异步操作。</span><span class="sxs-lookup"><span data-stu-id="0412f-194">You use `Async.RunSynchronously` to force the execution of the asynchronous operation.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L168-L168)]

## <a name="writing-to-an-append-blob"></a><span data-ttu-id="0412f-195">写入追加 blob</span><span class="sxs-lookup"><span data-stu-id="0412f-195">Writing to an append blob</span></span>

<span data-ttu-id="0412f-196">追加 blob 针对追加操作，例如日志记录优化。</span><span class="sxs-lookup"><span data-stu-id="0412f-196">An append blob is optimized for append operations, such as logging.</span></span> <span data-ttu-id="0412f-197">块 blob，相似的追加 blob 块组成，但当将新的块添加到追加 blob，始终追加到 blob 的末尾。</span><span class="sxs-lookup"><span data-stu-id="0412f-197">Like a block blob, an append blob is comprised of blocks, but when you add a new block to an append blob, it is always appended to the end of the blob.</span></span> <span data-ttu-id="0412f-198">无法更新或删除追加 blob 中的现有块。</span><span class="sxs-lookup"><span data-stu-id="0412f-198">You cannot update or delete an existing block in an append blob.</span></span> <span data-ttu-id="0412f-199">追加 blob 的块 Id 不公开，因为它们是用于块 blob。</span><span class="sxs-lookup"><span data-stu-id="0412f-199">The block IDs for an append blob are not exposed as they are for a block blob.</span></span>

<span data-ttu-id="0412f-200">追加 blob 中的每个块可以是不同的大小，最大为 4 MB，并追加 blob 可以包含 50,000 个块的最大值。</span><span class="sxs-lookup"><span data-stu-id="0412f-200">Each block in an append blob can be a different size, up to a maximum of 4 MB, and an append blob can include a maximum of 50,000 blocks.</span></span> <span data-ttu-id="0412f-201">因此，追加 blob 的最大大小是稍微大于 195 GB （4 MB X 50,000 块）。</span><span class="sxs-lookup"><span data-stu-id="0412f-201">The maximum size of an append blob is therefore slightly more than 195 GB (4 MB X 50,000 blocks).</span></span>

<span data-ttu-id="0412f-202">以下示例创建新的追加 blob，并将一些数据追加到其中，模拟一个简单的日志记录操作。</span><span class="sxs-lookup"><span data-stu-id="0412f-202">The following example creates a new append blob and appends some data to it, simulating a simple logging operation.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L174-L203)]

<span data-ttu-id="0412f-203">请参阅[了解块 Blob、 页 Blob 和追加 Blob](https://msdn.microsoft.com/library/azure/ee691964.aspx)有关三种 blob 之间的差异的详细信息。</span><span class="sxs-lookup"><span data-stu-id="0412f-203">See [Understanding Block Blobs, Page Blobs, and Append Blobs](https://msdn.microsoft.com/library/azure/ee691964.aspx) for more information about the differences between the three types of blobs.</span></span>

## <a name="concurrent-access"></a><span data-ttu-id="0412f-204">并发访问</span><span class="sxs-lookup"><span data-stu-id="0412f-204">Concurrent access</span></span>

<span data-ttu-id="0412f-205">若要允许从多个客户端或多个进程实例并发访问到某一 blob，可以使用**Etag**或**租约**。</span><span class="sxs-lookup"><span data-stu-id="0412f-205">To support concurrent access to a blob from multiple clients or multiple process instances, you can use **ETags** or **leases**.</span></span>

* <span data-ttu-id="0412f-206">**Etag** -提供用于检测 blob 或容器已被另一个进程修改</span><span class="sxs-lookup"><span data-stu-id="0412f-206">**Etag** - provides a way to detect that the blob or container has been modified by another process</span></span>

* <span data-ttu-id="0412f-207">**租约**-提供了一种方法来获取独占式可续订写入或删除的一段时间内对 blob 的访问</span><span class="sxs-lookup"><span data-stu-id="0412f-207">**Lease** - provides a way to obtain exclusive, renewable, write or delete access to a blob for a period of time</span></span>

<span data-ttu-id="0412f-208">有关详细信息，请参阅[在 Microsoft Azure 存储管理并发](https://azure.microsoft.com/blog/managing-concurrency-in-microsoft-azure-storage-2/)。</span><span class="sxs-lookup"><span data-stu-id="0412f-208">For more information, see [Managing Concurrency in Microsoft Azure Storage](https://azure.microsoft.com/blog/managing-concurrency-in-microsoft-azure-storage-2/).</span></span>

## <a name="naming-containers"></a><span data-ttu-id="0412f-209">命名容器</span><span class="sxs-lookup"><span data-stu-id="0412f-209">Naming containers</span></span>

<span data-ttu-id="0412f-210">在 Azure 存储中的每个 blob 必须驻留在一个容器。</span><span class="sxs-lookup"><span data-stu-id="0412f-210">Every blob in Azure storage must reside in a container.</span></span> <span data-ttu-id="0412f-211">该容器构成 blob 名称的一部分。</span><span class="sxs-lookup"><span data-stu-id="0412f-211">The container forms part of the blob name.</span></span> <span data-ttu-id="0412f-212">例如，`mydata`是这些示例 blob Uri 中的容器的名称：</span><span class="sxs-lookup"><span data-stu-id="0412f-212">For example, `mydata` is the name of the container in these sample blob URIs:</span></span>

- https://storagesample.blob.core.windows.net/mydata/blob1.txt
- https://storagesample.blob.core.windows.net/mydata/photos/myphoto.jpg

<span data-ttu-id="0412f-213">容器名称必须是有效的 DNS 名称，符合以下命名规则：</span><span class="sxs-lookup"><span data-stu-id="0412f-213">A container name must be a valid DNS name, conforming to the following naming rules:</span></span>

1. <span data-ttu-id="0412f-214">容器名称必须以字母或数字开头，并且可以包含字母、 数字和短划线 （-） 字符。</span><span class="sxs-lookup"><span data-stu-id="0412f-214">Container names must start with a letter or number, and can contain only letters, numbers, and the dash (-) character.</span></span>
1. <span data-ttu-id="0412f-215">必须立即前面和后面以字母或数字; 每个短划线 （-） 字符容器名称中不允许使用连续划线。</span><span class="sxs-lookup"><span data-stu-id="0412f-215">Every dash (-) character must be immediately preceded and followed by a letter or number; consecutive dashes are not permitted in container names.</span></span>
1. <span data-ttu-id="0412f-216">容器名称中的所有字母都必须小写。</span><span class="sxs-lookup"><span data-stu-id="0412f-216">All letters in a container name must be lowercase.</span></span>
1. <span data-ttu-id="0412f-217">容器名称必须介于 3 到 63 个字符。</span><span class="sxs-lookup"><span data-stu-id="0412f-217">Container names must be from 3 through 63 characters long.</span></span>

<span data-ttu-id="0412f-218">请注意，容器的名称必须始终为小写。</span><span class="sxs-lookup"><span data-stu-id="0412f-218">Note that the name of a container must always be lowercase.</span></span> <span data-ttu-id="0412f-219">如果在容器名称，包括大写字母或其他方式违反了容器命名规则，可能会收到 400 错误 （错误请求）。</span><span class="sxs-lookup"><span data-stu-id="0412f-219">If you include an upper-case letter in a container name, or otherwise violate the container naming rules, you may receive a 400 error (Bad Request).</span></span>

## <a name="managing-security-for-blobs"></a><span data-ttu-id="0412f-220">管理 blob 安全性</span><span class="sxs-lookup"><span data-stu-id="0412f-220">Managing security for blobs</span></span>

<span data-ttu-id="0412f-221">默认情况下，Azure 存储器随时满足你的数据安全通过限制对帐户所有者，拥有帐户访问密钥访问。</span><span class="sxs-lookup"><span data-stu-id="0412f-221">By default, Azure Storage keeps your data secure by limiting access to the account owner, who is in possession of the account access keys.</span></span> <span data-ttu-id="0412f-222">当需要共享存储帐户中的 blob 数据时，务必为此，不会影响你的帐户访问密钥的安全性。</span><span class="sxs-lookup"><span data-stu-id="0412f-222">When you need to share blob data in your storage account, it is important to do so without compromising the security of your account access keys.</span></span> <span data-ttu-id="0412f-223">此外，可以加密 blob 数据，以确保其安全会在网络传输和 Azure 存储中。</span><span class="sxs-lookup"><span data-stu-id="0412f-223">Additionally, you can encrypt blob data to ensure that it is secure going over the wire and in Azure Storage.</span></span>

### <a name="controlling-access-to-blob-data"></a><span data-ttu-id="0412f-224">控制对 blob 数据的访问权限</span><span class="sxs-lookup"><span data-stu-id="0412f-224">Controlling access to blob data</span></span>

<span data-ttu-id="0412f-225">默认情况下，你的存储帐户中的 blob 数据是仅供存储帐户所有者访问。</span><span class="sxs-lookup"><span data-stu-id="0412f-225">By default, the blob data in your storage account is accessible only to storage account owner.</span></span> <span data-ttu-id="0412f-226">默认情况下，针对 Blob 存储的请求进行身份验证需要帐户访问密钥。</span><span class="sxs-lookup"><span data-stu-id="0412f-226">Authenticating requests against Blob storage requires the account access key by default.</span></span> <span data-ttu-id="0412f-227">但是，你可能想要向其他用户提供特定的 blob 数据。</span><span class="sxs-lookup"><span data-stu-id="0412f-227">However, you might want to make certain blob data available to other users.</span></span>

### <a name="encrypting-blob-data"></a><span data-ttu-id="0412f-228">加密 blob 数据</span><span class="sxs-lookup"><span data-stu-id="0412f-228">Encrypting blob data</span></span>

<span data-ttu-id="0412f-229">Azure 存储支持加密 blob 数据在客户端和服务器上。</span><span class="sxs-lookup"><span data-stu-id="0412f-229">Azure Storage supports encrypting blob data both at the client and on the server.</span></span>

## <a name="next-steps"></a><span data-ttu-id="0412f-230">后续步骤</span><span class="sxs-lookup"><span data-stu-id="0412f-230">Next steps</span></span>

<span data-ttu-id="0412f-231">现在，你已了解 Blob 存储的基础知识，单击以下链接了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="0412f-231">Now that you've learned the basics of Blob storage, follow these links to learn more.</span></span>

### <a name="tools"></a><span data-ttu-id="0412f-232">工具</span><span class="sxs-lookup"><span data-stu-id="0412f-232">Tools</span></span>

- <span data-ttu-id="0412f-233">[F# AzureStorageTypeProvider](https://fsprojects.github.io/AzureStorageTypeProvider/)\\</span><span class="sxs-lookup"><span data-stu-id="0412f-233">[F# AzureStorageTypeProvider](https://fsprojects.github.io/AzureStorageTypeProvider/)\\</span></span>
<span data-ttu-id="0412f-234">F#类型提供程序可用于浏览 Blob、 表和队列的 Azure 存储资产并轻松地将应用对它们的 CRUD 操作。</span><span class="sxs-lookup"><span data-stu-id="0412f-234">An F# Type Provider which can be used to explore Blob, Table and Queue Azure Storage assets and easily apply CRUD operations on them.</span></span>

- <span data-ttu-id="0412f-235">[FSharp.Azure.Storage](https://github.com/fsprojects/FSharp.Azure.Storage)\\</span><span class="sxs-lookup"><span data-stu-id="0412f-235">[FSharp.Azure.Storage](https://github.com/fsprojects/FSharp.Azure.Storage)\\</span></span>
<span data-ttu-id="0412f-236">F#使用 Microsoft Azure 表存储服务 API</span><span class="sxs-lookup"><span data-stu-id="0412f-236">An F# API for using Microsoft Azure Table Storage service</span></span>

- <span data-ttu-id="0412f-237">[Microsoft Azure 存储资源管理器 (MASE)](/azure/vs-azure-tools-storage-manage-with-storage-explorer)\\</span><span class="sxs-lookup"><span data-stu-id="0412f-237">[Microsoft Azure Storage Explorer (MASE)](/azure/vs-azure-tools-storage-manage-with-storage-explorer)\\</span></span>
<span data-ttu-id="0412f-238">使您能够以可视方式处理 Azure 存储的数据在 Windows、 OS X 和 Linux 上的 microsoft 免费提供的独立应用。</span><span class="sxs-lookup"><span data-stu-id="0412f-238">A free, standalone app from Microsoft that enables you to work visually with Azure Storage data on Windows, OS X, and Linux.</span></span>

### <a name="blob-storage-reference"></a><span data-ttu-id="0412f-239">Blob 存储参考</span><span class="sxs-lookup"><span data-stu-id="0412f-239">Blob storage reference</span></span>

- [<span data-ttu-id="0412f-240">用于.NET 的 azure 存储 Api</span><span class="sxs-lookup"><span data-stu-id="0412f-240">Azure Storage APIs for .NET</span></span>](/dotnet/api/overview/azure/storage)
- [<span data-ttu-id="0412f-241">Azure 存储服务 REST API 参考</span><span class="sxs-lookup"><span data-stu-id="0412f-241">Azure Storage Services REST API Reference</span></span>](/rest/api/storageservices/Azure-Storage-Services-REST-API-Reference)

### <a name="related-guides"></a><span data-ttu-id="0412f-242">相关的指南</span><span class="sxs-lookup"><span data-stu-id="0412f-242">Related guides</span></span>

- [<span data-ttu-id="0412f-243">使用 C# 中的 Azure Blob 存储入门</span><span class="sxs-lookup"><span data-stu-id="0412f-243">Getting Started with Azure Blob Storage in C#</span></span>](https://azure.microsoft.com/resources/samples/storage-blob-dotnet-getting-started/)
- [<span data-ttu-id="0412f-244">使用 AzCopy 命令行实用工具 on Windows 传输数据</span><span class="sxs-lookup"><span data-stu-id="0412f-244">Transfer data with the AzCopy command-line utility on Windows</span></span>](/azure/storage/common/storage-use-azcopy)
- [<span data-ttu-id="0412f-245">使用 AzCopy 命令行实用工具 on Linux 传输数据</span><span class="sxs-lookup"><span data-stu-id="0412f-245">Transfer data with the AzCopy command-line utility on Linux</span></span>](/azure/storage/common/storage-use-azcopy-linux)
- [<span data-ttu-id="0412f-246">配置 Azure 存储连接字符串</span><span class="sxs-lookup"><span data-stu-id="0412f-246">Configure Azure Storage connection strings</span></span>](/azure/storage/common/storage-configure-connection-string)
- [<span data-ttu-id="0412f-247">Azure 存储团队博客</span><span class="sxs-lookup"><span data-stu-id="0412f-247">Azure Storage Team Blog</span></span>](https://blogs.msdn.microsoft.com/windowsazurestorage/)
- [<span data-ttu-id="0412f-248">快速入门：使用.NET 在对象存储中创建 blob</span><span class="sxs-lookup"><span data-stu-id="0412f-248">Quickstart: Use .NET to create a blob in object storage</span></span>](/azure/storage/blobs/storage-quickstart-blobs-dotnet)
