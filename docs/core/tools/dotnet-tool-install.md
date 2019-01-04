---
title: dotnet tool install 命令
description: dotnet tool install 命令在计算机上安装指定的 .NET Core 全局工具。
ms.date: 05/29/2018
ms.openlocfilehash: 251e7b04be96ac2340727fa03dbaa2d548110fa9
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53168710"
---
# <a name="dotnet-tool-install"></a><span data-ttu-id="fd00e-103">dotnet tool install</span><span class="sxs-lookup"><span data-stu-id="fd00e-103">dotnet tool install</span></span>

[!INCLUDE [topic-appliesto-net-core-21plus.md](../../../includes/topic-appliesto-net-core-21plus.md)]

## <a name="name"></a><span data-ttu-id="fd00e-104">name</span><span class="sxs-lookup"><span data-stu-id="fd00e-104">Name</span></span>

<span data-ttu-id="fd00e-105">`dotnet tool install` - 在计算机上安装指定的 [.NET Core 全局工具](global-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="fd00e-105">`dotnet tool install` - Installs the specified [.NET Core Global Tool](global-tools.md) on your machine.</span></span>

## <a name="synopsis"></a><span data-ttu-id="fd00e-106">摘要</span><span class="sxs-lookup"><span data-stu-id="fd00e-106">Synopsis</span></span>

```console
dotnet tool install <PACKAGE_NAME> <-g|--global> [--add-source] [--configfile] [--framework] [-v|--verbosity] [--version]
dotnet tool install <PACKAGE_NAME> <--tool-path> [--add-source] [--configfile] [--framework] [-v|--verbosity] [--version]
dotnet tool install <-h|--help>
```

## <a name="description"></a><span data-ttu-id="fd00e-107">说明</span><span class="sxs-lookup"><span data-stu-id="fd00e-107">Description</span></span>

<span data-ttu-id="fd00e-108">`dotnet tool install` 为用户提供一种在计算机上安装 .NET Core 全局工具的方法。</span><span class="sxs-lookup"><span data-stu-id="fd00e-108">The `dotnet tool install` command provides a way for you to install .NET Core Global Tools on your machine.</span></span> <span data-ttu-id="fd00e-109">若要使用此命令，需要使用 `--global` 选项指定用户范围的安装或者使用 `--tool-path` 选项指定安装路径。</span><span class="sxs-lookup"><span data-stu-id="fd00e-109">To use the command, you either have to specify that you want a user-wide installation using the `--global` option or you specify a path to install it using the `--tool-path` option.</span></span>

<span data-ttu-id="fd00e-110">指定 `-g`（或 `--global`）选项时，全局工具默认安装在以下目录中：</span><span class="sxs-lookup"><span data-stu-id="fd00e-110">Global Tools are installed in the following directories by default when you specify the `-g` (or `--global`) option:</span></span>

| <span data-ttu-id="fd00e-111">(OS)</span><span class="sxs-lookup"><span data-stu-id="fd00e-111">OS</span></span>          | <span data-ttu-id="fd00e-112">路径</span><span class="sxs-lookup"><span data-stu-id="fd00e-112">Path</span></span>                          |
|-------------|-------------------------------|
| <span data-ttu-id="fd00e-113">Linux/macOS</span><span class="sxs-lookup"><span data-stu-id="fd00e-113">Linux/macOS</span></span> | `$HOME/.dotnet/tools`         |
| <span data-ttu-id="fd00e-114">Windows</span><span class="sxs-lookup"><span data-stu-id="fd00e-114">Windows</span></span>     | `%USERPROFILE%\.dotnet\tools` |

## <a name="arguments"></a><span data-ttu-id="fd00e-115">自变量</span><span class="sxs-lookup"><span data-stu-id="fd00e-115">Arguments</span></span>

`PACKAGE_NAME`

<span data-ttu-id="fd00e-116">包含要安装的 .NET Core 全局工具的 NuGet 包的名称/ID。</span><span class="sxs-lookup"><span data-stu-id="fd00e-116">Name/ID of the NuGet package that contains the .NET Core Global Tool to install.</span></span>

## <a name="options"></a><span data-ttu-id="fd00e-117">选项</span><span class="sxs-lookup"><span data-stu-id="fd00e-117">Options</span></span>

`--add-source <SOURCE>`

<span data-ttu-id="fd00e-118">添加安装过程中要使用的其他 NuGet 包源。</span><span class="sxs-lookup"><span data-stu-id="fd00e-118">Adds an additional NuGet package source to use during installation.</span></span>

`--configfile <FILE>`

<span data-ttu-id="fd00e-119">要使用的 NuGet 配置 (nuget.config) 文件。</span><span class="sxs-lookup"><span data-stu-id="fd00e-119">The NuGet configuration (*nuget.config*) file to use.</span></span>

`--framework <FRAMEWORK>`

<span data-ttu-id="fd00e-120">指定要安装工具的[目标框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="fd00e-120">Specifies the [target framework](../../standard/frameworks.md) to install the tool for.</span></span> <span data-ttu-id="fd00e-121">默认情况下，.NET Core SDK 尝试选择最合适的目标框架。</span><span class="sxs-lookup"><span data-stu-id="fd00e-121">By default, the .NET Core SDK tries to choose the most appropriate target framework.</span></span>

`-g|--global`

<span data-ttu-id="fd00e-122">指定安装是用户范围的。</span><span class="sxs-lookup"><span data-stu-id="fd00e-122">Specifies that the installation is user wide.</span></span> <span data-ttu-id="fd00e-123">不能与 `--tool-path` 选项一起使用。</span><span class="sxs-lookup"><span data-stu-id="fd00e-123">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="fd00e-124">如果不指定此选项，则必须指定 `--tool-path` 选项。</span><span class="sxs-lookup"><span data-stu-id="fd00e-124">If you don't specify this option, you must specify the `--tool-path` option.</span></span>

`-h|--help`

<span data-ttu-id="fd00e-125">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="fd00e-125">Prints out a short help for the command.</span></span>

`--tool-path <PATH>`

<span data-ttu-id="fd00e-126">指定全局工具的安装位置。</span><span class="sxs-lookup"><span data-stu-id="fd00e-126">Specifies the location where to install the Global Tool.</span></span> <span data-ttu-id="fd00e-127">路径可以是绝对的，也可以是相对的。</span><span class="sxs-lookup"><span data-stu-id="fd00e-127">PATH can be absolute or relative.</span></span> <span data-ttu-id="fd00e-128">如果路径不存在，命令会尝试创建它。</span><span class="sxs-lookup"><span data-stu-id="fd00e-128">If PATH doesn't exist, the command tries to create it.</span></span> <span data-ttu-id="fd00e-129">不能与 `--global` 选项一起使用。</span><span class="sxs-lookup"><span data-stu-id="fd00e-129">Can't be combined with the `--global` option.</span></span> <span data-ttu-id="fd00e-130">如果不指定此选项，则必须指定 `--global` 选项。</span><span class="sxs-lookup"><span data-stu-id="fd00e-130">If you don't specify this option, you must specify the `--global` option.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="fd00e-131">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="fd00e-131">Sets the verbosity level of the command.</span></span> <span data-ttu-id="fd00e-132">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="fd00e-132">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version <VERSION_NUMBER>`

<span data-ttu-id="fd00e-133">要安装的工具版本。</span><span class="sxs-lookup"><span data-stu-id="fd00e-133">The version of the tool to install.</span></span> <span data-ttu-id="fd00e-134">默认情况下，安装最新的稳定包版本。</span><span class="sxs-lookup"><span data-stu-id="fd00e-134">By default, the latest stable package version is installed.</span></span> <span data-ttu-id="fd00e-135">使用此选项安装工具的预览版或较旧版本。</span><span class="sxs-lookup"><span data-stu-id="fd00e-135">Use this option to install preview or older versions of the tool.</span></span>

## <a name="examples"></a><span data-ttu-id="fd00e-136">示例</span><span class="sxs-lookup"><span data-stu-id="fd00e-136">Examples</span></span>

<span data-ttu-id="fd00e-137">在默认位置安装 [dotnetsay](https://www.nuget.org/packages/dotnetsay/) 全局工具：</span><span class="sxs-lookup"><span data-stu-id="fd00e-137">Installs the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) Global Tool in the default location:</span></span>

`dotnet tool install -g dotnetsay`

<span data-ttu-id="fd00e-138">在特定 Windows 文件夹安装 [dotnetsay](https://www.nuget.org/packages/dotnetsay/) 全局工具：</span><span class="sxs-lookup"><span data-stu-id="fd00e-138">Installs the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) Global Tool on a specific Windows folder:</span></span>

`dotnet tool install dotnetsay --tool-path c:\global-tools`

<span data-ttu-id="fd00e-139">在特定 Linux/macOS 文件夹安装 [dotnetsay](https://www.nuget.org/packages/dotnetsay/) 全局工具：</span><span class="sxs-lookup"><span data-stu-id="fd00e-139">Installs the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) Global Tool on a specific Linux/macOS folder:</span></span>

`dotnet tool install dotnetsay --tool-path ~/bin`

<span data-ttu-id="fd00e-140">安装 2.0.0 版的 [dotnetsay](https://www.nuget.org/packages/dotnetsay/) 全局工具：</span><span class="sxs-lookup"><span data-stu-id="fd00e-140">Installs version 2.0.0 of the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) Global Tool:</span></span>

`dotnet tool install -g dotnetsay --version 2.0.0`

## <a name="see-also"></a><span data-ttu-id="fd00e-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="fd00e-141">See also</span></span>

* [<span data-ttu-id="fd00e-142">.NET Core 全局工具</span><span class="sxs-lookup"><span data-stu-id="fd00e-142">.NET Core Global Tools</span></span>](global-tools.md)