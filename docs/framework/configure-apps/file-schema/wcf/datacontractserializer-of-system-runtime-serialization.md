---
title: <dataContractSerializer>< 的 >
ms.date: 03/30/2017
ms.assetid: d9b3d625-be3f-4768-8e0d-1b7e6929f6a8
ms.openlocfilehash: 380d9ba5b8407d78b5045fd34fcdf37c0818d6f9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919354"
---
# <a name="datacontractserializer-of-systemruntimeserialization"></a><span data-ttu-id="f2936-102">\<dataContractSerializer > 的\<></span><span class="sxs-lookup"><span data-stu-id="f2936-102">\<dataContractSerializer> of \<system.runtime.serialization></span></span>
<span data-ttu-id="f2936-103">包含 <xref:System.Runtime.Serialization.DataContractSerializer> 的配置数据。</span><span class="sxs-lookup"><span data-stu-id="f2936-103">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="f2936-104">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="f2936-104">\<system.runtime.serialization></span></span>  
<span data-ttu-id="f2936-105">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="f2936-105">\<dataContractSerializer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2936-106">语法</span><span class="sxs-lookup"><span data-stu-id="f2936-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f2936-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="f2936-107">Attributes and Elements</span></span>  
 <span data-ttu-id="f2936-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="f2936-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f2936-109">特性</span><span class="sxs-lookup"><span data-stu-id="f2936-109">Attributes</span></span>  
  
|<span data-ttu-id="f2936-110">元素</span><span class="sxs-lookup"><span data-stu-id="f2936-110">Element</span></span>|<span data-ttu-id="f2936-111">描述</span><span class="sxs-lookup"><span data-stu-id="f2936-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f2936-112">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="f2936-112">ignoreExtensionDataObject</span></span>|<span data-ttu-id="f2936-113">一个布尔值，指定在对终结点进行序列化或反序列化时，是否要忽略由该终结点提供的数据。</span><span class="sxs-lookup"><span data-stu-id="f2936-113">A Boolean value that specifies whether to ignore data supplied by the endpoint when it is being serialized or deserialized.</span></span> <span data-ttu-id="f2936-114">只可对 `<dataContractSerializer>` 元素下的 `<behavior>` 设置此属性。</span><span class="sxs-lookup"><span data-stu-id="f2936-114">This attribute is settable only on the `<dataContractSerializer>` under the `<behavior>` element.</span></span>|  
|<span data-ttu-id="f2936-115">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="f2936-115">maxItemsInObjectGraph</span></span>|<span data-ttu-id="f2936-116">一个整数，指定要序列化或反序列化的最大项数。</span><span class="sxs-lookup"><span data-stu-id="f2936-116">An integer that specifies the maximum number of items to serialize or deserialize.</span></span> <span data-ttu-id="f2936-117">此属性为 65536。</span><span class="sxs-lookup"><span data-stu-id="f2936-117">This attribute is 65536.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f2936-118">子元素</span><span class="sxs-lookup"><span data-stu-id="f2936-118">Child Elements</span></span>  
  
|<span data-ttu-id="f2936-119">元素</span><span class="sxs-lookup"><span data-stu-id="f2936-119">Element</span></span>|<span data-ttu-id="f2936-120">描述</span><span class="sxs-lookup"><span data-stu-id="f2936-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f2936-121">\<declaredTypes></span><span class="sxs-lookup"><span data-stu-id="f2936-121">\<declaredTypes></span></span>](declaredtypes.md)|<span data-ttu-id="f2936-122">包含在进行反序列化时 <xref:System.Runtime.Serialization.DataContractSerializer> 使用的已知类型。</span><span class="sxs-lookup"><span data-stu-id="f2936-122">Contains the known types that the <xref:System.Runtime.Serialization.DataContractSerializer> uses when deserializing.</span></span><br /><br /> <span data-ttu-id="f2936-123">有关数据协定和已知类型的详细信息, 请参阅[数据协定已知类型](../../../wcf/feature-details/data-contract-known-types.md)。</span><span class="sxs-lookup"><span data-stu-id="f2936-123">For more information about data contracts and known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f2936-124">父元素</span><span class="sxs-lookup"><span data-stu-id="f2936-124">Parent Elements</span></span>  
  
|<span data-ttu-id="f2936-125">元素</span><span class="sxs-lookup"><span data-stu-id="f2936-125">Element</span></span>|<span data-ttu-id="f2936-126">描述</span><span class="sxs-lookup"><span data-stu-id="f2936-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f2936-127">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="f2936-127">\<system.runtime.serialization></span></span>](system-runtime-serialization.md)|<span data-ttu-id="f2936-128">表示 <xref:System.Runtime.Serialization> 命名空间节的根元素，并包含 <xref:System.Runtime.Serialization.DataContractSerializer> 的设置选项的元素。</span><span class="sxs-lookup"><span data-stu-id="f2936-128">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f2936-129">备注</span><span class="sxs-lookup"><span data-stu-id="f2936-129">Remarks</span></span>  
 <span data-ttu-id="f2936-130">有关已知类型的详细信息, 请<xref:System.Runtime.Serialization.DataContractSerializer>参阅和[数据协定已知类型](../../../wcf/feature-details/data-contract-known-types.md)。</span><span class="sxs-lookup"><span data-stu-id="f2936-130">For more information about known types, see <xref:System.Runtime.Serialization.DataContractSerializer> and [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2936-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="f2936-131">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- [<span data-ttu-id="f2936-132">数据协定已知类型</span><span class="sxs-lookup"><span data-stu-id="f2936-132">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
