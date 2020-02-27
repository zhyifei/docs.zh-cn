---
title: dotnet clean 命令
description: dotnet clean 命令可清除当前目录。
ms.date: 02/14/2020
ms.openlocfilehash: 186f1ea07718a8e178f88c3d079cf6e2f1f8660b
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503756"
---
# <a name="dotnet-clean"></a><span data-ttu-id="a1a93-103">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="a1a93-103">dotnet clean</span></span>

<span data-ttu-id="a1a93-104">**本文适用于：** ✔️ .NET Core 2.x SDK 及更高版本</span><span class="sxs-lookup"><span data-stu-id="a1a93-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="a1a93-105">“属性”</span><span class="sxs-lookup"><span data-stu-id="a1a93-105">Name</span></span>

<span data-ttu-id="a1a93-106">`dotnet clean` - 清除项目输出。</span><span class="sxs-lookup"><span data-stu-id="a1a93-106">`dotnet clean` - Cleans the output of a project.</span></span>

## <a name="synopsis"></a><span data-ttu-id="a1a93-107">摘要</span><span class="sxs-lookup"><span data-stu-id="a1a93-107">Synopsis</span></span>

```dotnetcli
dotnet clean [<PROJECT>|<SOLUTION>] [-c|--configuration] [-f|--framework] [--interactive]
    [--nologo] [-o|--output] [-r|--runtime] [-v|--verbosity]
dotnet clean [-h|--help]
```

## <a name="description"></a><span data-ttu-id="a1a93-108">描述</span><span class="sxs-lookup"><span data-stu-id="a1a93-108">Description</span></span>

<span data-ttu-id="a1a93-109">`dotnet clean` 命令可清除上一个生成的输出。</span><span class="sxs-lookup"><span data-stu-id="a1a93-109">The `dotnet clean` command cleans the output of the previous build.</span></span> <span data-ttu-id="a1a93-110">它以 [MSBuild 目标](/visualstudio/msbuild/msbuild-targets) 的形式实现，以便在运行命令时对项目进行评估。</span><span class="sxs-lookup"><span data-stu-id="a1a93-110">It's implemented as an [MSBuild target](/visualstudio/msbuild/msbuild-targets), so the project is evaluated when the command is run.</span></span> <span data-ttu-id="a1a93-111">只会清除在生成过程中创建的输出。</span><span class="sxs-lookup"><span data-stu-id="a1a93-111">Only the outputs created during the build are cleaned.</span></span> <span data-ttu-id="a1a93-112">中间 (*obj*) 和最终输出 (*bin*) 文件夹都会被清除。</span><span class="sxs-lookup"><span data-stu-id="a1a93-112">Both intermediate (*obj*) and final output (*bin*) folders are cleaned.</span></span>

## <a name="arguments"></a><span data-ttu-id="a1a93-113">自变量</span><span class="sxs-lookup"><span data-stu-id="a1a93-113">Arguments</span></span>

`PROJECT | SOLUTION`

<span data-ttu-id="a1a93-114">要清理的 MSBuild 项目或解决方案。</span><span class="sxs-lookup"><span data-stu-id="a1a93-114">The MSBuild project or solution to clean.</span></span> <span data-ttu-id="a1a93-115">如果未指定项目或解决方案文件，MSBuild 会在当前工作目录中搜索文件扩展名以 *proj* 或 *sln* 结尾的文件并使用该文件。</span><span class="sxs-lookup"><span data-stu-id="a1a93-115">If a project or solution file is not specified, MSBuild searches the current working directory for a file that has a file extension that ends in *proj* or *sln*, and uses that file.</span></span>

## <a name="options"></a><span data-ttu-id="a1a93-116">选项</span><span class="sxs-lookup"><span data-stu-id="a1a93-116">Options</span></span>

* **`-c|--configuration <CONFIGURATION>`**

  <span data-ttu-id="a1a93-117">定义生成配置。</span><span class="sxs-lookup"><span data-stu-id="a1a93-117">Defines the build configuration.</span></span> <span data-ttu-id="a1a93-118">大多数项目的默认配置为 `Debug`，但你可以覆盖项目中的生成配置设置。</span><span class="sxs-lookup"><span data-stu-id="a1a93-118">The default for most projects is `Debug`, but you can override the build configuration settings in your project.</span></span> <span data-ttu-id="a1a93-119">只有在生成期间指定了此选项，才必须在清除时使用此选项。</span><span class="sxs-lookup"><span data-stu-id="a1a93-119">This option is only required when cleaning if you specified it during build time.</span></span>

* **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="a1a93-120">在生成时指定的[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="a1a93-120">The [framework](../../standard/frameworks.md) that was specified at build time.</span></span> <span data-ttu-id="a1a93-121">必须在[项目文件](csproj.md)中定义该框架。</span><span class="sxs-lookup"><span data-stu-id="a1a93-121">The framework must be defined in the [project file](csproj.md).</span></span> <span data-ttu-id="a1a93-122">如果在生成时指定了框架，则必须在清除时指定框架。</span><span class="sxs-lookup"><span data-stu-id="a1a93-122">If you specified the framework at build time, you must specify the framework when cleaning.</span></span>

* **`-h|--help`**

  <span data-ttu-id="a1a93-123">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="a1a93-123">Prints out a short help for the command.</span></span>

* **`--interactive`**

  <span data-ttu-id="a1a93-124">允许命令停止并等待用户输入或操作。</span><span class="sxs-lookup"><span data-stu-id="a1a93-124">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="a1a93-125">例如，完成身份验证。</span><span class="sxs-lookup"><span data-stu-id="a1a93-125">For example, to complete authentication.</span></span> <span data-ttu-id="a1a93-126">自 .NET Core 3.0 SDK 起可用。</span><span class="sxs-lookup"><span data-stu-id="a1a93-126">Available since .NET Core 3.0 SDK.</span></span>

* **`--nologo`**

  <span data-ttu-id="a1a93-127">不显示启动版权标志或版权消息。</span><span class="sxs-lookup"><span data-stu-id="a1a93-127">Doesn't display the startup banner or the copyright message.</span></span> <span data-ttu-id="a1a93-128">自 .NET Core 3.0 SDK 起可用。</span><span class="sxs-lookup"><span data-stu-id="a1a93-128">Available since .NET Core 3.0 SDK.</span></span>

* **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="a1a93-129">包含要清理的生成项目的目录。</span><span class="sxs-lookup"><span data-stu-id="a1a93-129">The directory that contains the build artifacts to clean.</span></span> <span data-ttu-id="a1a93-130">如果在生成项目时指定了框架，则使用输出目录开关指定 `-f|--framework <FRAMEWORK>` 开关。</span><span class="sxs-lookup"><span data-stu-id="a1a93-130">Specify the `-f|--framework <FRAMEWORK>` switch with the output directory switch if you specified the framework when the project was built.</span></span>

* **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="a1a93-131">清除指定运行时的输出文件夹。</span><span class="sxs-lookup"><span data-stu-id="a1a93-131">Cleans the output folder of the specified runtime.</span></span> <span data-ttu-id="a1a93-132">在创建[独立部署 (SCD)](../deploying/index.md#publish-self-contained) 时使用此选项。</span><span class="sxs-lookup"><span data-stu-id="a1a93-132">This is used when a [self-contained deployment](../deploying/index.md#publish-self-contained) was created.</span></span>

* **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="a1a93-133">设置 MSBuild 详细级别。</span><span class="sxs-lookup"><span data-stu-id="a1a93-133">Sets the MSBuild verbosity level.</span></span> <span data-ttu-id="a1a93-134">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="a1a93-134">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="a1a93-135">默认值为 `normal`。</span><span class="sxs-lookup"><span data-stu-id="a1a93-135">The default is `normal`.</span></span>

## <a name="examples"></a><span data-ttu-id="a1a93-136">示例</span><span class="sxs-lookup"><span data-stu-id="a1a93-136">Examples</span></span>

* <span data-ttu-id="a1a93-137">清除项目的默认生成：</span><span class="sxs-lookup"><span data-stu-id="a1a93-137">Clean a default build of the project:</span></span>

  ```dotnetcli
  dotnet clean
  ```

* <span data-ttu-id="a1a93-138">清除使用版本配置生成的项目：</span><span class="sxs-lookup"><span data-stu-id="a1a93-138">Clean a project built using the Release configuration:</span></span>

  ```dotnetcli
  dotnet clean --configuration Release
  ```
