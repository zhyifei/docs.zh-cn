---
title: dotnet nuget locals 命令
description: dotnet nuget locals 命令可清除或列出本地 NuGet 资源，如 http 请求缓存、临时缓存或整个计算机范围内的全局包文件夹。
author: karann-msft
ms.date: 06/26/2019
ms.openlocfilehash: 6436bbaee7ae50f4b225c32b2245c737b0d359c3
ms.sourcegitcommit: b5c59eaaf8bf48ef3ec259f228cb328d6d4c0ceb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2019
ms.locfileid: "67539258"
---
# <a name="dotnet-nuget-locals"></a><span data-ttu-id="bff97-103">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="bff97-103">dotnet nuget locals</span></span>

<span data-ttu-id="bff97-104">**本主题适用于：✓** .NET Core 1.x SDK 及更高版本</span><span class="sxs-lookup"><span data-stu-id="bff97-104">**This topic applies to: ✓** .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="bff97-105">name</span><span class="sxs-lookup"><span data-stu-id="bff97-105">Name</span></span>

<span data-ttu-id="bff97-106">`dotnet nuget locals` -清除或列出本地 NuGet 资源。</span><span class="sxs-lookup"><span data-stu-id="bff97-106">`dotnet nuget locals` - Clears or lists local NuGet resources.</span></span>

## <a name="synopsis"></a><span data-ttu-id="bff97-107">摘要</span><span class="sxs-lookup"><span data-stu-id="bff97-107">Synopsis</span></span>

```
dotnet nuget locals <CACHE_LOCATION> [(-c|--clear)|(-l|--list)] [--force-english-output]
dotnet nuget locals [-h|--help]
```

## <a name="description"></a><span data-ttu-id="bff97-108">说明</span><span class="sxs-lookup"><span data-stu-id="bff97-108">Description</span></span>

<span data-ttu-id="bff97-109">`dotnet nuget locals` 命令清除或列出 http 请求缓存中的本地 NuGet 资源，临时缓存或计算机范围的全局包文件夹。</span><span class="sxs-lookup"><span data-stu-id="bff97-109">The `dotnet nuget locals` command clears or lists local NuGet resources in the http-request cache, temporary cache, or machine-wide global packages folder.</span></span>

## <a name="arguments"></a><span data-ttu-id="bff97-110">自变量</span><span class="sxs-lookup"><span data-stu-id="bff97-110">Arguments</span></span>

* **`CACHE_LOCATION`**

  <span data-ttu-id="bff97-111">要列出或清除的缓存位置。</span><span class="sxs-lookup"><span data-stu-id="bff97-111">The cache location to list or clear.</span></span> <span data-ttu-id="bff97-112">可以接受以下值之一：</span><span class="sxs-lookup"><span data-stu-id="bff97-112">It accepts one of the following values:</span></span>

  * <span data-ttu-id="bff97-113">`all` - 表示指定的操作应用于所有缓存类型，即 http 请求缓存、全局包缓存和临时缓存。</span><span class="sxs-lookup"><span data-stu-id="bff97-113">`all` - Indicates that the specified operation is applied to all cache types: http-request cache, global packages cache, and the temporary cache.</span></span>
  * <span data-ttu-id="bff97-114">`http-cache` - 表示指定的操作仅应用于 http 请求缓存。</span><span class="sxs-lookup"><span data-stu-id="bff97-114">`http-cache` - Indicates that the specified operation is applied only to the http-request cache.</span></span> <span data-ttu-id="bff97-115">其他缓存位置不受影响。</span><span class="sxs-lookup"><span data-stu-id="bff97-115">The other cache locations aren't affected.</span></span>
  * <span data-ttu-id="bff97-116">`global-packages` - 表示指定的操作仅应用于全局包缓存。</span><span class="sxs-lookup"><span data-stu-id="bff97-116">`global-packages` - Indicates that the specified operation is applied only to the global packages cache.</span></span> <span data-ttu-id="bff97-117">其他缓存位置不受影响。</span><span class="sxs-lookup"><span data-stu-id="bff97-117">The other cache locations aren't affected.</span></span>
  * <span data-ttu-id="bff97-118">`temp` - 表示指定的操作仅应用于临时缓存。</span><span class="sxs-lookup"><span data-stu-id="bff97-118">`temp` - Indicates that the specified operation is applied only to the temporary cache.</span></span> <span data-ttu-id="bff97-119">其他缓存位置不受影响。</span><span class="sxs-lookup"><span data-stu-id="bff97-119">The other cache locations aren't affected.</span></span>

## <a name="options"></a><span data-ttu-id="bff97-120">选项</span><span class="sxs-lookup"><span data-stu-id="bff97-120">Options</span></span>

* **`--force-english-output`**

  <span data-ttu-id="bff97-121">使用固定的、基于英语的区域性强制运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="bff97-121">Forces the application to run using an invariant, English-based culture.</span></span>

* **`-h|--help`**

  <span data-ttu-id="bff97-122">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="bff97-122">Prints out a short help for the command.</span></span>

* **`-c|--clear`**

  <span data-ttu-id="bff97-123">清除选项对指定的缓存类型执行清除操作。</span><span class="sxs-lookup"><span data-stu-id="bff97-123">The clear option executes a clear operation on the specified cache type.</span></span> <span data-ttu-id="bff97-124">缓存目录的内容被以递归方式删除。</span><span class="sxs-lookup"><span data-stu-id="bff97-124">The contents of the cache directories are deleted recursively.</span></span> <span data-ttu-id="bff97-125">正在执行的用户/组必须具有对缓存目录中的文件的相关权限。</span><span class="sxs-lookup"><span data-stu-id="bff97-125">The executing user/group must have permission to the files in the cache directories.</span></span> <span data-ttu-id="bff97-126">反之，则显示错误，指示未清除的文件/文件夹。</span><span class="sxs-lookup"><span data-stu-id="bff97-126">If not, an error is displayed indicating the files/folders that weren't cleared.</span></span>

* **`-l|--list`**

  <span data-ttu-id="bff97-127">列表选项用于显示指定缓存类型的位置。</span><span class="sxs-lookup"><span data-stu-id="bff97-127">The list option is used to display the location of the specified cache type.</span></span>

## <a name="examples"></a><span data-ttu-id="bff97-128">示例</span><span class="sxs-lookup"><span data-stu-id="bff97-128">Examples</span></span>

* <span data-ttu-id="bff97-129">显示所有本地缓存目录的路径（http 缓存目录、全局包缓存目录和临时缓存目录）：</span><span class="sxs-lookup"><span data-stu-id="bff97-129">Displays the paths of all the local cache directories (http-cache directory, global-packages cache directory, and temporary cache directory):</span></span>

  ```console
  dotnet nuget locals –l all
  ```

* <span data-ttu-id="bff97-130">显示本地 http 缓存录的路径：</span><span class="sxs-lookup"><span data-stu-id="bff97-130">Displays the path for the local http-cache directory:</span></span>

  ```console
  dotnet nuget locals --list http-cache
  ```

* <span data-ttu-id="bff97-131">清除所有本地缓存目录的文件（http 缓存目录、全局包缓存目录和临时缓存目录）：</span><span class="sxs-lookup"><span data-stu-id="bff97-131">Clears all files from all local cache directories (http-cache directory, global-packages cache directory, and temporary cache directory):</span></span>

  ```console
  dotnet nuget locals --clear all
  ```

* <span data-ttu-id="bff97-132">清除本地全局包缓存目录中的所有文件：</span><span class="sxs-lookup"><span data-stu-id="bff97-132">Clears all files in local global-packages cache directory:</span></span>

  ```console
  dotnet nuget locals -c global-packages
  ```

* <span data-ttu-id="bff97-133">清除本地临时缓存目录中的所有文件：</span><span class="sxs-lookup"><span data-stu-id="bff97-133">Clears all files in local temporary cache directory:</span></span>

  ```console
  dotnet nuget locals -c temp
  ```

## <a name="troubleshooting"></a><span data-ttu-id="bff97-134">疑难解答</span><span class="sxs-lookup"><span data-stu-id="bff97-134">Troubleshooting</span></span>

<span data-ttu-id="bff97-135">有关使用 `dotnet nuget locals` 命令时的常见问题和错误的信息，请参阅[管理 NuGet 缓存](/nuget/consume-packages/managing-the-nuget-cache)。</span><span class="sxs-lookup"><span data-stu-id="bff97-135">For information on common problems and errors while using the `dotnet nuget locals` command, see [Managing the NuGet cache](/nuget/consume-packages/managing-the-nuget-cache).</span></span>
