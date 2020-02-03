---
title: 序列化
ms.date: 10/22/2008
ms.technology: dotnet-standard
ms.assetid: bebb27ac-9712-4196-9931-de19fc04dbac
ms.openlocfilehash: d29a7bc9f304b8d19e8af593166b8d847117424f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743630"
---
# <a name="serialization"></a>序列化
序列化是指将对象转换为可随时保存或传输的格式的过程。 例如，可以将对象序列化，使用 HTTP 在 Internet 上传输它，并在目标计算机上对其进行反序列化。

 .NET Framework 提供了针对各种序列化方案进行优化的三种主要序列化技术。 下表列出了这些技术以及与这些技术相关的主要框架类型。

|**技术名称**|**主要类型**|**方案**|
|-------------------------|--------------------|-------------------|
|**数据协定序列化**|<xref:System.Runtime.Serialization.DataContractAttribute> <br /> <xref:System.Runtime.Serialization.DataMemberAttribute> <br /> <xref:System.Runtime.Serialization.DataContractSerializer> <br /> <xref:System.Runtime.Serialization.NetDataContractSerializer> <br /> <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> <br /> <xref:System.Runtime.Serialization.ISerializable>|常规持久性<br />Web 服务<br />JSON|
|**XML 序列化**|<xref:System.Xml.Serialization.XmlSerializer>|对 XML 的结构具有完全控制的 XML 格式|
|**运行时序列化（二进制和 SOAP）**|<xref:System.SerializableAttribute> <br /> <xref:System.Runtime.Serialization.ISerializable> <br /> <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> <br /> <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>|.NET 远程处理|

 ✔️在设计新类型时要考虑序列化。

## <a name="choosing-the-right-serialization-technology-to-support"></a>选择要支持的合适的序列化技术
 ✔️如果可能需要在 Web 服务中保留或使用类型的实例，则应考虑支持数据协定序列化。

 如果需要对序列化类型时生成的 XML 格式进行更好的控制，✔️应考虑支持 XML 序列化，而不是或除了数据协定序列化。

 在某些互操作性场景中，这可能是必要的，在这些场景中，需要使用数据协定序列化不支持的 XML 构造，例如，生成 XML 属性。

 ✔️如果您的类型的实例需要跨 .NET 远程处理边界传递，则应考虑支持运行时序列化。

 ❌ 避免仅出于一般持久性原因而支持运行时序列化或 XML 序列化。 建议使用数据协定序列化。

## <a name="supporting-data-contract-serialization"></a>支持数据协定序列化
 类型可通过将 <xref:System.Runtime.Serialization.DataContractAttribute> 应用 <xref:System.Runtime.Serialization.DataMemberAttribute> 到类型的成员（字段和属性），来支持数据协定序列化。

 如果类型可用于部分信任，✔️考虑将类型为 public 的数据成员标记为公共。

 在完全信任的环境中，数据协定序列化程序可以序列化和反序列化非公共类型和成员，但在部分信任的环境中，只能序列化和反序列化公共成员。

 ✔️对所有已 <xref:System.Runtime.Serialization.DataMemberAttribute>的属性实现 getter 和 setter。 数据协定序列化程序需要将类型的 getter 和 setter 视为可序列化。 （在 .NET Framework 3.5 SP1 中，某些集合属性可以是只能获取的。）如果在部分信任环境中不使用该类型，则属性访问器中的一个或两个都可以是非公共的。

 ✔️考虑使用序列化回调来初始化已反序列化的实例。

 反序列化对象时，不调用任何构造函数。 （规则有例外。 在反序列化期间将调用标记为 <xref:System.Runtime.Serialization.CollectionDataContractAttribute> 的集合的构造函数。）因此，在正常构造期间执行的任何逻辑都需要作为一个序列化回调实现。

 `OnDeserializedAttribute` 是最常用的回调特性。 此系列中的其他属性还有 <xref:System.Runtime.Serialization.OnDeserializingAttribute>、<xref:System.Runtime.Serialization.OnSerializingAttribute> 和 <xref:System.Runtime.Serialization.OnSerializedAttribute>。 这些特性可分别用来标记在反序列化之前、序列化之前以及序列化之后执行的回调。

 ✔️考虑使用 <xref:System.Runtime.Serialization.KnownTypeAttribute> 指示在反序列化复杂对象图时应使用的具体类型。

 ✔️在创建或更改可序列化类型时，请考虑向后和向前兼容性。

 请记住，类型的未来版本的序列化流可反序列化为该类型的当前版本，反之亦然。

 请确保了解，数据成员（即使是私有的和内部的）在类型的未来版本中不能更改其名称、类型甚至顺序，除非特别注意使用数据协定特性的显式参数来保留协定。

 对可序列化类型进行更改时测试序列化的兼容性。 尝试将新版本反序列化为旧版本，以及将旧版本反序列化为新版本。

 ✔️考虑实现 <xref:System.Runtime.Serialization.IExtensibleDataObject>，以允许在类型的不同版本之间进行往返。

 序列化程序可通过此接口确保在转换期间不丢失任何数据。 <xref:System.Runtime.Serialization.IExtensibleDataObject.ExtensionData%2A?displayProperty=nameWithType> 属性用于存储来自当前版本未知的类型的未来版本的任何数据，因此它不能将它存储在其数据成员中。 当前版本随后被序列化并反序列化为未来版本时，附加数据将在序列化流中可用。

## <a name="supporting-xml-serialization"></a>支持 XML 序列化
 数据协定序列化是 .NET Framework 中的主要（默认）序列化技术，但也存在数据协定序列化不支持的序列化场景。 例如，它不能让您完全控制序列化程序生成或使用的 XML 的形状。 如果需要这样的精细控制，则必须使用 XML 序列化，并且需要设计类型以支持此序列化技术。

 ❌ 避免专门设计用于 XML 序列化的类型，除非您有很强的理由来控制生成的 XML 的形状。 此序列化技术已被上一节中讨论的数据协定序列化所取代。

 如果需要更好地控制序列化 XML 的形状，而不是应用 XML 序列化属性所提供的内容，则✔️考虑实现 <xref:System.Xml.Serialization.IXmlSerializable> 接口。 接口的两个方法（<xref:System.Xml.Serialization.IXmlSerializable.ReadXml%2A> 和 <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A>）允许你完全控制序列化的 XML 流。 还可以通过应用 `XmlSchemaProviderAttribute`来控制为类型生成的 XML 架构。

## <a name="supporting-runtime-serialization"></a>支持运行时序列化
 运行时序列化是 .NET Remoting 使用的技术。 如果你认为你的类型将使用 .NET Remoting 传输，则需要确保它们支持运行时序列化。

 可以通过应用 <xref:System.SerializableAttribute>提供对运行时序列化的基本支持，更高级的方案涉及实现一个简单的运行时可序列化模式（实现 <xref:System.Runtime.Serialization.ISerializable> 并提供序列化构造函数）。

 ✔️如果你的类型将与 .NET 远程处理一起使用，请考虑支持运行时序列化。 例如，<xref:System.AddIn?displayProperty=nameWithType> 命名空间使用 .NET 远程处理，因此在 `System.AddIn` 外接程序之间交换的所有类型都需要支持运行时序列化。

 如果希望完全控制序列化过程，✔️应考虑实现运行时可序列化模式。 例如，如果需要在对数据进行序列化或反序列化时转换数据。

 此模式非常简单。 您需要执行的全部操作就是实现 <xref:System.Runtime.Serialization.ISerializable> 接口，并提供在反序列化对象时使用的特殊构造函数。

 ✔️使序列化构造函数受到保护，并严格按照此处的示例中所示，提供两个类型和命名的参数。

```csharp
[Serializable]
public class Person : ISerializable
{
    protected Person(SerializationInfo info, StreamingContext context)
    {
        // ...
    }
}
```

 ✔️确实要显式实现 <xref:System.Runtime.Serialization.ISerializable> 成员。

 ✔️将链接要求应用到 <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=nameWithType> 实现。 这可确保只有完全受信任的核心和运行时序列化程序才能访问成员。

 *部分©2005，2009 Microsoft Corporation。保留所有权利。*

 *在 Pearson Education, Inc. 授权下，由 Addison-Wesley Professional 作为 Microsoft Windows 开发系列的一部分再版自 [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)（Framework 设计准则：可重用 .NET 库的约定、惯例和模式第 2 版），由 Krzysztof Cwalina 和 Brad Abrams 发布于 2008 年 10 月 22 日。

## <a name="see-also"></a>另请参阅

- [框架设计指南](../../../docs/standard/design-guidelines/index.md)
- [使用准则](../../../docs/standard/design-guidelines/usage-guidelines.md)
