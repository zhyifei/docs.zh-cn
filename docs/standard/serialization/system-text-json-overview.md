---
title: 使用C# -.NET 对 JSON 进行序列化和反序列化
author: tdykstra
ms.author: tdykstra
ms.date: 09/16/2019
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.assetid: 4d1111c0-9447-4231-a997-96a2b74b3453
ms.openlocfilehash: 5ce98a7908470a402779436db43333d46f5101fc
ms.sourcegitcommit: dfd612ba454ce775a766bcc6fe93bc1d43dfda47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2019
ms.locfileid: "72180155"
---
# <a name="json-serialization-in-net---overview"></a>.NET 中的 JSON 序列化-概述

@No__t 的命名空间提供了用于序列化和反序列化 JavaScript 对象表示法（JSON）的功能。

库设计通过广泛的功能集强调高性能和低内存分配。 内置 UTF-8 支持优化了编码为 UTF-8 的 JSON 文本的处理过程，这是针对 web 上的数据和磁盘上的文件的最流行的编码。

该库还提供了用于处理内存中文档对象模型（DOM）的类。 此功能允许对 JSON 文件或字符串中的元素进行随机只读访问。 

## <a name="how-to-get-the-library"></a>如何获取库

* 该库作为[.Net Core 3.0](https://aka.ms/netcore3download)共享框架的一部分内置。
* 对于其他目标框架，请安装[System.object](https://www.nuget.org/packages/System.Text.Json) NuGet 包。 包支持：
  * .NET Standard 2.0 及更高版本
  * .NET Framework 4.6.1 和更高版本
  * .NET Core 2.0、2.1 和2。2

## <a name="additional-resources"></a>其他资源

* [如何使用库](system-text-json-how-to.md)
* [源代码](https://github.com/dotnet/corefx/tree/master/src/System.Text.Json)
* [API 参考](xref:System.Text.Json)
* [路线图](https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/roadmap/README.md)
* Dotnet/corefx 存储库中的 GitHub 问题
  * [有关系统开发的讨论](https://github.com/dotnet/corefx/issues/33115)
  * [所有系统问题](https://github.com/dotnet/corefx/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json)
  * [标记为 json 功能的 system.web 问题-doc](https://github.com/dotnet/corefx/labels/json-functionality-doc)
