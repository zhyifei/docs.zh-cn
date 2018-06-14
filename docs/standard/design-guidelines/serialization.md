---
title: Serialization1
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: bebb27ac-9712-4196-9931-de19fc04dbac
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: db06feefdd9697fd53d64bce60ae11c7e74f8c88
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33578061"
---
# <a name="serialization"></a>序列化
序列化是将对象转换为一种格式，可以随时保存或传输的过程。 例如，你可以将对象序列化，传输通过 Internet 使用 HTTP，和目标计算机上反其序列化。  
  
 .NET Framework 提供了针对各种序列化方案进行了优化的三个主要的序列化技术。 下表列出了这些技术以及与这些技术相关的主要 Framework 类型。  
  
|**技术名称**|**主要类型**|**方案**|  
|-------------------------|--------------------|-------------------|  
|**数据协定序列化**|<xref:System.Runtime.Serialization.DataContractAttribute> <br /> <xref:System.Runtime.Serialization.DataMemberAttribute> <br /> <xref:System.Runtime.Serialization.DataContractSerializer> <br /> <xref:System.Runtime.Serialization.NetDataContractSerializer> <br /> <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> <br /> <xref:System.Runtime.Serialization.ISerializable>|常规持久性<br />Web 服务<br />JSON|  
|**XML 序列化**|<xref:System.Xml.Serialization.XmlSerializer>|具有完全控制权限的 XML 形状的 XML 格式|  
|**运行时序列化 （二进制和 SOAP）**|<xref:System.SerializableAttribute> <br /> <xref:System.Runtime.Serialization.ISerializable> <br /> <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> <br /> <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>|.NET 远程处理|  
  
 **✓ 执行**思考设计新类型时序列化。  
  
## <a name="choosing-the-right-serialization-technology-to-support"></a>选择要支持的合适的序列化技术  
 **请考虑 ✓**支持数据协定序列化，如果类型的实例可能需要保留或在 Web 服务中使用。  
  
 **请考虑 ✓**支持 XML 序列化而非或除了数据协定序列化，如果你需要更好地控制类型序列化时，会产生的 XML 格式。  
  
 这可能需要在某些互操作性方案需要使用 XML 构造不支持数据协定序列化，例如，若要生成的 XML 属性。  
  
 **请考虑 ✓**支持运行时序列化，如果需要穿越.NET 远程处理边界类型的实例。  
  
 **请避免 x**只是为了常规持久性原因支持运行时序列化或 XML 序列化。 而是希望数据协定序列化。  
  
## <a name="supporting-data-contract-serialization"></a>支持数据协定序列化  
 类型都可以通过应用支持数据协定序列化<xref:System.Runtime.Serialization.DataContractAttribute>为的类型和<xref:System.Runtime.Serialization.DataMemberAttribute>类型的成员 （字段和属性）。  
  
 **请考虑 ✓**标记的类型公共数据成员，如果可以在部分信任环境中使用该类型。  
  
 在完全信任，数据协定序列化程序进行序列化和反序列化非公共类型和成员，但可以序列化和反序列化在部分信任环境中只有公共成员。  
  
 **✓ 执行**实现具有的所有属性的 getter 和 setter <xref:System.Runtime.Serialization.DataMemberAttribute>。 数据协定序列化程序需要 getter 和 setter 要被视为可序列化的类型。 （在.NET Framework 3.5 SP1 中，一些集合属性可以是仅。）如果不会在部分信任模式下使用类型，则这两个属性访问器中的一个或两个都可以是非公共的。  
  
 **请考虑 ✓**的反序列化的实例初始化使用序列化回调。  
  
 反序列化对象时，不调用任何构造函数。 （有例外规则。 集合的构造函数标记有<xref:System.Runtime.Serialization.CollectionDataContractAttribute>在反序列化过程中调用。)因此，在正常构造过程中执行的任何逻辑需要作为一个序列化回调实现。  
  
 `OnDeserializedAttribute` 是最常使用的回调属性。 此系列中的其他属性还有 <xref:System.Runtime.Serialization.OnDeserializingAttribute>、<xref:System.Runtime.Serialization.OnSerializingAttribute> 和 <xref:System.Runtime.Serialization.OnSerializedAttribute>。 这些属性可分别用来标记在反序列化之前、序列化之前以及序列化之后执行的回调。  
  
 **请考虑 ✓**使用<xref:System.Runtime.Serialization.KnownTypeAttribute>以指示反序列化复杂对象图时，应使用的具体类型。  
  
 **✓ 执行**考虑向后和向前兼容性，当创建或更改可序列化类型。  
  
 请记住，类型的未来版本的序列化流可反序列化到类型的当前版本，反之亦然。  
  
 请确保你了解数据成员，甚至私有和内部，无法更改其名称、 类型，或者即使它们在类型的将来版本中的顺序，除非特别注意执行保留使用显式数据协定特性参数的协定.  
  
 当对可序列化类型进行更改，则测试序列化的兼容的性。 尝试将新版本反序列化为旧版本，以及将旧版本反序列化为新版本。  
  
 **请考虑 ✓**实现<xref:System.Runtime.Serialization.IExtensibleDataObject>以允许类型的不同版本之间的往返。  
  
 序列化程序可通过此接口确保在往返期间不丢失任何数据。 <xref:System.Runtime.Serialization.IExtensibleDataObject.ExtensionData%2A?displayProperty=nameWithType>属性用来存储到最新版本，未知的类型的将来版本中的任何数据，因此它不能将其存储在其数据成员。 在当前版本是随后序列化和反序列化为的未来版本，附加的数据将可序列化流中。  
  
## <a name="supporting-xml-serialization"></a>支持 XML 序列化  
 数据协定序列化是 main （默认值） 序列化技术在.NET Framework 中，但存在数据协定序列化不支持的序列化方案。 例如，数据协定序列化无法让您完全控制序列化程序生成或使用的 XML 的形状。 如果此类进行精细控制是必需的 XML 序列化具有要使用，并且需要设计你的类型来支持此序列化技术。  
  
 **请避免 x**专门为 XML 序列化设计你的类型，除非你有非常强的原因，若要控制 XML 的形状的生成。 此序列化技术已由上一节讨论的数据协定序列化所取代。  
  
 **请考虑 ✓**实现<xref:System.Xml.Serialization.IXmlSerializable>接口如果你想甚至更好地控制的序列化的 XML 形状比什么所提供的应用的 XML 序列化属性。 两种方法的接口，<xref:System.Xml.Serialization.IXmlSerializable.ReadXml%2A>和<xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A>，允许你完全控制的序列化的 XML 流。 你还可以控制获取通过将应用生成类型的 XML 架构`XmlSchemaProviderAttribute`。  
  
## <a name="supporting-runtime-serialization"></a>支持运行时序列化  
 运行时序列化是使用.NET 远程处理技术。 如果您认为您的类型将使用.NET 远程处理进行传输，你需要确保它们支持运行时序列化。  
  
 可以通过应用提供对运行时序列化的基本支持<xref:System.SerializableAttribute>，并且更高级的方案涉及实现简单的运行时可序列化模式 (实现<xref:System.Runtime.Serialization.ISerializable>并提供序列化构造函数)。  
  
 **请考虑 ✓**支持运行时序列化，如果在你的类型将使用.NET 远程处理。 例如，<xref:System.AddIn?displayProperty=nameWithType>命名空间使用.NET 远程处理，并因此所有类型之间都交换`System.AddIn`外接程序需要支持运行时序列化。  
  
 **请考虑 ✓**实现运行时可序列化模式，如果你想要完成控制序列化过程。 例如，如果您需要在对数据进行序列化或反序列化时转换数据。  
  
 此模式非常简单。 您需要执行的全部操作就是实现 <xref:System.Runtime.Serialization.ISerializable> 接口，并提供在反序列化对象时使用的特殊构造函数。  
  
 **✓ 执行**做出受保护的序列化构造函数并提供两个参数类型和名为在以下部分的示例所示完全一样。  
  
```  
[Serializable]  
public class Person : ISerializable {  
    protected Person(SerializationInfo info, StreamingContext context) {  
        ...  
    }  
}  
```  
  
 **✓ 执行**实现`ISerializable`成员显式。  
  
 **✓ 执行**应用到的链接要求<xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=nameWithType>实现。 这可确保仅完全受信任的核心应用程序和运行时序列化程序有权访问该成员。  
  
 *部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*  
  
 *通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*  
  
## <a name="see-also"></a>请参阅  
 [框架设计指南](../../../docs/standard/design-guidelines/index.md)  
 [使用准则](../../../docs/standard/design-guidelines/usage-guidelines.md)
