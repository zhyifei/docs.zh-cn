---
title: 用于移植到 .NET Core 的工具
description: 了解可以用于移植到 .NET Core 的一些工具
author: cartermp
ms.date: 12/07/2018
ms.openlocfilehash: 98b3a29f2287414b2cd323f1cbf2225905592b26
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "78157513"
---
# <a name="tools-to-help-with-porting-to-net-core"></a><span data-ttu-id="15fef-103">用于帮助移植到 .NET Core 的工具</span><span class="sxs-lookup"><span data-stu-id="15fef-103">Tools to help with porting to .NET Core</span></span>

<span data-ttu-id="15fef-104">你可能会发现本文中列出的工具在移植时非常有用：</span><span class="sxs-lookup"><span data-stu-id="15fef-104">You may find the tools listed in this article helpful when porting:</span></span>

- <span data-ttu-id="15fef-105">[.NET 可移植性分析器](../../standard/analyzers/portability-analyzer.md) - 可以生成报告的工具链，该报告说明代码在 .NET Framework 和 .NET Core 之间的可移植性：</span><span class="sxs-lookup"><span data-stu-id="15fef-105">[.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) - A toolchain that can generate a report of how portable your code is between .NET Framework and .NET Core:</span></span>
  - <span data-ttu-id="15fef-106">作为[命令行工具](https://github.com/Microsoft/dotnet-apiport/releases)</span><span class="sxs-lookup"><span data-stu-id="15fef-106">As a [command-line tool](https://github.com/Microsoft/dotnet-apiport/releases)</span></span>
  - <span data-ttu-id="15fef-107">作为 [Visual Studio 扩展](https://visualstudiogallery.msdn.microsoft.com/1177943e-cfb7-4822-a8a6-e56c7905292b)</span><span class="sxs-lookup"><span data-stu-id="15fef-107">As a [Visual Studio extension](https://visualstudiogallery.msdn.microsoft.com/1177943e-cfb7-4822-a8a6-e56c7905292b)</span></span>
- <span data-ttu-id="15fef-108">[.NET API 分析器](../../standard/analyzers/api-analyzer.md) - 一个 Roslyn 分析器，可用于发现不同平台上的潜在 C# API 兼容性风险，并检测是否调用了弃用的 API。</span><span class="sxs-lookup"><span data-stu-id="15fef-108">[.NET API analyzer](../../standard/analyzers/api-analyzer.md) - A Roslyn analyzer that discovers potential compatibility risks for C# APIs on different platforms and detects calls to deprecated APIs.</span></span>

<span data-ttu-id="15fef-109">此外，可以尝试使用 [CsprojToVs2017](https://github.com/hvanbakel/CsprojToVs2017) 工具将较小的解决方案或单个项目移植到 .NET Core 项目文件格式。</span><span class="sxs-lookup"><span data-stu-id="15fef-109">Additionally, you can attempt to port smaller solutions or individual projects to the .NET Core project file format with the [CsprojToVs2017](https://github.com/hvanbakel/CsprojToVs2017) tool.</span></span>

> [!WARNING]
> <span data-ttu-id="15fef-110">CsprojToVs2017 是第三方工具。</span><span class="sxs-lookup"><span data-stu-id="15fef-110">CsprojToVs2017 is a third-party tool.</span></span> <span data-ttu-id="15fef-111">不能保证它适用于所有项目，而且它可能会导致所依赖的行为发生细微变化。</span><span class="sxs-lookup"><span data-stu-id="15fef-111">There is no guarantee that it will work for all of your projects, and it may cause subtle changes in behavior that you depend on.</span></span> <span data-ttu-id="15fef-112">CsprojToVs2017 应作为一个起点  ，以自动化可自动执行的基本操作。</span><span class="sxs-lookup"><span data-stu-id="15fef-112">CsprojToVs2017 should be used as a _starting point_ that automates the basic things that can be automated.</span></span> <span data-ttu-id="15fef-113">它不是迁移项目文件格式的有保证的解决方案。</span><span class="sxs-lookup"><span data-stu-id="15fef-113">It is not a guaranteed solution to migrating project file formats.</span></span>
