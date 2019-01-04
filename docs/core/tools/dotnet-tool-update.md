---
title: dotnet tool update 命令
description: dotnet tool update 命令在你计算机上更新指定的 .NET Core 全局工具。
ms.date: 05/29/2018
ms.openlocfilehash: 2716f7f88ffe364bebacf970d7152f5509edc888
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53169731"
---
# <a name="dotnet-tool-update"></a><span data-ttu-id="ba7e3-103">dotnet tool update</span><span class="sxs-lookup"><span data-stu-id="ba7e3-103">dotnet tool update</span></span>

[!INCLUDE [topic-appliesto-net-core-21plus.md](../../../includes/topic-appliesto-net-core-21plus.md)]

## <a name="name"></a><span data-ttu-id="ba7e3-104">name</span><span class="sxs-lookup"><span data-stu-id="ba7e3-104">Name</span></span>

<span data-ttu-id="ba7e3-105">`dotnet tool update` - 在你的计算机上更新指定的 [.NET Core 全局工具](global-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="ba7e3-105">`dotnet tool update` - Updates the specified [.NET Core Global Tool](global-tools.md) on your machine.</span></span>

## <a name="synopsis"></a><span data-ttu-id="ba7e3-106">摘要</span><span class="sxs-lookup"><span data-stu-id="ba7e3-106">Synopsis</span></span>

```console
dotnet tool update <PACKAGE_NAME> <-g|--global> [--configfile] [--framework] [-v|--verbosity]
dotnet tool update <PACKAGE_NAME> <--tool-path> [--configfile] [--framework] [-v|--verbosity]
dotnet tool update <-h|--help>
```

## <a name="description"></a><span data-ttu-id="ba7e3-107">说明</span><span class="sxs-lookup"><span data-stu-id="ba7e3-107">Description</span></span>

<span data-ttu-id="ba7e3-108">`dotnet tool update` 命令让你可以将计算机上的 .NET Core 全局工具更新为包的最新稳定版。</span><span class="sxs-lookup"><span data-stu-id="ba7e3-108">The `dotnet tool update` command provides a way for you to update .NET Core Global Tools on your machine to the latest stable version of the package.</span></span> <span data-ttu-id="ba7e3-109">此命令卸载并重新安装工具，有效地对工具进行更新。</span><span class="sxs-lookup"><span data-stu-id="ba7e3-109">The command uninstalls and reinstalls a tool, effectively updating it.</span></span> <span data-ttu-id="ba7e3-110">若要使用此命令，需要使用 `--global` 选项指定从用户范围的安装中更新工具或使用 `--tool-path` 选项指定安装工具的路径。</span><span class="sxs-lookup"><span data-stu-id="ba7e3-110">To use the command, you either have to specify that you want to update a tool from a user-wide installation using the `--global` option or specify a path to where the tool is installed using the `--tool-path` option.</span></span>

## <a name="arguments"></a><span data-ttu-id="ba7e3-111">自变量</span><span class="sxs-lookup"><span data-stu-id="ba7e3-111">Arguments</span></span>

`PACKAGE_NAME`

<span data-ttu-id="ba7e3-112">包含要更新的 .NET Core 全局工具的 NuGet 包的名称/ID。</span><span class="sxs-lookup"><span data-stu-id="ba7e3-112">Name/ID of the NuGet package that contains the .NET Core Global Tool to update.</span></span> <span data-ttu-id="ba7e3-113">你可以使用 [dotnet tool list](dotnet-tool-list.md) 命令查找包名称。</span><span class="sxs-lookup"><span data-stu-id="ba7e3-113">You can find the package name using the [dotnet tool list](dotnet-tool-list.md) command.</span></span>

## <a name="options"></a><span data-ttu-id="ba7e3-114">选项</span><span class="sxs-lookup"><span data-stu-id="ba7e3-114">Options</span></span>

`--add-source <SOURCE>`

<span data-ttu-id="ba7e3-115">添加安装过程中要使用的其他 NuGet 包源。</span><span class="sxs-lookup"><span data-stu-id="ba7e3-115">Adds an additional NuGet package source to use during installation.</span></span>

`--configfile <FILE>`

<span data-ttu-id="ba7e3-116">要使用的 NuGet 配置 (nuget.config) 文件。</span><span class="sxs-lookup"><span data-stu-id="ba7e3-116">The NuGet configuration (*nuget.config*) file to use.</span></span>

`--framework <FRAMEWORK>`

<span data-ttu-id="ba7e3-117">指定要更新工具的[目标框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="ba7e3-117">Specifies the [target framework](../../standard/frameworks.md) to update the tool for.</span></span>

`-g|--global`

<span data-ttu-id="ba7e3-118">指定此更新用于用户范围的工具。</span><span class="sxs-lookup"><span data-stu-id="ba7e3-118">Specifies that the update is for a user-wide tool.</span></span> <span data-ttu-id="ba7e3-119">不能与 `--tool-path` 选项一起使用。</span><span class="sxs-lookup"><span data-stu-id="ba7e3-119">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="ba7e3-120">如果不指定此选项，则必须指定 `--tool-path` 选项。</span><span class="sxs-lookup"><span data-stu-id="ba7e3-120">If you don't specify this option, you must specify the `--tool-path` option.</span></span>

`-h|--help`

<span data-ttu-id="ba7e3-121">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="ba7e3-121">Prints out a short help for the command.</span></span>

`--tool-path <PATH>`

<span data-ttu-id="ba7e3-122">指定全局工具的安装位置。</span><span class="sxs-lookup"><span data-stu-id="ba7e3-122">Specifies the location where the Global Tool is installed.</span></span> <span data-ttu-id="ba7e3-123">路径可以是绝对的，也可以是相对的。</span><span class="sxs-lookup"><span data-stu-id="ba7e3-123">PATH can be absolute or relative.</span></span> <span data-ttu-id="ba7e3-124">不能与 `--global` 选项一起使用。</span><span class="sxs-lookup"><span data-stu-id="ba7e3-124">Can't be combined with the `--global` option.</span></span> <span data-ttu-id="ba7e3-125">如果不指定此选项，则必须指定 `--global` 选项。</span><span class="sxs-lookup"><span data-stu-id="ba7e3-125">If you don't specify this option, you must specify the `--global` option.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="ba7e3-126">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="ba7e3-126">Sets the verbosity level of the command.</span></span> <span data-ttu-id="ba7e3-127">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="ba7e3-127">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

## <a name="examples"></a><span data-ttu-id="ba7e3-128">示例</span><span class="sxs-lookup"><span data-stu-id="ba7e3-128">Examples</span></span>

<span data-ttu-id="ba7e3-129">更新 [dotnetsay](https://www.nuget.org/packages/dotnetsay/) 全局工具：</span><span class="sxs-lookup"><span data-stu-id="ba7e3-129">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) Global Tool:</span></span>

`dotnet tool update -g dotnetsay`

<span data-ttu-id="ba7e3-130">更新位于特定 Windows 文件夹的 [dotnetsay](https://www.nuget.org/packages/dotnetsay/) 全局工具：</span><span class="sxs-lookup"><span data-stu-id="ba7e3-130">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) Global Tool located on a specific Windows folder:</span></span>

`dotnet tool update dotnetsay --tool-path c:\global-tools`

<span data-ttu-id="ba7e3-131">更新位于特定 Linux/macOS 文件夹的 [dotnetsay](https://www.nuget.org/packages/dotnetsay/) 全局工具：</span><span class="sxs-lookup"><span data-stu-id="ba7e3-131">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) Global Tool located on a specific Linux/macOS folder:</span></span>

`dotnet tool update dotnetsay --tool-path ~/bin`

## <a name="see-also"></a><span data-ttu-id="ba7e3-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="ba7e3-132">See also</span></span>

* [<span data-ttu-id="ba7e3-133">.NET Core 全局工具</span><span class="sxs-lookup"><span data-stu-id="ba7e3-133">.NET Core Global Tools</span></span>](global-tools.md)