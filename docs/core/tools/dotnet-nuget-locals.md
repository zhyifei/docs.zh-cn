---
title: "dotnet-nuget-locals 命令 - .NET Core CLI"
description: "dotnet-nuget-locals 命令清除或列出本地 NuGet 资源，例如 http 请求缓存、临时缓存或计算机范围的全局包文件夹。"
keywords: "dotnet-nuget-locals, CLI, CLI 命令, .NET Core"
author: karann-msft
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 8440229e-317e-4dc1-9463-cba5fdb12c3b
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 2c9ea7b3b7c61b347cb7c56254773290f04a0cd6
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---

# <a name="dotnet-nuget-locals"></a><span data-ttu-id="1ed74-104">dotnet-nuget locals</span><span class="sxs-lookup"><span data-stu-id="1ed74-104">dotnet-nuget locals</span></span>

## <a name="name"></a><span data-ttu-id="1ed74-105">名称</span><span class="sxs-lookup"><span data-stu-id="1ed74-105">Name</span></span>

<span data-ttu-id="1ed74-106">`dotnet-nuget locals` -清除或列出本地 NuGet 资源。</span><span class="sxs-lookup"><span data-stu-id="1ed74-106">`dotnet-nuget locals` - Clears or lists local NuGet resources.</span></span> 

## <a name="synopsis"></a><span data-ttu-id="1ed74-107">摘要</span><span class="sxs-lookup"><span data-stu-id="1ed74-107">Synopsis</span></span>

`dotnet nuget locals <CACHE_LOCATION> [(-c|--clear)|(-l|--list)] [--force-english-output] [-h|--help]`

## <a name="description"></a><span data-ttu-id="1ed74-108">描述</span><span class="sxs-lookup"><span data-stu-id="1ed74-108">Description</span></span>

<span data-ttu-id="1ed74-109">`dotnet nuget locals` 命令清除或列出 http 请求缓存中的本地 NuGet 资源，临时缓存或计算机范围的全局包文件夹。</span><span class="sxs-lookup"><span data-stu-id="1ed74-109">The `dotnet nuget locals` command clears or lists local NuGet resources in the http-request cache, temporary cache, or machine-wide global packages folder.</span></span>

## <a name="arguments"></a><span data-ttu-id="1ed74-110">参数</span><span class="sxs-lookup"><span data-stu-id="1ed74-110">Arguments</span></span>

`CACHE_LOCATION`

<span data-ttu-id="1ed74-111">以下值之一：</span><span class="sxs-lookup"><span data-stu-id="1ed74-111">One of the following values:</span></span>

`all`

<span data-ttu-id="1ed74-112">表示指定的操作应用于所有缓存类型，即 http 请求缓存、全局包缓存和临时缓存。</span><span class="sxs-lookup"><span data-stu-id="1ed74-112">Indicates that the specified operation is applied to all cache types: http-request cache, global packages cache, and the temporary cache.</span></span>

`http-cache`

<span data-ttu-id="1ed74-113">表示指定的操作仅应用于 http 请求缓存。</span><span class="sxs-lookup"><span data-stu-id="1ed74-113">Indicates that the specified operation is applied only to the http-request cache.</span></span> <span data-ttu-id="1ed74-114">其他缓存位置不受影响。</span><span class="sxs-lookup"><span data-stu-id="1ed74-114">The other cache locations are not affected.</span></span>

`global-packages`

<span data-ttu-id="1ed74-115">表示指定的操作仅应用于全局包缓存。</span><span class="sxs-lookup"><span data-stu-id="1ed74-115">Indicates that the specified operation is applied only to the global packages cache.</span></span> <span data-ttu-id="1ed74-116">其他缓存位置不受影响。</span><span class="sxs-lookup"><span data-stu-id="1ed74-116">The other cache locations are not affected.</span></span>

`temp`

<span data-ttu-id="1ed74-117">表示指定的操作仅应用于临时缓存。</span><span class="sxs-lookup"><span data-stu-id="1ed74-117">Indicates that the specified operation is applied only to the temporary cache.</span></span> <span data-ttu-id="1ed74-118">其他缓存位置不受影响。</span><span class="sxs-lookup"><span data-stu-id="1ed74-118">The other cache locations are not affected.</span></span>

## <a name="options"></a><span data-ttu-id="1ed74-119">选项</span><span class="sxs-lookup"><span data-stu-id="1ed74-119">Options</span></span>

`-h|--help`

<span data-ttu-id="1ed74-120">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="1ed74-120">Prints out a short help for the command.</span></span>  

`-c|--clear`

<span data-ttu-id="1ed74-121">清除选项对指定的缓存类型执行清除操作。</span><span class="sxs-lookup"><span data-stu-id="1ed74-121">The clear option performs a clear operation on the specified cache type.</span></span> <span data-ttu-id="1ed74-122">缓存目录的内容被以递归方式删除。</span><span class="sxs-lookup"><span data-stu-id="1ed74-122">The contents of the cache directories are deleted recursively.</span></span> <span data-ttu-id="1ed74-123">正在执行的用户/组必须具有对缓存目录中的文件的相关权限。</span><span class="sxs-lookup"><span data-stu-id="1ed74-123">The executing user/group must have permission to the files in the cache directories.</span></span> <span data-ttu-id="1ed74-124">反之，则显示错误，指示未被清除的文件/文件夹。</span><span class="sxs-lookup"><span data-stu-id="1ed74-124">If not, an error is displayed indicating the files/folders which were not cleared.</span></span>

`-l|--list`

<span data-ttu-id="1ed74-125">列表选项用于显示指定缓存类型的位置。</span><span class="sxs-lookup"><span data-stu-id="1ed74-125">The list option is used to display the location of the specified cache type.</span></span> 

`--force-english-output`

<span data-ttu-id="1ed74-126">强制命令行输出以英语显示。</span><span class="sxs-lookup"><span data-stu-id="1ed74-126">Forces command-line output in English.</span></span>

## <a name="examples"></a><span data-ttu-id="1ed74-127">示例</span><span class="sxs-lookup"><span data-stu-id="1ed74-127">Examples</span></span>

<span data-ttu-id="1ed74-128">显示所有本地缓存目录的路径（http 缓存目录、全局包缓存目录和临时缓存目录）：</span><span class="sxs-lookup"><span data-stu-id="1ed74-128">Displays the paths of all the local cache directories (http-cache directory, global-packages cache directory, and temporary cache directory):</span></span>

`dotnet nuget locals –l all`

<span data-ttu-id="1ed74-129">显示本地 http 缓存录的路径：</span><span class="sxs-lookup"><span data-stu-id="1ed74-129">Displays the path for the local http-cache directory:</span></span>

`dotnet nuget locals --list http-cache`

<span data-ttu-id="1ed74-130">清除所有本地缓存目录的文件（http 缓存目录、全局包缓存目录和临时缓存目录）：</span><span class="sxs-lookup"><span data-stu-id="1ed74-130">Clears all files from all local cache directories (http-cache directory, global-packages cache directory, and temporary cache directory):</span></span>

`dotnet nuget locals --clear all`

<span data-ttu-id="1ed74-131">清除本地全局包缓存目录中的所有文件：</span><span class="sxs-lookup"><span data-stu-id="1ed74-131">Clears all files in local global-packages cache directory:</span></span>

`dotnet nuget locals -c global-packages`

<span data-ttu-id="1ed74-132">清除本地临时缓存目录中的所有文件：</span><span class="sxs-lookup"><span data-stu-id="1ed74-132">Clears all files in local temporary cache directory:</span></span>

`dotnet nuget locals -c temp`

## <a name="troubleshooting"></a><span data-ttu-id="1ed74-133">疑难解答</span><span class="sxs-lookup"><span data-stu-id="1ed74-133">Troubleshooting</span></span>

<span data-ttu-id="1ed74-134">有关使用 `dotnet nuget locals` 命令时的常见问题和错误的信息，请参阅[管理 NuGet 缓存](/nuget/consume-packages/managing-the-nuget-cache)。</span><span class="sxs-lookup"><span data-stu-id="1ed74-134">For information on common problems and errors while using the `dotnet nuget locals` command, see [Managing the NuGet cache](/nuget/consume-packages/managing-the-nuget-cache).</span></span>

