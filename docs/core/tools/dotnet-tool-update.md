---
title: dotnet tool update 命令
description: dotnet tool update 命令更新计算机上指定的 .NET Core 工具。
ms.date: 02/14/2020
ms.openlocfilehash: 50bb366fedfb0ea69b8b6007ff89e366b4f689de
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543412"
---
# <a name="dotnet-tool-update"></a><span data-ttu-id="ae2df-103">dotnet tool update</span><span class="sxs-lookup"><span data-stu-id="ae2df-103">dotnet tool update</span></span>

<span data-ttu-id="ae2df-104"> 本文适用于： ✔️ .NET Core 2.1 SDK 及更高版本</span><span class="sxs-lookup"><span data-stu-id="ae2df-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="ae2df-105">“属性”</span><span class="sxs-lookup"><span data-stu-id="ae2df-105">Name</span></span>

<span data-ttu-id="ae2df-106">`dotnet tool update` - 更新计算机上指定的 [.NET Core 工具](global-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="ae2df-106">`dotnet tool update` - Updates the specified [.NET Core tool](global-tools.md) on your machine.</span></span>

## <a name="synopsis"></a><span data-ttu-id="ae2df-107">摘要</span><span class="sxs-lookup"><span data-stu-id="ae2df-107">Synopsis</span></span>

```dotnetcli
dotnet tool update <PACKAGE_NAME> <-g|--global> [--configfile] [--framework] [-v|--verbosity] [--add-source]
dotnet tool update <PACKAGE_NAME> <--tool-path> [--configfile] [--framework] [-v|--verbosity] [--add-source]
dotnet tool update <PACKAGE_NAME> [--configfile] [--framework] [-v|--verbosity] [--add-source]
dotnet tool update <-h|--help>
```

## <a name="description"></a><span data-ttu-id="ae2df-108">描述</span><span class="sxs-lookup"><span data-stu-id="ae2df-108">Description</span></span>

<span data-ttu-id="ae2df-109">`dotnet tool update` 命令让你可以将计算机上的 .NET Core 工具更新为包的最新稳定版。</span><span class="sxs-lookup"><span data-stu-id="ae2df-109">The `dotnet tool update` command provides a way for you to update .NET Core tools on your machine to the latest stable version of the package.</span></span> <span data-ttu-id="ae2df-110">此命令卸载并重新安装工具，有效地对工具进行更新。</span><span class="sxs-lookup"><span data-stu-id="ae2df-110">The command uninstalls and reinstalls a tool, effectively updating it.</span></span> <span data-ttu-id="ae2df-111">若要使用命令，请指定以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="ae2df-111">To use the command, you specify one of the following options:</span></span>

* <span data-ttu-id="ae2df-112">若要更新安装在默认位置的全局工具，请使用 `--global` 选项</span><span class="sxs-lookup"><span data-stu-id="ae2df-112">To update a global tool that was installed in the default location, use the `--global` option</span></span>
* <span data-ttu-id="ae2df-113">若要更新安装在自定义位置的全局工具，请使用 `--tool-path` 选项。</span><span class="sxs-lookup"><span data-stu-id="ae2df-113">To update a global tool that was installed in a custom location, use the `--tool-path` option.</span></span>
* <span data-ttu-id="ae2df-114">若要更新本地工具，请省略 `--global` 和 `--tool-path` 选项。</span><span class="sxs-lookup"><span data-stu-id="ae2df-114">To update a local tool, omit the `--global` and `--tool-path` options.</span></span>

<span data-ttu-id="ae2df-115">**本地工具从 .NET Core SDK 3.0 开始可用。**</span><span class="sxs-lookup"><span data-stu-id="ae2df-115">**Local tools are available starting with .NET Core SDK 3.0.**</span></span>

## <a name="arguments"></a><span data-ttu-id="ae2df-116">自变量</span><span class="sxs-lookup"><span data-stu-id="ae2df-116">Arguments</span></span>

- **`PACKAGE_NAME`**

  <span data-ttu-id="ae2df-117">包含要更新的 .NET Core 全局工具的 NuGet 包的名称/ID。</span><span class="sxs-lookup"><span data-stu-id="ae2df-117">Name/ID of the NuGet package that contains the .NET Core global tool to update.</span></span> <span data-ttu-id="ae2df-118">你可以使用 [dotnet tool list](dotnet-tool-list.md) 命令查找包名称。</span><span class="sxs-lookup"><span data-stu-id="ae2df-118">You can find the package name using the [dotnet tool list](dotnet-tool-list.md) command.</span></span>

## <a name="options"></a><span data-ttu-id="ae2df-119">选项</span><span class="sxs-lookup"><span data-stu-id="ae2df-119">Options</span></span>

- **`--add-source <SOURCE>`**

  <span data-ttu-id="ae2df-120">添加安装过程中要使用的其他 NuGet 包源。</span><span class="sxs-lookup"><span data-stu-id="ae2df-120">Adds an additional NuGet package source to use during installation.</span></span>

- **`--configfile <FILE>`**

  <span data-ttu-id="ae2df-121">要使用的 NuGet 配置 (nuget.config) 文件  。</span><span class="sxs-lookup"><span data-stu-id="ae2df-121">The NuGet configuration (*nuget.config*) file to use.</span></span>

- **`--framework <FRAMEWORK>`**

  <span data-ttu-id="ae2df-122">指定要更新工具的[目标框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="ae2df-122">Specifies the [target framework](../../standard/frameworks.md) to update the tool for.</span></span>

- **`-g|--global`**

  <span data-ttu-id="ae2df-123">指定此更新用于用户范围的工具。</span><span class="sxs-lookup"><span data-stu-id="ae2df-123">Specifies that the update is for a user-wide tool.</span></span> <span data-ttu-id="ae2df-124">不能与 `--tool-path` 选项一起使用。</span><span class="sxs-lookup"><span data-stu-id="ae2df-124">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="ae2df-125">省略 `--global` 和 `--tool-path` 均指定要更新的工具是本地工具。</span><span class="sxs-lookup"><span data-stu-id="ae2df-125">Omitting both `--global` and `--tool-path` specifies that the tool to be updated is a local tool.</span></span> 

- **`-h|--help`**

  <span data-ttu-id="ae2df-126">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="ae2df-126">Prints out a short help for the command.</span></span>

- **`--tool-path <PATH>`**

  <span data-ttu-id="ae2df-127">指定全局工具的安装位置。</span><span class="sxs-lookup"><span data-stu-id="ae2df-127">Specifies the location where the global tool is installed.</span></span> <span data-ttu-id="ae2df-128">路径可以是绝对的，也可以是相对的。</span><span class="sxs-lookup"><span data-stu-id="ae2df-128">PATH can be absolute or relative.</span></span> <span data-ttu-id="ae2df-129">不能与 `--global` 选项一起使用。</span><span class="sxs-lookup"><span data-stu-id="ae2df-129">Can't be combined with the `--global` option.</span></span> <span data-ttu-id="ae2df-130">省略 `--global` 和 `--tool-path` 均指定要更新的工具是本地工具。</span><span class="sxs-lookup"><span data-stu-id="ae2df-130">Omitting both `--global` and `--tool-path` specifies that the tool to be updated is a local tool.</span></span> 

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="ae2df-131">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="ae2df-131">Sets the verbosity level of the command.</span></span> <span data-ttu-id="ae2df-132">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="ae2df-132">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

## <a name="examples"></a><span data-ttu-id="ae2df-133">示例</span><span class="sxs-lookup"><span data-stu-id="ae2df-133">Examples</span></span>

- **`dotnet tool update -g dotnetsay`**

  <span data-ttu-id="ae2df-134">更新 [dotnetsay](https://www.nuget.org/packages/dotnetsay/) 全局工具。</span><span class="sxs-lookup"><span data-stu-id="ae2df-134">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) global tool.</span></span>

- **`dotnet tool update dotnetsay --tool-path c:\global-tools`**

  <span data-ttu-id="ae2df-135">更新位于特定 Windows 目录的 [dotnetsay](https://www.nuget.org/packages/dotnetsay/) 全局工具。</span><span class="sxs-lookup"><span data-stu-id="ae2df-135">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) global tool located in a specific Windows directory.</span></span>

- **`dotnet tool update dotnetsay --tool-path ~/bin`**

  <span data-ttu-id="ae2df-136">更新位于特定 Linux/macOS 目录的 [dotnetsay](https://www.nuget.org/packages/dotnetsay/) 全局工具。</span><span class="sxs-lookup"><span data-stu-id="ae2df-136">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) global tool located in a specific Linux/macOS directory.</span></span>

- **`dotnet tool update dotnetsay`**

  <span data-ttu-id="ae2df-137">更新为当前目录安装的 [dotnetsay](https://www.nuget.org/packages/dotnetsay/) 本地工具。</span><span class="sxs-lookup"><span data-stu-id="ae2df-137">Updates the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) local tool installed for the current directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="ae2df-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="ae2df-138">See also</span></span>

- [<span data-ttu-id="ae2df-139">.NET Core 工具</span><span class="sxs-lookup"><span data-stu-id="ae2df-139">.NET Core tools</span></span>](global-tools.md)
