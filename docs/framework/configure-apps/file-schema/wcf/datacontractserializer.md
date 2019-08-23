---
title: dataContractSerializer
ms.date: 03/30/2017
ms.assetid: a47513a4-a96c-4350-8586-daacb05dee71
ms.openlocfilehash: 8814a48df8933cf08db78e397c24d42f2da26026
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919234"
---
# <a name="datacontractserializer"></a><span data-ttu-id="da069-102">dataContractSerializer</span><span class="sxs-lookup"><span data-stu-id="da069-102">dataContractSerializer</span></span>
<span data-ttu-id="da069-103">包含 <xref:System.Runtime.Serialization.DataContractSerializer> 的配置数据。</span><span class="sxs-lookup"><span data-stu-id="da069-103">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="da069-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="da069-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="da069-105">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="da069-105">\<behaviors></span></span>  
<span data-ttu-id="da069-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="da069-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="da069-107">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="da069-107">\<behavior></span></span>  
<span data-ttu-id="da069-108">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="da069-108">\<dataContractSerializer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da069-109">语法</span><span class="sxs-lookup"><span data-stu-id="da069-109">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"
                        maxItemsInObjectGraph="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="da069-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="da069-110">Attributes and Elements</span></span>  
 <span data-ttu-id="da069-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="da069-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="da069-112">特性</span><span class="sxs-lookup"><span data-stu-id="da069-112">Attributes</span></span>  
  
|<span data-ttu-id="da069-113">元素</span><span class="sxs-lookup"><span data-stu-id="da069-113">Element</span></span>|<span data-ttu-id="da069-114">描述</span><span class="sxs-lookup"><span data-stu-id="da069-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="da069-115">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="da069-115">ignoreExtensionDataObject</span></span>|<span data-ttu-id="da069-116">一个布尔值，指定在对终结点进行序列化或反序列化时，是否要忽略由该终结点提供的数据。</span><span class="sxs-lookup"><span data-stu-id="da069-116">A Boolean value that specifies whether to ignore data supplied by the endpoint, when it is being serialized or deserialized.</span></span>|  
|<span data-ttu-id="da069-117">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="da069-117">maxItemsInObjectGraph</span></span>|<span data-ttu-id="da069-118">一个整数，指定要序列化或反序列化的最大项数。</span><span class="sxs-lookup"><span data-stu-id="da069-118">An integer that specifies the maximum number of items to serialize or deserialize.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="da069-119">子元素</span><span class="sxs-lookup"><span data-stu-id="da069-119">Child Elements</span></span>  
 <span data-ttu-id="da069-120">无。</span><span class="sxs-lookup"><span data-stu-id="da069-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="da069-121">父元素</span><span class="sxs-lookup"><span data-stu-id="da069-121">Parent Elements</span></span>  
  
|<span data-ttu-id="da069-122">元素</span><span class="sxs-lookup"><span data-stu-id="da069-122">Element</span></span>|<span data-ttu-id="da069-123">描述</span><span class="sxs-lookup"><span data-stu-id="da069-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="da069-124">\<behavior></span><span class="sxs-lookup"><span data-stu-id="da069-124">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="da069-125">指定终结点行为。</span><span class="sxs-lookup"><span data-stu-id="da069-125">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="da069-126">备注</span><span class="sxs-lookup"><span data-stu-id="da069-126">Remarks</span></span>  
 <span data-ttu-id="da069-127">有关已知类型的更多信息，请参见 <xref:System.Runtime.Serialization.DataContractSerializer> 文档。</span><span class="sxs-lookup"><span data-stu-id="da069-127">See the <xref:System.Runtime.Serialization.DataContractSerializer> documentation for more information about known types.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="da069-128">在配置文件中，`<dataContractSerializer>` 行为元素（如果有）应始终在 `<enableWebScript>` 行为元素之前出现。</span><span class="sxs-lookup"><span data-stu-id="da069-128">The `<dataContractSerializer>` behavior element (if present) should always appear before the `<enableWebScript>` behavior element in the configuration file.</span></span> <span data-ttu-id="da069-129">否则，产生的行为将是不确定的。</span><span class="sxs-lookup"><span data-stu-id="da069-129">Otherwise, the resulting behavior is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da069-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="da069-130">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- <xref:System.ServiceModel.Configuration.DataContractSerializerElement>
- [<span data-ttu-id="da069-131">数据协定已知类型</span><span class="sxs-lookup"><span data-stu-id="da069-131">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="da069-132">数据传输和序列化</span><span class="sxs-lookup"><span data-stu-id="da069-132">Data Transfer and Serialization</span></span>](../../../wcf/feature-details/data-transfer-and-serialization.md)
