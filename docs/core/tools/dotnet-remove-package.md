---
title: "dotnet remove package 命令 - .NET Core CLI"
description: "dotnet remove package 命令可便于删除对项目的 NuGet 包引用。"
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.workload: dotnetcore
ms.openlocfilehash: 1bc8d9cdc4db1f103b73116b43e630185a2c35de
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="dotnet-remove-package"></a><span data-ttu-id="b39e3-103">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="b39e3-103">dotnet remove package</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="b39e3-104">name</span><span class="sxs-lookup"><span data-stu-id="b39e3-104">Name</span></span>

<span data-ttu-id="b39e3-105">`dotnet remove package` - 从项目文件删除包引用。</span><span class="sxs-lookup"><span data-stu-id="b39e3-105">`dotnet remove package` - Removes package reference from a project file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="b39e3-106">摘要</span><span class="sxs-lookup"><span data-stu-id="b39e3-106">Synopsis</span></span>

`dotnet remove [<PROJECT>] package <PACKAGE_NAME> [-h|--help]`

## <a name="description"></a><span data-ttu-id="b39e3-107">描述</span><span class="sxs-lookup"><span data-stu-id="b39e3-107">Description</span></span>

<span data-ttu-id="b39e3-108">使用 `dotnet remove package` 命令可方便地从项目删除 NuGet 包引用。</span><span class="sxs-lookup"><span data-stu-id="b39e3-108">The `dotnet remove package` command provides a convenient option to remove a NuGet package reference from a project.</span></span>

## <a name="arguments"></a><span data-ttu-id="b39e3-109">自变量</span><span class="sxs-lookup"><span data-stu-id="b39e3-109">Arguments</span></span>

`PROJECT`

<span data-ttu-id="b39e3-110">指定项目文件。</span><span class="sxs-lookup"><span data-stu-id="b39e3-110">Specifies the project file.</span></span> <span data-ttu-id="b39e3-111">如果未指定，此命令会搜索当前目录，以获取解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="b39e3-111">If not specified, the command will search the current directory for one.</span></span>

`PACKAGE_NAME`

<span data-ttu-id="b39e3-112">要删除的包引用。</span><span class="sxs-lookup"><span data-stu-id="b39e3-112">The package reference to remove.</span></span>

## <a name="options"></a><span data-ttu-id="b39e3-113">选项</span><span class="sxs-lookup"><span data-stu-id="b39e3-113">Options</span></span>

`-h|--help`

<span data-ttu-id="b39e3-114">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="b39e3-114">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="b39e3-115">示例</span><span class="sxs-lookup"><span data-stu-id="b39e3-115">Examples</span></span>

<span data-ttu-id="b39e3-116">从当前目录中的项目删除 `Newtonsoft.Json` NuGet 包：</span><span class="sxs-lookup"><span data-stu-id="b39e3-116">Removes `Newtonsoft.Json` NuGet package from a project in the current directory:</span></span>

`dotnet remove package Newtonsoft.Json`
