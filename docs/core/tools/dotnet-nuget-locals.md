---
title: dotnet nuget locals 命令 - .NET Core CLI
description: dotnet nuget locals 命令可清除或列出本地 NuGet 资源，如 http 请求缓存、临时缓存或整个计算机范围内的全局包文件夹。
author: karann-msft
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: conceptual
ms.prod: dotnet-core
ms.technology: dotnet-cli
ms.workload:
- dotnetcore
ms.openlocfilehash: 1dfa50ff0971a82b3f6aafd86492fd57d8cf6a82
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2018
---
# <a name="dotnet-nuget-locals"></a><span data-ttu-id="00789-103">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="00789-103">dotnet nuget locals</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="00789-104">name</span><span class="sxs-lookup"><span data-stu-id="00789-104">Name</span></span>

<span data-ttu-id="00789-105">`dotnet nuget locals` -清除或列出本地 NuGet 资源。</span><span class="sxs-lookup"><span data-stu-id="00789-105">`dotnet nuget locals` - Clears or lists local NuGet resources.</span></span>

## <a name="synopsis"></a><span data-ttu-id="00789-106">摘要</span><span class="sxs-lookup"><span data-stu-id="00789-106">Synopsis</span></span>

`dotnet nuget locals <CACHE_LOCATION> [(-c|--clear)|(-l|--list)] [--force-english-output] [-h|--help]`

## <a name="description"></a><span data-ttu-id="00789-107">描述</span><span class="sxs-lookup"><span data-stu-id="00789-107">Description</span></span>

<span data-ttu-id="00789-108">`dotnet nuget locals` 命令清除或列出 http 请求缓存中的本地 NuGet 资源，临时缓存或计算机范围的全局包文件夹。</span><span class="sxs-lookup"><span data-stu-id="00789-108">The `dotnet nuget locals` command clears or lists local NuGet resources in the http-request cache, temporary cache, or machine-wide global packages folder.</span></span>

## <a name="arguments"></a><span data-ttu-id="00789-109">自变量</span><span class="sxs-lookup"><span data-stu-id="00789-109">Arguments</span></span>

`CACHE_LOCATION`

<span data-ttu-id="00789-110">以下值之一：</span><span class="sxs-lookup"><span data-stu-id="00789-110">One of the following values:</span></span>

* <span data-ttu-id="00789-111">`all` - 表示指定的操作应用于所有缓存类型，即 http 请求缓存、全局包缓存和临时缓存。</span><span class="sxs-lookup"><span data-stu-id="00789-111">`all` - Indicates that the specified operation is applied to all cache types: http-request cache, global packages cache, and the temporary cache.</span></span>
* <span data-ttu-id="00789-112">`http-cache` - 表示指定的操作仅应用于 http 请求缓存。</span><span class="sxs-lookup"><span data-stu-id="00789-112">`http-cache` - Indicates that the specified operation is applied only to the http-request cache.</span></span> <span data-ttu-id="00789-113">其他缓存位置不受影响。</span><span class="sxs-lookup"><span data-stu-id="00789-113">The other cache locations are not affected.</span></span>
* <span data-ttu-id="00789-114">`global-packages` - 表示指定的操作仅应用于全局包缓存。</span><span class="sxs-lookup"><span data-stu-id="00789-114">`global-packages` - Indicates that the specified operation is applied only to the global packages cache.</span></span> <span data-ttu-id="00789-115">其他缓存位置不受影响。</span><span class="sxs-lookup"><span data-stu-id="00789-115">The other cache locations are not affected.</span></span>
* <span data-ttu-id="00789-116">`temp` - 表示指定的操作仅应用于临时缓存。</span><span class="sxs-lookup"><span data-stu-id="00789-116">`temp` - Indicates that the specified operation is applied only to the temporary cache.</span></span> <span data-ttu-id="00789-117">其他缓存位置不受影响。</span><span class="sxs-lookup"><span data-stu-id="00789-117">The other cache locations are not affected.</span></span>

## <a name="options"></a><span data-ttu-id="00789-118">选项</span><span class="sxs-lookup"><span data-stu-id="00789-118">Options</span></span>

`-h|--help`

<span data-ttu-id="00789-119">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="00789-119">Prints out a short help for the command.</span></span>

`-c|--clear`

<span data-ttu-id="00789-120">清除选项对指定的缓存类型执行清除操作。</span><span class="sxs-lookup"><span data-stu-id="00789-120">The clear option performs a clear operation on the specified cache type.</span></span> <span data-ttu-id="00789-121">缓存目录的内容被以递归方式删除。</span><span class="sxs-lookup"><span data-stu-id="00789-121">The contents of the cache directories are deleted recursively.</span></span> <span data-ttu-id="00789-122">正在执行的用户/组必须具有对缓存目录中的文件的相关权限。</span><span class="sxs-lookup"><span data-stu-id="00789-122">The executing user/group must have permission to the files in the cache directories.</span></span> <span data-ttu-id="00789-123">反之，则显示错误，指示未被清除的文件/文件夹。</span><span class="sxs-lookup"><span data-stu-id="00789-123">If not, an error is displayed indicating the files/folders which were not cleared.</span></span>

`-l|--list`

<span data-ttu-id="00789-124">列表选项用于显示指定缓存类型的位置。</span><span class="sxs-lookup"><span data-stu-id="00789-124">The list option is used to display the location of the specified cache type.</span></span> 

`--force-english-output`

<span data-ttu-id="00789-125">强制命令行输出以英语显示。</span><span class="sxs-lookup"><span data-stu-id="00789-125">Forces command-line output in English.</span></span>

## <a name="examples"></a><span data-ttu-id="00789-126">示例</span><span class="sxs-lookup"><span data-stu-id="00789-126">Examples</span></span>

<span data-ttu-id="00789-127">显示所有本地缓存目录的路径（http 缓存目录、全局包缓存目录和临时缓存目录）：</span><span class="sxs-lookup"><span data-stu-id="00789-127">Displays the paths of all the local cache directories (http-cache directory, global-packages cache directory, and temporary cache directory):</span></span>

`dotnet nuget locals –l all`

<span data-ttu-id="00789-128">显示本地 http 缓存录的路径：</span><span class="sxs-lookup"><span data-stu-id="00789-128">Displays the path for the local http-cache directory:</span></span>

`dotnet nuget locals --list http-cache`

<span data-ttu-id="00789-129">清除所有本地缓存目录的文件（http 缓存目录、全局包缓存目录和临时缓存目录）：</span><span class="sxs-lookup"><span data-stu-id="00789-129">Clears all files from all local cache directories (http-cache directory, global-packages cache directory, and temporary cache directory):</span></span>

`dotnet nuget locals --clear all`

<span data-ttu-id="00789-130">清除本地全局包缓存目录中的所有文件：</span><span class="sxs-lookup"><span data-stu-id="00789-130">Clears all files in local global-packages cache directory:</span></span>

`dotnet nuget locals -c global-packages`

<span data-ttu-id="00789-131">清除本地临时缓存目录中的所有文件：</span><span class="sxs-lookup"><span data-stu-id="00789-131">Clears all files in local temporary cache directory:</span></span>

`dotnet nuget locals -c temp`

## <a name="troubleshooting"></a><span data-ttu-id="00789-132">疑难解答</span><span class="sxs-lookup"><span data-stu-id="00789-132">Troubleshooting</span></span>

<span data-ttu-id="00789-133">有关使用 `dotnet nuget locals` 命令时的常见问题和错误的信息，请参阅[管理 NuGet 缓存](/nuget/consume-packages/managing-the-nuget-cache)。</span><span class="sxs-lookup"><span data-stu-id="00789-133">For information on common problems and errors while using the `dotnet nuget locals` command, see [Managing the NuGet cache](/nuget/consume-packages/managing-the-nuget-cache).</span></span>