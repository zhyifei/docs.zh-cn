---
title: <client>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.ServiceModel/client
- http://schemas.microsoft.com/.NetConfiguration/v2.0#client
ms.assetid: bf0f7031-76c8-4e7e-a6c6-9ad9119134be
ms.openlocfilehash: 2e0352efdd5b709984338fe4484b120bddb7d545
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59164354"
---
# <a name="client"></a><span data-ttu-id="5b154-101">\<client></span><span class="sxs-lookup"><span data-stu-id="5b154-101">\<client></span></span>
<span data-ttu-id="5b154-102">`client` 元素定义客户端可以连接的终结点的列表。</span><span class="sxs-lookup"><span data-stu-id="5b154-102">The `client` element defines a list of endpoints that a client can connect to.</span></span>  
  
 <span data-ttu-id="5b154-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="5b154-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="5b154-104">\<client></span><span class="sxs-lookup"><span data-stu-id="5b154-104">\<client></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b154-105">语法</span><span class="sxs-lookup"><span data-stu-id="5b154-105">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <client>
    <endpoint>
    </endpoint>
    <metadata>
    </metadata>
  </client>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5b154-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="5b154-106">Attributes and Elements</span></span>  
 <span data-ttu-id="5b154-107">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="5b154-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5b154-108">特性</span><span class="sxs-lookup"><span data-stu-id="5b154-108">Attributes</span></span>  
 <span data-ttu-id="5b154-109">None</span><span class="sxs-lookup"><span data-stu-id="5b154-109">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5b154-110">子元素</span><span class="sxs-lookup"><span data-stu-id="5b154-110">Child Elements</span></span>  
  
|<span data-ttu-id="5b154-111">元素</span><span class="sxs-lookup"><span data-stu-id="5b154-111">Element</span></span>|<span data-ttu-id="5b154-112">描述</span><span class="sxs-lookup"><span data-stu-id="5b154-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5b154-113">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="5b154-113">\<endpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-of-client.md)|<span data-ttu-id="5b154-114">包含终结点元素集合，这些元素指定此客户端可连接到的终结点。</span><span class="sxs-lookup"><span data-stu-id="5b154-114">Contains a collection of endpoint elements, that specify the endpoints that this client can connect to.</span></span>|  
|[<span data-ttu-id="5b154-115">\<metadata></span><span class="sxs-lookup"><span data-stu-id="5b154-115">\<metadata></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md)|<span data-ttu-id="5b154-116">包含用于处理元数据的设置。</span><span class="sxs-lookup"><span data-stu-id="5b154-116">Contains settings for processing metadata.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5b154-117">父元素</span><span class="sxs-lookup"><span data-stu-id="5b154-117">Parent Elements</span></span>  
  
|<span data-ttu-id="5b154-118">元素</span><span class="sxs-lookup"><span data-stu-id="5b154-118">Element</span></span>|<span data-ttu-id="5b154-119">描述</span><span class="sxs-lookup"><span data-stu-id="5b154-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5b154-120">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="5b154-120">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="5b154-121">所有 Windows Communication Foundation (WCF) 配置元素的根元素。</span><span class="sxs-lookup"><span data-stu-id="5b154-121">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5b154-122">备注</span><span class="sxs-lookup"><span data-stu-id="5b154-122">Remarks</span></span>  
 <span data-ttu-id="5b154-123">`client` 节定义客户端可以连接的终结点的列表。</span><span class="sxs-lookup"><span data-stu-id="5b154-123">The `client` section defines a list of endpoints that a client can connect to.</span></span> <span data-ttu-id="5b154-124">客户端节中列出的每个终结点都定义了它自己的绑定、行为和协定。</span><span class="sxs-lookup"><span data-stu-id="5b154-124">Each endpoint listed in the client section defines its own binding, behavior, and contract.</span></span> <span data-ttu-id="5b154-125">它由 `name` 和 `contract` 属性共同进行唯一标识。</span><span class="sxs-lookup"><span data-stu-id="5b154-125">It is uniquely identified by the combination of the `name` and `contract` attributes.</span></span> <span data-ttu-id="5b154-126">客户端代码指定要连接到该客户端实现的服务终结点的 `name`。</span><span class="sxs-lookup"><span data-stu-id="5b154-126">The client code specifies the `name` to connect to an endpoint for the service that the client implements.</span></span> <span data-ttu-id="5b154-127">如果省略 `name` 属性，则该终结点将作为其实现的协定的默认终结点。</span><span class="sxs-lookup"><span data-stu-id="5b154-127">If the `name` attribute is omitted, the endpoint acts as the default endpoint for the contract it implements.</span></span>  
  
 <span data-ttu-id="5b154-128">此外，本节还指定了用于处理元数据的设置。</span><span class="sxs-lookup"><span data-stu-id="5b154-128">In addition, this section also specifies settings for processing metadata.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5b154-129">示例</span><span class="sxs-lookup"><span data-stu-id="5b154-129">Example</span></span>  
  
```xml  
<client>
  <endpoint address="/HelloWorld/"
            bindingConfiguration="usingDefaults"
            name="MyBinding"
            binding="customBinding"
            contract="HelloWorld">
    <addressProperties actingAs="http://www.microsoft.com/TestActor"
                       identityData="BasicReadWrite"
                       identityType="Spn"
                       isAddressPrivate="false">
  </endpoint>
</client>
```  
  
## <a name="see-also"></a><span data-ttu-id="5b154-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="5b154-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientSection>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- [<span data-ttu-id="5b154-131">WCF 客户端配置</span><span class="sxs-lookup"><span data-stu-id="5b154-131">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="5b154-132">客户端</span><span class="sxs-lookup"><span data-stu-id="5b154-132">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
