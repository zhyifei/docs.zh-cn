---
title: "默认 XAML 架构上下文和 WPF XAML 架构上下文"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 04e06a15-09b3-4210-9bdf-9a64c2eccb83
caps.latest.revision: "7"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9ee7c83868934f1a524bb0068ea5e749e6cbfab4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="default-xaml-schema-context-and-wpf-xaml-schema-context"></a>默认 XAML 架构上下文和 WPF XAML 架构上下文
XAML 架构上下文是限定 XAML 生产环境中使用的特定 XAML 词汇如何与编写行为，包括如何类型映射解决时，程序集的加载方式、 如何某些读取器和编写器的对象进行交互的概念实体解释设置。 本主题介绍.NET Framework XAML 服务和基于 CLR 类型系统的关联的默认 XAML 架构上下文的功能。 本主题还介绍适用于 WPF XAML 架构上下文。  
  
## <a name="default-xaml-schema-context"></a>默认 XAML 架构上下文  
 .NET framework XAML 服务同时实施，并使用默认 XAML 架构上下文。 默认 XAML 架构上下文行为并不总是完全可见的 API 中<xref:System.Xaml.XamlSchemaContext>类。 但是，在许多情况下，默认 XAML 架构上下文影响行为将是通过公共 API 的 XAML 类型系统，如的成员可观测对象<xref:System.Xaml.XamlMember>或<xref:System.Xaml.XamlType>，或通过 XAML 读取器和 XAML 编写器使用上公开的 Api默认 XAML 架构上下文。  
  
 你可以创建<xref:System.Xaml.XamlSchemaContext>通过调用封装的默认行为<xref:System.Xaml.XamlSchemaContext>构造函数。 这将显式创建的默认 XAML 架构上下文。 如果 XAML 读取器或使用不显式采用的 Api 的 XAML 编写器初始化隐式创建的相同的默认 XAML 架构上下文<xref:System.Xaml.XamlSchemaContext>输入的参数。  
  
 默认 XAML 架构上下文依赖于 CLR 对其类型映射的行为的反射。 这包括检查定义 CLR <xref:System.Type>，和相关<xref:System.Reflection.PropertyInfo>或<xref:System.Reflection.MethodInfo>。 此外，为了在 XAML 类型或使用 CLR 后备类型的 XAML 成员信息的具体信息填充使用 CLR 归属类型或成员。 默认 XAML 架构上下文不需要类型系统扩展技术，如`Invoker`模式，因为所需的信息是从 CLR 类型系统可用。  
  
 对于程序集加载逻辑，默认 XAML 架构上下文依赖主要的 XAML 命名空间映射中提供任何程序集值。 此外，<xref:System.Xaml.XamlReaderSettings.LocalAssembly%2A>可以提示加载，如加载内部类型的方案某程序集。  
  
## <a name="wpf-xaml-schema-context"></a>WPF XAML 架构上下文  
 因为的 WPF 实现，提供有趣举例说明了可以通过实现的非默认 XAML 架构上下文中引入的功能的类型，本主题中描述的 WPF XAML 架构上下文。 此外，XAML 架构上下文概念中未讨论很大程度 WPF 文档，此迭代 WPF XAML;XAML 架构上下文便会启用的行为可能仅集成并讨论了默认 XAML 架构上下文的工作原理完全可以理解。 WPF XAML 架构上下文实现以下行为。  
  
 **查找重写：** WPF xaml 具有几个内容模型其中有不是函数的 XAML 内容属性<xref:System.Windows.Markup.ContentPropertyAttribute>特性化。 <xref:System.Xaml.XamlType.LookupContentProperty%2A>替代 WPF 实现此行为。  
  
 **WPF 表达式的延迟：** WPF 功能将值的延迟，直到运行时上下文可用的多个表达式类。 此外，模板扩展是依赖于延迟技术的运行时行为。  
  
 **类型系统查找优化：** WPF 都具有一个广泛 XAML 词汇和对象模型，包括到按原义数百个 WPF 定义类继承的基类成员定义。 此外，WPF 本身是分布在多个程序集。 WPF 优化使用查找表和其他技术其类型查找。 此基础上的默认 XAML 架构上下文和其基于 CLR 的类型查找提供了性能改进。 在其中查找表中不存在类型的情况下，该行为使用类似于默认 XAML 架构上下文的 XAML 架构上下文技术。  
  
 **XamlType 和 XamlMember 扩展：** WPF 通过扩展，与依赖项属性的属性概念和事件概念与路由事件。 若要为针对 XAML 处理操作的这些概念进行了更好的可视性，WPF 扩展<xref:System.Xaml.XamlType>和<xref:System.Xaml.XamlMember>，并添加报告依赖项属性和路由事件特征的内部属性。  
  
### <a name="accessing-the-wpf-xaml-schema-context"></a>访问 WPF XAML 架构上下文  
 如果你使用的基于 WPF 的 XAML 技术<xref:System.Windows.Markup.XamlReader?displayProperty=nameWithType>或<xref:System.Windows.Markup.XamlWriter?displayProperty=nameWithType>，WPF XAML 架构上下文已在使用这些 XAML 读取器和 XAML 编写器实现。  
  
 如果使用其他 XAML 读取器或未初始化的 XAML 编写器实现与 WPF XAML 架构上下文，你可能无法获得一个有效的 WPF XAML 架构上下文从<xref:System.Windows.Markup.XamlReader.GetWpfSchemaContext%2A?displayProperty=nameWithType>。 然后可以使用此值，作为使用其他 api 的初始化<xref:System.Xaml.XamlSchemaContext>。 例如，可以调用<xref:System.Xaml.XamlXmlReader.%23ctor%2A>的初始化，然后传递 WPF XAML 架构上下文。 或者，可以使用 WPF XAML 架构上下文的 XAML 类型系统操作。 这可能包括构造初始化<xref:System.Xaml.XamlType>或<xref:System.Xaml.XamlMember>，或调用<xref:System.Xaml.XamlSchemaContext.GetXamlType%2A?displayProperty=nameWithType>。  
  
 请注意，是否从纯的 XAML 节点流角度访问 WPF XAML 的某些方面，一些 WPF framework 功能可能不具有已按照尚未。 例如，控件的 WPF 模板尚未应用。 因此如果你访问一个属性，在运行时可能已填充整个可视化树，你可能只能看到引用模板的属性值。 提供的 WPF 标记扩展的服务上下文可能也不会准确如果提供非运行时的情况下，从和尝试写入对象图时，可能会导致异常。  
  
## <a name="xaml-and-assembly-loading"></a>XAML 和程序集加载  
 程序集加载的 XAML 和.NET Framework XAML 服务集成的 CLR 定义概念<xref:System.AppDomain>。 XAML 架构上下文解释如何加载程序集或类型查找在运行的时或设计时，基于使用<xref:System.AppDomain>和其他因素。 逻辑会略有不同，具体取决于 XAML 是 XAML 读取器的宽松 XAML，是 XAML 编译成由 DLL `XamlBuildTask`，或由 WPF 的生成 BAML `PresentationBuildTask`。  
  
 与 WPF 应用程序模型，这反过来使用集成，WPF XAML 架构上下文<xref:System.AppDomain>以及其他因素的 WPF 实现详细信息。  
  
#### <a name="xaml-reader-input-loose-xaml"></a>XAML 读取器输入 (宽松型 XAML)  
  
1.  XAML 架构上下文循环访问<xref:System.AppDomain>应用程序，查找匹配的名称，所有方面的已加载程序集的最近从最开始加载程序集。 如果找到匹配项，则该程序集用于解析。  
  
2.  否则，以下方法之一将基于 CLR <xref:System.Reflection.Assembly> API 用于加载程序集：  
  
    -   如果映射中限定的名称，调用<xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>的限定名称。  
  
    -   如果前面的步骤失败，使用短名称 （和公钥标记如果存在） 调用<xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>。  
  
    -   如果映射中非限定名称，则调用<xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=nameWithType>。  
  
#### <a name="xamlbuildtask"></a>XamlBuildTask  
 `XamlBuildTask`适用于[!INCLUDE[vsindigo](../../../includes/vsindigo-md.md)]和[!INCLUDE[TLA#tla_workflow](../../../includes/tlasharptla-workflow-md.md)]。  
  
 请注意，程序集引用了通过`XamlBuildTask`始终是完全限定。  
  
1.  调用<xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>的限定名称。  
  
2.  如果前面的步骤失败，使用短名称 （和公钥标记如果存在） 调用<xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>。  
  
#### <a name="baml-presentationbuildtask"></a>BAML (PresentationBuildTask)  
 有两个方面的 BAML 的程序集加载： 加载包含作为组件，BAML 的初始程序集和加载引用的 BAML 生产任何类型的类型支持程序集。  
  
##### <a name="assembly-load-for-initial-markup"></a>初始标记的程序集加载：  
 要加载的标记的程序集的引用始终是不合格的。  
  
1.  WPF XAML 架构上下文循环访问<xref:System.AppDomain>WPF 应用程序，查找匹配的名称，所有方面的已加载程序集的最近从最开始加载程序集。 如果找到匹配项，则该程序集用于解析。  
  
2.  如果前面的步骤失败，使用短名称 （和公钥标记如果存在） 调用<xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>。  
  
##### <a name="assembly-references-by-baml-types"></a>由 BAML 类型的程序集引用：  
 BAML 生产中使用的类型的程序集引用始终是完全限定，作为生成任务的输出。  
  
1.  WPF XAML 架构上下文循环访问<xref:System.AppDomain>WPF 应用程序，查找匹配的名称，所有方面的已加载程序集的最近从最开始加载程序集。 如果找到匹配项，则该程序集用于解析。  
  
2.  否则，以下方法之一用于加载程序集：  
  
    -   调用<xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>的限定名称。  
  
    -   如果一个短名称 + 公钥令牌的组合匹配 BAML 从加载的程序集中，使用该程序集。  
  
    -   使用短名称 + 公钥令牌来调用<xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>。  
  
## <a name="see-also"></a>请参阅  
 [了解 XAML 节点流结构和概念](../../../docs/framework/xaml-services/understanding-xaml-node-stream-structures-and-concepts.md)
