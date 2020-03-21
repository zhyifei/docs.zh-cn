---
title: 可互操作的对象引用
ms.date: 04/15/2019
ms.assetid: cb8da4c8-08ca-4220-a16b-e04c8f527f1b
ms.openlocfilehash: 0927f217a1666f8f27ca9c3e68f80a96b9c0f2b1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184705"
---
# <a name="interoperable-object-references"></a>可互操作的对象引用
默认情况下，<xref:System.Runtime.Serialization.DataContractSerializer>按值序列化对象。 可以使用 属性<xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A>指示数据协定序列化器在序列化对象时保留对象引用。  
  
## <a name="generated-xml"></a>生成的 XML  
 例如，请考虑下面的对象：  
  
```csharp  
[DataContract]  
public class X  
{  
    SomeClass someInstance = new SomeClass();  
    [DataMember]  
    public SomeClass A = someInstance;  
    [DataMember]  
    public SomeClass B = someInstance;  
}  
  
public class SomeClass
{  
}  
```  
  
 当 <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> 设置为 `false`（默认值）时，会生成下面的 XML：  
  
```xml  
<X>  
   <A>contents of someInstance</A>  
   <B>contents of someInstance</B>  
</X>  
```  
  
 当 <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> 设置为 `true` 时，会生成下面的 XML：  
  
```xml  
<X>  
   <A id="1">contents of someInstance</A>  
   <B ref="1"></B>  
</X>  
```  
  
 但是，<xref:System.Runtime.Serialization.XsdDataContractExporter>即使`preserveObjectReferences`属性设置为`true`，`id`也不会在其架构中描述 和`ref`属性。  
  
## <a name="using-isreference"></a>使用 IsReference  
 要根据描述该信息的架构生成有效的对象引用信息，请将<xref:System.Runtime.Serialization.DataContractAttribute>属性应用于类型，并将<xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A>标志设置为`true`。 以下示例通过添加`X``IsReference`：  
  
```csharp
[DataContract(IsReference=true)]
public class X
{  
     SomeClass someInstance = new SomeClass();
     [DataMember]
     public SomeClass A = someInstance;
     [DataMember]
     public SomeClass B = someInstance;
}
  
public class SomeClass
{
}  
````

 生成的 XML 如下：  

```xml
<X>  
    <A id="1">
        <Value>contents of A</Value>  
    </A>
    <B ref="1"></B>  
</X>
```  
  
 使用 `IsReference` 可确保消息往返时遵从架构要求。 如果没有它，当从架构生成类型时，该类型的 XML 输出不一定与最初假定的架构兼容。 换言之，虽然 `id` 和 `ref` 属性进行了序列化，但原始架构可能禁止这些属性（或所有属性）在 XML 中出现。 应用于`IsReference`数据成员后，该成员在四舍五入时继续被识别为*可引用*成员。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.CollectionDataContractAttribute>
- <xref:System.Runtime.Serialization.DataContractAttribute.IsReference?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.CollectionDataContractAttribute.IsReference?displayProperty=nameWithType>
