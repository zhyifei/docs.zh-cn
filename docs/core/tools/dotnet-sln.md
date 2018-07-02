---
title: dotnet sln 命令 - .NET Core CLI
description: 使用 dotnet-sln 命令，可以便捷地在解决方案文件中添加、删除和列出项目。
author: mairaw
ms.author: mairaw
ms.date: 06/13/2018
ms.openlocfilehash: 65ae402ef5519863886c8cf833598f5314b4bdad
ms.sourcegitcommit: 6bc4efca63e526ce6f2d257fa870f01f8c459ae4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2018
ms.locfileid: "36207760"
---
# <a name="dotnet-sln"></a><span data-ttu-id="5ba14-103">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="5ba14-103">dotnet sln</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="5ba14-104">name</span><span class="sxs-lookup"><span data-stu-id="5ba14-104">Name</span></span>

<span data-ttu-id="5ba14-105">`dotnet sln` - 修改 .NET Core 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="5ba14-105">`dotnet sln` - Modifies a .NET Core solution file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="5ba14-106">摘要</span><span class="sxs-lookup"><span data-stu-id="5ba14-106">Synopsis</span></span>

```
dotnet sln [<SOLUTION_NAME>] add <PROJECT> <PROJECT> ...
dotnet sln [<SOLUTION_NAME>] add <GLOBBING_PATTERN>
dotnet sln [<SOLUTION_NAME>] remove <PROJECT> <PROJECT> ...
dotnet sln [<SOLUTION_NAME>] remove <GLOBBING_PATTERN>
dotnet sln [<SOLUTION_NAME>] list
dotnet sln [-h|--help]
```

## <a name="description"></a><span data-ttu-id="5ba14-107">描述</span><span class="sxs-lookup"><span data-stu-id="5ba14-107">Description</span></span>

<span data-ttu-id="5ba14-108">使用 `dotnet sln` 命令，可以便捷地在解决方案文件中添加、删除和列出项目。</span><span class="sxs-lookup"><span data-stu-id="5ba14-108">The `dotnet sln` command provides a convenient way to add, remove, and list projects in a solution file.</span></span>

<span data-ttu-id="5ba14-109">若要使用 `dotnet sln` 命令，必须存在解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="5ba14-109">To use the `dotnet sln` command, the solution file must already exist.</span></span> <span data-ttu-id="5ba14-110">如果需要创建一个解决方案文件，请使用 [dotnet new](dotnet-new.md) 命令，如下例所示：</span><span class="sxs-lookup"><span data-stu-id="5ba14-110">If you need to create one, use the [dotnet new](dotnet-new.md) command, like in the following example:</span></span>

```
dotnet new sln
```

## <a name="commands"></a><span data-ttu-id="5ba14-111">命令</span><span class="sxs-lookup"><span data-stu-id="5ba14-111">Commands</span></span>

`add <PROJECT> ...`

`add <GLOBBING_PATTERN>`

<span data-ttu-id="5ba14-112">将一个或多个项目添加到解决方案文件中。</span><span class="sxs-lookup"><span data-stu-id="5ba14-112">Adds a project or multiple projects to the solution file.</span></span> <span data-ttu-id="5ba14-113">基于 Unix/Linux 的终端支持[通配模式](https://en.wikipedia.org/wiki/Glob_(programming))。</span><span class="sxs-lookup"><span data-stu-id="5ba14-113">[Globbing patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux based terminals.</span></span>

`remove <PROJECT> ...`

`remove <GLOBBING_PATTERN>`

<span data-ttu-id="5ba14-114">从解决方案文件中删除一个或多个项目。</span><span class="sxs-lookup"><span data-stu-id="5ba14-114">Removes a project or multiple projects from the solution file.</span></span> <span data-ttu-id="5ba14-115">基于 Unix/Linux 的终端支持[通配模式](https://en.wikipedia.org/wiki/Glob_(programming))。</span><span class="sxs-lookup"><span data-stu-id="5ba14-115">[Globbing patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux based terminals.</span></span>

`list`

<span data-ttu-id="5ba14-116">列出解决方案文件中的所有项目。</span><span class="sxs-lookup"><span data-stu-id="5ba14-116">Lists all projects in a solution file.</span></span>

## <a name="arguments"></a><span data-ttu-id="5ba14-117">自变量</span><span class="sxs-lookup"><span data-stu-id="5ba14-117">Arguments</span></span>

`SOLUTION_NAME`

<span data-ttu-id="5ba14-118">要使用的解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="5ba14-118">Solution file to use.</span></span> <span data-ttu-id="5ba14-119">如果未指定，此命令会搜索当前目录来获取一个项目文件。</span><span class="sxs-lookup"><span data-stu-id="5ba14-119">If not specified, the command searches the current directory for one.</span></span> <span data-ttu-id="5ba14-120">如果目录中有多个解决方案文件，必须指定一个。</span><span class="sxs-lookup"><span data-stu-id="5ba14-120">If there are multiple solution files in the directory, one must be specified.</span></span>

## <a name="options"></a><span data-ttu-id="5ba14-121">选项</span><span class="sxs-lookup"><span data-stu-id="5ba14-121">Options</span></span>

`-h|--help`

<span data-ttu-id="5ba14-122">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="5ba14-122">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="5ba14-123">示例</span><span class="sxs-lookup"><span data-stu-id="5ba14-123">Examples</span></span>

<span data-ttu-id="5ba14-124">将一个 C# 项目添加到解决方案中：</span><span class="sxs-lookup"><span data-stu-id="5ba14-124">Add a C# project to a solution:</span></span>

`dotnet sln todo.sln add todo-app/todo-app.csproj`

<span data-ttu-id="5ba14-125">从解决方案中删除一个 C# 项目：</span><span class="sxs-lookup"><span data-stu-id="5ba14-125">Remove a C# project from a solution:</span></span>

`dotnet sln todo.sln remove todo-app/todo-app.csproj`

<span data-ttu-id="5ba14-126">将多个 C# 项目添加到解决方案中：</span><span class="sxs-lookup"><span data-stu-id="5ba14-126">Add multiple C# projects to a solution:</span></span>

`dotnet sln todo.sln add todo-app/todo-app.csproj back-end/back-end.csproj`

<span data-ttu-id="5ba14-127">从解决方案中删除多个 C# 项目：</span><span class="sxs-lookup"><span data-stu-id="5ba14-127">Remove multiple C# projects from a solution:</span></span>

`dotnet sln todo.sln remove todo-app/todo-app.csproj back-end/back-end.csproj`

<span data-ttu-id="5ba14-128">使用通配模式将多个 C# 项目添加到解决方案中：</span><span class="sxs-lookup"><span data-stu-id="5ba14-128">Add multiple C# projects to a solution using a globbing pattern:</span></span>

`dotnet sln todo.sln add **/*.csproj`

<span data-ttu-id="5ba14-129">使用通配模式从解决方案中删除多个 C# 项目：</span><span class="sxs-lookup"><span data-stu-id="5ba14-129">Remove multiple C# projects from a solution using a globbing pattern:</span></span>

`dotnet sln todo.sln remove **/*.csproj`
