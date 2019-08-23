---
title: <knownType>
ms.date: 03/30/2017
ms.assetid: ee2b7be3-7148-4a3a-b861-48e7330615e5
ms.openlocfilehash: a0794314cfcb87df00d66b6832356fb130787eba
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69928867"
---
# <a name="knowntype"></a><span data-ttu-id="aa4fd-101">\<knownType></span><span class="sxs-lookup"><span data-stu-id="aa4fd-101">\<knownType></span></span>
<span data-ttu-id="aa4fd-102">指定在反序列化过程中将由 <xref:System.Runtime.Serialization.DataContractSerializer> 使用的类型。</span><span class="sxs-lookup"><span data-stu-id="aa4fd-102">Specifies a type to be used by <xref:System.Runtime.Serialization.DataContractSerializer> during deserialization.</span></span> <span data-ttu-id="aa4fd-103">该元素指定由某个“声明的类型”的字段或属性返回到“已知类型”。</span><span class="sxs-lookup"><span data-stu-id="aa4fd-103">The element specifies a "known type" that is returned by a field or property of a "declared type."</span></span> <span data-ttu-id="aa4fd-104">有关详细信息, 请参阅[数据协定已知类型](../../../wcf/feature-details/data-contract-known-types.md)。</span><span class="sxs-lookup"><span data-stu-id="aa4fd-104">For more information, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span></span>  
  
 <span data-ttu-id="aa4fd-105">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="aa4fd-105">\<system.runtime.serialization></span></span>  
<span data-ttu-id="aa4fd-106">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="aa4fd-106">\<dataContractSerializer></span></span>  
<span data-ttu-id="aa4fd-107">\<declaredTypes > 元素</span><span class="sxs-lookup"><span data-stu-id="aa4fd-107">\<declaredTypes> Element</span></span>  
<span data-ttu-id="aa4fd-108">\<添加 declaredTypes > \<的 ></span><span class="sxs-lookup"><span data-stu-id="aa4fd-108">\<add> of \<declaredTypes></span></span>  
<span data-ttu-id="aa4fd-109">\<knownType > 元素</span><span class="sxs-lookup"><span data-stu-id="aa4fd-109">\<knownType> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa4fd-110">语法</span><span class="sxs-lookup"><span data-stu-id="aa4fd-110">Syntax</span></span>  
  
```xml  
<knownType type="String">
  <parameter index="Integer"
             type="String" />
</knownType>
```  
  
## <a name="type"></a><span data-ttu-id="aa4fd-111">类型</span><span class="sxs-lookup"><span data-stu-id="aa4fd-111">Type</span></span>  
 `string`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aa4fd-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="aa4fd-112">Attributes and Elements</span></span>  
 <span data-ttu-id="aa4fd-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="aa4fd-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aa4fd-114">特性</span><span class="sxs-lookup"><span data-stu-id="aa4fd-114">Attributes</span></span>  
  
|<span data-ttu-id="aa4fd-115">特性</span><span class="sxs-lookup"><span data-stu-id="aa4fd-115">Attribute</span></span>|<span data-ttu-id="aa4fd-116">描述</span><span class="sxs-lookup"><span data-stu-id="aa4fd-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="aa4fd-117">type</span><span class="sxs-lookup"><span data-stu-id="aa4fd-117">type</span></span>|<span data-ttu-id="aa4fd-118">指定类型（包括命名空间）、程序集名称、版本、区域性和公钥标记。</span><span class="sxs-lookup"><span data-stu-id="aa4fd-118">Specifies the type (including namespace), assembly name, version, culture, and public key token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="aa4fd-119">子元素</span><span class="sxs-lookup"><span data-stu-id="aa4fd-119">Child Elements</span></span>  
  
|<span data-ttu-id="aa4fd-120">元素</span><span class="sxs-lookup"><span data-stu-id="aa4fd-120">Element</span></span>|<span data-ttu-id="aa4fd-121">描述</span><span class="sxs-lookup"><span data-stu-id="aa4fd-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aa4fd-122">\<parameter></span><span class="sxs-lookup"><span data-stu-id="aa4fd-122">\<parameter></span></span>](parameter.md)|<span data-ttu-id="aa4fd-123">当声明类型为泛型类型时指定参数索引。</span><span class="sxs-lookup"><span data-stu-id="aa4fd-123">Specifies a parameter index when the declared type is a generic type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="aa4fd-124">父元素</span><span class="sxs-lookup"><span data-stu-id="aa4fd-124">Parent Elements</span></span>  
  
|<span data-ttu-id="aa4fd-125">元素</span><span class="sxs-lookup"><span data-stu-id="aa4fd-125">Element</span></span>|<span data-ttu-id="aa4fd-126">描述</span><span class="sxs-lookup"><span data-stu-id="aa4fd-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aa4fd-127">\<add></span><span class="sxs-lookup"><span data-stu-id="aa4fd-127">\<add></span></span>](add-of-declaredtypes-element.md)|<span data-ttu-id="aa4fd-128">向声明类型的集合中添加一个声明类型。</span><span class="sxs-lookup"><span data-stu-id="aa4fd-128">Adds a declared type to the collection of declared types.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aa4fd-129">备注</span><span class="sxs-lookup"><span data-stu-id="aa4fd-129">Remarks</span></span>  
 <span data-ttu-id="aa4fd-130">有关已知类型的详细信息, 请参阅[数据协定已知类型](../../../wcf/feature-details/data-contract-known-types.md)和<xref:System.Runtime.Serialization.DataContractSerializer>。</span><span class="sxs-lookup"><span data-stu-id="aa4fd-130">For more information about known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="aa4fd-131">有关使用此元素的示例, 请参阅[ dataContractSerializer>。\<](datacontractserializer-element.md)</span><span class="sxs-lookup"><span data-stu-id="aa4fd-131">See the [\<dataContractSerializer>](datacontractserializer-element.md) for an example of using this element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aa4fd-132">示例</span><span class="sxs-lookup"><span data-stu-id="aa4fd-132">Example</span></span>  
  
```xml  
<add type="MyCompany.Library.Shape,
           MyAssembly, Version=2.0.0.0, Culture=neutral,
           PublicKeyToken=XXXXXX, processorArchitecture=MSIL">
  <knownType type="MyCompany.Library.Circle,
                   MyAssembly, Version=2.0.0.0, Culture=neutral,
                   PublicKeyToken=XXXXXX,
                   processorArchitecture=MSIL"/>
</add>
```  
  
## <a name="see-also"></a><span data-ttu-id="aa4fd-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="aa4fd-133">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="aa4fd-134">数据协定已知类型</span><span class="sxs-lookup"><span data-stu-id="aa4fd-134">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="aa4fd-135">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="aa4fd-135">\<dataContractSerializer></span></span>](datacontractserializer-element.md)
- [<span data-ttu-id="aa4fd-136">\<add></span><span class="sxs-lookup"><span data-stu-id="aa4fd-136">\<add></span></span>](add-of-declaredtypes-element.md)
