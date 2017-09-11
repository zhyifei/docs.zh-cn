---
title: "dotnet-list reference 命令- .NET Core CLI"
description: "使用 dotnet-list reference 命令可方便地列出项目到项目的引用。"
keywords: "dotnet-list, CLI, CLI 命令, .NET Core"
author: spboyer
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 8f954a0c-03f8-4fbc-a529-b313ab12c623
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 701345e4db51d26b9eefe8f02b6c0526934de5c9
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---

# <a name="dotnet-list-reference"></a><span data-ttu-id="14083-104">dotnet-list reference</span><span class="sxs-lookup"><span data-stu-id="14083-104">dotnet-list reference</span></span>

## <a name="name"></a><span data-ttu-id="14083-105">名称</span><span class="sxs-lookup"><span data-stu-id="14083-105">Name</span></span>

<span data-ttu-id="14083-106">`dotnet-list reference` - 列出项目到项目引用。</span><span class="sxs-lookup"><span data-stu-id="14083-106">`dotnet-list reference` - Lists project to project references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="14083-107">摘要</span><span class="sxs-lookup"><span data-stu-id="14083-107">Synopsis</span></span>

`dotnet list [<PROJECT>] reference [-h|--help]`

## <a name="description"></a><span data-ttu-id="14083-108">说明</span><span class="sxs-lookup"><span data-stu-id="14083-108">Description</span></span>

<span data-ttu-id="14083-109">使用 `dotnet list reference` 命令可方便地列出给定项目的项目引用。</span><span class="sxs-lookup"><span data-stu-id="14083-109">The `dotnet list reference` command provides a convenient option to list project references for a given project.</span></span>

## <a name="arguments"></a><span data-ttu-id="14083-110">参数</span><span class="sxs-lookup"><span data-stu-id="14083-110">Arguments</span></span>

`PROJECT`

<span data-ttu-id="14083-111">指定用于列出引用的项目文件。</span><span class="sxs-lookup"><span data-stu-id="14083-111">Specifies the project file to use for listing references.</span></span> <span data-ttu-id="14083-112">如果未指定，此命令会搜索当前目录，以获取项目文件。</span><span class="sxs-lookup"><span data-stu-id="14083-112">If not specified, the command will search the current directory for a project file.</span></span>

## <a name="options"></a><span data-ttu-id="14083-113">选项</span><span class="sxs-lookup"><span data-stu-id="14083-113">Options</span></span>

`-h|--help`

<span data-ttu-id="14083-114">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="14083-114">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="14083-115">示例</span><span class="sxs-lookup"><span data-stu-id="14083-115">Examples</span></span>

<span data-ttu-id="14083-116">列出指定项目的项目引用：</span><span class="sxs-lookup"><span data-stu-id="14083-116">List the project references for the specified project:</span></span>

`dotnet list app/app.csproj reference`

<span data-ttu-id="14083-117">列出当前目录中的项目的项目引用：</span><span class="sxs-lookup"><span data-stu-id="14083-117">List the project references for the project in the current directory:</span></span>

`dotnet list reference`

