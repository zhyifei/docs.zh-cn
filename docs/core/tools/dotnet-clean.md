---
title: dotnet clean 命令
description: dotnet clean 命令可清除当前目录。
ms.date: 06/26/2019
ms.openlocfilehash: 36630c046ff8f1ad8d513b4e64cfb74a8625776b
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/28/2019
ms.locfileid: "67422021"
---
# <a name="dotnet-clean"></a><span data-ttu-id="8770b-103">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="8770b-103">dotnet clean</span></span>

<span data-ttu-id="8770b-104">**本主题适用于：✓** .NET Core 1.x SDK 及更高版本</span><span class="sxs-lookup"><span data-stu-id="8770b-104">**This topic applies to: ✓** .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="8770b-105">name</span><span class="sxs-lookup"><span data-stu-id="8770b-105">Name</span></span>

<span data-ttu-id="8770b-106">`dotnet clean` - 清除项目输出。</span><span class="sxs-lookup"><span data-stu-id="8770b-106">`dotnet clean` - Cleans the output of a project.</span></span>

## <a name="synopsis"></a><span data-ttu-id="8770b-107">摘要</span><span class="sxs-lookup"><span data-stu-id="8770b-107">Synopsis</span></span>

```
dotnet clean [<PROJECT>|<SOLUTION>] [-c|--configuration] [-f|--framework] [--interactive] 
    [--nologo] [-o|--output] [-r|--runtime] [-v|--verbosity]
dotnet clean [-h|--help]
```

## <a name="description"></a><span data-ttu-id="8770b-108">说明</span><span class="sxs-lookup"><span data-stu-id="8770b-108">Description</span></span>

<span data-ttu-id="8770b-109">`dotnet clean` 命令可清除上一个生成的输出。</span><span class="sxs-lookup"><span data-stu-id="8770b-109">The `dotnet clean` command cleans the output of the previous build.</span></span> <span data-ttu-id="8770b-110">它以 [MSBuild 目标](/visualstudio/msbuild/msbuild-targets) 的形式实现，以便在运行命令时对项目进行评估。</span><span class="sxs-lookup"><span data-stu-id="8770b-110">It's implemented as an [MSBuild target](/visualstudio/msbuild/msbuild-targets), so the project is evaluated when the command is run.</span></span> <span data-ttu-id="8770b-111">只会清除在生成过程中创建的输出。</span><span class="sxs-lookup"><span data-stu-id="8770b-111">Only the outputs created during the build are cleaned.</span></span> <span data-ttu-id="8770b-112">中间 (*obj*) 和最终输出 (*bin*) 文件夹都会被清除。</span><span class="sxs-lookup"><span data-stu-id="8770b-112">Both intermediate (*obj*) and final output (*bin*) folders are cleaned.</span></span>

## <a name="arguments"></a><span data-ttu-id="8770b-113">自变量</span><span class="sxs-lookup"><span data-stu-id="8770b-113">Arguments</span></span>

`PROJECT | SOLUTION`

<span data-ttu-id="8770b-114">要清理的 MSBuild 项目或解决方案。</span><span class="sxs-lookup"><span data-stu-id="8770b-114">The MSBuild project or solution to clean.</span></span> <span data-ttu-id="8770b-115">如果未指定项目或解决方案文件，MSBuild 会在当前工作目录中搜索文件扩展名以 *proj* 或 *sln* 结尾的文件并使用该文件。</span><span class="sxs-lookup"><span data-stu-id="8770b-115">If a project or solution file is not specified, MSBuild searches the current working directory for a file that has a file extension that ends in *proj* or *sln*, and uses that file.</span></span>

## <a name="options"></a><span data-ttu-id="8770b-116">选项</span><span class="sxs-lookup"><span data-stu-id="8770b-116">Options</span></span>

* **`-c|--configuration {Debug|Release}`**

  <span data-ttu-id="8770b-117">定义生成配置。</span><span class="sxs-lookup"><span data-stu-id="8770b-117">Defines the build configuration.</span></span> <span data-ttu-id="8770b-118">默认值为 `Debug`。</span><span class="sxs-lookup"><span data-stu-id="8770b-118">The default value is `Debug`.</span></span> <span data-ttu-id="8770b-119">只有在生成期间指定了此选项，才必须在清除时使用此选项。</span><span class="sxs-lookup"><span data-stu-id="8770b-119">This option is only required when cleaning if you specified it during build time.</span></span>

* **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="8770b-120">在生成时指定的[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="8770b-120">The [framework](../../standard/frameworks.md) that was specified at build time.</span></span> <span data-ttu-id="8770b-121">必须在[项目文件](csproj.md)中定义该框架。</span><span class="sxs-lookup"><span data-stu-id="8770b-121">The framework must be defined in the [project file](csproj.md).</span></span> <span data-ttu-id="8770b-122">如果在生成时指定了框架，则必须在清除时指定框架。</span><span class="sxs-lookup"><span data-stu-id="8770b-122">If you specified the framework at build time, you must specify the framework when cleaning.</span></span>

* **`-h|--help`**

  <span data-ttu-id="8770b-123">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="8770b-123">Prints out a short help for the command.</span></span>

* **`--interactive`**

  <span data-ttu-id="8770b-124">允许命令停止并等待用户输入或操作。</span><span class="sxs-lookup"><span data-stu-id="8770b-124">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="8770b-125">例如，完成身份验证。</span><span class="sxs-lookup"><span data-stu-id="8770b-125">For example, to complete authentication.</span></span> <span data-ttu-id="8770b-126">自 .NET Core 3.0 SDK 起可用。</span><span class="sxs-lookup"><span data-stu-id="8770b-126">Available since .NET Core 3.0 SDK.</span></span>

* **`--nologo`**

  <span data-ttu-id="8770b-127">不显示启动版权标志或版权消息。</span><span class="sxs-lookup"><span data-stu-id="8770b-127">Doesn't display the startup banner or the copyright message.</span></span> <span data-ttu-id="8770b-128">自 .NET Core 3.0 SDK 起可用。</span><span class="sxs-lookup"><span data-stu-id="8770b-128">Available since .NET Core 3.0 SDK.</span></span>

* **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="8770b-129">包含要清理的生成项目的目录。</span><span class="sxs-lookup"><span data-stu-id="8770b-129">The directory that contains the build artifacts to clean.</span></span> <span data-ttu-id="8770b-130">如果在生成项目时指定了框架，则使用输出目录开关指定 `-f|--framework <FRAMEWORK>` 开关。</span><span class="sxs-lookup"><span data-stu-id="8770b-130">Specify the `-f|--framework <FRAMEWORK>` switch with the output directory switch if you specified the framework when the project was built.</span></span>

* **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="8770b-131">清除指定运行时的输出文件夹。</span><span class="sxs-lookup"><span data-stu-id="8770b-131">Cleans the output folder of the specified runtime.</span></span> <span data-ttu-id="8770b-132">在创建[独立部署 (SCD)](../deploying/index.md#self-contained-deployments-scd) 时使用此选项。</span><span class="sxs-lookup"><span data-stu-id="8770b-132">This is used when a [self-contained deployment](../deploying/index.md#self-contained-deployments-scd) was created.</span></span> <span data-ttu-id="8770b-133">自 .NET Core 2.0 SDK 起可用的选项。</span><span class="sxs-lookup"><span data-stu-id="8770b-133">Option available since .NET Core 2.0 SDK.</span></span>

* **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="8770b-134">设置 MSBuild 详细级别。</span><span class="sxs-lookup"><span data-stu-id="8770b-134">Sets the MSBuild verbosity level.</span></span> <span data-ttu-id="8770b-135">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="8770b-135">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="8770b-136">默认值为 `normal`。</span><span class="sxs-lookup"><span data-stu-id="8770b-136">The default is `normal`.</span></span>

## <a name="examples"></a><span data-ttu-id="8770b-137">示例</span><span class="sxs-lookup"><span data-stu-id="8770b-137">Examples</span></span>

* <span data-ttu-id="8770b-138">清除项目的默认生成：</span><span class="sxs-lookup"><span data-stu-id="8770b-138">Clean a default build of the project:</span></span>

  ```console
  dotnet clean
  ```

* <span data-ttu-id="8770b-139">清除使用版本配置生成的项目：</span><span class="sxs-lookup"><span data-stu-id="8770b-139">Clean a project built using the Release configuration:</span></span>

  ```console
  dotnet clean --configuration Release
  ```
