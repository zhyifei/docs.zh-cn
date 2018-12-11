---
title: Serialization1
ms.date: 10/22/2008
ms.technology: dotnet-standard
ms.assetid: bebb27ac-9712-4196-9931-de19fc04dbac
author: KrzysztofCwalina
ms.openlocfilehash: 3e21251710a44764bd06fbce83f97288b6925bc2
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53155101"
---
# <a name="serialization"></a>序列化
序列化是将对象转换为可以轻松地保持或传输的格式的过程。 例如，可以将对象序列化，使用 HTTP 在 Internet 上传输它，并在目标计算机上对其进行反序列化。  
  
 .NET Framework 提供了针对各种序列化方案进行了优化的三种主要序列化技术。 下表列出了这些技术以及与这些技术相关的主要框架类型。  
  
|**技术名称**|**主要类型**|**方案**|  
|-------------------------|--------------------|-------------------|  
|**数据协定序列化**|<xref:System.Runtime.Serialization.DataContractAttribute> <br /> <xref:System.Runtime.Serialization.DataMemberAttribute> <br /> <xref:System.Runtime.Serialization.DataContractSerializer> <br /> <xref:System.Runtime.Serialization.NetDataContractSerializer> <br /> <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> <br /> <xref:System.Runtime.Serialization.ISerializable>|常规持久性<br />Web 服务<br />JSON|  
|**XML 序列化**|<xref:System.Xml.Serialization.XmlSerializer>|对 XML 的结构具有完全控制的 XML 格式|  
|**运行时序列化 （二进制和 SOAP）**|<xref:System.SerializableAttribute> <br /> <xref:System.Runtime.Serialization.ISerializable> <br /> <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> <br /> <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>|.NET Remoting|  
  
 **✓ 务必**在设计新类型时考虑序列化。  
  
## <a name="choosing-the-right-serialization-technology-to-support"></a>选择要支持的合适的序列化技术  
 **✓ 考虑**支持数据协定序列化，如果类型的实例可能需要持久化或在 Web 服务中使用。  
  
 **✓ 考虑**如果需要对序列化类型时生成的 XML 格式进行更多控制，则支持 XML 序列化，而不是数据协定序列化，或者支持数据协定序列化之外的序列化。  
  
 在某些互操作性场景中，这可能是必要的，在这些场景中，需要使用数据协定序列化不支持的 XML 构造，例如，生成 XML 属性。  
  
 **✓ 考虑**支持运行时序列化，如果类型的实例需要跨 .NET Remoting 边界传输。  
  
 **X 避免**只是为了一般持久性原因而支持运行时序列化或 XML 序列化。 建议使用数据协定序列化。  
  
## <a name="supporting-data-contract-serialization"></a>支持数据协定序列化  
 类型可以通过对类型应用 <xref:System.Runtime.Serialization.DataContractAttribute> 和对类型的成员（字段和属性）应用 <xref:System.Runtime.Serialization.DataMemberAttribute> 来支持数据协定序列化。  
  
 **✓ 考虑**将类型的数据成员标记为公共，如果可以在部分信任环境中使用该类型。  
  
 在完全信任的环境中，数据协定序列化程序可以序列化和反序列化非公共类型和成员，但在部分信任的环境中，只能序列化和反序列化公共成员。  
  
 **✓ DO** 实现具有的所有属性的 getter 和 setter <xref:System.Runtime.Serialization.DataMemberAttribute>。 数据协定序列化程序需要 getter 和 setter 要被视为可序列化的类型。 （在.NET Framework 3.5 SP1 中，某些集合属性可以是只读。）如果不会在部分信任模式下使用类型，则这两个属性访问器中的一个或两个都可以是非公共的。  
  
 **✓ 考虑**使用序列化回调来初始化反序列化的实例。  
  
 反序列化对象时，不调用任何构造函数。 （有规则的例外情况。 集合的构造函数标有<xref:System.Runtime.Serialization.CollectionDataContractAttribute>反序列化期间调用。)因此，在正常构造期间执行的任何逻辑需要作为一个序列化回调实现。  
  
 `OnDeserializedAttribute` 是最常使用的回调特性。 此系列中的其他特性还有 <xref:System.Runtime.Serialization.OnDeserializingAttribute>、<xref:System.Runtime.Serialization.OnSerializingAttribute> 和 <xref:System.Runtime.Serialization.OnSerializedAttribute>。 这些特性可分别用来标记在反序列化之前、序列化之前以及序列化之后执行的回调。  
  
 **✓ 考虑**使用 <xref:System.Runtime.Serialization.KnownTypeAttribute> 以指示反序列化复杂对象图形时应使用的具体类型。  
  
 **✓ DO** 考虑向后和向前兼容性，当创建或更改可序列化类型。  
  
 请记住，类型的未来版本的序列化流可反序列化到类型的当前版本，反之亦然。  
  
 请确保您了解数据成员，甚至私有和内部，不能更改其名称、 类型或甚至它们在类型的未来版本中的顺序，除非特别留意将使用显式参数的数据协定特性的协定.  
  
 对可序列化类型进行更改时，请测试序列化的兼容性。 尝试将新版本反序列化为旧版本，以及将旧版本反序列化为新版本。  
  
 **✓ CONSIDER** 实现<xref:System.Runtime.Serialization.IExtensibleDataObject>以允许类型的不同版本之间的往返。  
  
 序列化程序可通过此接口确保在往返期间不丢失任何数据。 <xref:System.Runtime.Serialization.IExtensibleDataObject.ExtensionData%2A?displayProperty=nameWithType>属性用来存储最新版本，对于是未知的类型的未来版本中的任何数据，因此它不能将其存储在其数据成员。 随后序列化和反序列化为未来版本当前版本时, 的其他数据将可序列化流中。  
  
## <a name="supporting-xml-serialization"></a>支持 XML 序列化  
 数据协定序列化是主要 （默认） 序列化技术在.NET Framework 中，但不支持数据协定序列化的序列化方案。 例如，数据协定序列化无法让您完全控制序列化程序生成或使用的 XML 的形状。 如果需要此类精细控制，XML 序列化有要使用，您需要设计类型以支持此序列化技术。  
  
 **X AVOID** 专门为 XML 序列化设计你的类型，除非你有非常强的原因，若要控制 XML 的形状的生成。 此序列化技术已由上一节讨论的数据协定序列化所取代。  
  
 **✓ CONSIDER** 实现<xref:System.Xml.Serialization.IXmlSerializable>接口如果你想甚至更好地控制的序列化的 XML 形状比什么所提供的应用的 XML 序列化属性。 两种方法的接口<xref:System.Xml.Serialization.IXmlSerializable.ReadXml%2A>和<xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A>，允许你完全控制的序列化的 XML 流。 您还可以控制获取通过将应用生成的类型的 XML 架构`XmlSchemaProviderAttribute`。  
  
## <a name="supporting-runtime-serialization"></a>支持运行时序列化  
 运行时序列化是使用.NET 远程处理的技术。 如果您认为您的类型将使用.NET 远程处理进行传输，需要确保它们支持运行时序列化。  
  
 可以通过应用提供对运行时序列化的基本支持<xref:System.SerializableAttribute>，并更高级的方案涉及实现一个简单的运行时可序列化模式 (实现<xref:System.Runtime.Serialization.ISerializable>并提供序列化构造函数)。  
  
 **✓ CONSIDER** 支持运行时序列化，如果在你的类型将使用.NET 远程处理。 例如，<xref:System.AddIn?displayProperty=nameWithType>命名空间使用.NET 远程处理，因此所有类型之间都交换`System.AddIn`外接程序需要支持运行时序列化。  
  
 **✓ CONSIDER** 实现运行时可序列化模式，如果你想要完成控制序列化过程。 例如，如果您需要在对数据进行序列化或反序列化时转换数据。  
  
 此模式非常简单。 您需要执行的全部操作就是实现 <xref:System.Runtime.Serialization.ISerializable> 接口，并提供在反序列化对象时使用的特殊构造函数。  
  
 **✓ DO** 做出受保护的序列化构造函数并提供两个参数类型和名为在以下部分的示例所示完全一样。  
  
```csharp
[Serializable]  
public class Person : ISerializable {  
    protected Person(SerializationInfo info, StreamingContext context) {  
        ...  
    }  
}  
```
  
 **✓ DO** 实现`ISerializable`成员显式。  
  
 **✓ DO** 应用到的链接要求<xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=nameWithType>实现。 这可确保只有完全受信任的核心应用程序和运行时序列化程序有权访问该成员。  
  
 *部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*  
  
 *通过从 Pearson Education，Inc.的权限重新打印[Framework 设计准则：约定、 语法和模式的可重用.NET 库，第 2 版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)Krzysztof Cwalina 和 Brad Abrams，作为 Microsoft Windows 开发系列的一部分发布 2008 年 10 月 22 日由 Addison-wesley 专业人员。*  
  
## <a name="see-also"></a>请参阅

- [框架设计指南](../../../docs/standard/design-guidelines/index.md)  
- [使用准则](../../../docs/standard/design-guidelines/usage-guidelines.md)
