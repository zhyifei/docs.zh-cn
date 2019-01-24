---
title: 可互操作的对象引用
ms.date: 03/30/2017
ms.assetid: cb8da4c8-08ca-4220-a16b-e04c8f527f1b
ms.openlocfilehash: 5d2f7d93544cafab7cfe5d8dcbb8a4c5d5c5b576
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54582412"
---
# <a name="interoperable-object-references"></a><span data-ttu-id="ce829-102">可互操作的对象引用</span><span class="sxs-lookup"><span data-stu-id="ce829-102">Interoperable Object References</span></span>
<span data-ttu-id="ce829-103">默认情况下，<xref:System.Runtime.Serialization.DataContractSerializer> 按值序列化对象。</span><span class="sxs-lookup"><span data-stu-id="ce829-103">By default the <xref:System.Runtime.Serialization.DataContractSerializer> serializes objects by value.</span></span> <span data-ttu-id="ce829-104">可以使用 <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> 属性指示数据协定序列化程序在序列化类型的对象时保留对象引用。</span><span class="sxs-lookup"><span data-stu-id="ce829-104">You can use the <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> property to instruct the Data Contract Serializer to preserve object references when serializing objects of the type.</span></span>  
  
## <a name="generated-xml"></a><span data-ttu-id="ce829-105">生成的 XML</span><span class="sxs-lookup"><span data-stu-id="ce829-105">Generated XML</span></span>  
 <span data-ttu-id="ce829-106">例如，请考虑下面的对象：</span><span class="sxs-lookup"><span data-stu-id="ce829-106">As an example, consider the following object:</span></span>  
  
```  
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
  
 <span data-ttu-id="ce829-107">当 <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> 设置为 `false`（默认值）时，会生成下面的 XML：</span><span class="sxs-lookup"><span data-stu-id="ce829-107">With <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> set to `false` (the default), the following XML is generated:</span></span>  
  
```xml  
<X>  
   <A>contents of someInstance</A>  
   <B>contents of someInstance</B>  
</X>  
```  
  
 <span data-ttu-id="ce829-108">当 <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> 设置为 `true` 时，会生成下面的 XML：</span><span class="sxs-lookup"><span data-stu-id="ce829-108">With <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> set to `true`, the following XML is generated:</span></span>  
  
```xml  
<X>  
   <A id="1">contents of someInstance</A>  
   <B ref="1" />  
</X>  
```  
  
 <span data-ttu-id="ce829-109">但是，<xref:System.Runtime.Serialization.XsdDataContractExporter> 不在其架构中描述 `id` 和 `ref` 属性 (Attribute)，即使在 `preserveObjectReferences` 属性 (Property) 设置为 `true` 时也如此。</span><span class="sxs-lookup"><span data-stu-id="ce829-109">However, <xref:System.Runtime.Serialization.XsdDataContractExporter> does not describe the `id` and `ref` attributes in its schema, even when the `preserveObjectReferences` property is set to `true`.</span></span>  
  
## <a name="using-isreference"></a><span data-ttu-id="ce829-110">使用 IsReference</span><span class="sxs-lookup"><span data-stu-id="ce829-110">Using IsReference</span></span>  
 <span data-ttu-id="ce829-111">若要生成对象引用信息并使该信息对于描述它的架构有效，请将 <xref:System.Runtime.Serialization.DataContractAttribute> 特性应用于类型，并将 <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> 标志设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="ce829-111">To generate object reference information that is valid according to the schema that describes it, apply the <xref:System.Runtime.Serialization.DataContractAttribute> attribute to a type, and set the <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> flag to `true`.</span></span> <span data-ttu-id="ce829-112">在前面的示例类 `IsReference` 中使用 `X`：</span><span class="sxs-lookup"><span data-stu-id="ce829-112">Using `IsReference` in the previous example class `X`:</span></span>  
  
 `[DataContract(IsReference=true)] public class X`  
  
 `{`  
  
 `SomeClass someInstance = new SomeClass();`  
  
 `[DataMember]`  
  
 `public SomeClass A = someInstance;`  
  
 `[DataMember]`  
  
 `public SomeClass B = someInstance;`  
  
 `}`  
  
 `public class SomeClass`  
  
 `{`  
  
 `}`  
  
 <span data-ttu-id="ce829-113">生成的 XML 如下：</span><span class="sxs-lookup"><span data-stu-id="ce829-113">The generated XML is as follows:</span></span>  
  
 `<X>`  
  
 `<A id="1">`  
  
 `<Value>contents of A</Value>`  
  
 `</A>`  
  
 `<B ref="1">`  
  
 `</B>`  
  
 `</X>`  
  
 <span data-ttu-id="ce829-114">使用 `IsReference` 可确保消息往返时遵从架构要求。</span><span class="sxs-lookup"><span data-stu-id="ce829-114">Using `IsReference` ensures compliance on message round-tripping.</span></span> <span data-ttu-id="ce829-115">如果未使用该属性，则从架构生成某个类型时，为该类型发回的 XML 不一定与架构最初设定的内容一致。</span><span class="sxs-lookup"><span data-stu-id="ce829-115">Without it, when a type is generated from schema, what is sent back as XML for that type is not necessarily compatible with the schema originally assumed.</span></span> <span data-ttu-id="ce829-116">换言之，虽然 `id` 和 `ref` 属性进行了序列化，但原始架构可能禁止这些属性（或所有属性）在 XML 中出现。</span><span class="sxs-lookup"><span data-stu-id="ce829-116">In other words, although the `id` and `ref` attributes were serialized, the original schema could have barred these attributes (or all attributes) from occurring in the XML.</span></span> <span data-ttu-id="ce829-117">在将 `IsReference` 应用于某个数据成员时，该成员在往返时会继续被识别为“可引用”。</span><span class="sxs-lookup"><span data-stu-id="ce829-117">With `IsReference` applied to a data member, the member continues to be recognized as "referenceable" when roundtripped.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce829-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="ce829-118">See also</span></span>
- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.CollectionDataContractAttribute>
- <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A>
- <xref:System.Runtime.Serialization.CollectionDataContractAttribute.IsReference%2A>
