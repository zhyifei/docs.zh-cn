---
title: dotnet remove package 命令
description: dotnet remove package 命令可便于删除对项目的 NuGet 包引用。
ms.date: 05/29/2018
ms.openlocfilehash: 4cc8ac927b761547dc5e53be9abeba827bf1e1d9
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53168723"
---
# <a name="dotnet-remove-package"></a><span data-ttu-id="bf637-103">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="bf637-103">dotnet remove package</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="bf637-104">name</span><span class="sxs-lookup"><span data-stu-id="bf637-104">Name</span></span>

<span data-ttu-id="bf637-105">`dotnet remove package` - 从项目文件删除包引用。</span><span class="sxs-lookup"><span data-stu-id="bf637-105">`dotnet remove package` - Removes package reference from a project file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="bf637-106">摘要</span><span class="sxs-lookup"><span data-stu-id="bf637-106">Synopsis</span></span>

`dotnet remove [<PROJECT>] package <PACKAGE_NAME> [-h|--help]`

## <a name="description"></a><span data-ttu-id="bf637-107">说明</span><span class="sxs-lookup"><span data-stu-id="bf637-107">Description</span></span>

<span data-ttu-id="bf637-108">使用 `dotnet remove package` 命令可方便地从项目删除 NuGet 包引用。</span><span class="sxs-lookup"><span data-stu-id="bf637-108">The `dotnet remove package` command provides a convenient option to remove a NuGet package reference from a project.</span></span>

## <a name="arguments"></a><span data-ttu-id="bf637-109">自变量</span><span class="sxs-lookup"><span data-stu-id="bf637-109">Arguments</span></span>

`PROJECT`

<span data-ttu-id="bf637-110">指定项目文件。</span><span class="sxs-lookup"><span data-stu-id="bf637-110">Specifies the project file.</span></span> <span data-ttu-id="bf637-111">如果未指定，此命令会搜索当前目录来获取一个项目文件。</span><span class="sxs-lookup"><span data-stu-id="bf637-111">If not specified, the command searches the current directory for one.</span></span>

`PACKAGE_NAME`

<span data-ttu-id="bf637-112">要删除的包引用。</span><span class="sxs-lookup"><span data-stu-id="bf637-112">The package reference to remove.</span></span>

## <a name="options"></a><span data-ttu-id="bf637-113">选项</span><span class="sxs-lookup"><span data-stu-id="bf637-113">Options</span></span>

`-h|--help`

<span data-ttu-id="bf637-114">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="bf637-114">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="bf637-115">示例</span><span class="sxs-lookup"><span data-stu-id="bf637-115">Examples</span></span>

<span data-ttu-id="bf637-116">从当前目录中的项目删除 `Newtonsoft.Json` NuGet 包：</span><span class="sxs-lookup"><span data-stu-id="bf637-116">Removes `Newtonsoft.Json` NuGet package from a project in the current directory:</span></span>

`dotnet remove package Newtonsoft.Json`