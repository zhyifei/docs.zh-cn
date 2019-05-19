---
title: 用于移植到 .NET Core 的工具
description: 了解可以用于移植到 .NET Core 的一些工具
author: cartermp
ms.author: mairaw
ms.date: 12/07/2018
ms.openlocfilehash: d0b74b5708f31922b72fa0e236c8bbe69ae06217
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "65632253"
---
# <a name="tools-to-help-with-porting-to-net-core"></a>用于帮助移植到 .NET Core 的工具

你可能会发现本文中列出的工具在移植时非常有用：

* [.NET 可移植性分析器](../../standard/analyzers/portability-analyzer.md)，可以生成报告的工具链，该报告说明代码在 .NET Framework 和 .NET Core 之间的可移植性：作为[命令行工具](https://github.com/Microsoft/dotnet-apiport/releases)作为 [Visual Studio 扩展](https://visualstudiogallery.msdn.microsoft.com/1177943e-cfb7-4822-a8a6-e56c7905292b)
* [.NET API 分析器](../../standard/analyzers/api-analyzer.md) - 一个 Roslyn 分析器，可用于发现不同平台上的潜在 C# API 兼容性风险，并检测是否调用了弃用的 API。

此外，可以尝试使用 [CsprojToVs2017](https://github.com/hvanbakel/CsprojToVs2017) 工具将较小的解决方案或单个项目移植到 .NET Core 项目文件格式。

> [!WARNING] 
> CsprojToVs2017 是第三方工具。 不能保证它适用于所有项目，而且它可能会导致所依赖的行为发生细微变化。 CsprojToVs2017 应作为一个起点，以自动化可自动执行的基本操作。 它不是迁移项目文件格式的有保证的解决方案。
