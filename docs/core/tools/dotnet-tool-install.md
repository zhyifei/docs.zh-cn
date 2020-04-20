---
title: dotnet tool install 命令
description: dotnet tool install 命令在计算机上安装指定的 .NET Core 工具。
ms.date: 02/14/2020
ms.openlocfilehash: 723d25caa6009288dbb55d55f173b04d7b983450
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463364"
---
# <a name="dotnet-tool-install"></a><span data-ttu-id="9a14f-103">dotnet tool install</span><span class="sxs-lookup"><span data-stu-id="9a14f-103">dotnet tool install</span></span>

<span data-ttu-id="9a14f-104"> 本文适用于： ✔️ .NET Core 2.1 SDK 及更高版本</span><span class="sxs-lookup"><span data-stu-id="9a14f-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="9a14f-105">“属性”</span><span class="sxs-lookup"><span data-stu-id="9a14f-105">Name</span></span>

<span data-ttu-id="9a14f-106">`dotnet tool install` - 在计算机上安装指定的 [.NET Core 工具](global-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="9a14f-106">`dotnet tool install` - Installs the specified [.NET Core tool](global-tools.md) on your machine.</span></span>

## <a name="synopsis"></a><span data-ttu-id="9a14f-107">摘要</span><span class="sxs-lookup"><span data-stu-id="9a14f-107">Synopsis</span></span>

```dotnetcli
dotnet tool install <PACKAGE_NAME> -g|--global
    [--add-source <SOURCE>] [--configfile <FILE>]
    [--framework <FRAMEWORK>] [-v|--verbosity <LEVEL>]
    [--version <VERSION_NUMBER>]

dotnet tool install <PACKAGE_NAME> --tool-path <PATH>
    [--add-source <SOURCE>] [--configfile <FILE>]
    [--framework <FRAMEWORK>] [-v|--verbosity <LEVEL>]
    [--version <VERSION_NUMBER>]

dotnet tool install <PACKAGE_NAME>
    [--add-source <SOURCE>] [--configfile <FILE>]
    [--framework <FRAMEWORK>] [-v|--verbosity <LEVEL>]
    [--version <VERSION_NUMBER>]

dotnet tool install -h|--help
```

## <a name="description"></a><span data-ttu-id="9a14f-108">描述</span><span class="sxs-lookup"><span data-stu-id="9a14f-108">Description</span></span>

<span data-ttu-id="9a14f-109">`dotnet tool install` 命令为用户提供一种在计算机上安装 .NET Core 工具的方法。</span><span class="sxs-lookup"><span data-stu-id="9a14f-109">The `dotnet tool install` command provides a way for you to install .NET Core tools on your machine.</span></span> <span data-ttu-id="9a14f-110">若要使用命令，请指定以下安装选项之一：</span><span class="sxs-lookup"><span data-stu-id="9a14f-110">To use the command, you specify one of the following installation options:</span></span>

* <span data-ttu-id="9a14f-111">若要在默认位置中安装全局工具，请使用 `--global` 选项。</span><span class="sxs-lookup"><span data-stu-id="9a14f-111">To install a global tool in the default location, use the `--global` option.</span></span>
* <span data-ttu-id="9a14f-112">若要在自定义位置中安装全局工具，请使用 `--tool-path` 选项。</span><span class="sxs-lookup"><span data-stu-id="9a14f-112">To install a global tool in a custom location,  use the `--tool-path` option.</span></span>
* <span data-ttu-id="9a14f-113">若要安装本地工具，请省略 `--global` 和 `--tool-path` 选项。</span><span class="sxs-lookup"><span data-stu-id="9a14f-113">To install a local tool, omit the `--global` and `--tool-path` options.</span></span>

<span data-ttu-id="9a14f-114">**本地工具从 .NET Core SDK 3.0 开始可用。**</span><span class="sxs-lookup"><span data-stu-id="9a14f-114">**Local tools are available starting with .NET Core SDK 3.0.**</span></span>

<span data-ttu-id="9a14f-115">指定 `-g` 或 `--global` 选项时，全局工具默认安装在以下目录中：</span><span class="sxs-lookup"><span data-stu-id="9a14f-115">Global tools are installed in the following directories by default when you specify the `-g` or `--global` option:</span></span>

| <span data-ttu-id="9a14f-116">(OS)</span><span class="sxs-lookup"><span data-stu-id="9a14f-116">OS</span></span>          | <span data-ttu-id="9a14f-117">路径</span><span class="sxs-lookup"><span data-stu-id="9a14f-117">Path</span></span>                          |
|-------------|-------------------------------|
| <span data-ttu-id="9a14f-118">Linux/macOS</span><span class="sxs-lookup"><span data-stu-id="9a14f-118">Linux/macOS</span></span> | `$HOME/.dotnet/tools`         |
| <span data-ttu-id="9a14f-119">Windows</span><span class="sxs-lookup"><span data-stu-id="9a14f-119">Windows</span></span>     | `%USERPROFILE%\.dotnet\tools` |

<span data-ttu-id="9a14f-120">本地工具将添加到当前目录下的 .config 目录中的 tool-manifest.json 文件中   。</span><span class="sxs-lookup"><span data-stu-id="9a14f-120">Local tools are added to a *tool-manifest.json* file in a *.config* directory under the current directory.</span></span> <span data-ttu-id="9a14f-121">如果清单文件尚不存在，请通过运行以下命令来创建它：</span><span class="sxs-lookup"><span data-stu-id="9a14f-121">If a manifest file doesn't exist yet, create it by running the following command:</span></span>

```dotnetcli
dotnet new tool-manifest
```

<span data-ttu-id="9a14f-122">有关详细信息，请参阅[安装本地工具](global-tools.md#install-a-local-tool)。</span><span class="sxs-lookup"><span data-stu-id="9a14f-122">For more information, see [Install a local tool](global-tools.md#install-a-local-tool).</span></span>

## <a name="arguments"></a><span data-ttu-id="9a14f-123">自变量</span><span class="sxs-lookup"><span data-stu-id="9a14f-123">Arguments</span></span>

- **`PACKAGE_NAME`**

  <span data-ttu-id="9a14f-124">包含要安装的 .NET Core 工具的 NuGet 包的名称/ID。</span><span class="sxs-lookup"><span data-stu-id="9a14f-124">Name/ID of the NuGet package that contains the .NET Core tool to install.</span></span>

## <a name="options"></a><span data-ttu-id="9a14f-125">选项</span><span class="sxs-lookup"><span data-stu-id="9a14f-125">Options</span></span>

- **`add-source <SOURCE>`**

  <span data-ttu-id="9a14f-126">添加安装过程中要使用的其他 NuGet 包源。</span><span class="sxs-lookup"><span data-stu-id="9a14f-126">Adds an additional NuGet package source to use during installation.</span></span>

- **`configfile <FILE>`**

  <span data-ttu-id="9a14f-127">要使用的 NuGet 配置 (nuget.config) 文件  。</span><span class="sxs-lookup"><span data-stu-id="9a14f-127">The NuGet configuration (*nuget.config*) file to use.</span></span>

- **`framework <FRAMEWORK>`**

  <span data-ttu-id="9a14f-128">指定要安装工具的[目标框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="9a14f-128">Specifies the [target framework](../../standard/frameworks.md) to install the tool for.</span></span> <span data-ttu-id="9a14f-129">默认情况下，.NET Core SDK 尝试选择最合适的目标框架。</span><span class="sxs-lookup"><span data-stu-id="9a14f-129">By default, the .NET Core SDK tries to choose the most appropriate target framework.</span></span>

- **`-g|--global`**

  <span data-ttu-id="9a14f-130">指定安装是用户范围的。</span><span class="sxs-lookup"><span data-stu-id="9a14f-130">Specifies that the installation is user wide.</span></span> <span data-ttu-id="9a14f-131">不能与 `--tool-path` 选项一起使用。</span><span class="sxs-lookup"><span data-stu-id="9a14f-131">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="9a14f-132">省略 `--global` 和 `--tool-path` 指定本地工具安装。</span><span class="sxs-lookup"><span data-stu-id="9a14f-132">Omitting both `--global` and `--tool-path` specifies a local tool installation.</span></span>

- **`-h|--help`**

  <span data-ttu-id="9a14f-133">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="9a14f-133">Prints out a short help for the command.</span></span>

- **`tool-path <PATH>`**

  <span data-ttu-id="9a14f-134">指定全局工具的安装位置。</span><span class="sxs-lookup"><span data-stu-id="9a14f-134">Specifies the location where to install the Global Tool.</span></span> <span data-ttu-id="9a14f-135">路径可以是绝对的，也可以是相对的。</span><span class="sxs-lookup"><span data-stu-id="9a14f-135">PATH can be absolute or relative.</span></span> <span data-ttu-id="9a14f-136">如果路径不存在，命令会尝试创建它。</span><span class="sxs-lookup"><span data-stu-id="9a14f-136">If PATH doesn't exist, the command tries to create it.</span></span> <span data-ttu-id="9a14f-137">省略 `--global` 和 `--tool-path` 指定本地工具安装。</span><span class="sxs-lookup"><span data-stu-id="9a14f-137">Omitting both `--global` and `--tool-path` specifies a local tool installation.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="9a14f-138">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="9a14f-138">Sets the verbosity level of the command.</span></span> <span data-ttu-id="9a14f-139">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="9a14f-139">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

- **`--version <VERSION_NUMBER>`**

  <span data-ttu-id="9a14f-140">要安装的工具版本。</span><span class="sxs-lookup"><span data-stu-id="9a14f-140">The version of the tool to install.</span></span> <span data-ttu-id="9a14f-141">默认情况下，安装最新的稳定包版本。</span><span class="sxs-lookup"><span data-stu-id="9a14f-141">By default, the latest stable package version is installed.</span></span> <span data-ttu-id="9a14f-142">使用此选项安装工具的预览版或较旧版本。</span><span class="sxs-lookup"><span data-stu-id="9a14f-142">Use this option to install preview or older versions of the tool.</span></span>

## <a name="examples"></a><span data-ttu-id="9a14f-143">示例</span><span class="sxs-lookup"><span data-stu-id="9a14f-143">Examples</span></span>

- **`dotnet tool install -g dotnetsay`**

  <span data-ttu-id="9a14f-144">在默认位置中安装 [dotnetsay](https://www.nuget.org/packages/dotnetsay/) 全局工具。</span><span class="sxs-lookup"><span data-stu-id="9a14f-144">Installs [dotnetsay](https://www.nuget.org/packages/dotnetsay/) as a global tool in the default location.</span></span>

- **`dotnet tool install dotnetsay --tool-path c:\global-tools`**

  <span data-ttu-id="9a14f-145">在特定 Windows 目录中安装 [dotnetsay](https://www.nuget.org/packages/dotnetsay/) 全局工具。</span><span class="sxs-lookup"><span data-stu-id="9a14f-145">Installs [dotnetsay](https://www.nuget.org/packages/dotnetsay/) as a global tool in a specific Windows directory.</span></span>

- **`dotnet tool install dotnetsay --tool-path ~/bin`**

  <span data-ttu-id="9a14f-146">在特定 Linux/macOS 目录中安装 [dotnetsay](https://www.nuget.org/packages/dotnetsay/) 全局工具。</span><span class="sxs-lookup"><span data-stu-id="9a14f-146">Installs [dotnetsay](https://www.nuget.org/packages/dotnetsay/) as a global tool in a specific Linux/macOS directory.</span></span>

- **`dotnet tool install -g dotnetsay --version 2.0.0`**

  <span data-ttu-id="9a14f-147">安装 2.0.0 版的 [dotnetsay](https://www.nuget.org/packages/dotnetsay/) 全局工具。</span><span class="sxs-lookup"><span data-stu-id="9a14f-147">Installs version 2.0.0 of [dotnetsay](https://www.nuget.org/packages/dotnetsay/) as a global tool.</span></span>

- **`dotnet tool install dotnetsay`**

  <span data-ttu-id="9a14f-148">在当前目录中安装 [dotnetsay](https://www.nuget.org/packages/dotnetsay/) 本地工具。</span><span class="sxs-lookup"><span data-stu-id="9a14f-148">Installs [dotnetsay](https://www.nuget.org/packages/dotnetsay/) as a local tool for the current directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="9a14f-149">请参阅</span><span class="sxs-lookup"><span data-stu-id="9a14f-149">See also</span></span>

- [<span data-ttu-id="9a14f-150">.NET Core 工具</span><span class="sxs-lookup"><span data-stu-id="9a14f-150">.NET Core tools</span></span>](global-tools.md)
- [<span data-ttu-id="9a14f-151">教程：使用 .NET Core CLI 安装和使用 .NET Core 全局工具</span><span class="sxs-lookup"><span data-stu-id="9a14f-151">Tutorial: Install and use a .NET Core global tool using the .NET Core CLI</span></span>](global-tools-how-to-use.md)
- [<span data-ttu-id="9a14f-152">教程：使用 .NET Core CLI 安装和使用 .NET Core 本地工具</span><span class="sxs-lookup"><span data-stu-id="9a14f-152">Tutorial: Install and use a .NET Core local tool using the .NET Core CLI</span></span>](local-tools-how-to-use.md)
