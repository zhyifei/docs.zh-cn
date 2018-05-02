---
title: XAML 服务
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XAML [XAML Services], System.Xaml concepts
- XAML Services in WPF [XAML Services]
- System.Xaml [XAML Services], conceptual documentation
ms.assetid: 0e11f386-808c-4eae-9ba6-029ad7ba2211
caps.latest.revision: 13
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f36f22e8bf68520f5f57280d33cf37990feb2df6
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2018
---
# <a name="xaml-services"></a>XAML 服务
本主题介绍的技术集称为.NET Framework XAML 服务的功能。 服务和 Api 所述的大部分都位于引入 System.Xaml 的应用，这是程序集的程序集[!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)].NET 核心程序集。 服务包括读取器和编写器，架构类和架构支持的工厂，特性化的类、 XAML 语言内部函数支持和其他 XAML 语言功能。  
  
## <a name="about-this-documentation"></a>有关此文档  
 .NET Framework XAML 服务的概念性文档假定你有以前经验 XAML 语言以及如何它可能会将应用到一个特定的框架，例如[!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)]或 Windows Workflow Foundation 或特定的技术功能区域中，例如生成自定义项中的功能<xref:Microsoft.Build.Framework.XamlTypes>。 本文档不会尝试解释为标记语言、 XAML 语法术语或其他介绍性材料的 XAML 的基础知识。 相反，本文档重点介绍专门在 System.Xaml 程序集库中使用已启用.NET Framework XAML 服务。 这些 Api 的大部分都是为 XAML 语言集成和可扩展性的方案。 这可能包括以下任一项：  
  
-   扩展的基的 XAML 读取器或 XAML 编写器 （直接处理 XAML 节点流; 派生您自己的 XAML 读取器或 XAML 编写器） 的功能。  
  
-   定义没有特定的框架依赖项的 XAML 可用自定义类型和特性化的类型来传达其 XAML 类型.NET Framework XAML 服务的系统的特征。  
  
-   承载的应用程序，如可视化设计器或 XAML 标记源的交互式编辑器的组件的 XAML 读取器或 XAML 编写器。  
  
-   编写 XAML （标记扩展; 自定义类型的类型转换器） 的值转换器。  
  
-   定义自定义的 XAML 架构上下文 (用于后备类型源使用备用的程序集加载技术; 而不始终使用已知类型查找技术反射程序集; 使用未使用 CLR 的加载的程序集概念`AppDomain`和其关联的安全模型）。  
  
-   将扩展基的 XAML 类型系统。  
  
-   使用`Lookup`或`Invoker`技术来影响 XAML 类型系统以及如何评估类型后备。  
  
 如果你要查找对 XAML 作为一种语言的介绍性材料，则可能会尝试[XAML 概述 (WPF)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)。 该主题讨论 XAML 是新的受众这两项[!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)]并指向使用 XAML 标记和 XAML 语言功能。 另一个有用的文档中的介绍性材料是[XAML 语言规范](http://go.microsoft.com/fwlink/?LinkId=114525)。  
  
## <a name="net-framework-xaml-services-and-systemxaml-in-the-net-architecture"></a>.NET framework XAML 服务和 System.Xaml 中.NET 体系结构  
 在以前版本的[!INCLUDE[TLA#tla_netframewk](../../../includes/tlasharptla-netframewk-md.md)]，支持 XAML 语言功能所实现的基础构建的框架[!INCLUDE[TLA#tla_netframewk](../../../includes/tlasharptla-netframewk-md.md)] ([!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)]，Windows Workflow Foundation 和 Windows Communication Foundation (WCF))，因此不同和其行为，具体取决于哪个特定的框架已使用的 API 使用。 这包括 XAML 分析器及其对象图创建机制，XAML 语言内部函数、 序列化支持，依次类推。  
  
 在[!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]，.NET Framework XAML 服务和 System.Xaml 程序集中定义了大部分所需的支持 XAML 语言功能。 这包括用于 XAML 读取器和 XAML 编写器的基类，这些类。 添加到未出现在任何特定于框架的 XAML 实现的.NET Framework XAML 服务的最重要功能是 XAML 类型系统表示形式。 类型系统表示形式以侧重于 XAML 功能而不依赖于框架的特定功能的面向对象的方式显示 XAML。  
  
 XAML 类型系统时不受限制的标记窗体或运行时的 XAML 源中; 的详细信息也不受任何特定的后备类型系统限制。 XAML 类型系统包括类型、 成员、 XAML 架构上下文、 XML 级概念，和其他 XAML 语言概念或 XAML 内部函数的对象表示形式。 使用或扩展的 XAML 类型系统使能够派生自的类，如 XAML 读取器和 XAML 编写器和扩展的功能划分到一个框架，一种技术或使用应用程序启用的特定功能的 XAML 表示形式或发出 XAML。 XAML 架构上下文的概念允许从一个 XAML 对象编写器实现，一种技术的后备类型系统通过在上下文中和 XAML 节点中的程序集信息进行通信的组合的实际对象图写入操作源。 有关 XAML 架构概念的详细信息。 请参阅[默认 XAML 架构上下文和 WPF XAML 架构上下文](../../../docs/framework/xaml-services/default-xaml-schema-context-and-wpf-xaml-schema-context.md)。  
  
## <a name="xaml-node-streams-xaml-readers-and-xaml-writers"></a>XAML 节点流，XAML 读取器和 XAML 编写器  
 若要了解.NET Framework XAML 服务 XAML 语言和 XAML 用作一种语言的特定技术之间的关系中扮演的角色，最好先了解 XAML 节点流以及如何这一概念形状 API 的概念和术语。 XAML 节点流是 XAML 语言表示形式和 XAML 表示或定义的对象关系图之间概念中间。  
  
-   XAML 读取器是以某种形式处理的 XAML，并生成 XAML 节点流的实体。 在 API 中，XAML 读取器由基类<xref:System.Xaml.XamlReader>。  
  
-   XAML 编写器是处理 XAML 节点流并生成其他内容的实体。 在 API 中，XAML 编写器由基类<xref:System.Xaml.XamlWriter>。  
  
 涉及 XAML 的两个最常见方案是加载要实例化对象图，XAML 和从应用程序或工具中保存对象图和生成 XAML 表示形式 （通常以另存为文本文件的标记窗体）。 加载 XAML 和创建对象图通常称为在本文档在加载路径中。 保存或序列化到使用 XAML 现有对象图通常称为作为保存此文档中路径。  
  
 加载路径的最常见类型如下所述：  
  
-   启动与 XAML 表示形式，采用 UTF 编码 XML 格式和另存为文本文件。  
  
-   到该 XAML 加载<xref:System.Xaml.XamlXmlReader>。 <xref:System.Xaml.XamlXmlReader> 是<xref:System.Xaml.XamlReader>子类。  
  
-   结果是 XAML 节点流。 你可以访问的 XAML 节点流使用的各个节点<xref:System.Xaml.XamlXmlReader>  /  <xref:System.Xaml.XamlReader> API。 最典型的操作是无法进一步处理 XAML 节点流中，处理每个节点，使用"当前记录"比喻。  
  
-   将生成的节点传递到 XAML 节点流<xref:System.Xaml.XamlObjectWriter>API。 <xref:System.Xaml.XamlObjectWriter> 是<xref:System.Xaml.XamlWriter>子类。  
  
-   <xref:System.Xaml.XamlObjectWriter>中根据通过源 XAML 节点流的进度写入对象图，一次的一个对象。 这是通过的帮助下的 XAML 架构上下文并可以访问程序集和类型的后备类型系统和框架的实现。  
  
-   调用<xref:System.Xaml.XamlObjectWriter.Result%2A>要获取根对象的对象图的 XAML 节点流的末尾。  
  
 保存路径的最常见类型如下所述：  
  
-   开头的整个应用程序运行时间时，UI 内容和状态的运行时间或在运行时的总体应用程序的对象表示形式的较小段的对象图。  
  
-   从逻辑开始对象，如应用程序根目录或文档根，将对象加载到<xref:System.Xaml.XamlObjectReader>。 <xref:System.Xaml.XamlObjectReader> 是<xref:System.Xaml.XamlReader>子类。  
  
-   结果是 XAML 节点流。 你可以访问的 XAML 节点流使用的各个节点<xref:System.Xaml.XamlObjectReader>和<xref:System.Xaml.XamlReader>API。 最典型的操作是无法进一步处理 XAML 节点流中，处理每个节点，使用"当前记录"比喻。  
  
-   将生成的节点传递到 XAML 节点流<xref:System.Xaml.XamlXmlWriter>API。 <xref:System.Xaml.XamlXmlWriter> 是<xref:System.Xaml.XamlWriter>子类。  
  
-   <xref:System.Xaml.XamlXmlWriter>编码 XML UTF 中写入 XAML。 你可以将它保存为文本文件，作为流，或在其他窗体中。  
  
-   调用<xref:System.Xaml.XamlXmlWriter.Flush%2A>即可获得最终输出。  
  
 有关 XAML 节点流概念的详细信息，请参阅[了解 XAML 节点流结构和概念](../../../docs/framework/xaml-services/understanding-xaml-node-stream-structures-and-concepts.md)。  
  
### <a name="the-xamlservices-class"></a>XamlServices 类  
 它并不总是需要处理 XAML 节点流。 如果所需的基本的加载路径或保存路径 basic，则可以使用中的 Api<xref:System.Xaml.XamlServices>类。  
  
-   各种签名<xref:System.Xaml.XamlServices.Load%2A>实现了加载路径。 你可以加载文件或流，或者可以加载<xref:System.Xml.XmlReader>，<xref:System.IO.TextReader>或<xref:System.Xaml.XamlReader>，它们通过使用该读取器的 Api 进行加载来包装你的 XAML 输入。  
  
-   各种签名<xref:System.Xaml.XamlServices.Save%2A>保存对象图和生成流、 输出文件，或<xref:System.Xml.XmlWriter> / <xref:System.IO.TextWriter>实例。  
  
-   <xref:System.Xaml.XamlServices.Transform%2A> 将 XAML 转换通过链接一个加载路径或保存路径作为单个操作。 无法用于不同的架构上下文或不同的后备类型系统<xref:System.Xaml.XamlReader>和<xref:System.Xaml.XamlWriter>，这会影响如何转换产生的 XAML。  
  
 有关如何使用<xref:System.Xaml.XamlServices>，请参阅[XAMLServices 类和基本的 XAML 读取或写入](../../../docs/framework/xaml-services/xamlservices-class-and-basic-xaml-reading-or-writing.md)。  
  
## <a name="xaml-type-system"></a>XAML 类型系统  
 XAML 类型系统提供了所需的 XAML 节点流在给定的单个节点所使用的 Api。  
  
 <xref:System.Xaml.XamlType> 是你正在处理的启动对象节点和结束对象节点之间的对象的表示形式。  
  
 <xref:System.Xaml.XamlMember> 是要处理开始成员节点和结束成员节点之间的成员的表示形式。  
  
 如 Api<xref:System.Xaml.XamlType.GetAllMembers%2A>和<xref:System.Xaml.XamlType.GetMember%2A>和<xref:System.Xaml.XamlMember.DeclaringType%2A>报告之间的关系<xref:System.Xaml.XamlType>和<xref:System.Xaml.XamlMember>。  
  
 由.NET Framework XAML 服务实现的 XAML 类型系统的默认行为基于公共语言运行时 (CLR) 和 CLR 类型的程序集中的静态分析使用反射。 因此，对于特定的 CLR 类型，XAML 类型系统的默认实现可以公开该类型及其成员的 XAML 架构并将其报告在 XAML 类型系统方面。 在默认 XAML 类型系统中，可分配性的类型的概念映射到 CLR 继承和实例、 值类型和等等的概念也将映射到支持的行为和 CLR 的功能。  
  
## <a name="reference-for-xaml-language-features"></a>XAML 语言功能的引用  
 若要支持 XAML，.NET Framework XAML 服务提供 XAML 语言概念定义为 XAML 语言 XAML 命名空间的特定的实现。 为特定的参考页对它们进行介绍。 从由 XAML 读取器或 XAML 编写器定义的.NET Framework XAML 服务进行处理时，这些语言功能的行为方式的角度记录的语言功能。 有关更多信息，请参见 [XAML Namespace (x:) Language Features](../../../docs/framework/xaml-services/xaml-namespace-x-language-features.md)。
