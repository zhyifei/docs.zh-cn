---
title: dataContractSerializer
ms.date: 03/30/2017
ms.assetid: a47513a4-a96c-4350-8586-daacb05dee71
ms.openlocfilehash: a024ca89bd766681f25b992f1d2c66a92e3b31b7
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2019
ms.locfileid: "54150196"
---
# <a name="datacontractserializer"></a><span data-ttu-id="6acca-102">dataContractSerializer</span><span class="sxs-lookup"><span data-stu-id="6acca-102">dataContractSerializer</span></span>
<span data-ttu-id="6acca-103">包含 <xref:System.Runtime.Serialization.DataContractSerializer> 的配置数据。</span><span class="sxs-lookup"><span data-stu-id="6acca-103">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="6acca-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="6acca-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="6acca-105">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="6acca-105">\<behaviors></span></span>  
<span data-ttu-id="6acca-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="6acca-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="6acca-107">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="6acca-107">\<behavior></span></span>  
<span data-ttu-id="6acca-108">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="6acca-108">\<dataContractSerializer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6acca-109">语法</span><span class="sxs-lookup"><span data-stu-id="6acca-109">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"
                        maxItemsInObjectGraph="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6acca-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="6acca-110">Attributes and Elements</span></span>  
 <span data-ttu-id="6acca-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="6acca-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6acca-112">特性</span><span class="sxs-lookup"><span data-stu-id="6acca-112">Attributes</span></span>  
  
|<span data-ttu-id="6acca-113">元素</span><span class="sxs-lookup"><span data-stu-id="6acca-113">Element</span></span>|<span data-ttu-id="6acca-114">描述</span><span class="sxs-lookup"><span data-stu-id="6acca-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6acca-115">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="6acca-115">ignoreExtensionDataObject</span></span>|<span data-ttu-id="6acca-116">一个布尔值，指定在对终结点进行序列化或反序列化时，是否要忽略由该终结点提供的数据。</span><span class="sxs-lookup"><span data-stu-id="6acca-116">A Boolean value that specifies whether to ignore data supplied by the endpoint, when it is being serialized or deserialized.</span></span>|  
|<span data-ttu-id="6acca-117">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="6acca-117">maxItemsInObjectGraph</span></span>|<span data-ttu-id="6acca-118">一个整数，指定要序列化或反序列化的最大项数。</span><span class="sxs-lookup"><span data-stu-id="6acca-118">An integer that specifies the maximum number of items to serialize or deserialize.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6acca-119">子元素</span><span class="sxs-lookup"><span data-stu-id="6acca-119">Child Elements</span></span>  
 <span data-ttu-id="6acca-120">无。</span><span class="sxs-lookup"><span data-stu-id="6acca-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6acca-121">父元素</span><span class="sxs-lookup"><span data-stu-id="6acca-121">Parent Elements</span></span>  
  
|<span data-ttu-id="6acca-122">元素</span><span class="sxs-lookup"><span data-stu-id="6acca-122">Element</span></span>|<span data-ttu-id="6acca-123">描述</span><span class="sxs-lookup"><span data-stu-id="6acca-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6acca-124">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="6acca-124">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="6acca-125">指定终结点行为。</span><span class="sxs-lookup"><span data-stu-id="6acca-125">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6acca-126">备注</span><span class="sxs-lookup"><span data-stu-id="6acca-126">Remarks</span></span>  
 <span data-ttu-id="6acca-127">有关已知类型的更多信息，请参见 <xref:System.Runtime.Serialization.DataContractSerializer> 文档。</span><span class="sxs-lookup"><span data-stu-id="6acca-127">See the <xref:System.Runtime.Serialization.DataContractSerializer> documentation for more information about known types.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="6acca-128">在配置文件中，`<dataContractSerializer>` 行为元素（如果有）应始终在 `<enableWebScript>` 行为元素之前出现。</span><span class="sxs-lookup"><span data-stu-id="6acca-128">The `<dataContractSerializer>` behavior element (if present) should always appear before the `<enableWebScript>` behavior element in the configuration file.</span></span> <span data-ttu-id="6acca-129">否则，产生的行为将是不确定的。</span><span class="sxs-lookup"><span data-stu-id="6acca-129">Otherwise, the resulting behavior is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6acca-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="6acca-130">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>  
 <xref:System.ServiceModel.Configuration.DataContractSerializerElement>  
 [<span data-ttu-id="6acca-131">数据协定已知类型</span><span class="sxs-lookup"><span data-stu-id="6acca-131">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [<span data-ttu-id="6acca-132">数据传输和序列化</span><span class="sxs-lookup"><span data-stu-id="6acca-132">Data Transfer and Serialization</span></span>](../../../../../docs/framework/wcf/feature-details/data-transfer-and-serialization.md)
