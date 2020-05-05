---
title: 使用 C# 对 JSON 进行序列化和反序列化 - .NET
ms.date: 01/10/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 660a2831aa6a807486fc47eae880bcd11347c547
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159541"
---
# <a name="json-serialization-and-deserialization-marshalling-and-unmarshalling-in-net---overview"></a>.NET 中的 JSON 序列化和反序列化（封送和拆收）- 概述

`System.Text.Json` 命名空间提供用于序列化和反序列化 JavaScript 对象表示法 (JSON) 的功能。

库的设计强调对广泛的功能集实现高性能和低内存分配。 内置的 UTF-8 支持可优化读写以 UTF-8 编码的 JSON 文本的过程，UTF-8 编码是针对 Web 上的数据和磁盘上的文件的最普遍的编码方式。

库还提供了用于处理内存中文档对象模型 (DOM) 的类。 此功能允许对 JSON 文件或字符串中的元素进行随机只读访问。

## <a name="how-to-get-the-library"></a>如何获取库

* 该库是作为 [.NET Core 3.0](https://aka.ms/netcore3download) 共享框架的一部分内置的。
* 对于其他目标框架，请安装 [System.Text.Json](https://www.nuget.org/packages/System.Text.Json) NuGet 包。 包支持以下框架：
  * .NET Standard 2.0 及更高版本
  * .NET Framework 4.7.2 及更高版本
  * .NET Core 2.0、2.1 和 2.2

## <a name="additional-resources"></a>其他资源

* [如何使用库](system-text-json-how-to.md)
* [如何从 Newtonsoft.Json 迁移](system-text-json-migrate-from-newtonsoft-how-to.md)
* [如何编写转换器](system-text-json-converters-how-to.md)
* [System.Text.Json 源代码](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json)
* [System.Text.Json API 参考](xref:System.Text.Json)
* [System.Text.Json.Serialization API 参考](xref:System.Text.Json.Serialization)
<!-- * [Roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
