---
title: dotnet clean 命令
description: dotnet clean 命令可清除当前目录。
ms.date: 12/04/2018
ms.openlocfilehash: a25b7930794795e3dff5051a8ca1dd1b9c261dfd
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53169854"
---
# <a name="dotnet-clean"></a><span data-ttu-id="666a6-103">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="666a6-103">dotnet clean</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="666a6-104">name</span><span class="sxs-lookup"><span data-stu-id="666a6-104">Name</span></span>

<span data-ttu-id="666a6-105">`dotnet clean` - 清除项目输出。</span><span class="sxs-lookup"><span data-stu-id="666a6-105">`dotnet clean` - Cleans the output of a project.</span></span>

## <a name="synopsis"></a><span data-ttu-id="666a6-106">摘要</span><span class="sxs-lookup"><span data-stu-id="666a6-106">Synopsis</span></span>

```
dotnet clean [<PROJECT>] [-c|--configuration] [-f|--framework] [-o|--output] [-r|--runtime] [-v|--verbosity]
dotnet clean [-h|--help]
```

## <a name="description"></a><span data-ttu-id="666a6-107">说明</span><span class="sxs-lookup"><span data-stu-id="666a6-107">Description</span></span>

<span data-ttu-id="666a6-108">`dotnet clean` 命令可清除上一个生成的输出。</span><span class="sxs-lookup"><span data-stu-id="666a6-108">The `dotnet clean` command cleans the output of the previous build.</span></span> <span data-ttu-id="666a6-109">它以 [MSBuild 目标](/visualstudio/msbuild/msbuild-targets) 的形式实现，以便在运行命令时对项目进行评估。</span><span class="sxs-lookup"><span data-stu-id="666a6-109">It's implemented as an [MSBuild target](/visualstudio/msbuild/msbuild-targets), so the project is evaluated when the command is run.</span></span> <span data-ttu-id="666a6-110">只会清除在生成过程中创建的输出。</span><span class="sxs-lookup"><span data-stu-id="666a6-110">Only the outputs created during the build are cleaned.</span></span> <span data-ttu-id="666a6-111">中间 (*obj*) 和最终输出 (*bin*) 文件夹都会被清除。</span><span class="sxs-lookup"><span data-stu-id="666a6-111">Both intermediate (*obj*) and final output (*bin*) folders are cleaned.</span></span>

## <a name="arguments"></a><span data-ttu-id="666a6-112">自变量</span><span class="sxs-lookup"><span data-stu-id="666a6-112">Arguments</span></span>

`PROJECT`

<span data-ttu-id="666a6-113">要清除的 MSBuild 项目。</span><span class="sxs-lookup"><span data-stu-id="666a6-113">The MSBuild project to clean.</span></span> <span data-ttu-id="666a6-114">如果未指定项目文件，MSBuild 会在当前工作目录中搜索以 *proj* 结尾的文件扩展名并使用该文件。</span><span class="sxs-lookup"><span data-stu-id="666a6-114">If a project file is not specified, MSBuild searches the current working directory for a file that has a file extension that ends in *proj* and uses that file.</span></span>

## <a name="options"></a><span data-ttu-id="666a6-115">选项</span><span class="sxs-lookup"><span data-stu-id="666a6-115">Options</span></span>

* **`-c|--configuration {Debug|Release}`**

  <span data-ttu-id="666a6-116">定义生成配置。</span><span class="sxs-lookup"><span data-stu-id="666a6-116">Defines the build configuration.</span></span> <span data-ttu-id="666a6-117">默认值为 `Debug`。</span><span class="sxs-lookup"><span data-stu-id="666a6-117">The default value is `Debug`.</span></span> <span data-ttu-id="666a6-118">只有在生成期间指定了此选项，才必须在清除时使用此选项。</span><span class="sxs-lookup"><span data-stu-id="666a6-118">This option is only required when cleaning if you specified it during build time.</span></span>

* **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="666a6-119">在生成时指定的[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="666a6-119">The [framework](../../standard/frameworks.md) that was specified at build time.</span></span> <span data-ttu-id="666a6-120">必须在[项目文件](csproj.md)中定义该框架。</span><span class="sxs-lookup"><span data-stu-id="666a6-120">The framework must be defined in the [project file](csproj.md).</span></span> <span data-ttu-id="666a6-121">如果在生成时指定了框架，则必须在清除时指定框架。</span><span class="sxs-lookup"><span data-stu-id="666a6-121">If you specified the framework at build time, you must specify the framework when cleaning.</span></span>

* **`-h|--help`**

  <span data-ttu-id="666a6-122">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="666a6-122">Prints out a short help for the command.</span></span>

* **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="666a6-123">包含已生成的输出的目录。</span><span class="sxs-lookup"><span data-stu-id="666a6-123">Directory in which the build outputs are placed.</span></span> <span data-ttu-id="666a6-124">如果在生成项目时指定了框架，则使用输出目录开关指定 `-f|--framework <FRAMEWORK>` 开关。</span><span class="sxs-lookup"><span data-stu-id="666a6-124">Specify the `-f|--framework <FRAMEWORK>` switch with the output directory switch if you specified the framework when the project was built.</span></span>

* **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="666a6-125">清除指定运行时的输出文件夹。</span><span class="sxs-lookup"><span data-stu-id="666a6-125">Cleans the output folder of the specified runtime.</span></span> <span data-ttu-id="666a6-126">在创建[独立部署 (SCD)](../deploying/index.md#self-contained-deployments-scd) 时使用此选项。</span><span class="sxs-lookup"><span data-stu-id="666a6-126">This is used when a [self-contained deployment](../deploying/index.md#self-contained-deployments-scd) was created.</span></span> <span data-ttu-id="666a6-127">自 .NET Core 2.0 SDK 起可用的选项。</span><span class="sxs-lookup"><span data-stu-id="666a6-127">Option available since .NET Core 2.0 SDK.</span></span>

* **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="666a6-128">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="666a6-128">Sets the verbosity level of the command.</span></span> <span data-ttu-id="666a6-129">允许的级别为 q[uiet]、m[inimal]、n[ormal]、d[etailed] 和 diag[nostic]。</span><span class="sxs-lookup"><span data-stu-id="666a6-129">Allowed levels are q[uiet], m[inimal], n[ormal], d[etailed], and diag[nostic].</span></span>

## <a name="examples"></a><span data-ttu-id="666a6-130">示例</span><span class="sxs-lookup"><span data-stu-id="666a6-130">Examples</span></span>

* <span data-ttu-id="666a6-131">清除项目的默认生成：</span><span class="sxs-lookup"><span data-stu-id="666a6-131">Clean a default build of the project:</span></span>

  ```console
  dotnet clean
  ```

* <span data-ttu-id="666a6-132">清除使用版本配置生成的项目：</span><span class="sxs-lookup"><span data-stu-id="666a6-132">Clean a project built using the Release configuration:</span></span>

  ```console
  dotnet clean --configuration Release
  ```