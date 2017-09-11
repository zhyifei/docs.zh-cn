---
title: "dotnet-sln 命令 - .NET Core CLI"
description: "使用 dotnet-sln 命令，可以便捷地在解决方案文件中添加、删除和列出项目。"
keywords: "dotnet-sln, CLI, CLI 命令, .NET Core"
author: spboyer
ms.author: mairaw
ms.date: 04/11/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: e5a72d3e-c14b-4b0a-a978-c5e54a0988c6
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 606929fbcafddf47abf5da6d3c8ce97d5af06909
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---

# <a name="dotnet-sln"></a><span data-ttu-id="2738b-104">dotnet-sln</span><span class="sxs-lookup"><span data-stu-id="2738b-104">dotnet-sln</span></span>

## <a name="name"></a><span data-ttu-id="2738b-105">名称</span><span class="sxs-lookup"><span data-stu-id="2738b-105">Name</span></span>

<span data-ttu-id="2738b-106">`dotnet-sln` - 修改 .NET Core 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="2738b-106">`dotnet-sln` - Modifies a .NET Core solution file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="2738b-107">摘要</span><span class="sxs-lookup"><span data-stu-id="2738b-107">Synopsis</span></span>

```
dotnet sln [<SOLUTION_NAME>] add <PROJECT> <PROJECT> ...
dotnet sln [<SOLUTION_NAME>] add <GLOBBING_PATTERN>
dotnet sln [<SOLUTION_NAME>] remove <PROJECT> <PROJECT> ...
dotnet sln [<SOLUTION_NAME>] remove <GLOBBING_PATTERN>
dotnet sln [<SOLUTION_NAME>] list
dotnet sln [-h|--help]
```

## <a name="description"></a><span data-ttu-id="2738b-108">描述</span><span class="sxs-lookup"><span data-stu-id="2738b-108">Description</span></span>

<span data-ttu-id="2738b-109">使用 `dotnet sln` 命令，可以便捷地在解决方案文件中添加、删除和列出项目。</span><span class="sxs-lookup"><span data-stu-id="2738b-109">The `dotnet sln` command provides a convenient way to add, remove, and list projects in a solution file.</span></span>

## <a name="commands"></a><span data-ttu-id="2738b-110">命令</span><span class="sxs-lookup"><span data-stu-id="2738b-110">Commands</span></span>

`add <PROJECT> ...`

`add <GLOBBING_PATTERN>`

<span data-ttu-id="2738b-111">将一个或多个项目添加到解决方案文件中。</span><span class="sxs-lookup"><span data-stu-id="2738b-111">Adds a project or multiple projects to the solution file.</span></span> <span data-ttu-id="2738b-112">基于 Unix/Linux 的终端支持[通配模式](https://en.wikipedia.org/wiki/Glob_(programming))。</span><span class="sxs-lookup"><span data-stu-id="2738b-112">[Globbing patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux based terminals.</span></span>

`remove <PROJECT> ...`

`remove <GLOBBING_PATTERN>`

<span data-ttu-id="2738b-113">从解决方案文件中删除一个或多个项目。</span><span class="sxs-lookup"><span data-stu-id="2738b-113">Removes a project or multiple projects from the solution file.</span></span> <span data-ttu-id="2738b-114">基于 Unix/Linux 的终端支持[通配模式](https://en.wikipedia.org/wiki/Glob_(programming))。</span><span class="sxs-lookup"><span data-stu-id="2738b-114">[Globbing patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux based terminals.</span></span>

`list`

<span data-ttu-id="2738b-115">在解决方案文件中列出所有项目。</span><span class="sxs-lookup"><span data-stu-id="2738b-115">List all projects in a solution file.</span></span>

## <a name="arguments"></a><span data-ttu-id="2738b-116">参数</span><span class="sxs-lookup"><span data-stu-id="2738b-116">Arguments</span></span>

`SOLUTION_NAME`

<span data-ttu-id="2738b-117">要使用的解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="2738b-117">Solution file to use.</span></span> <span data-ttu-id="2738b-118">如果未指定，此命令会搜索当前目录来获取一个项目文件。</span><span class="sxs-lookup"><span data-stu-id="2738b-118">If not specified, the command searches the current directory for one.</span></span> <span data-ttu-id="2738b-119">如果目录中有多个解决方案文件，必须指定一个。</span><span class="sxs-lookup"><span data-stu-id="2738b-119">If there are multiple solution files in the directory, one must be specified.</span></span>

## <a name="options"></a><span data-ttu-id="2738b-120">选项</span><span class="sxs-lookup"><span data-stu-id="2738b-120">Options</span></span>

`-h|--help`

<span data-ttu-id="2738b-121">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="2738b-121">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="2738b-122">示例</span><span class="sxs-lookup"><span data-stu-id="2738b-122">Examples</span></span>

<span data-ttu-id="2738b-123">将一个 C# 项目添加到解决方案中：</span><span class="sxs-lookup"><span data-stu-id="2738b-123">Add a C# project to a solution:</span></span>

`dotnet sln todo.sln add todo-app/todo-app.csproj`

<span data-ttu-id="2738b-124">从解决方案中删除一个 C# 项目：</span><span class="sxs-lookup"><span data-stu-id="2738b-124">Remove a C# project from a solution:</span></span>

`dotnet sln todo.sln remove todo-app/todo-app.csproj`

<span data-ttu-id="2738b-125">将多个 C# 项目添加到解决方案中：</span><span class="sxs-lookup"><span data-stu-id="2738b-125">Add multiple C# projects to a solution:</span></span>

`dotnet sln todo.sln add todo-app/todo-app.csproj back-end/back-end.csproj`

<span data-ttu-id="2738b-126">从解决方案中删除多个 C# 项目：</span><span class="sxs-lookup"><span data-stu-id="2738b-126">Remove multiple C# projects from a solution:</span></span>

`dotnet sln todo.sln remove todo-app/todo-app.csproj back-end/back-end.csproj`

<span data-ttu-id="2738b-127">使用通配模式将多个 C# 项目添加到解决方案中：</span><span class="sxs-lookup"><span data-stu-id="2738b-127">Add multiple C# projects to a solution using a globbing pattern:</span></span>

`dotnet sln todo.sln add **/*.csproj`

<span data-ttu-id="2738b-128">使用通配模式从解决方案中删除多个 C# 项目：</span><span class="sxs-lookup"><span data-stu-id="2738b-128">Remove multiple C# projects from a solution using a globbing pattern:</span></span>

`dotnet sln todo.sln remove **/*.csproj`

