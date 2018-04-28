---
title: dotnet remove reference 命令 - .NET Core CLI
description: dotnet remove reference 命令可便于删除项目间引用。
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: conceptual
ms.prod: dotnet-core
ms.technology: dotnet-cli
ms.workload:
- dotnetcore
ms.openlocfilehash: 0b7fb2788ccc04b54bf02f0387141d501612c16d
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2018
---
# <a name="dotnet-remove-reference"></a><span data-ttu-id="bde7a-103">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="bde7a-103">dotnet remove reference</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="bde7a-104">name</span><span class="sxs-lookup"><span data-stu-id="bde7a-104">Name</span></span>

<span data-ttu-id="bde7a-105">`dotnet remove reference` - 删除“项目到项目”引用。</span><span class="sxs-lookup"><span data-stu-id="bde7a-105">`dotnet remove reference` - Removes project-to-project references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="bde7a-106">摘要</span><span class="sxs-lookup"><span data-stu-id="bde7a-106">Synopsis</span></span>

`dotnet remove [<PROJECT>] reference [-f|--framework] <PROJECT_REFERENCES> [-h|--help]`

## <a name="description"></a><span data-ttu-id="bde7a-107">描述</span><span class="sxs-lookup"><span data-stu-id="bde7a-107">Description</span></span>

<span data-ttu-id="bde7a-108">使用 `dotnet remove reference` 命令可方便地从项目删除项目引用。</span><span class="sxs-lookup"><span data-stu-id="bde7a-108">The `dotnet remove reference` command provides a convenient option to remove project references from a project.</span></span>

## <a name="arguments"></a><span data-ttu-id="bde7a-109">自变量</span><span class="sxs-lookup"><span data-stu-id="bde7a-109">Arguments</span></span>

`PROJECT`

<span data-ttu-id="bde7a-110">目标项目文件。</span><span class="sxs-lookup"><span data-stu-id="bde7a-110">Target project file.</span></span> <span data-ttu-id="bde7a-111">如果未指定，此命令会搜索当前目录来获取一个项目文件。</span><span class="sxs-lookup"><span data-stu-id="bde7a-111">If not specified, the command searches the current directory for one.</span></span>

`PROJECT_REFERENCES`

<span data-ttu-id="bde7a-112">要删除的项目到项目 (P2P) 引用。</span><span class="sxs-lookup"><span data-stu-id="bde7a-112">Project to project (P2P references to remove.</span></span> <span data-ttu-id="bde7a-113">可指定一个或多个项目。</span><span class="sxs-lookup"><span data-stu-id="bde7a-113">You can specify one or multiple projects.</span></span> <span data-ttu-id="bde7a-114">基于 Unix/Linux 的终端支持 [Glob 模式](https://en.wikipedia.org/wiki/Glob_(programming))。</span><span class="sxs-lookup"><span data-stu-id="bde7a-114">[Glob patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux based terminals.</span></span>

## <a name="options"></a><span data-ttu-id="bde7a-115">选项</span><span class="sxs-lookup"><span data-stu-id="bde7a-115">Options</span></span>

`-h|--help`

<span data-ttu-id="bde7a-116">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="bde7a-116">Prints out a short help for the command.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="bde7a-117">仅在以特定[框架](../../standard/frameworks.md)为目标时删除引用。</span><span class="sxs-lookup"><span data-stu-id="bde7a-117">Removes the reference only when targeting a specific [framework](../../standard/frameworks.md).</span></span>

## <a name="examples"></a><span data-ttu-id="bde7a-118">示例</span><span class="sxs-lookup"><span data-stu-id="bde7a-118">Examples</span></span>

<span data-ttu-id="bde7a-119">从指定项目删除项目引用：</span><span class="sxs-lookup"><span data-stu-id="bde7a-119">Remove a project reference from the specified project:</span></span>

`dotnet remove app/app.csproj reference lib/lib.csproj`

<span data-ttu-id="bde7a-120">从当前目录中的项目删除多个项目引用：</span><span class="sxs-lookup"><span data-stu-id="bde7a-120">Remove multiple project references from the project in the current directory:</span></span>

`dotnet remove reference lib1/lib1.csproj lib2/lib2.csproj`

<span data-ttu-id="bde7a-121">使用 Unix/Linux 的 glob 模式删除多个项目引用：</span><span class="sxs-lookup"><span data-stu-id="bde7a-121">Remove multiple project references using a glob pattern on Unix/Linux:</span></span>

`dotnet remove app/app.csproj reference **/*.csproj`
