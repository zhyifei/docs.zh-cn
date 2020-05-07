---
title: dotnet remove reference 命令
description: dotnet remove reference 命令可便于删除项目间引用。
ms.date: 02/14/2020
ms.openlocfilehash: a45153376d7d6eb764c1d2c6b473d04a273a2de1
ms.sourcegitcommit: c2c1269a81ffdcfc8675bcd9a8505b1a11ffb271
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/25/2020
ms.locfileid: "82158328"
---
# <a name="dotnet-remove-reference"></a><span data-ttu-id="4be06-103">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="4be06-103">dotnet remove reference</span></span>

<span data-ttu-id="4be06-104">**本文适用于：** ✔️ .NET Core 2.x SDK 及更高版本</span><span class="sxs-lookup"><span data-stu-id="4be06-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="4be06-105">“属性”</span><span class="sxs-lookup"><span data-stu-id="4be06-105">Name</span></span>

<span data-ttu-id="4be06-106">`dotnet remove reference` - 删除项目到项目 (P2P) 引用。</span><span class="sxs-lookup"><span data-stu-id="4be06-106">`dotnet remove reference` - Removes project-to-project (P2P) references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="4be06-107">摘要</span><span class="sxs-lookup"><span data-stu-id="4be06-107">Synopsis</span></span>

```dotnetcli
dotnet remove [<PROJECT>] reference [-f|--framework <FRAMEWORK>]
     <PROJECT_REFERENCES>

dotnet remove reference -h|--help
```

## <a name="description"></a><span data-ttu-id="4be06-108">描述</span><span class="sxs-lookup"><span data-stu-id="4be06-108">Description</span></span>

<span data-ttu-id="4be06-109">使用 `dotnet remove reference` 命令可方便地从项目删除项目引用。</span><span class="sxs-lookup"><span data-stu-id="4be06-109">The `dotnet remove reference` command provides a convenient option to remove project references from a project.</span></span>

## <a name="arguments"></a><span data-ttu-id="4be06-110">自变量</span><span class="sxs-lookup"><span data-stu-id="4be06-110">Arguments</span></span>

`PROJECT`

<span data-ttu-id="4be06-111">目标项目文件。</span><span class="sxs-lookup"><span data-stu-id="4be06-111">Target project file.</span></span> <span data-ttu-id="4be06-112">如果未指定，此命令会搜索当前目录来获取一个项目文件。</span><span class="sxs-lookup"><span data-stu-id="4be06-112">If not specified, the command searches the current directory for one.</span></span>

`PROJECT_REFERENCES`

<span data-ttu-id="4be06-113">要删除的项目到项目 (P2P) 引用。</span><span class="sxs-lookup"><span data-stu-id="4be06-113">Project-to-project (P2P) references to remove.</span></span> <span data-ttu-id="4be06-114">可指定一个或多个项目。</span><span class="sxs-lookup"><span data-stu-id="4be06-114">You can specify one or multiple projects.</span></span> <span data-ttu-id="4be06-115">基于 Unix/Linux 的终端支持 [Glob 模式](https://en.wikipedia.org/wiki/Glob_(programming))。</span><span class="sxs-lookup"><span data-stu-id="4be06-115">[Glob patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux based terminals.</span></span>

## <a name="options"></a><span data-ttu-id="4be06-116">选项</span><span class="sxs-lookup"><span data-stu-id="4be06-116">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="4be06-117">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="4be06-117">Prints out a short help for the command.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="4be06-118">仅在以特定[框架](../../standard/frameworks.md)为目标时使用 TFM 格式删除引用。</span><span class="sxs-lookup"><span data-stu-id="4be06-118">Removes the reference only when targeting a specific [framework](../../standard/frameworks.md) using the TFM format.</span></span>

## <a name="examples"></a><span data-ttu-id="4be06-119">示例</span><span class="sxs-lookup"><span data-stu-id="4be06-119">Examples</span></span>

- <span data-ttu-id="4be06-120">从指定项目删除项目引用：</span><span class="sxs-lookup"><span data-stu-id="4be06-120">Remove a project reference from the specified project:</span></span>

  ```dotnetcli
  dotnet remove app/app.csproj reference lib/lib.csproj
  ```

- <span data-ttu-id="4be06-121">从当前目录中的项目删除多个项目引用：</span><span class="sxs-lookup"><span data-stu-id="4be06-121">Remove multiple project references from the project in the current directory:</span></span>

  ```dotnetcli
  dotnet remove reference lib1/lib1.csproj lib2/lib2.csproj
  ```

- <span data-ttu-id="4be06-122">使用 Unix/Linux 的 glob 模式删除多个项目引用：</span><span class="sxs-lookup"><span data-stu-id="4be06-122">Remove multiple project references using a glob pattern on Unix/Linux:</span></span>

  ```dotnetcli
  dotnet remove app/app.csproj reference **/*.csproj`
  ```
