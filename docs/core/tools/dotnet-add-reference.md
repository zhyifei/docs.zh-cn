---
title: "dotnet-add reference 命令- .NET Core CLI"
description: "使用 dotnet-add reference 命令可方便地添加“项目到项目”引用。"
keywords: "dotnet-add, CLI, CLI 命令, .NET Core"
author: spboyer
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 5e2a3efd-443c-4f23-a1b1-a662a5387879
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 98491efc183ad62f47275d0832a32dde5899373d
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---

# <a name="dotnet-add-reference"></a><span data-ttu-id="49978-104">dotnet-add reference</span><span class="sxs-lookup"><span data-stu-id="49978-104">dotnet-add reference</span></span>

## <a name="name"></a><span data-ttu-id="49978-105">名称</span><span class="sxs-lookup"><span data-stu-id="49978-105">Name</span></span>

<span data-ttu-id="49978-106">`dotnet-add reference` - 添加项目到项目 (P2P) 引用。</span><span class="sxs-lookup"><span data-stu-id="49978-106">`dotnet-add reference` - Adds project-to-project (P2P) references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="49978-107">摘要</span><span class="sxs-lookup"><span data-stu-id="49978-107">Synopsis</span></span>

`dotnet add [<PROJECT>] reference [-f|--framework] <PROJECT_REFERENCES> [-h|--help]`

## <a name="description"></a><span data-ttu-id="49978-108">描述</span><span class="sxs-lookup"><span data-stu-id="49978-108">Description</span></span>

<span data-ttu-id="49978-109">使用 `dotnet add reference` 命令可方便地向项目添加项目引用。</span><span class="sxs-lookup"><span data-stu-id="49978-109">The `dotnet add reference` command provides a convenient option to add project references to a project.</span></span> <span data-ttu-id="49978-110">运行该命令后，会将 [`<ProjectReference>`](/visualstudio/msbuild/common-msbuild-project-items) 元素添加到项目文件。</span><span class="sxs-lookup"><span data-stu-id="49978-110">After running the command, the [`<ProjectReference>`](/visualstudio/msbuild/common-msbuild-project-items) elements are added to the project file.</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="app.csproj" />
  <ProjectReference Include="..\lib2\lib2.csproj" />
  <ProjectReference Include="..\lib1\lib1.csproj" />
</ItemGroup>
```

## <a name="arguments"></a><span data-ttu-id="49978-111">参数</span><span class="sxs-lookup"><span data-stu-id="49978-111">Arguments</span></span>

`PROJECT`

<span data-ttu-id="49978-112">指定项目文件。</span><span class="sxs-lookup"><span data-stu-id="49978-112">Specifies the project file.</span></span> <span data-ttu-id="49978-113">如果未指定，此命令会搜索当前目录，以获取解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="49978-113">If not specified, the command will search the current directory for one.</span></span>

`PROJECT_REFERENCES`

<span data-ttu-id="49978-114">要添加的项目到项目 (P2P) 引用。</span><span class="sxs-lookup"><span data-stu-id="49978-114">Project-to-project (P2P) references to add.</span></span> <span data-ttu-id="49978-115">指定一个或多个项目。</span><span class="sxs-lookup"><span data-stu-id="49978-115">Specify one or more projects.</span></span> <span data-ttu-id="49978-116">基于 Unix/Linux 的系统支持 [glob 模式](https://en.wikipedia.org/wiki/Glob_(programming))。</span><span class="sxs-lookup"><span data-stu-id="49978-116">[Glob patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux-based systems.</span></span>

## <a name="options"></a><span data-ttu-id="49978-117">选项</span><span class="sxs-lookup"><span data-stu-id="49978-117">Options</span></span>

`-h|--help`

<span data-ttu-id="49978-118">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="49978-118">Prints out a short help for the command.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="49978-119">仅在以特定[框架](../../standard/frameworks.md)为目标时添加项目引用。</span><span class="sxs-lookup"><span data-stu-id="49978-119">Adds project references only when targeting a specific [framework](../../standard/frameworks.md).</span></span>

## <a name="examples"></a><span data-ttu-id="49978-120">示例</span><span class="sxs-lookup"><span data-stu-id="49978-120">Examples</span></span>

<span data-ttu-id="49978-121">添加项目引用：</span><span class="sxs-lookup"><span data-stu-id="49978-121">Add a project reference:</span></span>

`dotnet add app/app.csproj reference lib/lib.csproj`

<span data-ttu-id="49978-122">添加多个项目引用：</span><span class="sxs-lookup"><span data-stu-id="49978-122">Add multiple project references:</span></span>

`dotnet add reference lib1/lib1.csproj lib2/lib2.csproj`

<span data-ttu-id="49978-123">使用 glob 模式在 Linux/Unix 上添加多个项目引用：</span><span class="sxs-lookup"><span data-stu-id="49978-123">Add multiple project references using a globbing pattern on Linux/Unix:</span></span>

`dotnet add app/app.csproj reference **/*.csproj`

