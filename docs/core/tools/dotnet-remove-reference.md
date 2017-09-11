---
title: "dotnet-remove reference 命令 - .NET Core CLI"
description: "使用 dotnet-remove reference 命令可方便地删除“项目到项目”引用。"
keywords: "dotnet-remove, CLI, CLI 命令, .NET Core"
author: spboyer
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 889c6b7e-a313-40b1-9fd3-6a6f4c52f1d0
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: e22f64370be4b56597a303d79d3aabe1ff22a78a
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---

# <a name="dotnet-remove-reference"></a><span data-ttu-id="676e3-104">dotnet-remove reference</span><span class="sxs-lookup"><span data-stu-id="676e3-104">dotnet-remove reference</span></span>

## <a name="name"></a><span data-ttu-id="676e3-105">名称</span><span class="sxs-lookup"><span data-stu-id="676e3-105">Name</span></span>

<span data-ttu-id="676e3-106">`dotnet-remove reference` - 删除“项目到项目”引用。</span><span class="sxs-lookup"><span data-stu-id="676e3-106">`dotnet-remove reference` - Removes project-to-project references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="676e3-107">摘要</span><span class="sxs-lookup"><span data-stu-id="676e3-107">Synopsis</span></span>

`dotnet remove [<PROJECT>] reference [-f|--framework] <PROJECT_REFERENCES> [-h|--help]`

## <a name="description"></a><span data-ttu-id="676e3-108">描述</span><span class="sxs-lookup"><span data-stu-id="676e3-108">Description</span></span>

<span data-ttu-id="676e3-109">使用 `dotnet remove reference` 命令可方便地从项目删除项目引用。</span><span class="sxs-lookup"><span data-stu-id="676e3-109">The `dotnet remove reference` command provides a convenient option to remove project references from a project.</span></span>

## <a name="arguments"></a><span data-ttu-id="676e3-110">参数</span><span class="sxs-lookup"><span data-stu-id="676e3-110">Arguments</span></span>

`PROJECT`

<span data-ttu-id="676e3-111">目标项目文件。</span><span class="sxs-lookup"><span data-stu-id="676e3-111">Target project file.</span></span> <span data-ttu-id="676e3-112">如果未指定，此命令会搜索当前目录来获取一个项目文件。</span><span class="sxs-lookup"><span data-stu-id="676e3-112">If not specified, the command searches the current directory for one.</span></span>

`PROJECT_REFERENCES`

<span data-ttu-id="676e3-113">要删除的项目到项目 (P2P) 引用。</span><span class="sxs-lookup"><span data-stu-id="676e3-113">Project to project (P2P references to remove.</span></span> <span data-ttu-id="676e3-114">可指定一个或多个项目。</span><span class="sxs-lookup"><span data-stu-id="676e3-114">You can specify one or multiple projects.</span></span> <span data-ttu-id="676e3-115">基于 Unix/Linux 的终端支持 [Glob 模式](https://en.wikipedia.org/wiki/Glob_(programming))。</span><span class="sxs-lookup"><span data-stu-id="676e3-115">[Glob patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux based terminals.</span></span>

## <a name="options"></a><span data-ttu-id="676e3-116">选项</span><span class="sxs-lookup"><span data-stu-id="676e3-116">Options</span></span>

`-h|--help`

<span data-ttu-id="676e3-117">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="676e3-117">Prints out a short help for the command.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="676e3-118">仅在以特定[框架](../../standard/frameworks.md)为目标时删除引用。</span><span class="sxs-lookup"><span data-stu-id="676e3-118">Removes the reference only when targeting a specific [framework](../../standard/frameworks.md).</span></span>

## <a name="examples"></a><span data-ttu-id="676e3-119">示例</span><span class="sxs-lookup"><span data-stu-id="676e3-119">Examples</span></span>

<span data-ttu-id="676e3-120">从指定项目删除项目引用：</span><span class="sxs-lookup"><span data-stu-id="676e3-120">Remove a project reference from the specified project:</span></span>

`dotnet remove app/app.csproj reference lib/lib.csproj`

<span data-ttu-id="676e3-121">从当前目录中的项目删除多个项目引用：</span><span class="sxs-lookup"><span data-stu-id="676e3-121">Remove multiple project references from the project in the current directory:</span></span>

`dotnet remove reference lib1/lib1.csproj lib2/lib2.csproj`

<span data-ttu-id="676e3-122">使用 Unix/Linux 的 glob 模式删除多个项目引用：</span><span class="sxs-lookup"><span data-stu-id="676e3-122">Remove multiple project references using a glob pattern on Unix/Linux:</span></span>

`dotnet remove app/app.csproj reference **/*.csproj`

