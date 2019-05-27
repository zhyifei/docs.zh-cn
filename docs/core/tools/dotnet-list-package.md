---
title: dotnet list package 命令
description: 使用“dotnet list package”命令，可以方便地列出项目或解决方案的包引用。
ms.date: 04/09/2019
ms.openlocfilehash: 88ef3302a955eadc4167384312e4eb721dd496fb
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "65631773"
---
# <a name="dotnet-list-package"></a><span data-ttu-id="3764c-103">dotnet list package</span><span class="sxs-lookup"><span data-stu-id="3764c-103">dotnet list package</span></span>

[!INCLUDE [topic-appliesto-net-core-22plus](../../../includes/topic-appliesto-net-core-22plus.md)]

## <a name="name"></a><span data-ttu-id="3764c-104">name</span><span class="sxs-lookup"><span data-stu-id="3764c-104">Name</span></span>

<span data-ttu-id="3764c-105">`dotnet list package` - 列出项目或解决方案的包引用。</span><span class="sxs-lookup"><span data-stu-id="3764c-105">`dotnet list package` - Lists the package references for a project or solution.</span></span>

## <a name="synopsis"></a><span data-ttu-id="3764c-106">摘要</span><span class="sxs-lookup"><span data-stu-id="3764c-106">Synopsis</span></span>

```
dotnet list [<PROJECT | SOLUTION>] package [--config] [--framework] [--highest-minor] [--highest-patch] 
   [--include-prerelease] [--include-transitive] [--outdated] [--source]
dotnet list package [-h|--help]
```

## <a name="description"></a><span data-ttu-id="3764c-107">说明</span><span class="sxs-lookup"><span data-stu-id="3764c-107">Description</span></span>

<span data-ttu-id="3764c-108">使用 `dotnet list package` 命令，可以方便地列出特定项目或解决方案的所有 NuGet 包引用。</span><span class="sxs-lookup"><span data-stu-id="3764c-108">The `dotnet list package` command provides a convenient option to list all NuGet package references for a specific project or a solution.</span></span> <span data-ttu-id="3764c-109">首先，需要生成项目，以提供必需资产以供此命令处理。</span><span class="sxs-lookup"><span data-stu-id="3764c-109">You first need to build the project in order to have the assets needed for this command to process.</span></span> <span data-ttu-id="3764c-110">下面的示例展示了 [SentimentAnalysis](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) 项目的 `dotnet list package` 命令输出：</span><span class="sxs-lookup"><span data-stu-id="3764c-110">The following example shows the output of the `dotnet list package` command for the [SentimentAnalysis](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) project:</span></span>

```output
Project 'SentimentAnalysis' has the following package references
   [netcoreapp2.1]:
   Top-level Package               Requested   Resolved
   > Microsoft.ML                  0.11.0      0.11.0
   > Microsoft.NETCore.App   (A)   [2.1.0, )   2.1.0

(A) : Auto-referenced package.
```

<span data-ttu-id="3764c-111">“已请求”列是指项目文件中指定的包版本，可以是一个范围。</span><span class="sxs-lookup"><span data-stu-id="3764c-111">The **Requested** column refers to the package version specified in the project file and can be a range.</span></span> <span data-ttu-id="3764c-112">“已解析”列列出了项目当前使用的版本，始终都是一个值。</span><span class="sxs-lookup"><span data-stu-id="3764c-112">The **Resolved** column lists the version that the project is currently using and is always a single value.</span></span> <span data-ttu-id="3764c-113">紧靠名称旁边显示 `(A)` 的包表示从项目设置（`Sdk` 类型、`<TargetFramework>` 或 `<TargetFrameworks>` 属性等）推断出的[隐式包引用](csproj.md#implicit-package-references)。</span><span class="sxs-lookup"><span data-stu-id="3764c-113">The packages displaying an `(A)` right next to their names represent [implicit package references](csproj.md#implicit-package-references) that are inferred from your project settings (`Sdk` type, `<TargetFramework>` or `<TargetFrameworks>` property, etc.)</span></span>

<span data-ttu-id="3764c-114">使用 `--outdated` 选项，可以确定项目中正在使用的包是否有更高版本。</span><span class="sxs-lookup"><span data-stu-id="3764c-114">Use the `--outdated` option to find out if there are newer versions available of the packages you're using in your projects.</span></span> <span data-ttu-id="3764c-115">默认情况下，`--outdated` 列出最新稳定包，除非已解析版本也是预发行版本。</span><span class="sxs-lookup"><span data-stu-id="3764c-115">By default, `--outdated` lists the latest stable packages unless the resolved version is also a prerelease version.</span></span> <span data-ttu-id="3764c-116">若要在列出更高版本时包含预发行版本，还请指定 `--include-prerelease` 选项。</span><span class="sxs-lookup"><span data-stu-id="3764c-116">To include prerelease versions when listing newer versions, also specify the `--include-prerelease` option.</span></span> <span data-ttu-id="3764c-117">下面的示例展示了上一个示例中相同项目的 `dotnet list package --outdated --include-prerelease` 命令输出：</span><span class="sxs-lookup"><span data-stu-id="3764c-117">The following examples shows the output of the `dotnet list package --outdated --include-prerelease` command for the same project as the previous example:</span></span>

```output
The following sources were used:
   https://api.nuget.org/v3/index.json

Project `SentimentAnalysis` has the following updates to its packages
   [netcoreapp2.1]:
   Top-level Package      Requested   Resolved   Latest
   > Microsoft.ML         0.11.0      0.11.0     1.0.0-preview
```

<span data-ttu-id="3764c-118">如果需要确定项目是否有可传递依赖关系，请使用 `--include-transitive` 选项。</span><span class="sxs-lookup"><span data-stu-id="3764c-118">If you need to find out whether your project has transitive dependencies, use the `--include-transitive` option.</span></span> <span data-ttu-id="3764c-119">如果在项目中添加包，它转而又依赖另一个包，就会出现可传递依赖关系。</span><span class="sxs-lookup"><span data-stu-id="3764c-119">Transitive dependencies occur when you add a package to your project that in turn relies on another package.</span></span> <span data-ttu-id="3764c-120">下面的示例展示了 [HelloPlugin](https://github.com/dotnet/samples/tree/master/core/extensions/AppWithPlugin/HelloPlugin) 项目的 `dotnet list package --include-transitive` 命令运行输出，其中显示顶级包及其依赖的包：</span><span class="sxs-lookup"><span data-stu-id="3764c-120">The following example shows the output from running the `dotnet list package --include-transitive` command for the [HelloPlugin](https://github.com/dotnet/samples/tree/master/core/extensions/AppWithPlugin/HelloPlugin) project, which displays top-level packages and the packages they depend on:</span></span>

```output
Project 'HelloPlugin' has the following package references
   [netcoreapp3.0]:
   Top-level Package                      Requested                    Resolved
   > Microsoft.NETCore.Platforms    (A)   [3.0.0-preview3.19128.7, )   3.0.0-preview3.19128.7
   > Microsoft.WindowsDesktop.App   (A)   [3.0.0-preview3-27504-2, )   3.0.0-preview3-27504-2

   Transitive Package               Resolved
   > Microsoft.NETCore.Targets      2.0.0
   > PluginBase                     1.0.0

(A) : Auto-referenced package.
```

## <a name="arguments"></a><span data-ttu-id="3764c-121">自变量</span><span class="sxs-lookup"><span data-stu-id="3764c-121">Arguments</span></span>

`PROJECT | SOLUTION`

<span data-ttu-id="3764c-122">要对其运行命令的项目或解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="3764c-122">The project or solution file to operate on.</span></span> <span data-ttu-id="3764c-123">如果未指定，此命令会搜索当前目录来获取一个项目文件。</span><span class="sxs-lookup"><span data-stu-id="3764c-123">If not specified, the command searches the current directory for one.</span></span> <span data-ttu-id="3764c-124">如果找到多个解决方案或项目，便会抛出错误。</span><span class="sxs-lookup"><span data-stu-id="3764c-124">If more than one solution or project is found, an error is thrown.</span></span>

## <a name="options"></a><span data-ttu-id="3764c-125">选项</span><span class="sxs-lookup"><span data-stu-id="3764c-125">Options</span></span>

* **`--config <SOURCE>`**

  <span data-ttu-id="3764c-126">在搜索版本更高的包时，要使用的 NuGet 源。</span><span class="sxs-lookup"><span data-stu-id="3764c-126">The NuGet sources to use when searching for newer packages.</span></span> <span data-ttu-id="3764c-127">需要使用 `--outdated` 选项。</span><span class="sxs-lookup"><span data-stu-id="3764c-127">Requires the `--outdated` option.</span></span>

* **`--framework <FRAMEWORK>`**

  <span data-ttu-id="3764c-128">只显示适用于指定[目标框架](../../standard/frameworks.md)的包。</span><span class="sxs-lookup"><span data-stu-id="3764c-128">Displays only the packages applicable for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="3764c-129">若要指定多个框架，请多次重复此选项。</span><span class="sxs-lookup"><span data-stu-id="3764c-129">To specify multiple frameworks, repeat the option multiple times.</span></span> <span data-ttu-id="3764c-130">例如：`--framework netcoreapp2.2 --framework netstandard2.0`。</span><span class="sxs-lookup"><span data-stu-id="3764c-130">For example: `--framework netcoreapp2.2 --framework netstandard2.0`.</span></span>

* **`-h|--help`**

  <span data-ttu-id="3764c-131">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="3764c-131">Prints out a short help for the command.</span></span>

* **`--highest-minor`**

  <span data-ttu-id="3764c-132">在搜索版本更高的包时，仅考虑有匹配的主版本号的包。</span><span class="sxs-lookup"><span data-stu-id="3764c-132">Considers only the packages with a matching major version number when searching for newer packages.</span></span> <span data-ttu-id="3764c-133">需要使用 `--outdated` 选项。</span><span class="sxs-lookup"><span data-stu-id="3764c-133">Requires the `--outdated` option.</span></span>

* **`--highest-patch`**

  <span data-ttu-id="3764c-134">在搜索版本更高的包时，仅考虑有匹配的主版本号和次要版本号的包。</span><span class="sxs-lookup"><span data-stu-id="3764c-134">Considers only the packages with a matching major and minor version numbers when searching for newer packages.</span></span> <span data-ttu-id="3764c-135">需要使用 `--outdated` 选项。</span><span class="sxs-lookup"><span data-stu-id="3764c-135">Requires the `--outdated` option.</span></span>

* **`--include-prerelease`**

  <span data-ttu-id="3764c-136">在搜索版本更高的包时，考虑有预发行版本的包。</span><span class="sxs-lookup"><span data-stu-id="3764c-136">Considers packages with prerelease versions when searching for newer packages.</span></span> <span data-ttu-id="3764c-137">需要使用 `--outdated` 选项。</span><span class="sxs-lookup"><span data-stu-id="3764c-137">Requires the `--outdated` option.</span></span>

* **`--include-transitive`**

  <span data-ttu-id="3764c-138">除了顶级包之外，还列出可传递包。</span><span class="sxs-lookup"><span data-stu-id="3764c-138">Lists transitive packages, in addition to the top-level packages.</span></span> <span data-ttu-id="3764c-139">如果指定此选项，可以获取顶级包所依赖的包列表。</span><span class="sxs-lookup"><span data-stu-id="3764c-139">When specifying this option, you get a list of packages that the top-level packages depend on.</span></span>

* **`--outdated`**

  <span data-ttu-id="3764c-140">列出版本更高的包。</span><span class="sxs-lookup"><span data-stu-id="3764c-140">Lists packages that have newer versions available.</span></span>

* **`-s|--source <SOURCE>`**

  <span data-ttu-id="3764c-141">在搜索版本更高的包时，要使用的 NuGet 源。</span><span class="sxs-lookup"><span data-stu-id="3764c-141">The NuGet sources to use when searching for newer packages.</span></span> <span data-ttu-id="3764c-142">需要使用 `--outdated` 选项。</span><span class="sxs-lookup"><span data-stu-id="3764c-142">Requires the `--outdated` option.</span></span>

## <a name="examples"></a><span data-ttu-id="3764c-143">示例</span><span class="sxs-lookup"><span data-stu-id="3764c-143">Examples</span></span>

* <span data-ttu-id="3764c-144">列出特定项目的包引用：</span><span class="sxs-lookup"><span data-stu-id="3764c-144">List package references of a specific project:</span></span>

  ```console
  dotnet list SentimentAnalysis.csproj package
  ```

* <span data-ttu-id="3764c-145">列出有更高版本（包括预发行版本）的包引用：</span><span class="sxs-lookup"><span data-stu-id="3764c-145">List package references that have newer versions available, including prerelease versions:</span></span>

  ```console
  dotnet list package --outdated --include-prerelease
  ```

* <span data-ttu-id="3764c-146">列出特定目标框架的包引用：</span><span class="sxs-lookup"><span data-stu-id="3764c-146">List package references for a specific target framework:</span></span>

  ```console
  dotnet list package --framework netcoreapp3.0
  ```
