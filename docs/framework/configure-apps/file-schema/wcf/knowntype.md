---
title: <knownType>
ms.date: 03/30/2017
ms.assetid: ee2b7be3-7148-4a3a-b861-48e7330615e5
ms.openlocfilehash: 1224a410d030669e340bd328c9158c85cdfeaeee
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55266450"
---
# <a name="knowntype"></a><span data-ttu-id="748d5-101">\<knownType></span><span class="sxs-lookup"><span data-stu-id="748d5-101">\<knownType></span></span>
<span data-ttu-id="748d5-102">指定在反序列化过程中将由 <xref:System.Runtime.Serialization.DataContractSerializer> 使用的类型。</span><span class="sxs-lookup"><span data-stu-id="748d5-102">Specifies a type to be used by <xref:System.Runtime.Serialization.DataContractSerializer> during deserialization.</span></span> <span data-ttu-id="748d5-103">该元素指定由某个“声明的类型”的字段或属性返回到“已知类型”。</span><span class="sxs-lookup"><span data-stu-id="748d5-103">The element specifies a "known type" that is returned by a field or property of a "declared type."</span></span> <span data-ttu-id="748d5-104">有关详细信息，请参阅[Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)。</span><span class="sxs-lookup"><span data-stu-id="748d5-104">For more information, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span></span>  
  
 <span data-ttu-id="748d5-105">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="748d5-105">\<system.runtime.serialization></span></span>  
<span data-ttu-id="748d5-106">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="748d5-106">\<dataContractSerializer></span></span>  
<span data-ttu-id="748d5-107">\<declaredTypes > 元素</span><span class="sxs-lookup"><span data-stu-id="748d5-107">\<declaredTypes> Element</span></span>  
<span data-ttu-id="748d5-108">\<添加 > 的\<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="748d5-108">\<add> of \<declaredTypes></span></span>  
<span data-ttu-id="748d5-109">\<knownType > 元素</span><span class="sxs-lookup"><span data-stu-id="748d5-109">\<knownType> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="748d5-110">语法</span><span class="sxs-lookup"><span data-stu-id="748d5-110">Syntax</span></span>  
  
```xml  
<knownType type="String">
  <parameter index="Integer"
             type="String" />
</knownType>
```  
  
## <a name="type"></a><span data-ttu-id="748d5-111">类型</span><span class="sxs-lookup"><span data-stu-id="748d5-111">Type</span></span>  
 `string`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="748d5-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="748d5-112">Attributes and Elements</span></span>  
 <span data-ttu-id="748d5-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="748d5-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="748d5-114">特性</span><span class="sxs-lookup"><span data-stu-id="748d5-114">Attributes</span></span>  
  
|<span data-ttu-id="748d5-115">特性</span><span class="sxs-lookup"><span data-stu-id="748d5-115">Attribute</span></span>|<span data-ttu-id="748d5-116">描述</span><span class="sxs-lookup"><span data-stu-id="748d5-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="748d5-117">类型</span><span class="sxs-lookup"><span data-stu-id="748d5-117">type</span></span>|<span data-ttu-id="748d5-118">指定类型（包括命名空间）、程序集名称、版本、区域性和公钥标记。</span><span class="sxs-lookup"><span data-stu-id="748d5-118">Specifies the type (including namespace), assembly name, version, culture, and public key token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="748d5-119">子元素</span><span class="sxs-lookup"><span data-stu-id="748d5-119">Child Elements</span></span>  
  
|<span data-ttu-id="748d5-120">元素</span><span class="sxs-lookup"><span data-stu-id="748d5-120">Element</span></span>|<span data-ttu-id="748d5-121">描述</span><span class="sxs-lookup"><span data-stu-id="748d5-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="748d5-122">\<parameter></span><span class="sxs-lookup"><span data-stu-id="748d5-122">\<parameter></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/parameter.md)|<span data-ttu-id="748d5-123">当声明类型为泛型类型时指定参数索引。</span><span class="sxs-lookup"><span data-stu-id="748d5-123">Specifies a parameter index when the declared type is a generic type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="748d5-124">父元素</span><span class="sxs-lookup"><span data-stu-id="748d5-124">Parent Elements</span></span>  
  
|<span data-ttu-id="748d5-125">元素</span><span class="sxs-lookup"><span data-stu-id="748d5-125">Element</span></span>|<span data-ttu-id="748d5-126">描述</span><span class="sxs-lookup"><span data-stu-id="748d5-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="748d5-127">\<add></span><span class="sxs-lookup"><span data-stu-id="748d5-127">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)|<span data-ttu-id="748d5-128">向声明类型的集合中添加一个声明类型。</span><span class="sxs-lookup"><span data-stu-id="748d5-128">Adds a declared type to the collection of declared types.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="748d5-129">备注</span><span class="sxs-lookup"><span data-stu-id="748d5-129">Remarks</span></span>  
 <span data-ttu-id="748d5-130">有关已知类型的详细信息，请参阅[Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)和<xref:System.Runtime.Serialization.DataContractSerializer>。</span><span class="sxs-lookup"><span data-stu-id="748d5-130">For more information about known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="748d5-131">请参阅[ \<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)有关使用此元素的示例。</span><span class="sxs-lookup"><span data-stu-id="748d5-131">See the [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) for an example of using this element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="748d5-132">示例</span><span class="sxs-lookup"><span data-stu-id="748d5-132">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="748d5-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="748d5-133">See also</span></span>
- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="748d5-134">数据协定已知类型</span><span class="sxs-lookup"><span data-stu-id="748d5-134">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="748d5-135">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="748d5-135">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)
- [<span data-ttu-id="748d5-136">\<add></span><span class="sxs-lookup"><span data-stu-id="748d5-136">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)
