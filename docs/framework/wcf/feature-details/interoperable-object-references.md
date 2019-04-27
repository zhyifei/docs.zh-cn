---
title: 可互操作对象的引用
ms.date: 04/15/2019
ms.assetid: cb8da4c8-08ca-4220-a16b-e04c8f527f1b
ms.openlocfilehash: ada9084f6ac3c97dc641571c0cb8379a2fac68a8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61918965"
---
# <a name="interoperable-object-references"></a>可互操作对象的引用
默认情况下，<xref:System.Runtime.Serialization.DataContractSerializer>将对象按值序列化。 可以使用<xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A>属性来指示数据协定序列化程序序列化对象时保留对象引用。  
  
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
  
 但是，<xref:System.Runtime.Serialization.XsdDataContractExporter>不会介绍`id`并`ref`其架构中的属性，即使`preserveObjectReferences`属性设置为`true`。  
  
## <a name="using-isreference"></a>使用 IsReference  
 若要生成有效描述它的架构的对象引用信息，请应用<xref:System.Runtime.Serialization.DataContractAttribute>属性的类型，并设置<xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A>标记，用于`true`。 下面的示例修改类`X`在前面的示例通过添加`IsReference`:  
  
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
  
 使用 `IsReference` 可确保消息往返时遵从架构要求。 如果没有它，从架构中，生成一个类型时的 XML 输出的类型不一定与架构最初设定兼容。 换言之，虽然 `id` 和 `ref` 属性进行了序列化，但原始架构可能禁止这些属性（或所有属性）在 XML 中出现。 与`IsReference`应用于数据成员，该成员将继续被识别为*可引用*时往返。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.CollectionDataContractAttribute>
- <xref:System.Runtime.Serialization.DataContractAttribute.IsReference?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.CollectionDataContractAttribute.IsReference?displayProperty=nameWithType>
