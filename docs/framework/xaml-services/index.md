---
title: XAML 服务
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], System.Xaml concepts
- XAML Services in WPF [XAML Services]
- System.Xaml [XAML Services], conceptual documentation
ms.assetid: 0e11f386-808c-4eae-9ba6-029ad7ba2211
ms.openlocfilehash: 8e1e8dc9a1410d05c19e4dd1bccb30c65d7c5e66
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837280"
---
# <a name="xaml-services"></a>XAML 服务
本主题介绍称为 .NET Framework XAML 服务的技术集的功能。 所述的大部分服务和 Api 都位于程序集 system.exception 中，该程序集是随 .NET Framework 4 组 .NET core 程序集引入的程序集。 服务包括读取器和编写器、架构类和架构支持、工厂、类的特性化、XAML 语言内部支持以及其他 XAML 语言功能。  
  
## <a name="about-this-documentation"></a>关于本文档  
 .NET Framework XAML 服务的概念文档假设你已掌握了 XAML 语言的经验，并且它可能适用于特定框架（例如 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 或 Windows Workflow Foundation）或特定技术功能区域（例如 <xref:Microsoft.Build.Framework.XamlTypes>中的生成自定义功能）。 本文档不会尝试将 XAML 基础知识解释为标记语言、XAML 语法术语或其他介绍性材料。 相反，本文档重点介绍如何专门使用在 system.exception 程序集库中启用 .NET Framework XAML 服务。 其中的大多数 Api 适用于 XAML 语言集成和扩展性。 这可能包括以下任何内容：  
  
- 扩展基 XAML 读取器或 XAML 编写器的功能（直接处理 XAML 节点流; 派生自己的 XAML 读取器或 XAML 编写器）。  
  
- 定义不具有特定框架依赖项的 XAML 可用自定义类型，并对这些类型进行特性化，以将其 XAML 类型系统特征传递到 .NET Framework XAML 服务。  
  
- 承载 XAML 读取器或 XAML 编写器作为应用程序的组件，如 XAML 标记源的可视化设计器或交互式编辑器。  
  
- 编写 XAML 值转换器（标记扩展; 自定义类型的类型转换器）。  
  
- 定义自定义 XAML 架构上下文（使用备用的程序集加载技术实现类型源）; 使用已知类型的查找技术而不是始终反射程序集; 使用已加载的程序集概念，不使用 CLR `AppDomain` 及其关联的安全模型）。  
  
- 扩展基 XAML 类型系统。  
  
- 使用 `Lookup` 或 `Invoker` 技术来影响 XAML 类型系统和如何计算类型 backings。  
  
 如果要在 XAML 上查找作为一种语言的介绍性资料，可以尝试[XAML 概述（WPF）](../../desktop-wpf/fundamentals/xaml.md)。 本主题讨论了 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 的新用户的 XAML，同时还讨论了如何使用 XAML 标记和 XAML 语言功能。 另一个有用文档是[XAML 语言规范](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10))中的介绍性材料。  
  
## <a name="net-framework-xaml-services-and-systemxaml-in-the-net-architecture"></a>.NET 体系结构中 .NET Framework XAML 服务和 system.exception  
 在早期版本的 Microsoft .NET Framework 中，对 XAML 语言功能的支持是由基于 Microsoft .NET Framework （[!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)]、Windows Workflow Foundation 和 Windows Communication Foundation （WCF））构建的框架实现的，因此，它的行为和使用的 API 取决于所使用的特定框架。 这包括 XAML 分析器及其对象关系图创建机制、XAML 语言内部函数、序列化支持等。  
  
 在 .NET Framework 4 中，.NET Framework XAML 服务和 System.object 程序集定义支持 XAML 语言功能所需的大部分内容。 这包括 XAML 读取器和 XAML 编写器的基类。 添加到任何特定于框架的 XAML 实现中的 .NET Framework XAML 服务的最重要功能是适用于 XAML 的类型系统表示形式。 类型系统表示形式以面向对象的方式，以面向对象的方式来表示 XAML 功能，而无需依赖于框架的特定功能。  
  
 XAML 类型系统不受 XAML 源的标记形式或运行时细节的限制;它也不受任何特定后备类型系统的限制。 XAML 类型系统包括类型、成员、XAML 架构上下文、XML 级别概念以及其他 XAML 语言概念或 XAML 内部函数的对象表示形式。 通过使用或扩展 XAML 类型系统，可以从 XAML 读取器和 XAML 编写器等类派生，并将 XAML 表示形式的功能扩展为框架、技术或使用或的应用程序所启用的特定功能。发出 XAML。 XAML 架构上下文的概念允许从 XAML 对象编写器实现的组合（一种技术的后备类型系统通过上下文中的程序集信息和 XAML 节点）组合进行实际的对象图写入操作源程序. 有关 XAML 架构概念的详细信息。 请参阅[默认 XAML 架构上下文和 WPF XAML 架构上下文](default-xaml-schema-context-and-wpf-xaml-schema-context.md)。  
  
## <a name="xaml-node-streams-xaml-readers-and-xaml-writers"></a>XAML 节点流、XAML 读取器和 XAML 编写器  
 若要理解 .NET Framework XAML 服务在 XAML 语言和使用 XAML 作为语言的特定技术之间的关系中扮演的角色，了解 XAML 节点流的概念以及该概念是如何形成 API 和规范. XAML 节点流是 XAML 语言表示形式与 XAML 表示或定义的对象图之间的概念中间。  
  
- XAML 读取器是一个实体，它以某种形式处理 XAML，并生成 XAML 节点流。 在 API 中，XAML 读取器由基类 <xref:System.Xaml.XamlReader>表示。  
  
- XAML 编写器是一个处理 XAML 节点流并生成其他内容的实体。 在 API 中，XAML 编写器由基类 <xref:System.Xaml.XamlWriter>表示。  
  
 涉及 XAML 的两种最常见的情况是加载 XAML 来实例化对象图，并从应用程序或工具保存对象图并生成 XAML 表示形式（通常以标记形式保存为文本文件）。 在此文档中，加载 XAML 和创建对象图通常被称为加载路径。 将现有对象图保存或序列化到 XAML 通常在此文档中称为保存路径。  
  
 最常见的加载路径类型可以描述如下：  
  
- 以 UTF 编码的 XML 格式开始使用 XAML 表示形式，并将其保存为文本文件。  
  
- 将该 XAML 加载到 <xref:System.Xaml.XamlXmlReader>中。 <xref:System.Xaml.XamlXmlReader> 是 <xref:System.Xaml.XamlReader> 子类。  
  
- 结果为 XAML 节点流。 您可以使用 <xref:System.Xaml.XamlXmlReader> / <xref:System.Xaml.XamlReader> API 来访问 XAML 节点流的各个节点。 此处最典型的操作是前进到 XAML 节点流，使用 "当前记录" 比喻处理每个节点。  
  
- 将生成的节点从 XAML 节点流传递到 <xref:System.Xaml.XamlObjectWriter> API。 <xref:System.Xaml.XamlObjectWriter> 是 <xref:System.Xaml.XamlWriter> 子类。  
  
- <xref:System.Xaml.XamlObjectWriter> 根据源 XAML 节点流中的进度，一次写入一个对象图。 这是通过 XAML 架构上下文和可访问后备类型系统和框架的程序集和类型的实现来完成的。  
  
- 在 XAML 节点流的末尾调用 <xref:System.Xaml.XamlObjectWriter.Result%2A>，以获取对象图的根对象。  
  
 最常见类型的保存路径可描述如下：  
  
- 从整个应用程序运行时的对象图、运行时的 UI 内容和状态，或者在运行时的整个应用程序对象表示形式的较小部分开始。  
  
- 从逻辑开始对象（如应用程序根或文档根）将对象加载到 <xref:System.Xaml.XamlObjectReader>中。 <xref:System.Xaml.XamlObjectReader> 是 <xref:System.Xaml.XamlReader> 子类。  
  
- 结果为 XAML 节点流。 您可以使用 <xref:System.Xaml.XamlObjectReader> 和 <xref:System.Xaml.XamlReader> API 访问 XAML 节点流的各个节点。 此处最典型的操作是前进到 XAML 节点流，使用 "当前记录" 比喻处理每个节点。  
  
- 将生成的节点从 XAML 节点流传递到 <xref:System.Xaml.XamlXmlWriter> API。 <xref:System.Xaml.XamlXmlWriter> 是 <xref:System.Xaml.XamlWriter> 子类。  
  
- <xref:System.Xaml.XamlXmlWriter> 将 XAML 编写为 XML UTF 编码。 可以将其另存为文本文件、流或其他格式。  
  
- 调用 <xref:System.Xaml.XamlXmlWriter.Flush%2A> 以获取最终输出。  
  
 有关 XAML 节点流概念的详细信息，请参阅[了解 Xaml 节点流结构和概念](understanding-xaml-node-stream-structures-and-concepts.md)。  
  
### <a name="the-xamlservices-class"></a>XamlServices 类  
 并非始终需要处理 XAML 节点流。 如果需要基本的加载路径或基本保存路径，可以使用 <xref:System.Xaml.XamlServices> 类中的 Api。  
  
- <xref:System.Xaml.XamlServices.Load%2A> 的各种签名实现加载路径。 可以加载文件或流，或者可以加载通过使用该读取器的 Api 进行加载来包装 XAML 输入的 <xref:System.Xml.XmlReader>、<xref:System.IO.TextReader> 或 <xref:System.Xaml.XamlReader>。  
  
- <xref:System.Xaml.XamlServices.Save%2A> 的各种签名保存对象图，并以流、文件或 <xref:System.Xml.XmlWriter>/<xref:System.IO.TextWriter> 实例形式生成输出。  
  
- <xref:System.Xaml.XamlServices.Transform%2A> 通过将加载路径和保存路径链接为单个操作来转换 XAML。 不同的架构上下文或不同的后备类型系统可用于 <xref:System.Xaml.XamlReader> 和 <xref:System.Xaml.XamlWriter>，这会影响生成的 XAML 的转换方式。  
  
 有关如何使用 <xref:System.Xaml.XamlServices>的详细信息，请参阅[XAMLServices 类和基本的 XAML 读取或写入](xamlservices-class-and-basic-xaml-reading-or-writing.md)。  
  
## <a name="xaml-type-system"></a>XAML 类型系统  
 XAML 类型系统提供了与 XAML 节点流中给定的单个节点协同工作所需的 Api。  
  
 <xref:System.Xaml.XamlType> 是对象的表示形式，即在开始对象节点和结束对象节点之间进行处理的对象。  
  
 <xref:System.Xaml.XamlMember> 是指对象成员的表示形式，即在开始成员节点和结束成员节点之间进行处理的方式。  
  
 Api （如 <xref:System.Xaml.XamlType.GetAllMembers%2A> 和 <xref:System.Xaml.XamlType.GetMember%2A> 和 <xref:System.Xaml.XamlMember.DeclaringType%2A> 报告 <xref:System.Xaml.XamlType> 和 <xref:System.Xaml.XamlMember>之间的关系。  
  
 XAML 类型系统的默认行为是由 .NET Framework XAML 服务实现的，该行为基于公共语言运行时（CLR），并使用反射对程序集中的 CLR 类型进行静态分析。 因此，对于特定的 CLR 类型，XAML 类型系统的默认实现可以公开该类型及其成员的 XAML 架构，并根据 XAML 类型系统对其进行报告。 在默认的 XAML 类型系统中，类型的依据的概念映射到 CLR 继承，而实例、值类型等的概念也映射到 CLR 的支持行为和功能。  
  
## <a name="reference-for-xaml-language-features"></a>XAML 语言功能的参考  
 为了支持 XAML，.NET Framework XAML 服务提供 xaml 语言概念的特定实现，如为 XAML 语言 XAML 命名空间定义的。 这些都记录为特定的参考页。 从语言功能的角度来看，这些语言功能是通过 XAML 读取器或 xaml 编写器处理的，由 .NET Framework XAML 服务定义。 有关更多信息，请参见 [XAML Namespace (x:) Language Features](xaml-namespace-x-language-features.md)。
