---
title: dotnet tool uninstall 命令
description: dotnet tool uninstall 命令从计算机上卸载指定的 .NET Core 工具。
ms.date: 02/14/2020
ms.openlocfilehash: 7a15c169c73cf5a743e0fa6f47645d6bccedbde3
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2020
ms.locfileid: "78157040"
---
# <a name="dotnet-tool-uninstall"></a><span data-ttu-id="d4f61-103">dotnet tool uninstall</span><span class="sxs-lookup"><span data-stu-id="d4f61-103">dotnet tool uninstall</span></span>

<span data-ttu-id="d4f61-104"> 本文适用于： ✔️ .NET Core 2.1 SDK 及更高版本</span><span class="sxs-lookup"><span data-stu-id="d4f61-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="d4f61-105">“属性”</span><span class="sxs-lookup"><span data-stu-id="d4f61-105">Name</span></span>

<span data-ttu-id="d4f61-106">`dotnet tool uninstall` - 从计算机上卸载指定的 [.NET Core 工具](global-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="d4f61-106">`dotnet tool uninstall` - Uninstalls the specified [.NET Core tool](global-tools.md) from your machine.</span></span>

## <a name="synopsis"></a><span data-ttu-id="d4f61-107">摘要</span><span class="sxs-lookup"><span data-stu-id="d4f61-107">Synopsis</span></span>

```dotnetcli
dotnet tool uninstall <PACKAGE_NAME> <-g|--global>
dotnet tool uninstall <PACKAGE_NAME> <--tool-path>
dotnet tool uninstall <PACKAGE_NAME>
dotnet tool uninstall <-h|--help>
```

## <a name="description"></a><span data-ttu-id="d4f61-108">描述</span><span class="sxs-lookup"><span data-stu-id="d4f61-108">Description</span></span>

<span data-ttu-id="d4f61-109">`dotnet tool uninstall` 提供一种从计算机上卸载 .NET Core 工具的方法。</span><span class="sxs-lookup"><span data-stu-id="d4f61-109">The `dotnet tool uninstall` command provides a way for you to uninstall .NET Core tools from your machine.</span></span> <span data-ttu-id="d4f61-110">若要使用命令，请指定以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="d4f61-110">To use the command, you specify one of the following options:</span></span>

* <span data-ttu-id="d4f61-111">若要卸载安装在默认位置的全局工具，请使用 `--global` 选项。</span><span class="sxs-lookup"><span data-stu-id="d4f61-111">To uninstall a global tool that was installed in the default location, use the `--global` option.</span></span>
* <span data-ttu-id="d4f61-112">若要卸载安装在自定义位置的全局工具，请使用 `--tool-path` 选项。</span><span class="sxs-lookup"><span data-stu-id="d4f61-112">To uninstall a global tool that was installed in a custom location,  use the `--tool-path` option.</span></span>
* <span data-ttu-id="d4f61-113">若要卸载本地工具，请省略 `--global` 和 `--tool-path` 选项。</span><span class="sxs-lookup"><span data-stu-id="d4f61-113">To uninstall a local tool, omit the `--global` and `--tool-path` options.</span></span>

<span data-ttu-id="d4f61-114">**本地工具从 .NET Core SDK 3.0 开始可用。**</span><span class="sxs-lookup"><span data-stu-id="d4f61-114">**Local tools are available starting with .NET Core SDK 3.0.**</span></span>

## <a name="arguments"></a><span data-ttu-id="d4f61-115">自变量</span><span class="sxs-lookup"><span data-stu-id="d4f61-115">Arguments</span></span>

- **`PACKAGE_NAME`**

  <span data-ttu-id="d4f61-116">包含要卸载的 .NET Core 工具的 NuGet 包的名称/ID。</span><span class="sxs-lookup"><span data-stu-id="d4f61-116">Name/ID of the NuGet package that contains the .NET Core tool to uninstall.</span></span> <span data-ttu-id="d4f61-117">你可以使用 [dotnet tool list](dotnet-tool-list.md) 命令查找包名称。</span><span class="sxs-lookup"><span data-stu-id="d4f61-117">You can find the package name using the [dotnet tool list](dotnet-tool-list.md) command.</span></span>

## <a name="options"></a><span data-ttu-id="d4f61-118">选项</span><span class="sxs-lookup"><span data-stu-id="d4f61-118">Options</span></span>

- **`-g|--global`**

  <span data-ttu-id="d4f61-119">指定要从用户范围的安装中删除工具。</span><span class="sxs-lookup"><span data-stu-id="d4f61-119">Specifies that the tool to be removed is from a user-wide installation.</span></span> <span data-ttu-id="d4f61-120">不能与 `--tool-path` 选项一起使用。</span><span class="sxs-lookup"><span data-stu-id="d4f61-120">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="d4f61-121">省略 `--global` 和 `--tool-path` 指定要删除的工具是本地工具。</span><span class="sxs-lookup"><span data-stu-id="d4f61-121">Omitting both `--global` and `--tool-path` specifies that the tool to be removed is a local tool.</span></span>

- **`-h|--help`**

  <span data-ttu-id="d4f61-122">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="d4f61-122">Prints out a short help for the command.</span></span>

- **`--tool-path <PATH>`**

  <span data-ttu-id="d4f61-123">指定卸载工具的位置。</span><span class="sxs-lookup"><span data-stu-id="d4f61-123">Specifies the location where to uninstall the tool.</span></span> <span data-ttu-id="d4f61-124">路径可以是绝对的，也可以是相对的。</span><span class="sxs-lookup"><span data-stu-id="d4f61-124">PATH can be absolute or relative.</span></span> <span data-ttu-id="d4f61-125">不能与 `--global` 选项一起使用。</span><span class="sxs-lookup"><span data-stu-id="d4f61-125">Can't be combined with the `--global` option.</span></span> <span data-ttu-id="d4f61-126">省略 `--global` 和 `--tool-path` 指定要删除的工具是本地工具。</span><span class="sxs-lookup"><span data-stu-id="d4f61-126">Omitting both `--global` and `--tool-path` specifies that the tool to be removed is a local tool.</span></span>

## <a name="examples"></a><span data-ttu-id="d4f61-127">示例</span><span class="sxs-lookup"><span data-stu-id="d4f61-127">Examples</span></span>

- **`dotnet tool uninstall -g dotnetsay`**

  <span data-ttu-id="d4f61-128">卸载 [dotnetsay](https://www.nuget.org/packages/dotnetsay/) 全局工具。</span><span class="sxs-lookup"><span data-stu-id="d4f61-128">Uninstalls the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) global tool.</span></span>

- **`dotnet tool uninstall dotnetsay --tool-path c:\global-tools`**

  <span data-ttu-id="d4f61-129">从特定 Windows 目录卸载 [dotnetsay](https://www.nuget.org/packages/dotnetsay/) 全局工具。</span><span class="sxs-lookup"><span data-stu-id="d4f61-129">Uninstalls the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) global tool from a specific Windows directory.</span></span>

- **`dotnet tool uninstall dotnetsay --tool-path ~/bin`**

  <span data-ttu-id="d4f61-130">从特定 Linux/macOS 目录卸载 [dotnetsay](https://www.nuget.org/packages/dotnetsay/) 全局工具。</span><span class="sxs-lookup"><span data-stu-id="d4f61-130">Uninstalls the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) global tool from a specific Linux/macOS directory.</span></span>

- **`dotnet tool uninstall dotnetsay`**

  <span data-ttu-id="d4f61-131">从当前目录卸载 [dotnetsay](https://www.nuget.org/packages/dotnetsay/) 全局工具。</span><span class="sxs-lookup"><span data-stu-id="d4f61-131">Uninstalls the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) local tool from the current directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="d4f61-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="d4f61-132">See also</span></span>

- [<span data-ttu-id="d4f61-133">.NET Core 工具</span><span class="sxs-lookup"><span data-stu-id="d4f61-133">.NET Core tools</span></span>](global-tools.md)
