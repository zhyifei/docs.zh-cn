---
title: <add> <declaredTypes>元素
ms.date: 03/30/2017
helpviewer_keywords:
- data contracts
- dataContractSerializer element
- DataContractSerializer
- DataContractAttribute
ms.assetid: c3d37ae4-8f1c-463f-b195-658c5a7e90a1
ms.openlocfilehash: 9b280a63e85beac3231bc1a414430239bea4a1f8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61701107"
---
# <a name="add-of-declaredtypes-element"></a><span data-ttu-id="7f4ca-102">\<添加 > 的\<declaredTypes > 元素</span><span class="sxs-lookup"><span data-stu-id="7f4ca-102">\<add> of \<declaredTypes> Element</span></span>
<span data-ttu-id="7f4ca-103">添加在反序列化过程中由 <xref:System.Runtime.Serialization.DataContractSerializer> 使用的类型。</span><span class="sxs-lookup"><span data-stu-id="7f4ca-103">Adds a type used by the <xref:System.Runtime.Serialization.DataContractSerializer> during deserialization.</span></span> <span data-ttu-id="7f4ca-104">每个声明类型都包含一些将作为声明类型的字段或属性返回的已知类型。</span><span class="sxs-lookup"><span data-stu-id="7f4ca-104">Each declared type includes the known types that will be returned as a field or property of the declared type.</span></span>  
  
 <span data-ttu-id="7f4ca-105">system.runtime.serialization</span><span class="sxs-lookup"><span data-stu-id="7f4ca-105">system.runtime.serialization</span></span>  
<span data-ttu-id="7f4ca-106">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="7f4ca-106">\<dataContractSerializer></span></span>  
<span data-ttu-id="7f4ca-107">\<declaredTypes></span><span class="sxs-lookup"><span data-stu-id="7f4ca-107">\<declaredTypes></span></span>  
<span data-ttu-id="7f4ca-108">\<添加 > 的\<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="7f4ca-108">\<add> of \<declaredTypes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f4ca-109">语法</span><span class="sxs-lookup"><span data-stu-id="7f4ca-109">Syntax</span></span>  
  
```xml  
<add type="String">
  <knownType type="String">
    <parameter index="Integer"
               type="String" />
  </knownType>
</add>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7f4ca-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="7f4ca-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7f4ca-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="7f4ca-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7f4ca-112">特性</span><span class="sxs-lookup"><span data-stu-id="7f4ca-112">Attributes</span></span>  
  
|<span data-ttu-id="7f4ca-113">特性</span><span class="sxs-lookup"><span data-stu-id="7f4ca-113">Attribute</span></span>|<span data-ttu-id="7f4ca-114">描述</span><span class="sxs-lookup"><span data-stu-id="7f4ca-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7f4ca-115">类型</span><span class="sxs-lookup"><span data-stu-id="7f4ca-115">type</span></span>|<span data-ttu-id="7f4ca-116">必需的字符串属性。</span><span class="sxs-lookup"><span data-stu-id="7f4ca-116">Required string attribute.</span></span><br /><br /> <span data-ttu-id="7f4ca-117">指定类型名称（包括命名空间）、程序集名称、版本号、区域性和公钥标记。</span><span class="sxs-lookup"><span data-stu-id="7f4ca-117">Specifies the type name (including namespace), assembly name, version number, culture, and public key token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7f4ca-118">子元素</span><span class="sxs-lookup"><span data-stu-id="7f4ca-118">Child Elements</span></span>  
  
|<span data-ttu-id="7f4ca-119">元素</span><span class="sxs-lookup"><span data-stu-id="7f4ca-119">Element</span></span>|<span data-ttu-id="7f4ca-120">描述</span><span class="sxs-lookup"><span data-stu-id="7f4ca-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7f4ca-121">\<knownType></span><span class="sxs-lookup"><span data-stu-id="7f4ca-121">\<knownType></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowntype.md)|<span data-ttu-id="7f4ca-122">指定要添加的声明类型的已知类型。</span><span class="sxs-lookup"><span data-stu-id="7f4ca-122">Specifies the known type for the declared type that is being added.</span></span> <span data-ttu-id="7f4ca-123">如果声明类型是泛型类型，则还必须向 `<knownType>` 元素添加一个参数元素，以指定用于返回已知类型的泛型参数。</span><span class="sxs-lookup"><span data-stu-id="7f4ca-123">If the declared type is a generic type, then you must also add a parameter element to the `<knownType>` element to specify which generic parameter is used to return the known type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7f4ca-124">父元素</span><span class="sxs-lookup"><span data-stu-id="7f4ca-124">Parent Elements</span></span>  
  
|<span data-ttu-id="7f4ca-125">元素</span><span class="sxs-lookup"><span data-stu-id="7f4ca-125">Element</span></span>|<span data-ttu-id="7f4ca-126">描述</span><span class="sxs-lookup"><span data-stu-id="7f4ca-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7f4ca-127">\<declaredTypes></span><span class="sxs-lookup"><span data-stu-id="7f4ca-127">\<declaredTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/declaredtypes.md)|<span data-ttu-id="7f4ca-128">包含在 <xref:System.Runtime.Serialization.DataContractSerializer> 进行反序列化过程中需要已知类型的类型。</span><span class="sxs-lookup"><span data-stu-id="7f4ca-128">Contains the types that require known types during deserialization by the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7f4ca-129">备注</span><span class="sxs-lookup"><span data-stu-id="7f4ca-129">Remarks</span></span>  
 <span data-ttu-id="7f4ca-130">有关已知类型的详细信息，请参阅[Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)和<xref:System.Runtime.Serialization.DataContractSerializer>。</span><span class="sxs-lookup"><span data-stu-id="7f4ca-130">For more information about known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="7f4ca-131">请参阅[ \<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)有关使用此元素的示例。</span><span class="sxs-lookup"><span data-stu-id="7f4ca-131">See the [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) for an example of using this element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7f4ca-132">如果将 <xref:System.Object> 类型添加为 `<declaredType>`，则会引发 <xref:System.Configuration.ConfigurationErrorsException>。</span><span class="sxs-lookup"><span data-stu-id="7f4ca-132">If you add the <xref:System.Object> type as a `<declaredType>`, a <xref:System.Configuration.ConfigurationErrorsException> is thrown.</span></span> <span data-ttu-id="7f4ca-133">这是因为，<xref:System.Object> 类型不能在配置中用作声明的类型。</span><span class="sxs-lookup"><span data-stu-id="7f4ca-133">This is because the <xref:System.Object> type cannot be used as a declared type in configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7f4ca-134">示例</span><span class="sxs-lookup"><span data-stu-id="7f4ca-134">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7f4ca-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="7f4ca-135">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="7f4ca-136">数据协定已知类型</span><span class="sxs-lookup"><span data-stu-id="7f4ca-136">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="7f4ca-137">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="7f4ca-137">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)
- [<span data-ttu-id="7f4ca-138">\<add> of \<declaredTypes></span><span class="sxs-lookup"><span data-stu-id="7f4ca-138">\<add> of \<declaredTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)
