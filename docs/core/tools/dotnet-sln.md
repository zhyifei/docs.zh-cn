---
title: dotnet sln 命令 - .NET Core CLI
description: 使用 dotnet-sln 命令，可以便捷地在解决方案文件中添加、删除和列出项目。
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: dd77281b55b3e7fc7c293e402d11de016ef73cf8
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2018
ms.locfileid: "34696707"
---
# <a name="dotnet-sln"></a><span data-ttu-id="76aea-103">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="76aea-103">dotnet sln</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="76aea-104">name</span><span class="sxs-lookup"><span data-stu-id="76aea-104">Name</span></span>

<span data-ttu-id="76aea-105">`dotnet sln` - 修改 .NET Core 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="76aea-105">`dotnet sln` - Modifies a .NET Core solution file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="76aea-106">摘要</span><span class="sxs-lookup"><span data-stu-id="76aea-106">Synopsis</span></span>

```
dotnet sln [<SOLUTION_NAME>] add <PROJECT> <PROJECT> ...
dotnet sln [<SOLUTION_NAME>] add <GLOBBING_PATTERN>
dotnet sln [<SOLUTION_NAME>] remove <PROJECT> <PROJECT> ...
dotnet sln [<SOLUTION_NAME>] remove <GLOBBING_PATTERN>
dotnet sln [<SOLUTION_NAME>] list
dotnet sln [-h|--help]
```

## <a name="description"></a><span data-ttu-id="76aea-107">描述</span><span class="sxs-lookup"><span data-stu-id="76aea-107">Description</span></span>

<span data-ttu-id="76aea-108">使用 `dotnet sln` 命令，可以便捷地在解决方案文件中添加、删除和列出项目。</span><span class="sxs-lookup"><span data-stu-id="76aea-108">The `dotnet sln` command provides a convenient way to add, remove, and list projects in a solution file.</span></span>

## <a name="commands"></a><span data-ttu-id="76aea-109">命令</span><span class="sxs-lookup"><span data-stu-id="76aea-109">Commands</span></span>

`add <PROJECT> ...`

`add <GLOBBING_PATTERN>`

<span data-ttu-id="76aea-110">将一个或多个项目添加到解决方案文件中。</span><span class="sxs-lookup"><span data-stu-id="76aea-110">Adds a project or multiple projects to the solution file.</span></span> <span data-ttu-id="76aea-111">基于 Unix/Linux 的终端支持[通配模式](https://en.wikipedia.org/wiki/Glob_(programming))。</span><span class="sxs-lookup"><span data-stu-id="76aea-111">[Globbing patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux based terminals.</span></span>

`remove <PROJECT> ...`

`remove <GLOBBING_PATTERN>`

<span data-ttu-id="76aea-112">从解决方案文件中删除一个或多个项目。</span><span class="sxs-lookup"><span data-stu-id="76aea-112">Removes a project or multiple projects from the solution file.</span></span> <span data-ttu-id="76aea-113">基于 Unix/Linux 的终端支持[通配模式](https://en.wikipedia.org/wiki/Glob_(programming))。</span><span class="sxs-lookup"><span data-stu-id="76aea-113">[Globbing patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux based terminals.</span></span>

`list`

<span data-ttu-id="76aea-114">列出解决方案文件中的所有项目。</span><span class="sxs-lookup"><span data-stu-id="76aea-114">Lists all projects in a solution file.</span></span>

## <a name="arguments"></a><span data-ttu-id="76aea-115">自变量</span><span class="sxs-lookup"><span data-stu-id="76aea-115">Arguments</span></span>

`SOLUTION_NAME`

<span data-ttu-id="76aea-116">要使用的解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="76aea-116">Solution file to use.</span></span> <span data-ttu-id="76aea-117">如果未指定，此命令会搜索当前目录来获取一个项目文件。</span><span class="sxs-lookup"><span data-stu-id="76aea-117">If not specified, the command searches the current directory for one.</span></span> <span data-ttu-id="76aea-118">如果目录中有多个解决方案文件，必须指定一个。</span><span class="sxs-lookup"><span data-stu-id="76aea-118">If there are multiple solution files in the directory, one must be specified.</span></span>

## <a name="options"></a><span data-ttu-id="76aea-119">选项</span><span class="sxs-lookup"><span data-stu-id="76aea-119">Options</span></span>

`-h|--help`

<span data-ttu-id="76aea-120">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="76aea-120">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="76aea-121">示例</span><span class="sxs-lookup"><span data-stu-id="76aea-121">Examples</span></span>

<span data-ttu-id="76aea-122">将一个 C# 项目添加到解决方案中：</span><span class="sxs-lookup"><span data-stu-id="76aea-122">Add a C# project to a solution:</span></span>

`dotnet sln todo.sln add todo-app/todo-app.csproj`

<span data-ttu-id="76aea-123">从解决方案中删除一个 C# 项目：</span><span class="sxs-lookup"><span data-stu-id="76aea-123">Remove a C# project from a solution:</span></span>

`dotnet sln todo.sln remove todo-app/todo-app.csproj`

<span data-ttu-id="76aea-124">将多个 C# 项目添加到解决方案中：</span><span class="sxs-lookup"><span data-stu-id="76aea-124">Add multiple C# projects to a solution:</span></span>

`dotnet sln todo.sln add todo-app/todo-app.csproj back-end/back-end.csproj`

<span data-ttu-id="76aea-125">从解决方案中删除多个 C# 项目：</span><span class="sxs-lookup"><span data-stu-id="76aea-125">Remove multiple C# projects from a solution:</span></span>

`dotnet sln todo.sln remove todo-app/todo-app.csproj back-end/back-end.csproj`

<span data-ttu-id="76aea-126">使用通配模式将多个 C# 项目添加到解决方案中：</span><span class="sxs-lookup"><span data-stu-id="76aea-126">Add multiple C# projects to a solution using a globbing pattern:</span></span>

`dotnet sln todo.sln add **/*.csproj`

<span data-ttu-id="76aea-127">使用通配模式从解决方案中删除多个 C# 项目：</span><span class="sxs-lookup"><span data-stu-id="76aea-127">Remove multiple C# projects from a solution using a globbing pattern:</span></span>

`dotnet sln todo.sln remove **/*.csproj`
