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
# <a name="interoperable-object-references"></a><span data-ttu-id="425d5-102">可互操作的对象引用</span><span class="sxs-lookup"><span data-stu-id="425d5-102">Interoperable object references</span></span>
<span data-ttu-id="425d5-103">默认情况下，<xref:System.Runtime.Serialization.DataContractSerializer>按值序列化对象。</span><span class="sxs-lookup"><span data-stu-id="425d5-103">By default, <xref:System.Runtime.Serialization.DataContractSerializer> serializes objects by value.</span></span> <span data-ttu-id="425d5-104">可以使用 属性<xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A>指示数据协定序列化器在序列化对象时保留对象引用。</span><span class="sxs-lookup"><span data-stu-id="425d5-104">You can use the <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> property to instruct the data contract serializer to preserve object references when serializing objects.</span></span>  
  
## <a name="generated-xml"></a><span data-ttu-id="425d5-105">生成的 XML</span><span class="sxs-lookup"><span data-stu-id="425d5-105">Generated XML</span></span>  
 <span data-ttu-id="425d5-106">例如，请考虑下面的对象：</span><span class="sxs-lookup"><span data-stu-id="425d5-106">As an example, consider the following object:</span></span>  
  
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
  
 <span data-ttu-id="425d5-107">当 <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> 设置为 `false`（默认值）时，会生成下面的 XML：</span><span class="sxs-lookup"><span data-stu-id="425d5-107">With <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> set to `false` (the default), the following XML is generated:</span></span>  
  
```xml  
<X>  
   <A>contents of someInstance</A>  
   <B>contents of someInstance</B>  
</X>  
```  
  
 <span data-ttu-id="425d5-108">当 <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> 设置为 `true` 时，会生成下面的 XML：</span><span class="sxs-lookup"><span data-stu-id="425d5-108">With <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> set to `true`, the following XML is generated:</span></span>  
  
```xml  
<X>  
   <A id="1">contents of someInstance</A>  
   <B ref="1"></B>  
</X>  
```  
  
 <span data-ttu-id="425d5-109">但是，<xref:System.Runtime.Serialization.XsdDataContractExporter>即使`preserveObjectReferences`属性设置为`true`，`id`也不会在其架构中描述 和`ref`属性。</span><span class="sxs-lookup"><span data-stu-id="425d5-109">However, <xref:System.Runtime.Serialization.XsdDataContractExporter> doesn't describe the `id` and `ref` attributes in its schema, even when the `preserveObjectReferences` property is set to `true`.</span></span>  
  
## <a name="using-isreference"></a><span data-ttu-id="425d5-110">使用 IsReference</span><span class="sxs-lookup"><span data-stu-id="425d5-110">Using IsReference</span></span>  
 <span data-ttu-id="425d5-111">要根据描述该信息的架构生成有效的对象引用信息，请将<xref:System.Runtime.Serialization.DataContractAttribute>属性应用于类型，并将<xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A>标志设置为`true`。</span><span class="sxs-lookup"><span data-stu-id="425d5-111">To generate object reference information that's valid according to the schema that describes it, apply the <xref:System.Runtime.Serialization.DataContractAttribute> attribute to a type, and set the <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> flag to `true`.</span></span> <span data-ttu-id="425d5-112">以下示例通过添加`X``IsReference`：</span><span class="sxs-lookup"><span data-stu-id="425d5-112">The following example modifies class `X` in the previous example by adding `IsReference`:</span></span>  
  
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

 <span data-ttu-id="425d5-113">生成的 XML 如下：</span><span class="sxs-lookup"><span data-stu-id="425d5-113">The generated XML is as follows:</span></span>  

```xml
<X>  
    <A id="1">
        <Value>contents of A</Value>  
    </A>
    <B ref="1"></B>  
</X>
```  
  
 <span data-ttu-id="425d5-114">使用 `IsReference` 可确保消息往返时遵从架构要求。</span><span class="sxs-lookup"><span data-stu-id="425d5-114">Using `IsReference` ensures compliance on message round-tripping.</span></span> <span data-ttu-id="425d5-115">如果没有它，当从架构生成类型时，该类型的 XML 输出不一定与最初假定的架构兼容。</span><span class="sxs-lookup"><span data-stu-id="425d5-115">Without it, when a type is generated from schema, the XML output for that type isn't necessarily compatible with the schema originally assumed.</span></span> <span data-ttu-id="425d5-116">换言之，虽然 `id` 和 `ref` 属性进行了序列化，但原始架构可能禁止这些属性（或所有属性）在 XML 中出现。</span><span class="sxs-lookup"><span data-stu-id="425d5-116">In other words, although the `id` and `ref` attributes were serialized, the original schema could have barred these attributes (or all attributes) from occurring in the XML.</span></span> <span data-ttu-id="425d5-117">应用于`IsReference`数据成员后，该成员在四舍五入时继续被识别为*可引用*成员。</span><span class="sxs-lookup"><span data-stu-id="425d5-117">With `IsReference` applied to a data member, the member continues to be recognized as *referenceable* when round-tripped.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="425d5-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="425d5-118">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.CollectionDataContractAttribute>
- <xref:System.Runtime.Serialization.DataContractAttribute.IsReference?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.CollectionDataContractAttribute.IsReference?displayProperty=nameWithType>
