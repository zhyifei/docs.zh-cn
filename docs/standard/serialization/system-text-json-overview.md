---
title: 使用C# -.NET 对 JSON 进行序列化和反序列化
ms.date: 01/10/2020
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: c05783963ba521109fb542f247ec9e62fdb5c2d9
ms.sourcegitcommit: dfad244ba549702b649bfef3bb057e33f24a8fb2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2020
ms.locfileid: "75904647"
---
# <a name="json-serialization-and-deserialization-marshalling-and-unmarshalling-in-net---overview"></a>.NET 中的 JSON 序列化和反序列化（封送和 unmarshalling）-概述

`System.Text.Json` 命名空间提供用于序列化和反序列化 JavaScript 对象表示法（JSON）的功能。

库设计通过广泛的功能集强调高性能和低内存分配。 内置 UTF-8 支持优化了编码为 UTF-8 的 JSON 文本的处理过程，这是针对 web 上的数据和磁盘上的文件的最流行的编码。

该库还提供了用于处理内存中文档对象模型（DOM）的类。 此功能允许对 JSON 文件或字符串中的元素进行随机只读访问。 

## <a name="how-to-get-the-library"></a>如何获取库

* 该库作为[.Net Core 3.0](https://aka.ms/netcore3download)共享框架的一部分内置。
* 对于其他目标框架，请安装[System.object](https://www.nuget.org/packages/System.Text.Json) NuGet 包。 包支持：
  * .NET Standard 2.0 及更高版本
  * .NET Framework 4.7.2 和更高版本
  * .NET Core 2.0、2.1 和2.2

## <a name="additional-resources"></a>其他资源

* [如何使用库](system-text-json-how-to.md)
* [如何从 Newtonsoft.json 迁移](system-text-json-migrate-from-newtonsoft-how-to.md)
* [如何编写转换器](system-text-json-converters-how-to.md)
* [System.web 源文件](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json)
* [System.web API 参考](xref:System.Text.Json)
* [System.web. 串行化 API 参考](xref:System.Text.Json.Serialization)
<!-- * [Roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
