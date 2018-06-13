---
title: dataContractSerializer
ms.date: 03/30/2017
ms.assetid: a47513a4-a96c-4350-8586-daacb05dee71
ms.openlocfilehash: 0528ae823db500da3c3a1efc6934951c4e41cea7
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32748005"
---
# <a name="datacontractserializer"></a><span data-ttu-id="5d6a8-102">dataContractSerializer</span><span class="sxs-lookup"><span data-stu-id="5d6a8-102">dataContractSerializer</span></span>
<span data-ttu-id="5d6a8-103">包含 <xref:System.Runtime.Serialization.DataContractSerializer> 的配置数据。</span><span class="sxs-lookup"><span data-stu-id="5d6a8-103">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="5d6a8-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="5d6a8-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="5d6a8-105">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="5d6a8-105">\<behaviors></span></span>  
<span data-ttu-id="5d6a8-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="5d6a8-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="5d6a8-107">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="5d6a8-107">\<behavior></span></span>  
<span data-ttu-id="5d6a8-108">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="5d6a8-108">\<dataContractSerializer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d6a8-109">语法</span><span class="sxs-lookup"><span data-stu-id="5d6a8-109">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"  
      maxItemsInObjectGraph="Integer" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5d6a8-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="5d6a8-110">Attributes and Elements</span></span>  
 <span data-ttu-id="5d6a8-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="5d6a8-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5d6a8-112">特性</span><span class="sxs-lookup"><span data-stu-id="5d6a8-112">Attributes</span></span>  
  
|<span data-ttu-id="5d6a8-113">元素</span><span class="sxs-lookup"><span data-stu-id="5d6a8-113">Element</span></span>|<span data-ttu-id="5d6a8-114">描述</span><span class="sxs-lookup"><span data-stu-id="5d6a8-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5d6a8-115">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="5d6a8-115">ignoreExtensionDataObject</span></span>|<span data-ttu-id="5d6a8-116">一个布尔值，指定在对终结点进行序列化或反序列化时，是否要忽略由该终结点提供的数据。</span><span class="sxs-lookup"><span data-stu-id="5d6a8-116">A Boolean value that specifies whether to ignore data supplied by the endpoint, when it is being serialized or deserialized.</span></span>|  
|<span data-ttu-id="5d6a8-117">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="5d6a8-117">maxItemsInObjectGraph</span></span>|<span data-ttu-id="5d6a8-118">一个整数，指定要序列化或反序列化的最大项数。</span><span class="sxs-lookup"><span data-stu-id="5d6a8-118">An integer that specifies the maximum number of items to serialize or deserialize.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5d6a8-119">子元素</span><span class="sxs-lookup"><span data-stu-id="5d6a8-119">Child Elements</span></span>  
 <span data-ttu-id="5d6a8-120">无。</span><span class="sxs-lookup"><span data-stu-id="5d6a8-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5d6a8-121">父元素</span><span class="sxs-lookup"><span data-stu-id="5d6a8-121">Parent Elements</span></span>  
  
|<span data-ttu-id="5d6a8-122">元素</span><span class="sxs-lookup"><span data-stu-id="5d6a8-122">Element</span></span>|<span data-ttu-id="5d6a8-123">描述</span><span class="sxs-lookup"><span data-stu-id="5d6a8-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5d6a8-124">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="5d6a8-124">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="5d6a8-125">指定终结点行为。</span><span class="sxs-lookup"><span data-stu-id="5d6a8-125">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5d6a8-126">备注</span><span class="sxs-lookup"><span data-stu-id="5d6a8-126">Remarks</span></span>  
 <span data-ttu-id="5d6a8-127">有关已知类型的更多信息，请参见 <xref:System.Runtime.Serialization.DataContractSerializer> 文档。</span><span class="sxs-lookup"><span data-stu-id="5d6a8-127">See the <xref:System.Runtime.Serialization.DataContractSerializer> documentation for more information about known types.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="5d6a8-128">在配置文件中，`<dataContractSerializer>` 行为元素（如果有）应始终在 `<enableWebScript>` 行为元素之前出现。</span><span class="sxs-lookup"><span data-stu-id="5d6a8-128">The `<dataContractSerializer>` behavior element (if present) should always appear before the `<enableWebScript>` behavior element in the configuration file.</span></span> <span data-ttu-id="5d6a8-129">否则，产生的行为将是不确定的。</span><span class="sxs-lookup"><span data-stu-id="5d6a8-129">Otherwise, the resulting behavior is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d6a8-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="5d6a8-130">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>  
 <xref:System.ServiceModel.Configuration.DataContractSerializerElement>  
 [<span data-ttu-id="5d6a8-131">数据协定已知类型</span><span class="sxs-lookup"><span data-stu-id="5d6a8-131">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [<span data-ttu-id="5d6a8-132">数据传输和序列化</span><span class="sxs-lookup"><span data-stu-id="5d6a8-132">Data Transfer and Serialization</span></span>](../../../../../docs/framework/wcf/feature-details/data-transfer-and-serialization.md)
