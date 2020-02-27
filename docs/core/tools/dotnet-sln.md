---
title: dotnet sln 命令
description: 使用 dotnet-sln 命令，可以便捷地在解决方案文件中添加、删除和列出项目。
ms.date: 02/14/2020
ms.openlocfilehash: b2455c04a46b2a10b8142d8ddc2d8129f2154b27
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543477"
---
# <a name="dotnet-sln"></a><span data-ttu-id="d25f5-103">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="d25f5-103">dotnet sln</span></span>

<span data-ttu-id="d25f5-104">**本文适用于：** ✔️ .NET Core 2.x SDK 及更高版本</span><span class="sxs-lookup"><span data-stu-id="d25f5-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="d25f5-105">“属性”</span><span class="sxs-lookup"><span data-stu-id="d25f5-105">Name</span></span>

<span data-ttu-id="d25f5-106">`dotnet sln` - 在 .NET Core 解决方案文件中列出或修改项目。</span><span class="sxs-lookup"><span data-stu-id="d25f5-106">`dotnet sln` - Lists or modifies the projects in a .NET Core solution file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="d25f5-107">摘要</span><span class="sxs-lookup"><span data-stu-id="d25f5-107">Synopsis</span></span>

```dotnetcli
dotnet sln [<SOLUTION_FILE>] [command] [-h|--help]
```

## <a name="description"></a><span data-ttu-id="d25f5-108">描述</span><span class="sxs-lookup"><span data-stu-id="d25f5-108">Description</span></span>

<span data-ttu-id="d25f5-109">使用 `dotnet sln` 命令，可以便捷地在解决方案文件中列出和修改项目。</span><span class="sxs-lookup"><span data-stu-id="d25f5-109">The `dotnet sln` command provides a convenient way to list and modify projects in a solution file.</span></span>

<span data-ttu-id="d25f5-110">若要使用 `dotnet sln` 命令，必须存在解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="d25f5-110">To use the `dotnet sln` command, the solution file must already exist.</span></span> <span data-ttu-id="d25f5-111">如果需要创建一个解决方案文件，请使用 [dotnet new](dotnet-new.md) 命令，如下例所示：</span><span class="sxs-lookup"><span data-stu-id="d25f5-111">If you need to create one, use the [dotnet new](dotnet-new.md) command, as in the following example:</span></span>

```dotnetcli
dotnet new sln
```

## <a name="arguments"></a><span data-ttu-id="d25f5-112">自变量</span><span class="sxs-lookup"><span data-stu-id="d25f5-112">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="d25f5-113">要使用的解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="d25f5-113">The solution file to use.</span></span> <span data-ttu-id="d25f5-114">如果省略此参数，此命令会搜索当前目录来获取一个解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="d25f5-114">If this argument is omitted, the command searches the current directory for one.</span></span> <span data-ttu-id="d25f5-115">如果未找到解决方案文件或找到多个解决方案文件，则该命令将失败。</span><span class="sxs-lookup"><span data-stu-id="d25f5-115">If it finds no solution file or multiple solution files, the command fails.</span></span>

## <a name="options"></a><span data-ttu-id="d25f5-116">选项</span><span class="sxs-lookup"><span data-stu-id="d25f5-116">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="d25f5-117">打印出有关如何使用命令的说明。</span><span class="sxs-lookup"><span data-stu-id="d25f5-117">Prints out a description of how to use the command.</span></span>

## <a name="commands"></a><span data-ttu-id="d25f5-118">命令</span><span class="sxs-lookup"><span data-stu-id="d25f5-118">Commands</span></span>

### `list`

<span data-ttu-id="d25f5-119">列出解决方案文件中的所有项目。</span><span class="sxs-lookup"><span data-stu-id="d25f5-119">Lists all projects in a solution file.</span></span>

#### <a name="synopsis"></a><span data-ttu-id="d25f5-120">摘要</span><span class="sxs-lookup"><span data-stu-id="d25f5-120">Synopsis</span></span>

```dotnetcli
dotnet sln list [-h|--help]
```

#### <a name="arguments"></a><span data-ttu-id="d25f5-121">自变量</span><span class="sxs-lookup"><span data-stu-id="d25f5-121">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="d25f5-122">要使用的解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="d25f5-122">The solution file to use.</span></span> <span data-ttu-id="d25f5-123">如果省略此参数，此命令会搜索当前目录来获取一个解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="d25f5-123">If this argument is omitted, the command searches the current directory for one.</span></span> <span data-ttu-id="d25f5-124">如果未找到解决方案文件或找到多个解决方案文件，则该命令将失败。</span><span class="sxs-lookup"><span data-stu-id="d25f5-124">If it finds no solution file or multiple solution files, the command fails.</span></span>

#### <a name="options"></a><span data-ttu-id="d25f5-125">选项</span><span class="sxs-lookup"><span data-stu-id="d25f5-125">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="d25f5-126">打印出有关如何使用命令的说明。</span><span class="sxs-lookup"><span data-stu-id="d25f5-126">Prints out a description of how to use the command.</span></span>
  
### `add`

<span data-ttu-id="d25f5-127">将一个或多个项目添加到解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="d25f5-127">Adds one or more projects to the solution file.</span></span>

#### <a name="synopsis"></a><span data-ttu-id="d25f5-128">摘要</span><span class="sxs-lookup"><span data-stu-id="d25f5-128">Synopsis</span></span>

```dotnetcli
dotnet sln [<SOLUTION_FILE>] add [--in-root] [-s|--solution-folder] <PROJECT_PATH> [<PROJECT_PATH>...]
dotnet sln add [-h|--help]
```

#### <a name="arguments"></a><span data-ttu-id="d25f5-129">自变量</span><span class="sxs-lookup"><span data-stu-id="d25f5-129">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="d25f5-130">要使用的解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="d25f5-130">The solution file to use.</span></span> <span data-ttu-id="d25f5-131">如果未指定，此命令会搜索当前目录以获取一个解决方案文件，如果找到多个解决方案文件，则该命令将失败。</span><span class="sxs-lookup"><span data-stu-id="d25f5-131">If it is unspecified, the command searches the current directory for one and fails if there are multiple solution files.</span></span>

- **`PROJECT_PATH`**

  <span data-ttu-id="d25f5-132">要添加到解决方案的一个或多个项目的路径。</span><span class="sxs-lookup"><span data-stu-id="d25f5-132">The path to the project or projects to add to the solution.</span></span> <span data-ttu-id="d25f5-133">Unix/Linux shell [glob 模式](https://en.wikipedia.org/wiki/Glob_(programming))扩展由 `dotnet sln` 命令正确处理。</span><span class="sxs-lookup"><span data-stu-id="d25f5-133">Unix/Linux shell [globbing pattern](https://en.wikipedia.org/wiki/Glob_(programming)) expansions are processed correctly by the `dotnet sln` command.</span></span>

#### <a name="options"></a><span data-ttu-id="d25f5-134">选项</span><span class="sxs-lookup"><span data-stu-id="d25f5-134">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="d25f5-135">打印出有关如何使用命令的说明。</span><span class="sxs-lookup"><span data-stu-id="d25f5-135">Prints out a description of how to use the command.</span></span>

- **`--in-root`**

  <span data-ttu-id="d25f5-136">将项目放在解决方案的根目录下，而不是创建解决方案文件夹。</span><span class="sxs-lookup"><span data-stu-id="d25f5-136">Places the projects in the root of the solution, rather than creating a solution folder.</span></span> <span data-ttu-id="d25f5-137">自 .NET Core 3.0 SDK 起可用。</span><span class="sxs-lookup"><span data-stu-id="d25f5-137">Available since .NET Core 3.0 SDK.</span></span>

- **`-s|--solution-folder`**

  <span data-ttu-id="d25f5-138">要将项目添加到的目标解决方案文件夹路径。</span><span class="sxs-lookup"><span data-stu-id="d25f5-138">The destination solution folder path to add the projects to.</span></span> <span data-ttu-id="d25f5-139">自 .NET Core 3.0 SDK 起可用。</span><span class="sxs-lookup"><span data-stu-id="d25f5-139">Available since .NET Core 3.0 SDK.</span></span>

### `remove`

<span data-ttu-id="d25f5-140">从解决方案文件中删除一个或多个项目。</span><span class="sxs-lookup"><span data-stu-id="d25f5-140">Removes a project or multiple projects from the solution file.</span></span>

#### <a name="synopsis"></a><span data-ttu-id="d25f5-141">摘要</span><span class="sxs-lookup"><span data-stu-id="d25f5-141">Synopsis</span></span>

```dotnetcli
dotnet sln [<SOLUTION_FILE>] remove <PROJECT_PATH> [<PROJECT_PATH>...]
dotnet sln [<SOLUTION_FILE>] remove [-h|--help]
```

#### <a name="arguments"></a><span data-ttu-id="d25f5-142">自变量</span><span class="sxs-lookup"><span data-stu-id="d25f5-142">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="d25f5-143">要使用的解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="d25f5-143">The solution file to use.</span></span> <span data-ttu-id="d25f5-144">如果保留未指定，此命令会搜索当前目录以获取一个解决方案文件，如果找到多个解决方案文件，则该命令将失败。</span><span class="sxs-lookup"><span data-stu-id="d25f5-144">If is left unspecified, the command searches the current directory for one and fails if there are multiple solution files.</span></span>

- **`PROJECT_PATH`**

  <span data-ttu-id="d25f5-145">要添加到解决方案的一个或多个项目的路径。</span><span class="sxs-lookup"><span data-stu-id="d25f5-145">The path to the project or projects to add to the solution.</span></span> <span data-ttu-id="d25f5-146">Unix/Linux shell [glob 模式](https://en.wikipedia.org/wiki/Glob_(programming))扩展由 `dotnet sln` 命令正确处理。</span><span class="sxs-lookup"><span data-stu-id="d25f5-146">Unix/Linux shell [globbing pattern](https://en.wikipedia.org/wiki/Glob_(programming)) expansions are processed correctly by the `dotnet sln` command.</span></span>

#### <a name="options"></a><span data-ttu-id="d25f5-147">选项</span><span class="sxs-lookup"><span data-stu-id="d25f5-147">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="d25f5-148">打印出有关如何使用命令的说明。</span><span class="sxs-lookup"><span data-stu-id="d25f5-148">Prints out a description of how to use the command.</span></span>

## <a name="examples"></a><span data-ttu-id="d25f5-149">示例</span><span class="sxs-lookup"><span data-stu-id="d25f5-149">Examples</span></span>

- <span data-ttu-id="d25f5-150">在解决方案中列出项目：</span><span class="sxs-lookup"><span data-stu-id="d25f5-150">List the projects in a solution:</span></span>

  ```dotnetcli
  dotnet sln todo.sln list
  ```

- <span data-ttu-id="d25f5-151">将一个 C# 项目添加到解决方案中：</span><span class="sxs-lookup"><span data-stu-id="d25f5-151">Add a C# project to a solution:</span></span>

  ```dotnetcli
  dotnet sln add todo-app/todo-app.csproj
  ```

- <span data-ttu-id="d25f5-152">从解决方案中删除一个 C# 项目：</span><span class="sxs-lookup"><span data-stu-id="d25f5-152">Remove a C# project from a solution:</span></span>

  ```dotnetcli
  dotnet sln remove todo-app/todo-app.csproj
  ```

- <span data-ttu-id="d25f5-153">将多个 C# 项目添加到解决方案的根目录中：</span><span class="sxs-lookup"><span data-stu-id="d25f5-153">Add multiple C# projects to the root of a solution:</span></span>

  ```dotnetcli
  dotnet sln todo.sln add todo-app/todo-app.csproj back-end/back-end.csproj --in-root
  ```

- <span data-ttu-id="d25f5-154">将多个 C# 项目添加到解决方案中：</span><span class="sxs-lookup"><span data-stu-id="d25f5-154">Add multiple C# projects to a solution:</span></span>

  ```dotnetcli
  dotnet sln todo.sln add todo-app/todo-app.csproj back-end/back-end.csproj
  ```

- <span data-ttu-id="d25f5-155">从解决方案中删除多个 C# 项目：</span><span class="sxs-lookup"><span data-stu-id="d25f5-155">Remove multiple C# projects from a solution:</span></span>

  ```dotnetcli
  dotnet sln todo.sln remove todo-app/todo-app.csproj back-end/back-end.csproj
  ```

- <span data-ttu-id="d25f5-156">使用 glob 模式（仅限 Unix/Linux）将多个 C# 项目添加到解决方案中：</span><span class="sxs-lookup"><span data-stu-id="d25f5-156">Add multiple C# projects to a solution using a globbing pattern (Unix/Linux only):</span></span>

  ```dotnetcli
  dotnet sln todo.sln add **/*.csproj
  ```

- <span data-ttu-id="d25f5-157">使用 glob 模式（仅限 Unix/Linux）将多个 C# 项目从解决方案中删除：</span><span class="sxs-lookup"><span data-stu-id="d25f5-157">Remove multiple C# projects from a solution using a globbing pattern (Unix/Linux only):</span></span>

  ```dotnetcli
  dotnet sln todo.sln remove **/*.csproj
  ```
