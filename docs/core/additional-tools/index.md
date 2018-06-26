---
title: 其他 .NET Core 工具
description: 可支持和扩展 .NET Core 功能的其他工具的概述。
author: mlacouture
ms.author: johalex
ms.date: 01/19/2018
ms.custom: mvc
ms.openlocfilehash: 5f744fd63116ac453a2a7db8eb94f12738c95f21
ms.sourcegitcommit: c217b067985905cb21eafc5dd9a83568d7ff4e45
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/22/2018
ms.locfileid: "36315194"
---
# <a name="net-core-additional-tools"></a><span data-ttu-id="e1e36-103">其他 .NET Core 工具</span><span class="sxs-lookup"><span data-stu-id="e1e36-103">.NET Core additional tools</span></span>

<span data-ttu-id="e1e36-104">本节除了 [.NET Core 命令行接口 (CLI)](..\tools\index.md) 工具外，还编译了可支持和扩展 .NET Core 功能的工具列表。</span><span class="sxs-lookup"><span data-stu-id="e1e36-104">This section compiles a list of tools that support and extend the .NET Core functionality, in addition to the [.NET Core command-line interface (CLI)](..\tools\index.md) tools.</span></span>

## <a name="wcf-web-service-reference-toolwcf-web-service-reference-guidemd"></a>[<span data-ttu-id="e1e36-105">WCF Web 服务引用工具</span><span class="sxs-lookup"><span data-stu-id="e1e36-105">WCF Web Service Reference tool</span></span>](wcf-web-service-reference-guide.md)

<span data-ttu-id="e1e36-106">WCF (Windows Communication Foundation) Web 服务引用是一个 Visual Studio 连接服务提供程序，首次推出是在 [Visual Studio 2017 版本 15.5](https://visualstudio.microsoft.com/news/releasenotes/vs2017-relnotes#WCFTools) 中。</span><span class="sxs-lookup"><span data-stu-id="e1e36-106">The WCF (Windows Communication Foundation) Web Service Reference is a Visual Studio connected service provider that made its debut in [Visual Studio 2017 version 15.5](https://visualstudio.microsoft.com/news/releasenotes/vs2017-relnotes#WCFTools).</span></span> <span data-ttu-id="e1e36-107">此工具可从网络位置上的当前解决方案中的 Web 服务中或从 WSDL 文件中检索元数据，并生成与 .NET Core 兼容的源文件，此文件通过可用于访问 Web 服务操作的方法定义了 WCF 代理类。</span><span class="sxs-lookup"><span data-stu-id="e1e36-107">This tool retrieves metadata from a web service in the current solution, on a network location, or from a WSDL file, and generates a source file compatible with .NET Core, defining a WCF proxy class with methods that you can use to access the web service operations.</span></span>

## <a name="wcf-dotnet-svcutil-tooldotnet-svcutil-guidemd"></a>[<span data-ttu-id="e1e36-108">WCF dotnet-svcutil 工具</span><span class="sxs-lookup"><span data-stu-id="e1e36-108">WCF dotnet-svcutil tool</span></span>](dotnet-svcutil-guide.md)

<span data-ttu-id="e1e36-109">WCF (Windows Communication Foundation) dotnet-svcutil 工具是一种 .NET Core CLI 工具，此工具从网络位置上的 Web 服务中或从 WSDL 文件中检索元数据，并生成与 .NET Core 兼容的源文件，此文件通过可用于访问 Web 服务操作的方法定义了 WCF 代理类。</span><span class="sxs-lookup"><span data-stu-id="e1e36-109">The WCF (Windows Communication Foundation) dotnet-svcutil tool is a .NET Core CLI tool that retrieves metadata from a web service on a network location or from a WSDL file, and generates a source file compatible with .NET Core, defining a WCF proxy class with methods that you can use to access the web service operations.</span></span> <span data-ttu-id="e1e36-110">dotnet-svcutil 工具是 [WCF Web 服务引用](/dotnet/core/additional-tools/wcf-web-service-reference-guide) Visual Studio 连接服务提供程序（随 Visual Studio 2017 v15.5 首次推出）的替代选项。</span><span class="sxs-lookup"><span data-stu-id="e1e36-110">The **dotnet-svcutil** tool is an alternative option to the [**WCF Web Service Reference**](/dotnet/core/additional-tools/wcf-web-service-reference-guide) Visual Studio connected service provider which first shipped with Visual Studio 2017 v15.5.</span></span> <span data-ttu-id="e1e36-111">dotnet-svcutil 工具作为一种 .NET Core CLI 工具，可跨平台地用于 Linux、macOS 和 Windows。</span><span class="sxs-lookup"><span data-stu-id="e1e36-111">The **dotnet-svcutil** tool as a .NET Core CLI tool, is available cross-platform on Linux, macOS, and Windows.</span></span>

## <a name="xml-serializer-generatorxml-serializer-generatormd"></a>[<span data-ttu-id="e1e36-112">XML 序列化程序生成器</span><span class="sxs-lookup"><span data-stu-id="e1e36-112">XML Serializer Generator</span></span>](xml-serializer-generator.md)

<span data-ttu-id="e1e36-113">正如 [Xml Serializer Generator (sgen.exe)](../../standard/serialization/xml-serializer-generator-tool-sgen-exe.md) 适用于 .NET Framework，[Microsoft.XmlSerializer.Generator NuGet 包](https://www.nuget.org/packages/Microsoft.XmlSerializer.Generator) 是适用于 .NET Core 和 .NET 标准库的解决方案。</span><span class="sxs-lookup"><span data-stu-id="e1e36-113">Like the [Xml Serializer Generator (sgen.exe)](../../standard/serialization/xml-serializer-generator-tool-sgen-exe.md) for the .NET Framework, the [Microsoft.XmlSerializer.Generator NuGet package](https://www.nuget.org/packages/Microsoft.XmlSerializer.Generator) is the solution for .NET Core and .NET Standard libraries.</span></span> <span data-ttu-id="e1e36-114">它为程序集中包含的类型创建 XML 序列化程序集，从而提高使用 <xref:System.Xml.Serialization.XmlSerializer> 序列化或反序列化这些类型对象时，XML 序列化的启动性能。</span><span class="sxs-lookup"><span data-stu-id="e1e36-114">It creates an XML serialization assembly for types contained in an assembly to improve the startup performance of XML serialization when serializing or de-serializing objects of those types using <xref:System.Xml.Serialization.XmlSerializer>.</span></span>