---
title: "dotnet-remove package 命令 - .NET Core CLI"
description: "使用 dotnet-remove package 命令可方便地删除对项目的 NuGet 包引用。"
keywords: "dotnet-remove, CLI, CLI 命令, .NET Core"
author: spboyer
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 2fcc8d37-16b3-4581-8038-832160e72d36
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a3fef846d5850e2c2a158ccd1f30a84e8f23f793
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---

# <a name="dotnet-remove-package"></a><span data-ttu-id="22cca-104">dotnet-remove package</span><span class="sxs-lookup"><span data-stu-id="22cca-104">dotnet-remove package</span></span>

## <a name="name"></a><span data-ttu-id="22cca-105">名称</span><span class="sxs-lookup"><span data-stu-id="22cca-105">Name</span></span>

<span data-ttu-id="22cca-106">`dotnet-remove package` - 从项目文件删除包引用。</span><span class="sxs-lookup"><span data-stu-id="22cca-106">`dotnet-remove package` - Removes package reference from a project file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="22cca-107">摘要</span><span class="sxs-lookup"><span data-stu-id="22cca-107">Synopsis</span></span>

`dotnet remove [<PROJECT>] package <PACKAGE_NAME> [-h|--help]`

## <a name="description"></a><span data-ttu-id="22cca-108">描述</span><span class="sxs-lookup"><span data-stu-id="22cca-108">Description</span></span>

<span data-ttu-id="22cca-109">使用 `dotnet remove package` 命令可方便地从项目删除 NuGet 包引用。</span><span class="sxs-lookup"><span data-stu-id="22cca-109">The `dotnet remove package` command provides a convenient option to remove a NuGet package reference from a project.</span></span>

## <a name="arguments"></a><span data-ttu-id="22cca-110">参数</span><span class="sxs-lookup"><span data-stu-id="22cca-110">Arguments</span></span>

`PROJECT`

<span data-ttu-id="22cca-111">指定项目文件。</span><span class="sxs-lookup"><span data-stu-id="22cca-111">Specifies the project file.</span></span> <span data-ttu-id="22cca-112">如果未指定，此命令会搜索当前目录，以获取解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="22cca-112">If not specified, the command will search the current directory for one.</span></span>

`PACKAGE_NAME`

<span data-ttu-id="22cca-113">要删除的包引用。</span><span class="sxs-lookup"><span data-stu-id="22cca-113">The package reference to remove.</span></span>

## <a name="options"></a><span data-ttu-id="22cca-114">选项</span><span class="sxs-lookup"><span data-stu-id="22cca-114">Options</span></span>

`-h|--help`

<span data-ttu-id="22cca-115">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="22cca-115">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="22cca-116">示例</span><span class="sxs-lookup"><span data-stu-id="22cca-116">Examples</span></span>

<span data-ttu-id="22cca-117">从当前目录中的项目删除 `Newtonsoft.Json` NuGet 包：</span><span class="sxs-lookup"><span data-stu-id="22cca-117">Removes `Newtonsoft.Json` NuGet package from a project in the current directory:</span></span>

`dotnet remove package Newtonsoft.Json`

