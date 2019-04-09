---
title: <dataContractSerializer> of <system.runtime.serialization>
ms.date: 03/30/2017
ms.assetid: d9b3d625-be3f-4768-8e0d-1b7e6929f6a8
ms.openlocfilehash: c81fdb040f2e0d6c9a3728d8ed3b917443ecb42e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59115357"
---
# <a name="datacontractserializer-of-systemruntimeserialization"></a><span data-ttu-id="d5b61-102">\<dataContractSerializer> of \<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="d5b61-102">\<dataContractSerializer> of \<system.runtime.serialization></span></span>
<span data-ttu-id="d5b61-103">包含 <xref:System.Runtime.Serialization.DataContractSerializer> 的配置数据。</span><span class="sxs-lookup"><span data-stu-id="d5b61-103">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="d5b61-104">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="d5b61-104">\<system.runtime.serialization></span></span>  
<span data-ttu-id="d5b61-105">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="d5b61-105">\<dataContractSerializer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5b61-106">语法</span><span class="sxs-lookup"><span data-stu-id="d5b61-106">Syntax</span></span>  
  
```xml  
<configuration>
  <system.runtime.serialization>
    <dataContractSerializer ignoreExtensionDataObject="Boolean"
                            maxItemsInObjectGraph="Integer">
      <declaredTypes>
        <add type="String">
          <knownType type="String">
            <parameter index="Integer"
                       type="String" />
          </knownType>
        </add>
      </declaredTypes>
    <dataContractSerializer>
  </system.runtime.serialization>
</configuration>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d5b61-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d5b61-107">Attributes and Elements</span></span>  
 <span data-ttu-id="d5b61-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="d5b61-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d5b61-109">特性</span><span class="sxs-lookup"><span data-stu-id="d5b61-109">Attributes</span></span>  
  
|<span data-ttu-id="d5b61-110">元素</span><span class="sxs-lookup"><span data-stu-id="d5b61-110">Element</span></span>|<span data-ttu-id="d5b61-111">描述</span><span class="sxs-lookup"><span data-stu-id="d5b61-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d5b61-112">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="d5b61-112">ignoreExtensionDataObject</span></span>|<span data-ttu-id="d5b61-113">一个布尔值，指定在对终结点进行序列化或反序列化时，是否要忽略由该终结点提供的数据。</span><span class="sxs-lookup"><span data-stu-id="d5b61-113">A Boolean value that specifies whether to ignore data supplied by the endpoint when it is being serialized or deserialized.</span></span> <span data-ttu-id="d5b61-114">只可对 `<dataContractSerializer>` 元素下的 `<behavior>` 设置此属性。</span><span class="sxs-lookup"><span data-stu-id="d5b61-114">This attribute is settable only on the `<dataContractSerializer>` under the `<behavior>` element.</span></span>|  
|<span data-ttu-id="d5b61-115">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="d5b61-115">maxItemsInObjectGraph</span></span>|<span data-ttu-id="d5b61-116">一个整数，指定要序列化或反序列化的最大项数。</span><span class="sxs-lookup"><span data-stu-id="d5b61-116">An integer that specifies the maximum number of items to serialize or deserialize.</span></span> <span data-ttu-id="d5b61-117">此属性为 65536。</span><span class="sxs-lookup"><span data-stu-id="d5b61-117">This attribute is 65536.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d5b61-118">子元素</span><span class="sxs-lookup"><span data-stu-id="d5b61-118">Child Elements</span></span>  
  
|<span data-ttu-id="d5b61-119">元素</span><span class="sxs-lookup"><span data-stu-id="d5b61-119">Element</span></span>|<span data-ttu-id="d5b61-120">描述</span><span class="sxs-lookup"><span data-stu-id="d5b61-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d5b61-121">\<declaredTypes></span><span class="sxs-lookup"><span data-stu-id="d5b61-121">\<declaredTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/declaredtypes.md)|<span data-ttu-id="d5b61-122">包含在进行反序列化时 <xref:System.Runtime.Serialization.DataContractSerializer> 使用的已知类型。</span><span class="sxs-lookup"><span data-stu-id="d5b61-122">Contains the known types that the <xref:System.Runtime.Serialization.DataContractSerializer> uses when deserializing.</span></span><br /><br /> <span data-ttu-id="d5b61-123">有关数据协定和已知的类型的详细信息，请参阅[Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)。</span><span class="sxs-lookup"><span data-stu-id="d5b61-123">For more information about data contracts and known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d5b61-124">父元素</span><span class="sxs-lookup"><span data-stu-id="d5b61-124">Parent Elements</span></span>  
  
|<span data-ttu-id="d5b61-125">元素</span><span class="sxs-lookup"><span data-stu-id="d5b61-125">Element</span></span>|<span data-ttu-id="d5b61-126">描述</span><span class="sxs-lookup"><span data-stu-id="d5b61-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d5b61-127">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="d5b61-127">\<system.runtime.serialization></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)|<span data-ttu-id="d5b61-128">表示 <xref:System.Runtime.Serialization> 命名空间节的根元素，并包含 <xref:System.Runtime.Serialization.DataContractSerializer> 的设置选项的元素。</span><span class="sxs-lookup"><span data-stu-id="d5b61-128">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d5b61-129">备注</span><span class="sxs-lookup"><span data-stu-id="d5b61-129">Remarks</span></span>  
 <span data-ttu-id="d5b61-130">有关已知类型的详细信息，请参阅<xref:System.Runtime.Serialization.DataContractSerializer>并[Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)。</span><span class="sxs-lookup"><span data-stu-id="d5b61-130">For more information about known types, see <xref:System.Runtime.Serialization.DataContractSerializer> and [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5b61-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="d5b61-131">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- [<span data-ttu-id="d5b61-132">数据协定已知类型</span><span class="sxs-lookup"><span data-stu-id="d5b61-132">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
