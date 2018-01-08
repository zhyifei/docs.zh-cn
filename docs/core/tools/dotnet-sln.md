---
title: "dotnet sln 命令 - .NET Core CLI"
description: "使用 dotnet-sln 命令，可以便捷地在解决方案文件中添加、删除和列出项目。"
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.workload: dotnetcore
ms.openlocfilehash: c90cfec0e2197e2519bf3f7aae1c9569db79aadf
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="dotnet-sln"></a><span data-ttu-id="1b833-103">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="1b833-103">dotnet sln</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="1b833-104">name</span><span class="sxs-lookup"><span data-stu-id="1b833-104">Name</span></span>

<span data-ttu-id="1b833-105">`dotnet-sln` - 修改 .NET Core 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="1b833-105">`dotnet-sln` - Modifies a .NET Core solution file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="1b833-106">摘要</span><span class="sxs-lookup"><span data-stu-id="1b833-106">Synopsis</span></span>

```
dotnet sln [<SOLUTION_NAME>] add <PROJECT> <PROJECT> ...
dotnet sln [<SOLUTION_NAME>] add <GLOBBING_PATTERN>
dotnet sln [<SOLUTION_NAME>] remove <PROJECT> <PROJECT> ...
dotnet sln [<SOLUTION_NAME>] remove <GLOBBING_PATTERN>
dotnet sln [<SOLUTION_NAME>] list
dotnet sln [-h|--help]
```

## <a name="description"></a><span data-ttu-id="1b833-107">描述</span><span class="sxs-lookup"><span data-stu-id="1b833-107">Description</span></span>

<span data-ttu-id="1b833-108">使用 `dotnet sln` 命令，可以便捷地在解决方案文件中添加、删除和列出项目。</span><span class="sxs-lookup"><span data-stu-id="1b833-108">The `dotnet sln` command provides a convenient way to add, remove, and list projects in a solution file.</span></span>

## <a name="commands"></a><span data-ttu-id="1b833-109">命令</span><span class="sxs-lookup"><span data-stu-id="1b833-109">Commands</span></span>

`add <PROJECT> ...`

`add <GLOBBING_PATTERN>`

<span data-ttu-id="1b833-110">将一个或多个项目添加到解决方案文件中。</span><span class="sxs-lookup"><span data-stu-id="1b833-110">Adds a project or multiple projects to the solution file.</span></span> <span data-ttu-id="1b833-111">基于 Unix/Linux 的终端支持[通配模式](https://en.wikipedia.org/wiki/Glob_(programming))。</span><span class="sxs-lookup"><span data-stu-id="1b833-111">[Globbing patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux based terminals.</span></span>

`remove <PROJECT> ...`

`remove <GLOBBING_PATTERN>`

<span data-ttu-id="1b833-112">从解决方案文件中删除一个或多个项目。</span><span class="sxs-lookup"><span data-stu-id="1b833-112">Removes a project or multiple projects from the solution file.</span></span> <span data-ttu-id="1b833-113">基于 Unix/Linux 的终端支持[通配模式](https://en.wikipedia.org/wiki/Glob_(programming))。</span><span class="sxs-lookup"><span data-stu-id="1b833-113">[Globbing patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux based terminals.</span></span>

`list`

<span data-ttu-id="1b833-114">列出解决方案文件中的所有项目。</span><span class="sxs-lookup"><span data-stu-id="1b833-114">Lists all projects in a solution file.</span></span>

## <a name="arguments"></a><span data-ttu-id="1b833-115">自变量</span><span class="sxs-lookup"><span data-stu-id="1b833-115">Arguments</span></span>

`SOLUTION_NAME`

<span data-ttu-id="1b833-116">要使用的解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="1b833-116">Solution file to use.</span></span> <span data-ttu-id="1b833-117">如果未指定，此命令会搜索当前目录来获取一个项目文件。</span><span class="sxs-lookup"><span data-stu-id="1b833-117">If not specified, the command searches the current directory for one.</span></span> <span data-ttu-id="1b833-118">如果目录中有多个解决方案文件，必须指定一个。</span><span class="sxs-lookup"><span data-stu-id="1b833-118">If there are multiple solution files in the directory, one must be specified.</span></span>

## <a name="options"></a><span data-ttu-id="1b833-119">选项</span><span class="sxs-lookup"><span data-stu-id="1b833-119">Options</span></span>

`-h|--help`

<span data-ttu-id="1b833-120">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="1b833-120">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="1b833-121">示例</span><span class="sxs-lookup"><span data-stu-id="1b833-121">Examples</span></span>

<span data-ttu-id="1b833-122">将一个 C# 项目添加到解决方案中：</span><span class="sxs-lookup"><span data-stu-id="1b833-122">Add a C# project to a solution:</span></span>

`dotnet sln todo.sln add todo-app/todo-app.csproj`

<span data-ttu-id="1b833-123">从解决方案中删除一个 C# 项目：</span><span class="sxs-lookup"><span data-stu-id="1b833-123">Remove a C# project from a solution:</span></span>

`dotnet sln todo.sln remove todo-app/todo-app.csproj`

<span data-ttu-id="1b833-124">将多个 C# 项目添加到解决方案中：</span><span class="sxs-lookup"><span data-stu-id="1b833-124">Add multiple C# projects to a solution:</span></span>

`dotnet sln todo.sln add todo-app/todo-app.csproj back-end/back-end.csproj`

<span data-ttu-id="1b833-125">从解决方案中删除多个 C# 项目：</span><span class="sxs-lookup"><span data-stu-id="1b833-125">Remove multiple C# projects from a solution:</span></span>

`dotnet sln todo.sln remove todo-app/todo-app.csproj back-end/back-end.csproj`

<span data-ttu-id="1b833-126">使用通配模式将多个 C# 项目添加到解决方案中：</span><span class="sxs-lookup"><span data-stu-id="1b833-126">Add multiple C# projects to a solution using a globbing pattern:</span></span>

`dotnet sln todo.sln add **/*.csproj`

<span data-ttu-id="1b833-127">使用通配模式从解决方案中删除多个 C# 项目：</span><span class="sxs-lookup"><span data-stu-id="1b833-127">Remove multiple C# projects from a solution using a globbing pattern:</span></span>

`dotnet sln todo.sln remove **/*.csproj`