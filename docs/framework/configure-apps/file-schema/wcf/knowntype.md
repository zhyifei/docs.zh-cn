---
title: '&lt;knownType&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ee2b7be3-7148-4a3a-b861-48e7330615e5
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 439d241d73df4db2820eac72c5e88e7d9023c6a5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltknowntypegt"></a><span data-ttu-id="da9dc-102">&lt;knownType&gt;</span><span class="sxs-lookup"><span data-stu-id="da9dc-102">&lt;knownType&gt;</span></span>
<span data-ttu-id="da9dc-103">指定在反序列化过程中将由 <xref:System.Runtime.Serialization.DataContractSerializer> 使用的类型。</span><span class="sxs-lookup"><span data-stu-id="da9dc-103">Specifies a type to be used by <xref:System.Runtime.Serialization.DataContractSerializer> during deserialization.</span></span> <span data-ttu-id="da9dc-104">该元素指定由某个“声明的类型”的字段或属性返回到“已知类型”。</span><span class="sxs-lookup"><span data-stu-id="da9dc-104">The element specifies a "known type" that is returned by a field or property of a "declared type."</span></span> <span data-ttu-id="da9dc-105">有关详细信息，请参阅[数据协定已知类型](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)。</span><span class="sxs-lookup"><span data-stu-id="da9dc-105">For more information, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span></span>  
  
 <span data-ttu-id="da9dc-106">\<system.runtime.serialization ></span><span class="sxs-lookup"><span data-stu-id="da9dc-106">\<system.runtime.serialization></span></span>  
<span data-ttu-id="da9dc-107">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="da9dc-107">\<dataContractSerializer></span></span>  
<span data-ttu-id="da9dc-108">\<d d > 元素</span><span class="sxs-lookup"><span data-stu-id="da9dc-108">\<declaredTypes> Element</span></span>  
<span data-ttu-id="da9dc-109">\<添加 > 的\<d d ></span><span class="sxs-lookup"><span data-stu-id="da9dc-109">\<add> of \<declaredTypes></span></span>  
<span data-ttu-id="da9dc-110">\<knownType > 元素</span><span class="sxs-lookup"><span data-stu-id="da9dc-110">\<knownType> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da9dc-111">语法</span><span class="sxs-lookup"><span data-stu-id="da9dc-111">Syntax</span></span>  
  
```xml  
<knownType type="String">  
     <parameter index="Integer"  
                type="String" />  
</knownType>  
```  
  
## <a name="type"></a><span data-ttu-id="da9dc-112">类型</span><span class="sxs-lookup"><span data-stu-id="da9dc-112">Type</span></span>  
 `string`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="da9dc-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="da9dc-113">Attributes and Elements</span></span>  
 <span data-ttu-id="da9dc-114">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="da9dc-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="da9dc-115">特性</span><span class="sxs-lookup"><span data-stu-id="da9dc-115">Attributes</span></span>  
  
|<span data-ttu-id="da9dc-116">特性</span><span class="sxs-lookup"><span data-stu-id="da9dc-116">Attribute</span></span>|<span data-ttu-id="da9dc-117">描述</span><span class="sxs-lookup"><span data-stu-id="da9dc-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="da9dc-118">类型</span><span class="sxs-lookup"><span data-stu-id="da9dc-118">type</span></span>|<span data-ttu-id="da9dc-119">指定类型（包括命名空间）、程序集名称、版本、区域性和公钥标记。</span><span class="sxs-lookup"><span data-stu-id="da9dc-119">Specifies the type (including namespace), assembly name, version, culture, and public key token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="da9dc-120">子元素</span><span class="sxs-lookup"><span data-stu-id="da9dc-120">Child Elements</span></span>  
  
|<span data-ttu-id="da9dc-121">元素</span><span class="sxs-lookup"><span data-stu-id="da9dc-121">Element</span></span>|<span data-ttu-id="da9dc-122">描述</span><span class="sxs-lookup"><span data-stu-id="da9dc-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="da9dc-123">\<参数 ></span><span class="sxs-lookup"><span data-stu-id="da9dc-123">\<parameter></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/parameter.md)|<span data-ttu-id="da9dc-124">当声明类型为泛型类型时指定参数索引。</span><span class="sxs-lookup"><span data-stu-id="da9dc-124">Specifies a parameter index when the declared type is a generic type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="da9dc-125">父元素</span><span class="sxs-lookup"><span data-stu-id="da9dc-125">Parent Elements</span></span>  
  
|<span data-ttu-id="da9dc-126">元素</span><span class="sxs-lookup"><span data-stu-id="da9dc-126">Element</span></span>|<span data-ttu-id="da9dc-127">描述</span><span class="sxs-lookup"><span data-stu-id="da9dc-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="da9dc-128">\<add></span><span class="sxs-lookup"><span data-stu-id="da9dc-128">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)|<span data-ttu-id="da9dc-129">向声明类型的集合中添加一个声明类型。</span><span class="sxs-lookup"><span data-stu-id="da9dc-129">Adds a declared type to the collection of declared types.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="da9dc-130">备注</span><span class="sxs-lookup"><span data-stu-id="da9dc-130">Remarks</span></span>  
 <span data-ttu-id="da9dc-131">有关已知类型的详细信息，请参阅[数据协定已知类型](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)和<xref:System.Runtime.Serialization.DataContractSerializer>。</span><span class="sxs-lookup"><span data-stu-id="da9dc-131">For more information about known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="da9dc-132">请参阅[ \<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)有关使用此元素的示例。</span><span class="sxs-lookup"><span data-stu-id="da9dc-132">See the [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) for an example of using this element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="da9dc-133">示例</span><span class="sxs-lookup"><span data-stu-id="da9dc-133">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="da9dc-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="da9dc-134">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 [<span data-ttu-id="da9dc-135">数据协定已知类型</span><span class="sxs-lookup"><span data-stu-id="da9dc-135">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [<span data-ttu-id="da9dc-136">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="da9dc-136">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)  
 [<span data-ttu-id="da9dc-137">\<add></span><span class="sxs-lookup"><span data-stu-id="da9dc-137">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)
