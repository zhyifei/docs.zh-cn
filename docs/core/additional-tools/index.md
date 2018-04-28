---
title: 其他 .NET Core 工具
description: 可支持和扩展 .NET Core 功能的其他工具的概述。
author: mlacouture
manager: wpickett
ms.author: johalex
ms.date: 01/19/2018
ms.topic: conceptual
ms.prod: dotnet-core
ms.custom: mvc
ms.workload:
- dotnetcore
ms.openlocfilehash: 2e33cdbcbe9c81e6c3af84f8f2795ee3dc6e28ae
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2018
---
# <a name="net-core-additional-tools"></a>其他 .NET Core 工具

本节除了 [.NET Core 命令行接口 (CLI)](..\tools\index.md) 工具外，还编译了可支持和扩展 .NET Core 功能的工具列表。

## <a name="wcf-web-service-reference-toolwcf-web-service-reference-guidemd"></a>[WCF Web 服务引用工具](wcf-web-service-reference-guide.md)

WCF Web 服务引用是一个 Visual Studio 连接服务提供程序，首次推出是在 [Visual Studio 2017 版本 15.5](https://www.visualstudio.com/news/releasenotes/vs2017-relnotes#WCFTools) 中。 此工具可从网络位置的当前解决方案的 web 服务中或从 WSDL 文件中检索元数据，并生成包含可用于访问 web 服务的 Windows Communication Foundation (WCF) 客户端代理代码的可兼容 .NET Core 的源文件。

## <a name="xml-serializer-generatorxml-serializer-generatormd"></a>[XML 序列化程序生成器](xml-serializer-generator.md)

正如 [Xml Serializer Generator (sgen.exe)](../../standard/serialization/xml-serializer-generator-tool-sgen-exe.md) 适用于 .NET Framework，[Microsoft.XmlSerializer.Generator NuGet 包](https://www.nuget.org/packages/Microsoft.XmlSerializer.Generator) 是适用于 .NET Core 和 .NET 标准库的解决方案。 它为程序集中包含的类型创建 XML 序列化程序集，从而提高使用 <xref:System.Xml.Serialization.XmlSerializer> 序列化或反序列化这些类型对象时，XML 序列化的启动性能。