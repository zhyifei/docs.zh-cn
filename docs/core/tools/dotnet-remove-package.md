---
title: dotnet remove package 命令 - .NET Core CLI
description: dotnet remove package 命令可便于删除对项目的 NuGet 包引用。
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: ed6086bfdfadaa06494c857fc74687f1273af971
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2018
ms.locfileid: "34696853"
---
# <a name="dotnet-remove-package"></a><span data-ttu-id="dc4f9-103">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="dc4f9-103">dotnet remove package</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="dc4f9-104">name</span><span class="sxs-lookup"><span data-stu-id="dc4f9-104">Name</span></span>

<span data-ttu-id="dc4f9-105">`dotnet remove package` - 从项目文件删除包引用。</span><span class="sxs-lookup"><span data-stu-id="dc4f9-105">`dotnet remove package` - Removes package reference from a project file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="dc4f9-106">摘要</span><span class="sxs-lookup"><span data-stu-id="dc4f9-106">Synopsis</span></span>

`dotnet remove [<PROJECT>] package <PACKAGE_NAME> [-h|--help]`

## <a name="description"></a><span data-ttu-id="dc4f9-107">描述</span><span class="sxs-lookup"><span data-stu-id="dc4f9-107">Description</span></span>

<span data-ttu-id="dc4f9-108">使用 `dotnet remove package` 命令可方便地从项目删除 NuGet 包引用。</span><span class="sxs-lookup"><span data-stu-id="dc4f9-108">The `dotnet remove package` command provides a convenient option to remove a NuGet package reference from a project.</span></span>

## <a name="arguments"></a><span data-ttu-id="dc4f9-109">自变量</span><span class="sxs-lookup"><span data-stu-id="dc4f9-109">Arguments</span></span>

`PROJECT`

<span data-ttu-id="dc4f9-110">指定项目文件。</span><span class="sxs-lookup"><span data-stu-id="dc4f9-110">Specifies the project file.</span></span> <span data-ttu-id="dc4f9-111">如果未指定，此命令会搜索当前目录来获取一个项目文件。</span><span class="sxs-lookup"><span data-stu-id="dc4f9-111">If not specified, the command searches the current directory for one.</span></span>

`PACKAGE_NAME`

<span data-ttu-id="dc4f9-112">要删除的包引用。</span><span class="sxs-lookup"><span data-stu-id="dc4f9-112">The package reference to remove.</span></span>

## <a name="options"></a><span data-ttu-id="dc4f9-113">选项</span><span class="sxs-lookup"><span data-stu-id="dc4f9-113">Options</span></span>

`-h|--help`

<span data-ttu-id="dc4f9-114">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="dc4f9-114">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="dc4f9-115">示例</span><span class="sxs-lookup"><span data-stu-id="dc4f9-115">Examples</span></span>

<span data-ttu-id="dc4f9-116">从当前目录中的项目删除 `Newtonsoft.Json` NuGet 包：</span><span class="sxs-lookup"><span data-stu-id="dc4f9-116">Removes `Newtonsoft.Json` NuGet package from a project in the current directory:</span></span>

`dotnet remove package Newtonsoft.Json`