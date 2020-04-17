---
title: .NET XAML 服务的 XAML 命名空间
ms.date: 03/30/2017
ms.assetid: e4f15f13-c420-4c1e-aeab-9b6f50212047
ms.openlocfilehash: 2ae57d08fade85c59fea2a54b653a2f775b57415
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "81433060"
---
# <a name="xaml-namespaces-for-net-xaml-services"></a>.NET XAML 服务的 XAML 命名空间
XAML 命名空间是一个扩展 XML 命名空间定义的概念。 与 XML 命名空间类似，可以使用标记中`xmlns`的属性定义 XAML 命名空间。 XAML 命名空间也表示在 XAML 节点流和其他 XAML 服务 API 中。 本主题定义了 XAML 命名空间概念，并介绍了如何定义 XAML 命名空间并由 XAML 架构上下文和 .NET XAML 服务的其他方面使用。  
  
## <a name="xml-namespace-and-xaml-namespace"></a>XML 命名空间和 XAML 命名空间  
 XAML 命名空间是一个专门的 XML 命名空间，就像 XAML 是 XML 的专用形式，并使用基本的 XML 形式进行标记一样。 在标记中，通过应用于元素`xmlns`的属性声明 XAML 命名空间及其映射。 可以`xmlns`对声明 XAML 命名空间的同一元素进行声明。 对元素所做的 XAML 命名空间声明对该元素、该元素的所有属性以及该元素的所有子级都有效。 属性可以使用与包含该属性的元素不相同的 XAML 命名空间，只要属性名称本身在标记中引用前缀作为其属性名称的一部分。  
  
 XAML 命名空间与 XML 命名空间的区别是，XML 命名空间可用于引用架构或仅用于区分实体。 对于 XAML，XAML 中使用的类型和成员最终必须解析为支持类型，并且 XML 架构概念不能很好地应用于此功能。 XAML 命名空间包含 XAML 架构上下文必须具有的信息，以便执行此类型映射。  
  
## <a name="xaml-namespace-components"></a>XAML 命名空间组件  
 XAML 命名空间定义有两个组件：前缀和标识符。 当在标记中声明 XAML 命名空间或在 XAML 类型系统中定义时，每个组件都存在。  
  
 前缀可以是[XML 1.0 规范中 W3C 命名空间](https://www.w3.org/TR/REC-xml-names/)允许的任何字符串。 按照惯例，前缀通常是短字符串，因为前缀在典型的标记文件中重复多次。 某些用于多个 XAML 实现中的 XAML 命名空间使用特定的常规前缀。 例如，XAML 语言 XAML 命名空间通常使用前缀`x`进行映射。 您可以定义默认的 XAML 命名空间，其中前缀在定义中未给出，但如果by.NET XAML 服务 API 定义或查询，则表示为空字符串。 通常，特意选择默认 XAML 命名空间，以便 XAML 实现技术及其方案和词汇量最大限度地省略标记。  
  
 标识符可以是[XML 1.0 规范中 W3C 命名空间](https://www.w3.org/TR/REC-xml-names/)允许的任何字符串。 按照惯例，XML 命名空间或 XAML 命名空间的标识符通常以 URI 形式提供，通常作为协议限定的绝对 URI。 通常，定义特定 XAML 词汇表的版本信息作为路径字符串的一部分隐含。 XAML 命名空间添加除 XML URI 约定之外的其他标识符约定。 对于 XAML 命名空间，标识符传达 XAML 架构上下文所需的信息，以便解析在 XAML 命名空间下指定为元素的类型，或向成员解析属性。  
  
 为了将信息传达给 XAML 架构上下文，XAML 命名空间的标识符可能仍以 URI 形式。 但是，在这种情况下，URI 也声明为特定程序集或程序集列表中的匹配标识符。 这是通过在装配体中分配 程序集来实现<xref:System.Windows.Markup.XmlnsDefinitionAttribute>的。 在 .NET XAML 服务中，默认的 XAML 架构上下文支持此方法，用于标识 XAML 命名空间和在属性程序集中支持基于 CLR 的类型解析行为。 更一般情况下，此约定可用于 XAML 架构上下文合并 CLR 或基于默认 XAML 架构上下文的情况，这是从 CLR 程序集读取 CLR 属性所必需的。  
  
 XAML 命名空间也可以由通信 CLR 命名空间和类型定义程序集的约定标识。 此约定用于包含类型的程序集中不存在<xref:System.Windows.Markup.XmlnsDefinitionAttribute>归因的情况。 此约定可能比 URI 约定复杂，并且具有歧义和重复的可能性，因为有多种方式引用程序集。  
  
 使用 CLR 命名空间和程序集约定的标识符的最基本形式如下：  
  
 `clr-namespace:clrnsName; assembly=assemblyShortName`
  
 `clr-namespace:`是`; assembly=`语法的文本组件。  
  
 *clrnsName*是标识 CLR 命名空间的字符串名称。 此字符串名称包括任何内部点字符 （.），这些字符提供有关 CLR 命名空间及其与其他 CLR 命名空间的关系的提示。
  
 *程序集ShortName*是定义 XAML 中有用的类型的程序集的字符串名称。 要通过声明的 XAML 命名空间访问的类型应由程序集定义，并在*clrnsName*指定的 CLR 命名空间中声明。 此字符串名称通常与 报告<xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType>的信息并行。  
  
 CLR 命名空间和程序集约定的更完整定义如下：  
  
 `clr-namespace:clrnsName; assembly=assemblyName`
  
 *程序集名称*表示作为<xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>输入合法的任何字符串。 此字符串可以包括区域性、公钥或版本信息（这些概念的定义在<xref:System.Reflection.Assembly>的参考主题中定义。 COFF 格式和证据（如其他过载使用<xref:System.Reflection.Assembly.Load%2A>）与 XAML 程序集加载目的无关;所有加载信息必须作为字符串显示。  
  
 为程序集指定公钥是 XAML 安全性的有用技术，或者用于删除如果程序集以简单名称加载或预先存在于缓存或应用程序域中可能存在的歧义。 有关详细信息，请参阅[XAML 安全注意事项](security-considerations.md)。  
  
## <a name="xaml-namespace-declarations-in-the-xaml-services-api"></a>XAML 服务 API 中的 XAML 命名空间声明  
 在 XAML 服务 API 中，XAML 命名空间声明<xref:System.Xaml.NamespaceDeclaration>由对象表示。 如果要在代码中声明 XAML 命名空间，则调用<xref:System.Xaml.NamespaceDeclaration.%23ctor%28System.String%2CSystem.String%29>构造函数。 和`ns``prefix`参数指定为字符串，提供这些参数的输入对应于本主题中前面提供的 XAML 命名空间标识符和 XAML 命名空间前缀的定义。  
  
 如果要作为 XAML 节点流的一部分或通过对 XAML 类型系统的其他访问来检查 XAML 命名<xref:System.Xaml.NamespaceDeclaration.Namespace%2A?displayProperty=nameWithType>空间信息，则报告 XAML<xref:System.Xaml.NamespaceDeclaration.Prefix%2A?displayProperty=nameWithType>命名空间标识符，并报告 XAML 命名空间前缀。  
  
 在 XAML 节点流中，XAML 命名空间信息可以显示为 XAML 节点，该节点位于它所应用的实体之前。 这包括 XAML 命名空间信息在 XAML`StartObject`根元素之前的情况。 有关更多信息，请参见 [Understanding XAML Node Stream Structures and Concepts](understanding-xaml-node-stream-structures-and-concepts.md)。  
  
 对于许多使用 .NET XAML 服务 API 的方案，预计至少存在一个 XAML 命名空间声明，并且声明必须包含或引用 XAML 架构上下文所需的信息。 XAML 命名空间必须指定要加载的程序集，或者帮助解析命名空间和程序集中已加载或 XAML 架构上下文已知的特定类型。  
  
 为了生成 XAML 节点流，必须通过 XAML 架构上下文提供 XAML 类型信息。 如果不首先确定要创建的每个节点的相关 XAML 命名空间，则无法确定 XAML 类型信息。 此时，尚未创建类型实例，但 XAML 架构上下文可能需要从定义程序集和备份类型中查找信息。 例如`<Party><PartyFavor/></Party>`，为了处理标记，XAML 架构上下文必须能够确定`ContentProperty`的名称`Party`和类型，因此还必须知道`Party`和`PartyFavor`的 XAML 命名空间信息。 对于默认 XAML 架构上下文，静态反射报告在节点流中生成 XAML 类型节点所需的许多 XAML 类型系统信息。  
  
 为了从 XAML 节点流生成对象图，必须在原始标记中使用的每个 XAML 前缀中存在 XAML 命名空间声明，并记录在 XAML 节点流中。 此时，将创建实例，并发生真正的类型映射行为。  
  
 如果需要预填充 XAML 命名空间信息，在标记中未定义要使用 XAML 架构上下文的 XAML 命名空间的情况下，可以使用的一种技术是在<xref:System.Xml.XmlParserContext>中声明<xref:System.Xml.XmlReader>的 XML 命名空间声明。 然后，使用<xref:System.Xml.XmlReader>它作为 XAML 读取器构造函数的<xref:System.Xaml.XamlServices.Load%28System.Xml.XmlReader%29?displayProperty=nameWithType>输入，或 。  
  
 在 .NET XAML 服务中与 XAML 命名空间处理相关的另外两个<xref:System.Windows.Markup.XmlnsDefinitionAttribute> <xref:System.Windows.Markup.XmlnsPrefixAttribute>API 是属性和 。 这些属性适用于程序集。 <xref:System.Windows.Markup.XmlnsDefinitionAttribute>XAML 架构上下文用于解释包含 URI 的任何 XAML 命名空间声明。 <xref:System.Windows.Markup.XmlnsPrefixAttribute>由发出 XAML 的工具使用，以便可以使用可预测的前缀序列化特定的 XAML 命名空间。 有关详细信息，请参阅[自定义类型和库的 XAML 相关 CLR 属性](clr-attributes-with-custom-types-and-libraries.md)。  
  
## <a name="see-also"></a>请参阅

- [了解 XAML 节点流结构和概念](understanding-xaml-node-stream-structures-and-concepts.md)
