---
title: <knownType>
ms.date: 03/30/2017
ms.assetid: ee2b7be3-7148-4a3a-b861-48e7330615e5
ms.openlocfilehash: 61f51b2ecd572ba254317a01e0f514503c7cc9e4
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397872"
---
# <a name="knowntype"></a><span data-ttu-id="73977-101">\<knownType></span><span class="sxs-lookup"><span data-stu-id="73977-101">\<knownType></span></span>
<span data-ttu-id="73977-102">指定在反序列化过程中将由 <xref:System.Runtime.Serialization.DataContractSerializer> 使用的类型。</span><span class="sxs-lookup"><span data-stu-id="73977-102">Specifies a type to be used by <xref:System.Runtime.Serialization.DataContractSerializer> during deserialization.</span></span> <span data-ttu-id="73977-103">该元素指定由某个“声明的类型”的字段或属性返回到“已知类型”。</span><span class="sxs-lookup"><span data-stu-id="73977-103">The element specifies a "known type" that is returned by a field or property of a "declared type."</span></span> <span data-ttu-id="73977-104">有关详细信息，请参阅[数据协定已知类型](../../../wcf/feature-details/data-contract-known-types.md)。</span><span class="sxs-lookup"><span data-stu-id="73977-104">For more information, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span></span>  
  
<span data-ttu-id="73977-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="73977-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="73977-106">&nbsp;&nbsp;[ **\<system.object >** ](system-runtime-serialization.md)</span><span class="sxs-lookup"><span data-stu-id="73977-106">&nbsp;&nbsp;[**\<system.runtime.serialization>**](system-runtime-serialization.md)</span></span>\
<span data-ttu-id="73977-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<dataContractSerializer >** ](datacontractserializer.md)</span><span class="sxs-lookup"><span data-stu-id="73977-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<dataContractSerializer>**](datacontractserializer.md)</span></span>\
<span data-ttu-id="73977-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<declaredTypes >** ](declaredtypes.md)</span><span class="sxs-lookup"><span data-stu-id="73977-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<declaredTypes>**](declaredtypes.md)</span></span>\
<span data-ttu-id="73977-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<添加 >** ](add-of-declaredtypes-element.md)</span><span class="sxs-lookup"><span data-stu-id="73977-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-of-declaredtypes-element.md)</span></span>\
<span data-ttu-id="73977-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<knownType >**</span><span class="sxs-lookup"><span data-stu-id="73977-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<knownType>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73977-111">语法</span><span class="sxs-lookup"><span data-stu-id="73977-111">Syntax</span></span>  
  
```xml  
<knownType type="String">
  <parameter index="Integer"
             type="String" />
</knownType>
```  
  
## <a name="type"></a><span data-ttu-id="73977-112">类型</span><span class="sxs-lookup"><span data-stu-id="73977-112">Type</span></span>  
 `string`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="73977-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="73977-113">Attributes and Elements</span></span>  
 <span data-ttu-id="73977-114">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="73977-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="73977-115">特性</span><span class="sxs-lookup"><span data-stu-id="73977-115">Attributes</span></span>  
  
|<span data-ttu-id="73977-116">特性</span><span class="sxs-lookup"><span data-stu-id="73977-116">Attribute</span></span>|<span data-ttu-id="73977-117">描述</span><span class="sxs-lookup"><span data-stu-id="73977-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="73977-118">type</span><span class="sxs-lookup"><span data-stu-id="73977-118">type</span></span>|<span data-ttu-id="73977-119">指定类型（包括命名空间）、程序集名称、版本、区域性和公钥标记。</span><span class="sxs-lookup"><span data-stu-id="73977-119">Specifies the type (including namespace), assembly name, version, culture, and public key token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="73977-120">子元素</span><span class="sxs-lookup"><span data-stu-id="73977-120">Child Elements</span></span>  
  
|<span data-ttu-id="73977-121">元素</span><span class="sxs-lookup"><span data-stu-id="73977-121">Element</span></span>|<span data-ttu-id="73977-122">描述</span><span class="sxs-lookup"><span data-stu-id="73977-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="73977-123">\<parameter></span><span class="sxs-lookup"><span data-stu-id="73977-123">\<parameter></span></span>](parameter.md)|<span data-ttu-id="73977-124">当声明类型为泛型类型时指定参数索引。</span><span class="sxs-lookup"><span data-stu-id="73977-124">Specifies a parameter index when the declared type is a generic type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="73977-125">父元素</span><span class="sxs-lookup"><span data-stu-id="73977-125">Parent Elements</span></span>  
  
|<span data-ttu-id="73977-126">元素</span><span class="sxs-lookup"><span data-stu-id="73977-126">Element</span></span>|<span data-ttu-id="73977-127">描述</span><span class="sxs-lookup"><span data-stu-id="73977-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="73977-128">\<add></span><span class="sxs-lookup"><span data-stu-id="73977-128">\<add></span></span>](add-of-declaredtypes-element.md)|<span data-ttu-id="73977-129">向声明类型的集合中添加一个声明类型。</span><span class="sxs-lookup"><span data-stu-id="73977-129">Adds a declared type to the collection of declared types.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="73977-130">备注</span><span class="sxs-lookup"><span data-stu-id="73977-130">Remarks</span></span>  
 <span data-ttu-id="73977-131">有关已知类型的详细信息，请参阅[数据协定已知类型](../../../wcf/feature-details/data-contract-known-types.md)和<xref:System.Runtime.Serialization.DataContractSerializer>。</span><span class="sxs-lookup"><span data-stu-id="73977-131">For more information about known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="73977-132">有关使用此元素的示例，请参阅[ dataContractSerializer>。\<](datacontractserializer-element.md)</span><span class="sxs-lookup"><span data-stu-id="73977-132">See the [\<dataContractSerializer>](datacontractserializer-element.md) for an example of using this element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="73977-133">示例</span><span class="sxs-lookup"><span data-stu-id="73977-133">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="73977-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="73977-134">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="73977-135">数据协定已知类型</span><span class="sxs-lookup"><span data-stu-id="73977-135">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="73977-136">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="73977-136">\<dataContractSerializer></span></span>](datacontractserializer-element.md)
- [<span data-ttu-id="73977-137">\<add></span><span class="sxs-lookup"><span data-stu-id="73977-137">\<add></span></span>](add-of-declaredtypes-element.md)
