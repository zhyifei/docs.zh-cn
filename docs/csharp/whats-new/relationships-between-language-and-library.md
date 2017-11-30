---
title: "语言功能和库类型之间的关系 |Microsoft 文档"
description: "语言功能通常依赖于实现的库类型。 了解该关系。"
keywords: "C# 语言设计中，标准库"
author: billwagner
ms.author: wiwagn
ms.date: 07/20/2017
ms.topic: article
ms.prod: .net
ms.devlang: devlang-csharp
ms.openlocfilehash: 93fd26a72743fcf45df3904cb8d0c787d8a228a8
ms.sourcegitcommit: bbde43da655ae7bea1977f7af7345eb87bd7fd5f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/21/2017
---
# <a name="relationships-between-language-features-and-library-types"></a>语言功能和库类型之间的关系

C# 语言定义需要能够在这些类型上的某些类型和某些可访问的成员的标准库。 编译器将生成用于许多不同的语言功能的这些必需的类型和成员的代码。 如有必要，有包含所需的较新版本的语言，在编写代码，这些类型或成员具有尚未部署的环境时的类型的 NuGet 包。

此依赖于标准库功能已被自其第一个版本以来 C# 语言的一部分。 在该版本中，包括示例：

* <xref:System.Exception>-用于编译器生成的所有异常。
* <xref:System.String>-C#`string`类型是同义词<xref:System.String>。
* <xref:System.Int32>-的同义词`int`。

该第一个版本很简单： 编译器和标准库提供的在一起，且每个只有一个版本。

后续版本的 C# 具有偶尔添加新类型或成员的依赖关系。 示例包括： <xref:System.Runtime.CompilerServices.INotifyCompletion>，<xref:System.Runtime.CompilerServices.CallerFilePathAttribute>和<xref:System.Runtime.CompilerServices.CallerMemberNameAttribute>。 通过上添加依赖关系的 C# 7.0 继续这<xref:System.ValueTuple>实现[元组](../tuples.md)语言功能。

语言设计团队将采取措施以最小化的类型和成员在符合标准库中所需的外围应用。 该目标是针对其中新的库功能并入无缝语言的干净设计平衡。 将需要新类型的将来版本的 C# 中的新增功能和标准库中的成员。 请务必了解如何管理你的工作中的这些依赖关系。

## <a name="managing-your-dependencies"></a>管理依赖项

从支持的平台上的.NET 库的发行周期将 C# 编译器工具现在会分离。 实际上，不同的.NET 库有不同的发布周期： 在 Windows 上的.NET Framework 是 relesed 与 Windows 更新，在单独的计划，以及 Xamarin 版本的库更新附带了适用于每个目标平台的 Xamarin 工具附带的.NET 核心。

大多数时间，你不会注意到这些更改。 但是，当你正在使用的语言不需要功能尚未.NET 库中的较新版本在该平台上，你将引用 NuGet 程序包，以提供这些新类型。
作为新的 framework 安装更新，你的应用程序支持的平台，你可以删除额外的引用。

这种分离意味着你可以使用新语言功能，即使你将可能没有相应的 framework 的计算机。
