---
title: dotnet tool list 命令 - .NET Core CLI
description: dotnet tool list 命令从计算机中列出指定的 .NET Core 全局工具。
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: e2bea974207d3098ed67b69ed16a72a03c44cd8b
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2018
ms.locfileid: "43467051"
---
# <a name="dotnet-tool-list"></a><span data-ttu-id="52684-103">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="52684-103">dotnet tool list</span></span>

[!INCLUDE [topic-appliesto-net-core-21plus.md](../../../includes/topic-appliesto-net-core-21plus.md)]

## <a name="name"></a><span data-ttu-id="52684-104">name</span><span class="sxs-lookup"><span data-stu-id="52684-104">Name</span></span>

<span data-ttu-id="52684-105">`dotnet tool list` - 列出当前安装在计算机上的默认目录中或指定路径中的所有 [.NET Core 全局工具](global-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="52684-105">`dotnet tool list` - Lists all [.NET Core Global Tools](global-tools.md) currently installed in the default directory on your machine or in the specified path.</span></span>

## <a name="synopsis"></a><span data-ttu-id="52684-106">摘要</span><span class="sxs-lookup"><span data-stu-id="52684-106">Synopsis</span></span>

```console
dotnet tool list <-g|--global>
dotnet tool list <--tool-path>
dotnet tool list <-h|--help>
```

## <a name="description"></a><span data-ttu-id="52684-107">描述</span><span class="sxs-lookup"><span data-stu-id="52684-107">Description</span></span>

<span data-ttu-id="52684-108">`dotnet tool list` 命令让你可以列出计算机上（当前用户配置文件）或特定路径中安装的所有用户范围的 .NET Core 全局工具。</span><span class="sxs-lookup"><span data-stu-id="52684-108">The `dotnet tool list` command provides a way for you to list all .NET Core Global Tools installed user-wide on your machine (current user profile) or in the specified path.</span></span> <span data-ttu-id="52684-109">此命令列出包名称、安装的版本以及全局工具命令。</span><span class="sxs-lookup"><span data-stu-id="52684-109">The command lists the package name, version installed, and the Global Tool command.</span></span> <span data-ttu-id="52684-110">若要使用此 list 命令，需要使用 `--global` 选项指定要查看所有用户范围的工具或者使用 `--tool-path` 选项指定自定义路径。</span><span class="sxs-lookup"><span data-stu-id="52684-110">To use the list command, you either have to specify that you want to see all user-wide tools using the `--global` option or specify a custom path using the `--tool-path` option.</span></span>

## <a name="options"></a><span data-ttu-id="52684-111">选项</span><span class="sxs-lookup"><span data-stu-id="52684-111">Options</span></span>

`-g|--global`

<span data-ttu-id="52684-112">列出用户范围的全局工具。</span><span class="sxs-lookup"><span data-stu-id="52684-112">Lists user-wide Global Tools.</span></span> <span data-ttu-id="52684-113">不能与 `--tool-path` 选项一起使用。</span><span class="sxs-lookup"><span data-stu-id="52684-113">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="52684-114">如果不指定此选项，则必须指定 `--tool-path` 选项。</span><span class="sxs-lookup"><span data-stu-id="52684-114">If you don't specify this option, you must specify the `--tool-path` option.</span></span>

`-h|--help`

<span data-ttu-id="52684-115">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="52684-115">Prints out a short help for the command.</span></span>

`--tool-path <PATH>`

<span data-ttu-id="52684-116">指定用于查找全局工具的自定义位置。</span><span class="sxs-lookup"><span data-stu-id="52684-116">Specifies a custom location where to find Global Tools.</span></span> <span data-ttu-id="52684-117">路径可以是绝对的，也可以是相对的。</span><span class="sxs-lookup"><span data-stu-id="52684-117">PATH can be absolute or relative.</span></span> <span data-ttu-id="52684-118">不能与 `--global` 选项一起使用。</span><span class="sxs-lookup"><span data-stu-id="52684-118">Can't be combined with the `--global` option.</span></span> <span data-ttu-id="52684-119">如果不指定此选项，则必须指定 `--global` 选项。</span><span class="sxs-lookup"><span data-stu-id="52684-119">If you don't specify this option, you must specify the `--global` option.</span></span>

## <a name="examples"></a><span data-ttu-id="52684-120">示例</span><span class="sxs-lookup"><span data-stu-id="52684-120">Examples</span></span>

<span data-ttu-id="52684-121">列出计算机上安装的所有用户范围的全局工具（当前用户配置文件）：</span><span class="sxs-lookup"><span data-stu-id="52684-121">Lists all Global Tools installed user-wide on your machine (current user profile):</span></span>

`dotnet tool list -g`

<span data-ttu-id="52684-122">列出特定 Windows 文件夹中的全局工具：</span><span class="sxs-lookup"><span data-stu-id="52684-122">Lists the Global Tools from a specific Windows folder:</span></span>

`dotnet tool list --tool-path c:\global-tools`

<span data-ttu-id="52684-123">列出特定 Linux/macOS 文件夹中的全局工具：</span><span class="sxs-lookup"><span data-stu-id="52684-123">Lists the Global Tools from a specific Linux/macOS folder:</span></span>

`dotnet tool list --tool-path ~/bin`

## <a name="see-also"></a><span data-ttu-id="52684-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="52684-124">See also</span></span>

* [<span data-ttu-id="52684-125">.NET Core 全局工具</span><span class="sxs-lookup"><span data-stu-id="52684-125">.NET Core Global Tools</span></span>](global-tools.md)