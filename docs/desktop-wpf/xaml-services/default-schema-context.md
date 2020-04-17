---
title: 默认 XAML 架构上下文和 WPF XAML 架构上下文
ms.date: 03/30/2017
ms.assetid: 04e06a15-09b3-4210-9bdf-9a64c2eccb83
ms.openlocfilehash: 2e92372de61230a98a02282cc28fc3f479cd94eb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "81433078"
---
# <a name="default-xaml-schema-context-and-wpf-xaml-schema-context"></a>默认 XAML 架构上下文和 WPF XAML 架构上下文
XAML 架构上下文是一个概念实体，它限定了使用特定 XAML 词汇表的 XAML 生产如何与对象写入行为进行交互，包括类型映射解析方式、程序集的加载方式、如何解释某些读取器和编写器设置。 本主题介绍 .NET XAML 服务的功能和基于 CLR 类型系统的关联的默认 XAML 架构上下文。 本主题还介绍用于 WPF 的 XAML 架构上下文。

## <a name="default-xaml-schema-context"></a>默认 XAML 架构上下文

.NET XAML 服务既实现并使用默认的 XAML 架构上下文。 默认 XAML 架构上下文行为并不总是在<xref:System.Xaml.XamlSchemaContext>类的 API 中完全可见。 但是，在许多情况下，默认 XAML 架构上下文影响的行为可以通过 XAML 类型系统的常见 API（如<xref:System.Xaml.XamlMember>或 的成员<xref:System.Xaml.XamlType>或 或通过使用默认 XAML 架构上下文的 XAML 读取器和 XAML 写入器上公开的 API 来观察）。

可以通过调用构造函数<xref:System.Xaml.XamlSchemaContext>创建封装默认行为的<xref:System.Xaml.XamlSchemaContext>。 这显式创建默认的 XAML 架构上下文。 如果使用不显式采用<xref:System.Xaml.XamlSchemaContext>输入参数的 API 初始化 XAML 读取器或 XAML 编写器，则隐式创建相同的默认 XAML 架构上下文。

默认 XAML 架构上下文依赖于 CLR 反射的类型映射行为。 这包括检查定义的 CLR<xref:System.Type>和相关<xref:System.Reflection.PropertyInfo>或<xref:System.Reflection.MethodInfo>。 此外，使用类型或成员的 CLR 归因来填写使用 CLR 支持类型的 XAML 类型或 XAML 成员信息的详细信息。 默认 XAML 架构上下文不需要类型系统扩展技术（如`Invoker`模式），因为 CLR 类型系统提供了必要的信息。

对于程序集加载逻辑，默认 XAML 架构上下文主要依赖于 XAML 命名空间映射中提供的任何程序集值。 此外，<xref:System.Xaml.XamlReaderSettings.LocalAssembly%2A>还可以提示要加载的程序集，用于加载内部类型等方案。

## <a name="wpf-xaml-schema-context"></a>WPF XAML 架构上下文

本主题将介绍 WPF XAML 架构上下文，因为 WPF 实现提供了通过实现非默认 XAML 架构上下文可以引入的功能类型的有趣说明。 此外，解决 WPF XAML 的 WPF 文档中没有过多讨论 XAML 架构上下文概念;仅当与讨论默认 XAML 架构上下文的工作原理集成时，XAML 架构上下文启用的行为可能完全可以理解。 WPF XAML 架构上下文实现以下行为。

**查找覆盖：** WPF 具有一些适用于 XAML 的内容模型，其中有 XAML 内容<xref:System.Windows.Markup.ContentPropertyAttribute>属性，这些属性在不被归因的情况下起作用。 <xref:System.Xaml.XamlType.LookupContentProperty%2A>覆盖 WPF 实现此行为。

**WPF 表达式的延迟：** WPF 具有多个表达式类，这些表达式类将值延迟到运行时上下文可用。 此外，模板扩展是依赖于延迟技术的运行时行为。

**类型系统查找优化：** WPF 具有广泛的 XAML 词汇表和对象模型，包括继承到数百个 WPF 定义的类的基类成员定义。 此外，WPF 本身分布在多个程序集中。 WPF 使用查找表和其他技术优化其类型查找。 这提供了与默认 XAML 架构上下文及其基于 CLR 的类型查找的性能改进。 在查找表中不存在类型的情况下，行为使用类似于默认 XAML 架构上下文的 XAML 架构上下文技术。

**XamlType 和 Xaml 成员扩展：** WPF 扩展具有依赖项属性的属性概念，以及具有路由事件的事件概念。 为了给这些概念提供 XAML 处理操作的更大可见性，WPF <xref:System.Xaml.XamlType> <xref:System.Xaml.XamlMember>扩展 和，并添加报告依赖项属性和路由事件特征的内部属性。

### <a name="accessing-the-wpf-xaml-schema-context"></a>访问 WPF XAML 架构上下文

如果您使用的是基于 WPF<xref:System.Windows.Markup.XamlReader?displayProperty=nameWithType>或<xref:System.Windows.Markup.XamlWriter?displayProperty=nameWithType>的 XAML 技术，则 WPF XAML 架构上下文已在这些 XAML 读取器和 XAML 编写器实现上使用。

如果使用其他未使用 WPF XAML 架构上下文初始化的 XAML 读取器或 XAML 编写器实现，则可以从<xref:System.Windows.Markup.XamlReader.GetWpfSchemaContext%2A?displayProperty=nameWithType>获取工作 WPF XAML 架构上下文。 然后，可以将此值用作使用 的其他 API 的初始化<xref:System.Xaml.XamlSchemaContext>。 例如，您可以调用<xref:System.Xaml.XamlXmlReader.%23ctor%2A>初始化并传递 WPF XAML 架构上下文。 或者，您可以将 WPF XAML 架构上下文用于 XAML 类型系统操作。 这可能包括<xref:System.Xaml.XamlType>或<xref:System.Xaml.XamlMember>的构造初始化或调用<xref:System.Xaml.XamlSchemaContext.GetXamlType%2A?displayProperty=nameWithType>。

请注意，如果从纯 XAML 节点流的角度来看访问 WPF XAML 的某些方面，则某些 WPF 框架功能可能尚未执行。 例如，尚未应用控件的 WPF 模板。 因此，如果您访问在运行时可能使用完整可视化树填充的属性，则可能只看到引用模板的属性值。 如果从非运行时情况提供，则为 WPF 标记扩展提供的服务上下文也可能不准确，并且在尝试写入对象图时可能会导致异常。

## <a name="xaml-and-assembly-loading"></a>XAML 和装配负载

XAML 和 .NET XAML 服务的程序集加载与 CLR 定义的概<xref:System.AppDomain>念集成在一起。 XAML 架构上下文根据 使用<xref:System.AppDomain>和其他因素解释如何在运行时或设计时加载程序集或查找类型。 逻辑略有不同，具体取决于 XAML 对于 XAML 读取器是松散的 XAML，XAML 是否由`XamlBuildTask`编译为 DLL，还是由 WPF 生成的`PresentationBuildTask`BAML。

WPF 的 XAML 架构上下文与 WPF 应用程序模型集成，而<xref:System.AppDomain>WPF 应用程序模型又使用 WPF 实现详细信息的其他因素。

#### <a name="xaml-reader-input-loose-xaml"></a>XAML读卡器输入（松散 XAML）

01. XAML 架构上下文遍达<xref:System.AppDomain>应用程序，查找与名称的所有方面匹配的已加载程序集，从最近加载的程序集开始。 如果找到匹配项，则该程序集用于解析。

02. 否则，基于 CLR <xref:System.Reflection.Assembly> API 的以下技术之一用于加载程序集：

    - 如果名称在映射中限定，则调用<xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>限定名称。

    - 如果上一步骤失败，请使用短名称（如果存在公钥令牌）调用<xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>。

    - 如果名称在映射中为非限定，请<xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=nameWithType>调用 。

#### <a name="xamlbuildtask"></a>XamlBuildTask

`XamlBuildTask`用于 Windows 通信基础 （WCF） 和 Windows 工作流基础。

请注意，通过的`XamlBuildTask`程序集引用始终完全限定。

1. 调用<xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>限定名称。

2. 如果上一步骤失败，请使用短名称（如果存在公钥令牌）调用<xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>。

#### <a name="baml-presentationbuildtask"></a>BAML（演示构建任务）

BAML 的程序集加载有两个方面：加载包含 BAML 作为组件的初始程序集，以及为 BAML 生产引用的任何类型的类型加载类型支持程序集。

##### <a name="assembly-load-for-initial-markup"></a>初始标记的装配负载：

对程序集的引用始终不限定以加载标记。

1. WPF XAML 架构上下文遍达 WPF 应用程序的，<xref:System.AppDomain>查找与名称的所有方面匹配的已加载程序集，从最近加载的程序集开始。 如果找到匹配项，则该程序集用于解析。

2. 如果上一步骤失败，请使用短名称（如果存在公钥令牌）调用<xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>。

##### <a name="assembly-references-by-baml-types"></a>按 BAML 类型进行的程序集引用：

作为生成任务的输出，BAML 生产中使用的类型的程序集引用始终完全限定。

01. WPF XAML 架构上下文遍达 WPF 应用程序的，<xref:System.AppDomain>查找与名称的所有方面匹配的已加载程序集，从最近加载的程序集开始。 如果找到匹配项，则该程序集用于解析。

02. 否则，使用以下技术之一加载程序集：

    - 调用<xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>限定名称。
  
    - 如果短名称 + 公钥令牌组合与从 BAML 加载的程序集匹配，请使用该程序集。

    - 使用短名称 + 公钥令牌<xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>调用 。

## <a name="see-also"></a>请参阅

- [了解 XAML 节点流结构和概念](understanding-xaml-node-stream-structures-and-concepts.md)
