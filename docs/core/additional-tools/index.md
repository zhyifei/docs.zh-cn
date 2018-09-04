---
title: 其他 .NET Core 工具
description: 可支持和扩展 .NET Core 功能的其他工具的概述。
author: mlacouture
ms.author: johalex
ms.date: 01/19/2018
ms.custom: mvc
ms.openlocfilehash: ba63ef6cdc092d06e267637112070e7cd5133a45
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43511749"
---
# <a name="net-core-additional-tools"></a>其他 .NET Core 工具

本节除了 [.NET Core 命令行接口 (CLI)](..\tools\index.md) 工具外，还编译了可支持和扩展 .NET Core 功能的工具列表。

## <a name="wcf-web-service-reference-toolwcf-web-service-reference-guidemd"></a>[WCF Web 服务引用工具](wcf-web-service-reference-guide.md)

WCF (Windows Communication Foundation) Web 服务引用是一个 Visual Studio 连接服务提供程序，首次推出是在 [Visual Studio 2017 版本 15.5](https://visualstudio.microsoft.com/news/releasenotes/vs2017-relnotes#WCFTools) 中。 此工具可从网络位置上的当前解决方案中的 Web 服务中或从 WSDL 文件中检索元数据，并生成与 .NET Core 兼容的源文件，此文件通过可用于访问 Web 服务操作的方法定义了 WCF 代理类。

## <a name="wcf-dotnet-svcutil-tooldotnet-svcutil-guidemd"></a>[WCF dotnet-svcutil 工具](dotnet-svcutil-guide.md)

WCF (Windows Communication Foundation) dotnet-svcutil 工具是一种 .NET Core CLI 工具，此工具从网络位置上的 Web 服务中或从 WSDL 文件中检索元数据，并生成与 .NET Core 兼容的源文件，此文件通过可用于访问 Web 服务操作的方法定义了 WCF 代理类。 dotnet-svcutil 工具是 [WCF Web 服务引用](wcf-web-service-reference-guide.md) Visual Studio 连接服务提供程序（随 Visual Studio 2017 v15.5 首次推出）的替代选项。 dotnet-svcutil 工具作为一种 .NET Core CLI 工具，可跨平台地用于 Linux、macOS 和 Windows。

## <a name="xml-serializer-generatorxml-serializer-generatormd"></a>[XML 序列化程序生成器](xml-serializer-generator.md)

正如 [Xml Serializer Generator (sgen.exe)](../../standard/serialization/xml-serializer-generator-tool-sgen-exe.md) 适用于 .NET Framework，[Microsoft.XmlSerializer.Generator NuGet 包](https://www.nuget.org/packages/Microsoft.XmlSerializer.Generator) 是适用于 .NET Core 和 .NET 标准库的解决方案。 它为程序集中包含的类型创建 XML 序列化程序集，从而提高使用 <xref:System.Xml.Serialization.XmlSerializer> 序列化或反序列化这些类型对象时，XML 序列化的启动性能。