---
title: dotnet sln 命令
description: 使用 dotnet-sln 命令，可以便捷地在解决方案文件中添加、删除和列出项目。
ms.date: 06/13/2018
ms.openlocfilehash: 3f18d6a2851d955d07cecc0cbc4c161cf0ec3e08
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2019
ms.locfileid: "70202787"
---
# <a name="dotnet-sln"></a><span data-ttu-id="48ae9-103">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="48ae9-103">dotnet sln</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="48ae9-104">name</span><span class="sxs-lookup"><span data-stu-id="48ae9-104">Name</span></span>

<span data-ttu-id="48ae9-105">`dotnet sln` - 修改 .NET Core 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="48ae9-105">`dotnet sln` - Modifies a .NET Core solution file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="48ae9-106">摘要</span><span class="sxs-lookup"><span data-stu-id="48ae9-106">Synopsis</span></span>

```console
dotnet sln [<SOLUTION_NAME>] add <PROJECT> <PROJECT> ...
dotnet sln [<SOLUTION_NAME>] add <GLOBBING_PATTERN>
dotnet sln [<SOLUTION_NAME>] remove <PROJECT> <PROJECT> ...
dotnet sln [<SOLUTION_NAME>] remove <GLOBBING_PATTERN>
dotnet sln [<SOLUTION_NAME>] list
dotnet sln [-h|--help]
```

## <a name="description"></a><span data-ttu-id="48ae9-107">说明</span><span class="sxs-lookup"><span data-stu-id="48ae9-107">Description</span></span>

<span data-ttu-id="48ae9-108">使用 `dotnet sln` 命令，可以便捷地在解决方案文件中添加、删除和列出项目。</span><span class="sxs-lookup"><span data-stu-id="48ae9-108">The `dotnet sln` command provides a convenient way to add, remove, and list projects in a solution file.</span></span>

<span data-ttu-id="48ae9-109">若要使用 `dotnet sln` 命令，必须存在解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="48ae9-109">To use the `dotnet sln` command, the solution file must already exist.</span></span> <span data-ttu-id="48ae9-110">如果需要创建一个解决方案文件，请使用 [dotnet new](dotnet-new.md) 命令，如下例所示：</span><span class="sxs-lookup"><span data-stu-id="48ae9-110">If you need to create one, use the [dotnet new](dotnet-new.md) command, like in the following example:</span></span>

```console
dotnet new sln
```

## <a name="commands"></a><span data-ttu-id="48ae9-111">命令</span><span class="sxs-lookup"><span data-stu-id="48ae9-111">Commands</span></span>

`add <PROJECT> ...`

`add <GLOBBING_PATTERN>`

<span data-ttu-id="48ae9-112">将一个或多个项目添加到解决方案文件中。</span><span class="sxs-lookup"><span data-stu-id="48ae9-112">Adds a project or multiple projects to the solution file.</span></span> <span data-ttu-id="48ae9-113">基于 Unix/Linux 的终端支持[通配模式](https://en.wikipedia.org/wiki/Glob_(programming))。</span><span class="sxs-lookup"><span data-stu-id="48ae9-113">[Globbing patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux based terminals.</span></span>

`remove <PROJECT> ...`

`remove <GLOBBING_PATTERN>`

<span data-ttu-id="48ae9-114">从解决方案文件中删除一个或多个项目。</span><span class="sxs-lookup"><span data-stu-id="48ae9-114">Removes a project or multiple projects from the solution file.</span></span> <span data-ttu-id="48ae9-115">基于 Unix/Linux 的终端支持[通配模式](https://en.wikipedia.org/wiki/Glob_(programming))。</span><span class="sxs-lookup"><span data-stu-id="48ae9-115">[Globbing patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux based terminals.</span></span>

`list`

<span data-ttu-id="48ae9-116">列出解决方案文件中的所有项目。</span><span class="sxs-lookup"><span data-stu-id="48ae9-116">Lists all projects in a solution file.</span></span>

## <a name="arguments"></a><span data-ttu-id="48ae9-117">自变量</span><span class="sxs-lookup"><span data-stu-id="48ae9-117">Arguments</span></span>

`SOLUTION_NAME`

<span data-ttu-id="48ae9-118">要使用的解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="48ae9-118">Solution file to use.</span></span> <span data-ttu-id="48ae9-119">如果未指定，此命令会搜索当前目录来获取一个项目文件。</span><span class="sxs-lookup"><span data-stu-id="48ae9-119">If not specified, the command searches the current directory for one.</span></span> <span data-ttu-id="48ae9-120">如果目录中有多个解决方案文件，必须指定一个。</span><span class="sxs-lookup"><span data-stu-id="48ae9-120">If there are multiple solution files in the directory, one must be specified.</span></span>

## <a name="options"></a><span data-ttu-id="48ae9-121">选项</span><span class="sxs-lookup"><span data-stu-id="48ae9-121">Options</span></span>

`-h|--help`

<span data-ttu-id="48ae9-122">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="48ae9-122">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="48ae9-123">示例</span><span class="sxs-lookup"><span data-stu-id="48ae9-123">Examples</span></span>

<span data-ttu-id="48ae9-124">将一个 C# 项目添加到解决方案中：</span><span class="sxs-lookup"><span data-stu-id="48ae9-124">Add a C# project to a solution:</span></span>

`dotnet sln todo.sln add todo-app/todo-app.csproj`

<span data-ttu-id="48ae9-125">从解决方案中删除一个 C# 项目：</span><span class="sxs-lookup"><span data-stu-id="48ae9-125">Remove a C# project from a solution:</span></span>

`dotnet sln todo.sln remove todo-app/todo-app.csproj`

<span data-ttu-id="48ae9-126">将多个 C# 项目添加到解决方案中：</span><span class="sxs-lookup"><span data-stu-id="48ae9-126">Add multiple C# projects to a solution:</span></span>

`dotnet sln todo.sln add todo-app/todo-app.csproj back-end/back-end.csproj`

<span data-ttu-id="48ae9-127">从解决方案中删除多个 C# 项目：</span><span class="sxs-lookup"><span data-stu-id="48ae9-127">Remove multiple C# projects from a solution:</span></span>

`dotnet sln todo.sln remove todo-app/todo-app.csproj back-end/back-end.csproj`

<span data-ttu-id="48ae9-128">使用通配模式将多个 C# 项目添加到解决方案中：</span><span class="sxs-lookup"><span data-stu-id="48ae9-128">Add multiple C# projects to a solution using a globbing pattern:</span></span>

`dotnet sln todo.sln add **/*.csproj`

<span data-ttu-id="48ae9-129">使用通配模式从解决方案中删除多个 C# 项目：</span><span class="sxs-lookup"><span data-stu-id="48ae9-129">Remove multiple C# projects from a solution using a globbing pattern:</span></span>

`dotnet sln todo.sln remove **/*.csproj`

> [!NOTE]
> <span data-ttu-id="48ae9-130">通配不是 CLI 功能，而是命令行界面的一个功能。</span><span class="sxs-lookup"><span data-stu-id="48ae9-130">Globbing is not a CLI feature but rather a feature of the command shell.</span></span> <span data-ttu-id="48ae9-131">必须使用支持通配的 shell 才可成功地展开文件。</span><span class="sxs-lookup"><span data-stu-id="48ae9-131">To successfully expand the files, you must use a shell that supports globbing.</span></span> <span data-ttu-id="48ae9-132">有关通配的详细信息，请参阅[维基百科](https://en.wikipedia.org/wiki/Glob_(programming))。</span><span class="sxs-lookup"><span data-stu-id="48ae9-132">For more information about globbing, see [Wikipedia](https://en.wikipedia.org/wiki/Glob_(programming)).</span></span>
