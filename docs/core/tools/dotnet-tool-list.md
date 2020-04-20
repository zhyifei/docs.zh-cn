---
title: dotnet tool list 命令
description: dotnet 工具列表命令列出计算机上安装的 .NET Core 工具。
ms.date: 02/14/2020
ms.openlocfilehash: 28f9155407d1238f8b0960b69b34ea329ca0e8e6
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463348"
---
# <a name="dotnet-tool-list"></a><span data-ttu-id="6aa4c-103">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="6aa4c-103">dotnet tool list</span></span>

<span data-ttu-id="6aa4c-104">本文适用于： ✔️ .NET Core 2.1 SDK 及更高版本</span><span class="sxs-lookup"><span data-stu-id="6aa4c-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="6aa4c-105">“属性”</span><span class="sxs-lookup"><span data-stu-id="6aa4c-105">Name</span></span>

<span data-ttu-id="6aa4c-106">`dotnet tool list` - 列出计算机上当前安装的所有指定类型的 [.NET Core 工具](global-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="6aa4c-106">`dotnet tool list` - Lists all [.NET Core tools](global-tools.md) of the specified type currently installed on your machine.</span></span>

## <a name="synopsis"></a><span data-ttu-id="6aa4c-107">摘要</span><span class="sxs-lookup"><span data-stu-id="6aa4c-107">Synopsis</span></span>

```dotnetcli
dotnet tool list -g|--global

dotnet tool list --tool-path <PATH>

dotnet tool list

dotnet tool list -h|--help
```

## <a name="description"></a><span data-ttu-id="6aa4c-108">描述</span><span class="sxs-lookup"><span data-stu-id="6aa4c-108">Description</span></span>

<span data-ttu-id="6aa4c-109">`dotnet tool list` 命令为用户提供一种在计算机上安装所有 .NET Core 全局工具、工具路径工具或本地工具的方法。</span><span class="sxs-lookup"><span data-stu-id="6aa4c-109">The `dotnet tool list` command provides a way for you to list all .NET Core global, tool-path, or local Tools installed on your machine.</span></span> <span data-ttu-id="6aa4c-110">此命令列出包名称、安装的版本以及工具命令。</span><span class="sxs-lookup"><span data-stu-id="6aa4c-110">The command lists the package name, version installed, and the tool command.</span></span>  <span data-ttu-id="6aa4c-111">若要使用命令，请指定以下项之一：</span><span class="sxs-lookup"><span data-stu-id="6aa4c-111">To use the command, you specify one of the following:</span></span>

* <span data-ttu-id="6aa4c-112">在默认位置安装全局工具。</span><span class="sxs-lookup"><span data-stu-id="6aa4c-112">A global tool installed in the default location.</span></span> <span data-ttu-id="6aa4c-113">使用 `--global` 选项</span><span class="sxs-lookup"><span data-stu-id="6aa4c-113">Use the `--global` option</span></span>
* <span data-ttu-id="6aa4c-114">在自定义位置安装全局工具。</span><span class="sxs-lookup"><span data-stu-id="6aa4c-114">A global tool installed in a custom location.</span></span> <span data-ttu-id="6aa4c-115">使用 `--tool-path` 选项。</span><span class="sxs-lookup"><span data-stu-id="6aa4c-115">Use the `--tool-path` option.</span></span>
* <span data-ttu-id="6aa4c-116">运行本地工具。</span><span class="sxs-lookup"><span data-stu-id="6aa4c-116">A local tool.</span></span> <span data-ttu-id="6aa4c-117">省略 `--global` 和 `--tool-path` 选项。</span><span class="sxs-lookup"><span data-stu-id="6aa4c-117">Omit the `--global` and `--tool-path` options.</span></span>

<span data-ttu-id="6aa4c-118">**本地工具从 .NET Core SDK 3.0 开始可用。**</span><span class="sxs-lookup"><span data-stu-id="6aa4c-118">**Local tools are available starting with .NET Core SDK 3.0.**</span></span>

## <a name="options"></a><span data-ttu-id="6aa4c-119">选项</span><span class="sxs-lookup"><span data-stu-id="6aa4c-119">Options</span></span>

- **`-g|--global`**

  <span data-ttu-id="6aa4c-120">列出用户范围的全局工具。</span><span class="sxs-lookup"><span data-stu-id="6aa4c-120">Lists user-wide global tools.</span></span> <span data-ttu-id="6aa4c-121">不能与 `--tool-path` 选项一起使用。</span><span class="sxs-lookup"><span data-stu-id="6aa4c-121">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="6aa4c-122">省略 `--global` 和 `--tool-path` 将列出本地工具。</span><span class="sxs-lookup"><span data-stu-id="6aa4c-122">Omitting both `--global` and `--tool-path` lists local tools.</span></span>

- **`-h|--help`**

  <span data-ttu-id="6aa4c-123">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="6aa4c-123">Prints out a short help for the command.</span></span>

- **`--tool-path <PATH>`**

  <span data-ttu-id="6aa4c-124">指定用于查找全局工具的自定义位置。</span><span class="sxs-lookup"><span data-stu-id="6aa4c-124">Specifies a custom location where to find global tools.</span></span> <span data-ttu-id="6aa4c-125">路径可以是绝对的，也可以是相对的。</span><span class="sxs-lookup"><span data-stu-id="6aa4c-125">PATH can be absolute or relative.</span></span> <span data-ttu-id="6aa4c-126">不能与 `--global` 选项一起使用。</span><span class="sxs-lookup"><span data-stu-id="6aa4c-126">Can't be combined with the `--global` option.</span></span> <span data-ttu-id="6aa4c-127">省略 `--global` 和 `--tool-path` 将列出本地工具。</span><span class="sxs-lookup"><span data-stu-id="6aa4c-127">Omitting both `--global` and `--tool-path` lists local tools.</span></span>

## <a name="examples"></a><span data-ttu-id="6aa4c-128">示例</span><span class="sxs-lookup"><span data-stu-id="6aa4c-128">Examples</span></span>

- **`dotnet tool list -g`**

  <span data-ttu-id="6aa4c-129">列出计算机上安装的所有用户范围的全局工具（当前用户配置文件）。</span><span class="sxs-lookup"><span data-stu-id="6aa4c-129">Lists all global tools installed user-wide on your machine (current user profile).</span></span>

- **`dotnet tool list --tool-path c:\global-tools`**

  <span data-ttu-id="6aa4c-130">列出特定 Windows 目录中的全局工具。</span><span class="sxs-lookup"><span data-stu-id="6aa4c-130">Lists the global tools from a specific Windows directory.</span></span>

- **`dotnet tool list --tool-path ~/bin`**

  <span data-ttu-id="6aa4c-131">列出特定 Linux/macOS 目录中的全局工具。</span><span class="sxs-lookup"><span data-stu-id="6aa4c-131">Lists the global tools from a specific Linux/macOS directory.</span></span>

- **`dotnet tool list`**

  <span data-ttu-id="6aa4c-132">列出当前目录中所有可用的本地工具。</span><span class="sxs-lookup"><span data-stu-id="6aa4c-132">Lists all local tools available in the current directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="6aa4c-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="6aa4c-133">See also</span></span>

- [<span data-ttu-id="6aa4c-134">.NET Core 工具</span><span class="sxs-lookup"><span data-stu-id="6aa4c-134">.NET Core tools</span></span>](global-tools.md)
- [<span data-ttu-id="6aa4c-135">教程：使用 .NET Core CLI 安装和使用 .NET Core 全局工具</span><span class="sxs-lookup"><span data-stu-id="6aa4c-135">Tutorial: Install and use a .NET Core global tool using the .NET Core CLI</span></span>](global-tools-how-to-use.md)
- [<span data-ttu-id="6aa4c-136">教程：使用 .NET Core CLI 安装和使用 .NET Core 本地工具</span><span class="sxs-lookup"><span data-stu-id="6aa4c-136">Tutorial: Install and use a .NET Core local tool using the .NET Core CLI</span></span>](local-tools-how-to-use.md)
