---
title: <add>of <declaredTypes>元素
ms.date: 03/30/2017
helpviewer_keywords:
- data contracts
- dataContractSerializer element
- DataContractSerializer
- DataContractAttribute
ms.assetid: c3d37ae4-8f1c-463f-b195-658c5a7e90a1
ms.openlocfilehash: a001e8743b2c24f68b1b23cbccf3e5ac162c4e71
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400655"
---
# <a name="add-of-declaredtypes-element"></a><span data-ttu-id="3018d-102">\<添加 declaredTypes > \<元素的 ></span><span class="sxs-lookup"><span data-stu-id="3018d-102">\<add> of \<declaredTypes> Element</span></span>
<span data-ttu-id="3018d-103">添加在反序列化过程中由 <xref:System.Runtime.Serialization.DataContractSerializer> 使用的类型。</span><span class="sxs-lookup"><span data-stu-id="3018d-103">Adds a type used by the <xref:System.Runtime.Serialization.DataContractSerializer> during deserialization.</span></span> <span data-ttu-id="3018d-104">每个声明类型都包含一些将作为声明类型的字段或属性返回的已知类型。</span><span class="sxs-lookup"><span data-stu-id="3018d-104">Each declared type includes the known types that will be returned as a field or property of the declared type.</span></span>  
  
<span data-ttu-id="3018d-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3018d-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3018d-106">&nbsp;&nbsp;[ **\<system.object >** ](system-runtime-serialization.md)</span><span class="sxs-lookup"><span data-stu-id="3018d-106">&nbsp;&nbsp;[**\<system.runtime.serialization>**](system-runtime-serialization.md)</span></span>\
<span data-ttu-id="3018d-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<dataContractSerializer >** ](datacontractserializer.md)</span><span class="sxs-lookup"><span data-stu-id="3018d-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<dataContractSerializer>**](datacontractserializer.md)</span></span>\
<span data-ttu-id="3018d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<declaredTypes >** ](declaredtypes.md)</span><span class="sxs-lookup"><span data-stu-id="3018d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<declaredTypes>**](declaredtypes.md)</span></span>\
<span data-ttu-id="3018d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<添加 >**</span><span class="sxs-lookup"><span data-stu-id="3018d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3018d-110">语法</span><span class="sxs-lookup"><span data-stu-id="3018d-110">Syntax</span></span>  
  
```xml  
<add type="String">
  <knownType type="String">
    <parameter index="Integer"
               type="String" />
  </knownType>
</add>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3018d-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="3018d-111">Attributes and Elements</span></span>  
 <span data-ttu-id="3018d-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="3018d-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3018d-113">特性</span><span class="sxs-lookup"><span data-stu-id="3018d-113">Attributes</span></span>  
  
|<span data-ttu-id="3018d-114">特性</span><span class="sxs-lookup"><span data-stu-id="3018d-114">Attribute</span></span>|<span data-ttu-id="3018d-115">描述</span><span class="sxs-lookup"><span data-stu-id="3018d-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3018d-116">type</span><span class="sxs-lookup"><span data-stu-id="3018d-116">type</span></span>|<span data-ttu-id="3018d-117">必需的字符串属性。</span><span class="sxs-lookup"><span data-stu-id="3018d-117">Required string attribute.</span></span><br /><br /> <span data-ttu-id="3018d-118">指定类型名称（包括命名空间）、程序集名称、版本号、区域性和公钥标记。</span><span class="sxs-lookup"><span data-stu-id="3018d-118">Specifies the type name (including namespace), assembly name, version number, culture, and public key token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3018d-119">子元素</span><span class="sxs-lookup"><span data-stu-id="3018d-119">Child Elements</span></span>  
  
|<span data-ttu-id="3018d-120">元素</span><span class="sxs-lookup"><span data-stu-id="3018d-120">Element</span></span>|<span data-ttu-id="3018d-121">描述</span><span class="sxs-lookup"><span data-stu-id="3018d-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3018d-122">\<knownType></span><span class="sxs-lookup"><span data-stu-id="3018d-122">\<knownType></span></span>](knowntype.md)|<span data-ttu-id="3018d-123">指定要添加的声明类型的已知类型。</span><span class="sxs-lookup"><span data-stu-id="3018d-123">Specifies the known type for the declared type that is being added.</span></span> <span data-ttu-id="3018d-124">如果声明类型是泛型类型，则还必须向 `<knownType>` 元素添加一个参数元素，以指定用于返回已知类型的泛型参数。</span><span class="sxs-lookup"><span data-stu-id="3018d-124">If the declared type is a generic type, then you must also add a parameter element to the `<knownType>` element to specify which generic parameter is used to return the known type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3018d-125">父元素</span><span class="sxs-lookup"><span data-stu-id="3018d-125">Parent Elements</span></span>  
  
|<span data-ttu-id="3018d-126">元素</span><span class="sxs-lookup"><span data-stu-id="3018d-126">Element</span></span>|<span data-ttu-id="3018d-127">描述</span><span class="sxs-lookup"><span data-stu-id="3018d-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3018d-128">\<declaredTypes></span><span class="sxs-lookup"><span data-stu-id="3018d-128">\<declaredTypes></span></span>](declaredtypes.md)|<span data-ttu-id="3018d-129">包含在 <xref:System.Runtime.Serialization.DataContractSerializer> 进行反序列化过程中需要已知类型的类型。</span><span class="sxs-lookup"><span data-stu-id="3018d-129">Contains the types that require known types during deserialization by the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3018d-130">备注</span><span class="sxs-lookup"><span data-stu-id="3018d-130">Remarks</span></span>  
 <span data-ttu-id="3018d-131">有关已知类型的详细信息，请参阅[数据协定已知类型](../../../wcf/feature-details/data-contract-known-types.md)和<xref:System.Runtime.Serialization.DataContractSerializer>。</span><span class="sxs-lookup"><span data-stu-id="3018d-131">For more information about known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="3018d-132">有关使用此元素的示例，请参阅[ dataContractSerializer>。\<](datacontractserializer-element.md)</span><span class="sxs-lookup"><span data-stu-id="3018d-132">See the [\<dataContractSerializer>](datacontractserializer-element.md) for an example of using this element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3018d-133">如果将 <xref:System.Object> 类型添加为 `<declaredType>`，则会引发 <xref:System.Configuration.ConfigurationErrorsException>。</span><span class="sxs-lookup"><span data-stu-id="3018d-133">If you add the <xref:System.Object> type as a `<declaredType>`, a <xref:System.Configuration.ConfigurationErrorsException> is thrown.</span></span> <span data-ttu-id="3018d-134">这是因为，<xref:System.Object> 类型不能在配置中用作声明的类型。</span><span class="sxs-lookup"><span data-stu-id="3018d-134">This is because the <xref:System.Object> type cannot be used as a declared type in configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3018d-135">示例</span><span class="sxs-lookup"><span data-stu-id="3018d-135">Example</span></span>  
  
```xml  
<add type="MyCompany.Library.Shape,
           MyAssembly, Version=2.0.0.0, Culture=neutral,
           PublicKeyToken=XXXXXX, processorArchitecture=MSIL">
  <knownType type="MyCompany.Library.Circle,
                   MyAssembly, Version=2.0.0.0, Culture=neutral,
                   PublicKeyToken=XXXXXX,
                   processorArchitecture=MSIL" />
</add>
```  
  
## <a name="see-also"></a><span data-ttu-id="3018d-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="3018d-136">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="3018d-137">数据协定已知类型</span><span class="sxs-lookup"><span data-stu-id="3018d-137">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="3018d-138">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="3018d-138">\<dataContractSerializer></span></span>](datacontractserializer-element.md)
- [<span data-ttu-id="3018d-139">\<添加 declaredTypes > \<的 ></span><span class="sxs-lookup"><span data-stu-id="3018d-139">\<add> of \<declaredTypes></span></span>](add-of-declaredtypes-element.md)
