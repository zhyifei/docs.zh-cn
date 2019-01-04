---
title: dotnet remove reference 命令
description: dotnet remove reference 命令可便于删除项目间引用。
ms.date: 05/29/2018
ms.openlocfilehash: bfac4721743babcf48fd8e86a50c8df136e1bfce
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53170608"
---
# <a name="dotnet-remove-reference"></a><span data-ttu-id="746f0-103">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="746f0-103">dotnet remove reference</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="746f0-104">name</span><span class="sxs-lookup"><span data-stu-id="746f0-104">Name</span></span>

<span data-ttu-id="746f0-105">`dotnet remove reference` - 删除“项目到项目”引用。</span><span class="sxs-lookup"><span data-stu-id="746f0-105">`dotnet remove reference` - Removes project-to-project references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="746f0-106">摘要</span><span class="sxs-lookup"><span data-stu-id="746f0-106">Synopsis</span></span>

`dotnet remove [<PROJECT>] reference [-f|--framework] <PROJECT_REFERENCES> [-h|--help]`

## <a name="description"></a><span data-ttu-id="746f0-107">说明</span><span class="sxs-lookup"><span data-stu-id="746f0-107">Description</span></span>

<span data-ttu-id="746f0-108">使用 `dotnet remove reference` 命令可方便地从项目删除项目引用。</span><span class="sxs-lookup"><span data-stu-id="746f0-108">The `dotnet remove reference` command provides a convenient option to remove project references from a project.</span></span>

## <a name="arguments"></a><span data-ttu-id="746f0-109">自变量</span><span class="sxs-lookup"><span data-stu-id="746f0-109">Arguments</span></span>

`PROJECT`

<span data-ttu-id="746f0-110">目标项目文件。</span><span class="sxs-lookup"><span data-stu-id="746f0-110">Target project file.</span></span> <span data-ttu-id="746f0-111">如果未指定，此命令会搜索当前目录来获取一个项目文件。</span><span class="sxs-lookup"><span data-stu-id="746f0-111">If not specified, the command searches the current directory for one.</span></span>

`PROJECT_REFERENCES`

<span data-ttu-id="746f0-112">要删除的项目到项目 (P2P) 引用。</span><span class="sxs-lookup"><span data-stu-id="746f0-112">Project-to-project (P2P) references to remove.</span></span> <span data-ttu-id="746f0-113">可指定一个或多个项目。</span><span class="sxs-lookup"><span data-stu-id="746f0-113">You can specify one or multiple projects.</span></span> <span data-ttu-id="746f0-114">基于 Unix/Linux 的终端支持 [Glob 模式](https://en.wikipedia.org/wiki/Glob_(programming))。</span><span class="sxs-lookup"><span data-stu-id="746f0-114">[Glob patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux based terminals.</span></span>

## <a name="options"></a><span data-ttu-id="746f0-115">选项</span><span class="sxs-lookup"><span data-stu-id="746f0-115">Options</span></span>

`-h|--help`

<span data-ttu-id="746f0-116">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="746f0-116">Prints out a short help for the command.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="746f0-117">仅在以特定[框架](../../standard/frameworks.md)为目标时删除引用。</span><span class="sxs-lookup"><span data-stu-id="746f0-117">Removes the reference only when targeting a specific [framework](../../standard/frameworks.md).</span></span>

## <a name="examples"></a><span data-ttu-id="746f0-118">示例</span><span class="sxs-lookup"><span data-stu-id="746f0-118">Examples</span></span>

<span data-ttu-id="746f0-119">从指定项目删除项目引用：</span><span class="sxs-lookup"><span data-stu-id="746f0-119">Remove a project reference from the specified project:</span></span>

`dotnet remove app/app.csproj reference lib/lib.csproj`

<span data-ttu-id="746f0-120">从当前目录中的项目删除多个项目引用：</span><span class="sxs-lookup"><span data-stu-id="746f0-120">Remove multiple project references from the project in the current directory:</span></span>

`dotnet remove reference lib1/lib1.csproj lib2/lib2.csproj`

<span data-ttu-id="746f0-121">使用 Unix/Linux 的 glob 模式删除多个项目引用：</span><span class="sxs-lookup"><span data-stu-id="746f0-121">Remove multiple project references using a glob pattern on Unix/Linux:</span></span>

`dotnet remove app/app.csproj reference **/*.csproj`
