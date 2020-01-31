---
title: dotnet sln 命令
description: 使用 dotnet-sln 命令，可以便捷地在解决方案文件中添加、删除和列出项目。
ms.date: 10/29/2019
ms.openlocfilehash: e344deaae0867202a79a3c38df48a2be8d4d7d13
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76733081"
---
# <a name="dotnet-sln"></a><span data-ttu-id="8e805-103">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="8e805-103">dotnet sln</span></span>

<span data-ttu-id="8e805-104"> 本文适用于：✔️ .NET Core 1.x SDK 及更高版本</span><span class="sxs-lookup"><span data-stu-id="8e805-104">**This article applies to:** ✔️ .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="8e805-105">“属性”</span><span class="sxs-lookup"><span data-stu-id="8e805-105">Name</span></span>

<span data-ttu-id="8e805-106">`dotnet sln` - 修改 .NET Core 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="8e805-106">`dotnet sln` - Modifies a .NET Core solution file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="8e805-107">摘要</span><span class="sxs-lookup"><span data-stu-id="8e805-107">Synopsis</span></span>

```dotnetcli
dotnet sln [<SOLUTION_FILE>] [command] [-h|--help]
```

## <a name="description"></a><span data-ttu-id="8e805-108">描述</span><span class="sxs-lookup"><span data-stu-id="8e805-108">Description</span></span>

<span data-ttu-id="8e805-109">使用 `dotnet sln` 命令，可以便捷地在解决方案文件中添加、删除和列出项目。</span><span class="sxs-lookup"><span data-stu-id="8e805-109">The `dotnet sln` command provides a convenient way to add, remove, and list projects in a solution file.</span></span>

<span data-ttu-id="8e805-110">若要使用 `dotnet sln` 命令，必须存在解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="8e805-110">To use the `dotnet sln` command, the solution file must already exist.</span></span> <span data-ttu-id="8e805-111">如果需要创建一个解决方案文件，请使用 [dotnet new](dotnet-new.md) 命令，如下例所示：</span><span class="sxs-lookup"><span data-stu-id="8e805-111">If you need to create one, use the [dotnet new](dotnet-new.md) command, like in the following example:</span></span>

```dotnetcli
dotnet new sln
```

## <a name="arguments"></a><span data-ttu-id="8e805-112">自变量</span><span class="sxs-lookup"><span data-stu-id="8e805-112">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="8e805-113">要使用的解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="8e805-113">The solution file to use.</span></span> <span data-ttu-id="8e805-114">如果未指定，此命令会搜索当前目录来获取一个项目文件。</span><span class="sxs-lookup"><span data-stu-id="8e805-114">If not specified, the command searches the current directory for one.</span></span> <span data-ttu-id="8e805-115">如果目录中有多个解决方案文件，必须指定一个。</span><span class="sxs-lookup"><span data-stu-id="8e805-115">If there are multiple solution files in the directory, one must be specified.</span></span>

## <a name="options"></a><span data-ttu-id="8e805-116">选项</span><span class="sxs-lookup"><span data-stu-id="8e805-116">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="8e805-117">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="8e805-117">Prints out a short help for the command.</span></span>

## <a name="commands"></a><span data-ttu-id="8e805-118">命令</span><span class="sxs-lookup"><span data-stu-id="8e805-118">Commands</span></span>

### `add`

<span data-ttu-id="8e805-119">将一个或多个项目添加到解决方案文件中。</span><span class="sxs-lookup"><span data-stu-id="8e805-119">Adds a project or multiple projects to the solution file.</span></span>

#### <a name="synopsis"></a><span data-ttu-id="8e805-120">摘要</span><span class="sxs-lookup"><span data-stu-id="8e805-120">Synopsis</span></span>

```dotnetcli
dotnet sln [<SOLUTION_FILE>] add [--in-root] [-s|--solution-folder] <PROJECT_PATH>
dotnet sln add [-h|--help]
```

#### <a name="arguments"></a><span data-ttu-id="8e805-121">自变量</span><span class="sxs-lookup"><span data-stu-id="8e805-121">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="8e805-122">要使用的解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="8e805-122">The solution file to use.</span></span> <span data-ttu-id="8e805-123">如果未指定，此命令会搜索当前目录来获取一个项目文件。</span><span class="sxs-lookup"><span data-stu-id="8e805-123">If not specified, the command searches the current directory for one.</span></span> <span data-ttu-id="8e805-124">如果目录中有多个解决方案文件，必须指定一个。</span><span class="sxs-lookup"><span data-stu-id="8e805-124">If there are multiple solution files in the directory, one must be specified.</span></span>

- **`PROJECT_PATH`**

  <span data-ttu-id="8e805-125">要添加到解决方案的项目的路径。</span><span class="sxs-lookup"><span data-stu-id="8e805-125">The path to the project to add to the solution.</span></span> <span data-ttu-id="8e805-126">通过用空格将项目彼此隔开，可以添加多个项目。</span><span class="sxs-lookup"><span data-stu-id="8e805-126">Add multiple projects by adding one after the other separated by spaces.</span></span> <span data-ttu-id="8e805-127">Unix/Linux shell [glob 模式](https://en.wikipedia.org/wiki/Glob_(programming))扩展由 `dotnet sln` 命令正确处理。</span><span class="sxs-lookup"><span data-stu-id="8e805-127">Unix/Linux shell [globbing pattern](https://en.wikipedia.org/wiki/Glob_(programming)) expansions are processed correctly by the `dotnet sln` command.</span></span>

#### <a name="options"></a><span data-ttu-id="8e805-128">选项</span><span class="sxs-lookup"><span data-stu-id="8e805-128">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="8e805-129">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="8e805-129">Prints out a short help for the command.</span></span>

- **`--in-root`**

  <span data-ttu-id="8e805-130">将项目放在解决方案的根目录下，而不是创建解决方案文件夹。</span><span class="sxs-lookup"><span data-stu-id="8e805-130">Places the projects in the root of the solution, rather than creating a solution folder.</span></span> <span data-ttu-id="8e805-131">自 .NET Core 3.0 SDK 起可用。</span><span class="sxs-lookup"><span data-stu-id="8e805-131">Available since .NET Core 3.0 SDK.</span></span>

- **`-s|--solution-folder`**

  <span data-ttu-id="8e805-132">要将项目添加到的目标解决方案文件夹路径。</span><span class="sxs-lookup"><span data-stu-id="8e805-132">The destination solution folder path to add the projects to.</span></span> <span data-ttu-id="8e805-133">自 .NET Core 3.0 SDK 起可用。</span><span class="sxs-lookup"><span data-stu-id="8e805-133">Available since .NET Core 3.0 SDK.</span></span>

### `remove`

<span data-ttu-id="8e805-134">从解决方案文件中删除一个或多个项目。</span><span class="sxs-lookup"><span data-stu-id="8e805-134">Removes a project or multiple projects from the solution file.</span></span>

#### <a name="synopsis"></a><span data-ttu-id="8e805-135">摘要</span><span class="sxs-lookup"><span data-stu-id="8e805-135">Synopsis</span></span>

```dotnetcli
dotnet sln [<SOLUTION_FILE>] remove <PROJECT_PATH>
dotnet sln [<SOLUTION_FILE>] remove [-h|--help]
```

#### <a name="arguments"></a><span data-ttu-id="8e805-136">自变量</span><span class="sxs-lookup"><span data-stu-id="8e805-136">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="8e805-137">要使用的解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="8e805-137">The solution file to use.</span></span> <span data-ttu-id="8e805-138">如果未指定，此命令会搜索当前目录来获取一个项目文件。</span><span class="sxs-lookup"><span data-stu-id="8e805-138">If not specified, the command searches the current directory for one.</span></span> <span data-ttu-id="8e805-139">如果目录中有多个解决方案文件，必须指定一个。</span><span class="sxs-lookup"><span data-stu-id="8e805-139">If there are multiple solution files in the directory, one must be specified.</span></span>

- **`PROJECT_PATH`**

  <span data-ttu-id="8e805-140">要从解决方案中删除的项目路径。</span><span class="sxs-lookup"><span data-stu-id="8e805-140">The path to the project to remove from the solution.</span></span> <span data-ttu-id="8e805-141">通过用空格将项目彼此隔开，可以删除多个项目。</span><span class="sxs-lookup"><span data-stu-id="8e805-141">Remove multiple projects by adding one after the other separated by spaces.</span></span> <span data-ttu-id="8e805-142">Unix/Linux shell [glob 模式](https://en.wikipedia.org/wiki/Glob_(programming))扩展由 `dotnet sln` 命令正确处理。</span><span class="sxs-lookup"><span data-stu-id="8e805-142">Unix/Linux shell [globbing pattern](https://en.wikipedia.org/wiki/Glob_(programming)) expansions are processed correctly by the `dotnet sln` command.</span></span>

#### <a name="options"></a><span data-ttu-id="8e805-143">选项</span><span class="sxs-lookup"><span data-stu-id="8e805-143">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="8e805-144">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="8e805-144">Prints out a short help for the command.</span></span>

### `list`

<span data-ttu-id="8e805-145">列出解决方案文件中的所有项目。</span><span class="sxs-lookup"><span data-stu-id="8e805-145">Lists all projects in a solution file.</span></span>

#### <a name="synopsis"></a><span data-ttu-id="8e805-146">摘要</span><span class="sxs-lookup"><span data-stu-id="8e805-146">Synopsis</span></span>

```dotnetcli
dotnet sln list [-h|--help]
```

#### <a name="arguments"></a><span data-ttu-id="8e805-147">自变量</span><span class="sxs-lookup"><span data-stu-id="8e805-147">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="8e805-148">要使用的解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="8e805-148">The solution file to use.</span></span> <span data-ttu-id="8e805-149">如果未指定，此命令会搜索当前目录来获取一个项目文件。</span><span class="sxs-lookup"><span data-stu-id="8e805-149">If not specified, the command searches the current directory for one.</span></span> <span data-ttu-id="8e805-150">如果目录中有多个解决方案文件，必须指定一个。</span><span class="sxs-lookup"><span data-stu-id="8e805-150">If there are multiple solution files in the directory, one must be specified.</span></span>

#### <a name="options"></a><span data-ttu-id="8e805-151">选项</span><span class="sxs-lookup"><span data-stu-id="8e805-151">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="8e805-152">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="8e805-152">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="8e805-153">示例</span><span class="sxs-lookup"><span data-stu-id="8e805-153">Examples</span></span>

- <span data-ttu-id="8e805-154">将一个 C# 项目添加到解决方案中：</span><span class="sxs-lookup"><span data-stu-id="8e805-154">Add a C# project to a solution:</span></span>

  ```dotnetcli
  dotnet sln todo.sln add todo-app/todo-app.csproj
  ```

- <span data-ttu-id="8e805-155">从解决方案中删除一个 C# 项目：</span><span class="sxs-lookup"><span data-stu-id="8e805-155">Remove a C# project from a solution:</span></span>

  ```dotnetcli
  dotnet sln todo.sln remove todo-app/todo-app.csproj
  ```

- <span data-ttu-id="8e805-156">将多个 C# 项目添加到解决方案中：</span><span class="sxs-lookup"><span data-stu-id="8e805-156">Add multiple C# projects to a solution:</span></span>

  ```dotnetcli
  dotnet sln todo.sln add todo-app/todo-app.csproj back-end/back-end.csproj
  ```

- <span data-ttu-id="8e805-157">从解决方案中删除多个 C# 项目：</span><span class="sxs-lookup"><span data-stu-id="8e805-157">Remove multiple C# projects from a solution:</span></span>

  ```dotnetcli
  dotnet sln todo.sln remove todo-app/todo-app.csproj back-end/back-end.csproj
  ```

- <span data-ttu-id="8e805-158">使用 glob 模式（仅限 Unix/Linux）将多个 C# 项目添加到解决方案中：</span><span class="sxs-lookup"><span data-stu-id="8e805-158">Add multiple C# projects to a solution using a globbing pattern (Unix/Linux only):</span></span>

  ```dotnetcli
  dotnet sln todo.sln add **/*.csproj
  ```

- <span data-ttu-id="8e805-159">使用 glob 模式（仅限 Unix/Linux）将多个 C# 项目从解决方案中删除：</span><span class="sxs-lookup"><span data-stu-id="8e805-159">Remove multiple C# projects from a solution using a globbing pattern (Unix/Linux only):</span></span>

  ```dotnetcli
  dotnet sln todo.sln remove **/*.csproj
  ```
