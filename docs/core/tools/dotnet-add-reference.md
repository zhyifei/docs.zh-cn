---
title: "dotnet-add reference 命令- .NET Core CLI"
description: "dotnet add reference 命令可便于添加项目间引用。"
author: mairaw
ms.author: mairaw
ms.date: 09/19/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.workload: dotnetcore
ms.openlocfilehash: 9a79468168979a7c89efe48e11175f926e39cf4f
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="dotnet-add-reference"></a><span data-ttu-id="48f0f-103">dotnet-add reference</span><span class="sxs-lookup"><span data-stu-id="48f0f-103">dotnet-add reference</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="48f0f-104">name</span><span class="sxs-lookup"><span data-stu-id="48f0f-104">Name</span></span>

<span data-ttu-id="48f0f-105">`dotnet add reference` - 添加项目到项目 (P2P) 引用。</span><span class="sxs-lookup"><span data-stu-id="48f0f-105">`dotnet add reference` - Adds project-to-project (P2P) references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="48f0f-106">摘要</span><span class="sxs-lookup"><span data-stu-id="48f0f-106">Synopsis</span></span>

`dotnet add [<PROJECT>] reference [-f|--framework] <PROJECT_REFERENCES> [-h|--help]`

## <a name="description"></a><span data-ttu-id="48f0f-107">描述</span><span class="sxs-lookup"><span data-stu-id="48f0f-107">Description</span></span>

<span data-ttu-id="48f0f-108">使用 `dotnet add reference` 命令可方便地向项目添加项目引用。</span><span class="sxs-lookup"><span data-stu-id="48f0f-108">The `dotnet add reference` command provides a convenient option to add project references to a project.</span></span> <span data-ttu-id="48f0f-109">运行该命令后，会将 [`<ProjectReference>`](/visualstudio/msbuild/common-msbuild-project-items) 元素添加到项目文件。</span><span class="sxs-lookup"><span data-stu-id="48f0f-109">After running the command, the [`<ProjectReference>`](/visualstudio/msbuild/common-msbuild-project-items) elements are added to the project file.</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="app.csproj" />
  <ProjectReference Include="..\lib2\lib2.csproj" />
  <ProjectReference Include="..\lib1\lib1.csproj" />
</ItemGroup>
```

## <a name="arguments"></a><span data-ttu-id="48f0f-110">自变量</span><span class="sxs-lookup"><span data-stu-id="48f0f-110">Arguments</span></span>

`PROJECT`

<span data-ttu-id="48f0f-111">指定项目文件。</span><span class="sxs-lookup"><span data-stu-id="48f0f-111">Specifies the project file.</span></span> <span data-ttu-id="48f0f-112">如果未指定，此命令会搜索当前目录来获取一个项目文件。</span><span class="sxs-lookup"><span data-stu-id="48f0f-112">If not specified, the command searches the current directory for one.</span></span>

`PROJECT_REFERENCES`

<span data-ttu-id="48f0f-113">要添加的项目到项目 (P2P) 引用。</span><span class="sxs-lookup"><span data-stu-id="48f0f-113">Project-to-project (P2P) references to add.</span></span> <span data-ttu-id="48f0f-114">指定一个或多个项目。</span><span class="sxs-lookup"><span data-stu-id="48f0f-114">Specify one or more projects.</span></span> <span data-ttu-id="48f0f-115">基于 Unix/Linux 的系统支持 [glob 模式](https://en.wikipedia.org/wiki/Glob_(programming))。</span><span class="sxs-lookup"><span data-stu-id="48f0f-115">[Glob patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux-based systems.</span></span>

## <a name="options"></a><span data-ttu-id="48f0f-116">选项</span><span class="sxs-lookup"><span data-stu-id="48f0f-116">Options</span></span>

`-h|--help`

<span data-ttu-id="48f0f-117">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="48f0f-117">Prints out a short help for the command.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="48f0f-118">仅在以特定[框架](../../standard/frameworks.md)为目标时添加项目引用。</span><span class="sxs-lookup"><span data-stu-id="48f0f-118">Adds project references only when targeting a specific [framework](../../standard/frameworks.md).</span></span>

## <a name="examples"></a><span data-ttu-id="48f0f-119">示例</span><span class="sxs-lookup"><span data-stu-id="48f0f-119">Examples</span></span>

<span data-ttu-id="48f0f-120">添加项目引用：</span><span class="sxs-lookup"><span data-stu-id="48f0f-120">Add a project reference:</span></span>

`dotnet add app/app.csproj reference lib/lib.csproj`

<span data-ttu-id="48f0f-121">向当前目录中的项目添加多个项目引用：</span><span class="sxs-lookup"><span data-stu-id="48f0f-121">Add multiple project references to the project in the current directory:</span></span>

`dotnet add reference lib1/lib1.csproj lib2/lib2.csproj`

<span data-ttu-id="48f0f-122">使用 glob 模式在 Linux/Unix 上添加多个项目引用：</span><span class="sxs-lookup"><span data-stu-id="48f0f-122">Add multiple project references using a globbing pattern on Linux/Unix:</span></span>

`dotnet add app/app.csproj reference **/*.csproj`
