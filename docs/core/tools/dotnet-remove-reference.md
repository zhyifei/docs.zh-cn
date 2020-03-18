---
title: dotnet remove reference 命令
description: dotnet remove reference 命令可便于删除项目间引用。
ms.date: 02/14/2020
ms.openlocfilehash: fcadf677faaf9281fb019c3c4bb16efc906b1aa1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "77503619"
---
# <a name="dotnet-remove-reference"></a><span data-ttu-id="9180a-103">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="9180a-103">dotnet remove reference</span></span>

<span data-ttu-id="9180a-104">**本文适用于：** ✔️ .NET Core 2.x SDK 及更高版本</span><span class="sxs-lookup"><span data-stu-id="9180a-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="9180a-105">名称</span><span class="sxs-lookup"><span data-stu-id="9180a-105">Name</span></span>

<span data-ttu-id="9180a-106">`dotnet remove reference` - 删除“项目到项目”引用。</span><span class="sxs-lookup"><span data-stu-id="9180a-106">`dotnet remove reference` - Removes project-to-project references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="9180a-107">摘要</span><span class="sxs-lookup"><span data-stu-id="9180a-107">Synopsis</span></span>

```dotnetcli
dotnet remove [<PROJECT>] reference [-f|--framework] <PROJECT_REFERENCES> [-h|--help]
```

## <a name="description"></a><span data-ttu-id="9180a-108">说明</span><span class="sxs-lookup"><span data-stu-id="9180a-108">Description</span></span>

<span data-ttu-id="9180a-109">使用 `dotnet remove reference` 命令可方便地从项目删除项目引用。</span><span class="sxs-lookup"><span data-stu-id="9180a-109">The `dotnet remove reference` command provides a convenient option to remove project references from a project.</span></span>

## <a name="arguments"></a><span data-ttu-id="9180a-110">参数</span><span class="sxs-lookup"><span data-stu-id="9180a-110">Arguments</span></span>

`PROJECT`

<span data-ttu-id="9180a-111">目标项目文件。</span><span class="sxs-lookup"><span data-stu-id="9180a-111">Target project file.</span></span> <span data-ttu-id="9180a-112">如果未指定，此命令会搜索当前目录来获取一个项目文件。</span><span class="sxs-lookup"><span data-stu-id="9180a-112">If not specified, the command searches the current directory for one.</span></span>

`PROJECT_REFERENCES`

<span data-ttu-id="9180a-113">要删除的项目到项目 (P2P) 引用。</span><span class="sxs-lookup"><span data-stu-id="9180a-113">Project-to-project (P2P) references to remove.</span></span> <span data-ttu-id="9180a-114">可指定一个或多个项目。</span><span class="sxs-lookup"><span data-stu-id="9180a-114">You can specify one or multiple projects.</span></span> <span data-ttu-id="9180a-115">基于 Unix/Linux 的终端支持 [Glob 模式](https://en.wikipedia.org/wiki/Glob_(programming))。</span><span class="sxs-lookup"><span data-stu-id="9180a-115">[Glob patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux based terminals.</span></span>

## <a name="options"></a><span data-ttu-id="9180a-116">选项</span><span class="sxs-lookup"><span data-stu-id="9180a-116">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="9180a-117">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="9180a-117">Prints out a short help for the command.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="9180a-118">仅在以特定[框架](../../standard/frameworks.md)为目标时删除引用。</span><span class="sxs-lookup"><span data-stu-id="9180a-118">Removes the reference only when targeting a specific [framework](../../standard/frameworks.md).</span></span>

## <a name="examples"></a><span data-ttu-id="9180a-119">示例</span><span class="sxs-lookup"><span data-stu-id="9180a-119">Examples</span></span>

- <span data-ttu-id="9180a-120">从指定项目删除项目引用：</span><span class="sxs-lookup"><span data-stu-id="9180a-120">Remove a project reference from the specified project:</span></span>

  ```dotnetcli
  dotnet remove app/app.csproj reference lib/lib.csproj
  ```

- <span data-ttu-id="9180a-121">从当前目录中的项目删除多个项目引用：</span><span class="sxs-lookup"><span data-stu-id="9180a-121">Remove multiple project references from the project in the current directory:</span></span>

  ```dotnetcli
  dotnet remove reference lib1/lib1.csproj lib2/lib2.csproj
  ```

- <span data-ttu-id="9180a-122">使用 Unix/Linux 的 glob 模式删除多个项目引用：</span><span class="sxs-lookup"><span data-stu-id="9180a-122">Remove multiple project references using a glob pattern on Unix/Linux:</span></span>

  ```dotnetcli
  dotnet remove app/app.csproj reference **/*.csproj`
  ```
