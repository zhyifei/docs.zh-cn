---
title: <declaredTypes>
ms.date: 03/30/2017
helpviewer_keywords:
- dataContractSerializer element
- declaredTypes element
- DataContractSerializer
- KnownTypes
- <declaredTypes> element
ms.assetid: f35184e4-9d9e-4d37-8fb4-d5b58220eb3e
ms.openlocfilehash: 8919ee717012f8badcf7015bf8d850ed431c5943
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61701159"
---
# <a name="declaredtypes"></a><span data-ttu-id="1c679-101">\<declaredTypes></span><span class="sxs-lookup"><span data-stu-id="1c679-101">\<declaredTypes></span></span>
<span data-ttu-id="1c679-102">包含在进行反序列化时 <xref:System.Runtime.Serialization.DataContractSerializer> 使用的已知类型。</span><span class="sxs-lookup"><span data-stu-id="1c679-102">Contains the known types that the <xref:System.Runtime.Serialization.DataContractSerializer> uses when deserializing.</span></span>  
  
 <span data-ttu-id="1c679-103">有关数据协定和已知的类型的详细信息，请参阅[Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)。</span><span class="sxs-lookup"><span data-stu-id="1c679-103">For more information about data contracts and known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span></span>  
  
 <span data-ttu-id="1c679-104">system.runtime.serialization</span><span class="sxs-lookup"><span data-stu-id="1c679-104">system.runtime.serialization</span></span>  
<span data-ttu-id="1c679-105">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="1c679-105">\<dataContractSerializer></span></span>  
<span data-ttu-id="1c679-106">\<declaredTypes></span><span class="sxs-lookup"><span data-stu-id="1c679-106">\<declaredTypes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c679-107">语法</span><span class="sxs-lookup"><span data-stu-id="1c679-107">Syntax</span></span>  
  
```xml  
<configuration>
  <system.runtime.serialization>
    <dataContractSerializer>
      <declaredTypes>
        <add type="String ">
          <knownType type="String">
            <parameter index="Integer"/>
          </knownType>
        </add>
      </declaredTypes>
    <dataContractSerializer>
  </system.runtime.serialization>
</configuration>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1c679-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="1c679-108">Attributes and Elements</span></span>  
 <span data-ttu-id="1c679-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="1c679-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1c679-110">特性</span><span class="sxs-lookup"><span data-stu-id="1c679-110">Attributes</span></span>  
 <span data-ttu-id="1c679-111">无。</span><span class="sxs-lookup"><span data-stu-id="1c679-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1c679-112">子元素</span><span class="sxs-lookup"><span data-stu-id="1c679-112">Child Elements</span></span>  
  
|<span data-ttu-id="1c679-113">元素</span><span class="sxs-lookup"><span data-stu-id="1c679-113">Element</span></span>|<span data-ttu-id="1c679-114">描述</span><span class="sxs-lookup"><span data-stu-id="1c679-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1c679-115">\<add></span><span class="sxs-lookup"><span data-stu-id="1c679-115">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)|<span data-ttu-id="1c679-116">添加需要已知类型的类型。</span><span class="sxs-lookup"><span data-stu-id="1c679-116">Adds types that require known types.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1c679-117">父元素</span><span class="sxs-lookup"><span data-stu-id="1c679-117">Parent Elements</span></span>  
  
|<span data-ttu-id="1c679-118">元素</span><span class="sxs-lookup"><span data-stu-id="1c679-118">Element</span></span>|<span data-ttu-id="1c679-119">描述</span><span class="sxs-lookup"><span data-stu-id="1c679-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1c679-120">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="1c679-120">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-of-system-runtime-serialization.md)|<span data-ttu-id="1c679-121">包含 <xref:System.Runtime.Serialization.DataContractSerializer> 的配置数据。</span><span class="sxs-lookup"><span data-stu-id="1c679-121">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1c679-122">备注</span><span class="sxs-lookup"><span data-stu-id="1c679-122">Remarks</span></span>  
 <span data-ttu-id="1c679-123">有关已知类型的详细信息，请参阅[Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)和<xref:System.Runtime.Serialization.DataContractSerializer>。</span><span class="sxs-lookup"><span data-stu-id="1c679-123">For more information about known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1c679-124">示例</span><span class="sxs-lookup"><span data-stu-id="1c679-124">Example</span></span>  
 <span data-ttu-id="1c679-125">下面的 XML 代码演示声明的类型和添加到已知的类型`DataContractSerializer`元素。</span><span class="sxs-lookup"><span data-stu-id="1c679-125">The following XML code shows declared types and known types added to a `DataContractSerializer` element.</span></span> <span data-ttu-id="1c679-126">此示例演示要添加的三个类型。</span><span class="sxs-lookup"><span data-stu-id="1c679-126">The example shows three types being added.</span></span> <span data-ttu-id="1c679-127">第一个类型是名为“Orders”的自定义类型，它使用一个名为“Item”的已知类型。</span><span class="sxs-lookup"><span data-stu-id="1c679-127">The first is a custom type named "Orders" that uses a known type named "Item".</span></span> <span data-ttu-id="1c679-128">第二个声明类型 <xref:System.Collections.Generic.List%601>，它使用 `Item` 作为已知类型。</span><span class="sxs-lookup"><span data-stu-id="1c679-128">The second declared type is a <xref:System.Collections.Generic.List%601> that uses `Item` as a known type.</span></span> <span data-ttu-id="1c679-129">最后，第三个声明类型是 <xref:System.Collections.Generic.Dictionary%602>。</span><span class="sxs-lookup"><span data-stu-id="1c679-129">Finally the third declared type is a <xref:System.Collections.Generic.Dictionary%602>.</span></span> <span data-ttu-id="1c679-130"><xref:System.Collections.Generic.Dictionary%602> 类类型是泛型类型，并带有两个类型参数。</span><span class="sxs-lookup"><span data-stu-id="1c679-130">The <xref:System.Collections.Generic.Dictionary%602> class type is a generic type, with two type parameters.</span></span> <span data-ttu-id="1c679-131">第一个参数表示键，第二个参数表示值。</span><span class="sxs-lookup"><span data-stu-id="1c679-131">The first represents the key and the second represents the value.</span></span> <span data-ttu-id="1c679-132">下面的示例将第二个类型的 <xref:System.Collections.Generic.List%601>（值）添加到已知类型的列表中。</span><span class="sxs-lookup"><span data-stu-id="1c679-132">The following example adds a <xref:System.Collections.Generic.List%601> of the second type (the value) to the list of known types.</span></span> <span data-ttu-id="1c679-133">必须使用 `index` 属性来指定在已知类型中使用的类型参数。</span><span class="sxs-lookup"><span data-stu-id="1c679-133">You must use the `index` attribute to specify which type parameter to use in the known type.</span></span> <span data-ttu-id="1c679-134">在此例中，通过将 index 属性设置为“1”（基于零的集合）来指示值类型。</span><span class="sxs-lookup"><span data-stu-id="1c679-134">In this case, the value type is indicated by the index attribute set to "1" (the collection is zero-based).</span></span>  
  
```xml  
<configuration>
  <system.runtime.serialization>
    <dataContractSerializer>
      <declaredTypes>
        <add type="Examples.Types.Orders, SerializationTypes, Version = 2.0.0.0, Culture = neutral, PublicKeyToken=null">
          <knownType type="Examples.Types.Item, SerializationTypes, Version=2.0.0.0, Culture=neutral, PublicKey=null" />
        </add>
        <add type="System.Collections.Generic.List`1, SerializationTypes, Version = 2.0.0.0, Culture = neutral, PublicKeyToken=null">
          <knownType type="Examples.Types.Item, SerializationTypes, Version=2.0.0.0, Culture=neutral, PublicKey=null" />
        </add>
        <add type="System.Collections.Generic.Dictionary`2, SerializationTypes, Version = 2.0.0.0, Culture = neutral, PublicKeyToken=null">
          <knownType type="System.Collections.Generic.List`1, SerializationTypes, Version = 2.0.0.0, Culture = neutral, PublicKeyToken=null">
            <parameter index="1"/>
          </knownType>
        </add>
      </declaredTypes>
    <dataContractSerializer>
  </system.runtime.serialization>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="1c679-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="1c679-135">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="1c679-136">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="1c679-136">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)
- [<span data-ttu-id="1c679-137">数据协定已知类型</span><span class="sxs-lookup"><span data-stu-id="1c679-137">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="1c679-138">\<add></span><span class="sxs-lookup"><span data-stu-id="1c679-138">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)
