---
title: Serialization1
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: bebb27ac-9712-4196-9931-de19fc04dbac
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fd66f8d8589baaa6fc5e22ce0b68beafac916fdf
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "44087113"
---
# <a name="serialization"></a>序列化
序列化是将对象转换为可以轻松地保持或传输的格式的过程。例如，可以将对象序列化，使用 HTTP 在 Internet 上传输它，并在目标计算机上对其进行反序列化。
  
 .NET Framework 提供了针对各种序列化方案进行了优化的三种主要序列化技术。下表列出了这些技术以及与这些技术相关的主要框架类型。  
  
|**技术名称**|**主要类型**|**方案**|  
|-------------------------|--------------------|-------------------|  
|**数据协定序列化**|<xref:System.Runtime.Serialization.DataContractAttribute> <br /> <xref:System.Runtime.Serialization.DataMemberAttribute> <br /> <xref:System.Runtime.Serialization.DataContractSerializer> <br /> <xref:System.Runtime.Serialization.NetDataContractSerializer> <br /> <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> <br /> <xref:System.Runtime.Serialization.ISerializable>|常规持久性<br />Web 服务<br />JSON|  
|**XML 序列化**|<xref:System.Xml.Serialization.XmlSerializer>|对 XML 的结构具有完全控制的 XML 格式|  
|**运行时序列化 （二进制和 SOAP）**|<xref:System.SerializableAttribute> <br /> <xref:System.Runtime.Serialization.ISerializable> <br /> <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> <br /> <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>|.NET Remoting|

**✓ 务必** 在设计新类型时考虑序列化。

## <a name="choosing-the-right-serialization-technology-to-support"></a>选择要支持的合适的序列化技术  
**✓ 考虑** 支持数据协定序列化，如果类型的实例可能需要持久化或在 Web 服务中使用。  

**✓ 考虑** 如果您需要对序列化类型时生成的XML格式进行更多控制，则支持 XML 序列化，而不是数据协定序列化，或者除了数据协定序列化之外。  

在某些互操作性场景中，这可能是必要的，在这些场景中，您需要使用数据协定序列化不支持的 XML 构造，例如，生成 XML 属性。

**✓ 考虑** 如果您的类型的实例需要跨 .NET Remoting 边界传输，则支持运行时序列化。

**X 避免** 只是为了一般持久性原因而支持运行时序列化或 XML 序列化。应更倾向使用数据协定序列化。  

## <a name="supporting-data-contract-serialization"></a>支持数据协定序列化
类型可以通过对类型应用 <xref:System.Runtime.Serialization.DataContractAttribute> 和对类型的成员（字段和属性）应用 <xref:System.Runtime.Serialization.DataMemberAttribute> 来支持数据协定序列化。
  
**✓ 考虑** 如果可以在部分信任环境中使用该类型，则将类型的数据成员标记为公共的。

在完全信任的环境中，数据协定序列化程序可以序列化和反序列化非公共类型和成员，但在部分信任的环境中，只有公共成员可以被序列化和反序列化。
  
**✓ 务必** 在所有具有 <xref:System.Runtime.Serialization.DataMemberAttribute> 的属性上实现 getter 和 setter。数据协定序列化程序需要将类型的 getter 和 setter 视为可序列化的。（在 .NET Framework 3.5 SP1 中，某些集合属性可以是只读的。）如果该类型不会在部分信任环境下使用，则这两个属性访问器中的一个或两个都可以是非公共的。

**✓ 考虑** 使用序列化回调来初始化反序列化的实例。

反序列化对象时，不调用构造函数。（该规则有例外。以 <xref:System.Runtime.Serialization.CollectionDataContractAttribute> 标记的集合的构造函数在反序列化期间会被调用。）因此，在正常构造期间执行的任何逻辑都需要实现为序列化回调之一。

`OnDeserializedAttribute` 是最常使用的回调属性。此系列中的其他属性还有 <xref:System.Runtime.Serialization.OnDeserializingAttribute>、<xref:System.Runtime.Serialization.OnSerializingAttribute> 和 <xref:System.Runtime.Serialization.OnSerializedAttribute>。这些属性可分别用来标记在反序列化之前、序列化之前以及序列化之后执行的回调。
  
**✓ 考虑** 使用 <xref:System.Runtime.Serialization.KnownTypeAttribute> 以指示反序列化复杂对象图时应使用的具体类型。  

**✓ 务必** 在创建或更改可序列化类型时，考虑向后和向前兼容性。

请记住，类型的未来版本的序列化流可反序列化为该类型的当前版本，反之亦然。

请确保您理解数据成员（即使是私有的和内部的）在类型的未来版本中不能更改其名称、类型甚至顺序，除非特别注意使用数据协定属性的显式参数来保留协定。
  
对可序列化类型进行更改时，请测试序列化的兼容性。尝试将新版本反序列化为旧版本，以及将旧版本反序列化为新版本。
  
**✓ 考虑** 实现 <xref:System.Runtime.Serialization.IExtensibleDataObject> 以允许类型的不同版本之间进行转换。  
  
序列化程序可通过此接口确保在转换期间不丢失任何数据。<xref:System.Runtime.Serialization.IExtensibleDataObject.ExtensionData%2A?displayProperty=nameWithType> 属性用来存储类型未来版本中的所有数据，该类型对当前版本来说是未知类型，因此不能将其存储在其数据成员中。当前版本随后被序列化并反序列化为未来版本时，附加数据将在序列化流中可用。
  
## <a name="supporting-xml-serialization"></a>支持 XML 序列化
数据协定序列化是 .NET Framework 中的主要（默认）序列化技术，但也存在数据协定序列化不支持的序列化场景。例如，它不能让您完全控制序列化程序生成或使用的 XML 的形状。如果需要这样的精细控制，则必须使用 XML 序列化，并且您需要设计类型以支持此序列化技术。

**X 避免** 专门为 XML 序列化设计您的类型，除非您有非常强大的理由来控制所生成的 XML 的格式。此序列化技术已被上一节中讨论的数据合同序列化所取代。

**✓ 考虑** 如果您希望比应用 XML 序列化属性更多地控制序列化 XML 的格式，则实现 <xref:System.Xml.Serialization.IXmlSerializable> 接口。接口的两种方法， <xref:System.Xml.Serialization.IXmlSerializable.ReadXml%2A> 和<xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A>，允许您完全控制序列化的 XML 流。您还可以通过应用 `XmlSchemaProviderAttribute` 来控制为该类型生成的 XML 架构。
  
## <a name="supporting-runtime-serialization"></a>支持运行时序列化
运行时序列化是.NET Remoting使用的技术。如果您认为您的类型将使用.NET Remoting传输，则需要确保它们支持运行时序列化。

可以通过应用 <xref:System.SerializableAttribute> 来提供对运行时序列化的基本支持，更高级的场景涉及实现一个简单的运行时可序列化模式（实现 <xref:System.Runtime.Serialization.ISerializable> 并提供序列化构造函数）。

**✓ 考虑** 如果您的类型将与 .NET Remoting 一起使用，则支持运行时序列化。例如，<xref:System.AddIn?displayProperty=nameWithType> 命名空间使用 .NET Remoting，因此在 `System.AddIn` 加载项之间交换的所有类型都需要支持运行时序列化。

**✓ 考虑** 如果要完全控制序列化过程，请实现运行时可序列化模式。例如，如果您需要在对数据进行序列化或反序列化时转换数据。

此模式非常简单。您需要做的就是实现 <xref:System.Runtime.Serialization.ISerializable> 接口，并提供在反序列化对象时使用的特殊构造函数。  

**✓ 务必** 做出受保护的序列化构造函数并提供两个参数类型和名为在以下部分的示例所示完全一样。  使序列化构造函数为受保护的，并提供类型和命名与此处示例完全一致的两个参数。

```
[Serializable]  
public class Person : ISerializable {  
    protected Person(SerializationInfo info, StreamingContext context) {  
        ...  
    }  
}
```

**✓ 务必** 显示实现 `ISerializable` 成员。

**✓ 务必** 应用一个链接要求到 <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=nameWithType> 实现。这可确保只有完全受信任的核心应用程序和运行时序列化程序有权访问该成员。  

*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*

*经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*
  
## <a name="see-also"></a>请参阅

- [框架设计指南](../../../docs/standard/design-guidelines/index.md)  
- [使用准则](../../../docs/standard/design-guidelines/usage-guidelines.md)
