---
title: ".NET Framework XAML 服务的 XAML 命名空间"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e4f15f13-c420-4c1e-aeab-9b6f50212047
caps.latest.revision: "3"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: e09279209bf3d6925b61d55d6988b5af658f5aab
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="xaml-namespaces-for-net-framework-xaml-services"></a>.NET Framework XAML 服务的 XAML 命名空间
XAML 命名空间是扩展的 XML 命名空间定义一个概念。 类似于 XML 命名空间，你可以定义 XAML 命名空间使用`xmlns`标记中的属性。 XAML 命名空间还表示 XAML 节点流和其他 XAML 服务 Api 中。 本主题定义 XAML 命名空间概念，并介绍如何 XAML 命名空间可以定义和使用的 XAML 架构上下文和.NET Framework XAML 服务的其他方面。  
  
## <a name="xml-namespace-and-xaml-namespace"></a>XML Namespace 和 XAML Namespace  
 XAML 命名空间是专用的 XML 命名空间，就像 XAML 是一种特殊的形式的 XML，并用于其标记的基本 XML 格式。 在标记中，声明 XAML 命名空间，通过映射`xmlns`应用于某个元素的属性。 `xmlns`可以对同一 XAML 命名空间声明中的元素进行声明。 对元素的 XAML 命名空间声明可用于该元素，该元素的所有特性和该元素的所有子级。 属性可以使用不包含属性的元素相同处理程序，但前提是属性名称本身引用前缀中标记其属性名称的一部分的 XAML 命名空间。  
  
 XAML 命名空间而不是 XML 命名空间的区别是 XML 命名空间可能用于引用架构，或可能用于只需区分实体。 对于 XAML 的类型和成员，因为 XAML 中使用最终必须解析为后备类型，并很好地适应此功能不适用于 XML 架构概念。 XAML 命名空间包含的 XAML 架构上下文必须具有可用才能执行此类型映射信息。  
  
## <a name="xaml-namespace-components"></a>XAML Namespace 组件  
 XAML 命名空间定义具有两个组件： 前缀和标识符。 每个组件都存在时在标记中，声明 XAML 命名空间或将其在 XAML 类型系统中定义。  
  
 前缀可以是任意字符串，如允许的[W3C XML 1.0 规范中的命名空间](http://go.microsoft.com/fwlink/?LinkID=161735)。 按照约定的前缀是通常很短字符串，因为前缀在典型的标记文件中重复多次。 某些旨在用于多个 XAML 实现的 XAML 命名空间使用特定的传统前缀。 例如，在 XAML 语言 XAML 命名空间通常映射使用前缀`x`。 你可以定义默认 XAML 命名空间，其中前缀定义中不提供，但如果定义或查询 by.NET Framework XAML 服务 API 都表示为一个空字符串。 通常情况下，才能升级以最大化模式的量前缀省略有意选择默认 XAML 命名空间的 XAML 实现的一种技术及其方案和词汇表的标记。  
  
 标识符可以是任意字符串，如允许的[W3C XML 1.0 规范中的命名空间](http://go.microsoft.com/fwlink/?LinkID=161735)。 按照约定，标识符的 XML 命名空间或 XAML 命名空间通常提供 URI 形式中通常作为协议限定的绝对 URI。 通常情况下，定义的特定 XAML 词汇的版本信息会进行隐式作为路径字符串的一部分。 XAML 命名空间添加到 XML URI 约定之外其他标识符约定。 对于 XAML 命名空间中，标识符进行通信，以便解析类型指定为下 XAML 命名空间，元素或特性解析为成员需要 XAML 架构上下文的信息。  
  
 为了信息传达给 XAML 架构上下文，URI 形式可能仍是 XAML 命名空间的标识符。 但是，在这种情况下 URI 也声明为特定的程序集或程序集的列表中的匹配标识符。 将执行此操作的程序集通过特性化的程序集中<xref:System.Windows.Markup.XmlnsDefinitionAttribute>。 通过在.NET Framework XAML 服务的默认 XAML 架构上下文来支持此方法确定的 XAML 命名空间并在属性化程序集中支持的基于 CLR 的类型解析行为。 一般来说，此约定可用于 XAML 架构上下文包含 CLR 或基于为读取从 CLR 程序集的 CLR 属性是必需的默认 XAML 架构上下文的情况。  
  
 XAML 命名空间也可以通过通信 CLR 命名空间和类型定义的程序集的约定来识别。 未在情况下使用此约定<xref:System.Windows.Markup.XmlnsDefinitionAttribute>归属中包含类型的程序集存在。 此约定可能比 URI 约定中，更复杂，也可能会有多义性和复制，因为有多种方法来引用程序集。  
  
 使用的 CLR 命名空间和程序集约定的标识符的最基本形式如下所示：  
  
 `clr-namespace:`*clrnsName* `; assembly=` *程序集*  
  
 `clr-namespace:`和`; assembly=`是文本的语法组件。  
  
 *clrnsName*是标识的 CLR 命名空间的字符串名称。 此字符串名称包括提供有关的 CLR 命名空间和及其与其他 CLR 命名空间的关系的提示的任何内部圆点字符 （.）。  
  
 *程序集*是定义可在 XAML 中的类型的程序集的字符串名称。 要通过声明 XAML 命名空间访问的类型应由程序集定义并专门在指定的 CLR 命名空间内声明*clrnsName*。 此字符串名称通常与信息报告的<xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType>。  
  
 更完整的 CLR 命名空间和程序集约定定义如下所示：  
  
 `clr-namespace:`*clrnsName* `; assembly=` *程序集名称*  
  
 *assemblyName*表示作为是合法的任何字符串<xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>输入。 此字符串可以包含区域性、 公钥或版本信息 (这些概念的定义中的参考主题定义<xref:System.Reflection.Assembly>)。 COFF 格式和证据 (如使用的其他重载<xref:System.Reflection.Assembly.Load%2A>) 不相关的 XAML 程序集加载目的; 所有加载信息必须都显示为字符串。  
  
 指定程序集的公共密钥是有用的技术进行 XAML 安全，或者为了删除如果程序集加载的简单名称，或者预存在缓存或应用程序域中可以存在的可能不明确性。 有关详细信息，请参阅[XAML 安全注意事项](../../../docs/framework/xaml-services/xaml-security-considerations.md)。  
  
## <a name="xaml-namespace-declarations-in-the-xaml-services-api"></a>XAML 服务 API 中的 XAML Namespace 声明  
 在 XAML 服务 API 中，由 XAML 命名空间声明<xref:System.Xaml.NamespaceDeclaration>对象。 如果你声明的 XAML 命名空间中的代码，则调用<xref:System.Xaml.NamespaceDeclaration.%23ctor%28System.String%2CSystem.String%29>构造函数。 `ns`和`prefix`参数被指定为字符串，而要为这些参数提供的输入对应于 XAML 命名空间标识符和 XAML 命名空间前缀的定义中，如本主题中前面提供。  
  
 如果您要检查 XAML 命名空间信息以作为一部分的 XAML 节点流，或通过 XAML 类型系统，其他访问<xref:System.Xaml.NamespaceDeclaration.Namespace%2A?displayProperty=nameWithType>报告 XAML 命名空间标识符，和<xref:System.Xaml.NamespaceDeclaration.Prefix%2A?displayProperty=nameWithType>报告的 XAML 命名空间前缀。  
  
 在 XAML 节点流，XAML 命名空间信息可以显示为前面它所应用于实体的 XAML 节点。 这包括其中之前的 XAML 命名空间信息的情况下`StartObject`的 XAML 根元素。 有关更多信息，请参见 [Understanding XAML Node Stream Structures and Concepts](../../../docs/framework/xaml-services/understanding-xaml-node-stream-structures-and-concepts.md)。  
  
 对于使用.NET Framework XAML 服务 API 的许多方案，应至少一个 XAML 命名空间声明存在，并且声明必须包含或指所需的 XAML 架构上下文的信息。 XAML 命名空间必须指定要加载的或帮助解决集中命名空间和已加载或 XAML 架构上下文中的已知的程序集的特定类型的程序集。  
  
 若要生成 XAML 节点流，XAML 类型信息必须可用，通过 XAML 架构上下文。 先确定要创建每个节点相关的 XAML 命名空间，无法确定的 XAML 类型信息。 此时，没有的类型创建实例，但 XAML 架构上下文可能需要查找来自定义程序集和备份类型的信息。 例如，为了处理标记`<Party><PartyFavor/></Party>`，XAML 架构上下文必须能够确定的名称和类型`ContentProperty`的`Party`，因此还必须知道的 XAML 命名空间信息`Party`和`PartyFavor`。 对于默认 XAML 架构上下文，静态的反射会报告很多在节点流中生成 XAML 类型节点所需的 XAML 类型系统信息。  
  
 为了从 XAML 节点流中生成对象图，请 XAML 命名空间声明必须存在的每个 XAML 前缀在 XAML 节点流中记录和原始标记中使用。 此时，正在创建实例，并且出现 true 的类型映射行为。  
  
 如果你需要用于预先填充 XAML 命名空间信息，请在标记中，不定义你想要使用的 XAML 架构上下文的 XAML 命名空间的情况下可以使用的一种方法是声明中的 XML 命名空间声明<xref:System.Xml.XmlParserContext>为<xref:System.Xml.XmlReader>. 然后使用该<xref:System.Xml.XmlReader>作为输入的 XAML 读取器构造函数，或<xref:System.Xaml.XamlServices.Load%28System.Xml.XmlReader%29?displayProperty=nameWithType>。  
  
 在.NET Framework XAML 服务中处理的 XAML 命名空间相关的两个其他 API 是属性<xref:System.Windows.Markup.XmlnsDefinitionAttribute>和<xref:System.Windows.Markup.XmlnsPrefixAttribute>。 这些属性应用于程序集。 <xref:System.Windows.Markup.XmlnsDefinitionAttribute>用于 XAML 架构上下文解释包括一个 URI 的任何 XAML 命名空间声明。 <xref:System.Windows.Markup.XmlnsPrefixAttribute>使用发出 XAML，特定 XAML 命名空间就可序列化可预测的前缀的工具。 有关详细信息，请参阅[的自定义类型和库的 XAML-Related CLR 特性](../../../docs/framework/xaml-services/xaml-related-clr-attributes-for-custom-types-and-libraries.md)。  
  
## <a name="see-also"></a>另请参阅  
 [了解 XAML 节点流结构和概念](../../../docs/framework/xaml-services/understanding-xaml-node-stream-structures-and-concepts.md)
