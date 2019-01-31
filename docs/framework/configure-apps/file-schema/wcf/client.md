---
title: <client>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.ServiceModel/client
- http://schemas.microsoft.com/.NetConfiguration/v2.0#client
ms.assetid: bf0f7031-76c8-4e7e-a6c6-9ad9119134be
ms.openlocfilehash: 93365c109f015b2ec72b5216dcb8c46258d022e2
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55280899"
---
# <a name="client"></a><span data-ttu-id="357b7-101">\<client></span><span class="sxs-lookup"><span data-stu-id="357b7-101">\<client></span></span>
<span data-ttu-id="357b7-102">`client` 元素定义客户端可以连接的终结点的列表。</span><span class="sxs-lookup"><span data-stu-id="357b7-102">The `client` element defines a list of endpoints that a client can connect to.</span></span>  
  
 <span data-ttu-id="357b7-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="357b7-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="357b7-104">\<client></span><span class="sxs-lookup"><span data-stu-id="357b7-104">\<client></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="357b7-105">语法</span><span class="sxs-lookup"><span data-stu-id="357b7-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="357b7-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="357b7-106">Attributes and Elements</span></span>  
 <span data-ttu-id="357b7-107">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="357b7-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="357b7-108">特性</span><span class="sxs-lookup"><span data-stu-id="357b7-108">Attributes</span></span>  
 <span data-ttu-id="357b7-109">无</span><span class="sxs-lookup"><span data-stu-id="357b7-109">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="357b7-110">子元素</span><span class="sxs-lookup"><span data-stu-id="357b7-110">Child Elements</span></span>  
  
|<span data-ttu-id="357b7-111">元素</span><span class="sxs-lookup"><span data-stu-id="357b7-111">Element</span></span>|<span data-ttu-id="357b7-112">描述</span><span class="sxs-lookup"><span data-stu-id="357b7-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="357b7-113">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="357b7-113">\<endpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-of-client.md)|<span data-ttu-id="357b7-114">包含终结点元素集合，这些元素指定此客户端可连接到的终结点。</span><span class="sxs-lookup"><span data-stu-id="357b7-114">Contains a collection of endpoint elements, that specify the endpoints that this client can connect to.</span></span>|  
|[<span data-ttu-id="357b7-115">\<metadata></span><span class="sxs-lookup"><span data-stu-id="357b7-115">\<metadata></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md)|<span data-ttu-id="357b7-116">包含用于处理元数据的设置。</span><span class="sxs-lookup"><span data-stu-id="357b7-116">Contains settings for processing metadata.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="357b7-117">父元素</span><span class="sxs-lookup"><span data-stu-id="357b7-117">Parent Elements</span></span>  
  
|<span data-ttu-id="357b7-118">元素</span><span class="sxs-lookup"><span data-stu-id="357b7-118">Element</span></span>|<span data-ttu-id="357b7-119">描述</span><span class="sxs-lookup"><span data-stu-id="357b7-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="357b7-120">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="357b7-120">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="357b7-121">所有 Windows Communication Foundation (WCF) 配置元素的根元素。</span><span class="sxs-lookup"><span data-stu-id="357b7-121">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="357b7-122">备注</span><span class="sxs-lookup"><span data-stu-id="357b7-122">Remarks</span></span>  
 <span data-ttu-id="357b7-123">`client` 节定义客户端可以连接的终结点的列表。</span><span class="sxs-lookup"><span data-stu-id="357b7-123">The `client` section defines a list of endpoints that a client can connect to.</span></span> <span data-ttu-id="357b7-124">客户端节中列出的每个终结点都定义了它自己的绑定、行为和协定。</span><span class="sxs-lookup"><span data-stu-id="357b7-124">Each endpoint listed in the client section defines its own binding, behavior, and contract.</span></span> <span data-ttu-id="357b7-125">它由 `name` 和 `contract` 属性共同进行唯一标识。</span><span class="sxs-lookup"><span data-stu-id="357b7-125">It is uniquely identified by the combination of the `name` and `contract` attributes.</span></span> <span data-ttu-id="357b7-126">客户端代码指定要连接到该客户端实现的服务终结点的 `name`。</span><span class="sxs-lookup"><span data-stu-id="357b7-126">The client code specifies the `name` to connect to an endpoint for the service that the client implements.</span></span> <span data-ttu-id="357b7-127">如果省略 `name` 属性，则该终结点将作为其实现的协定的默认终结点。</span><span class="sxs-lookup"><span data-stu-id="357b7-127">If the `name` attribute is omitted, the endpoint acts as the default endpoint for the contract it implements.</span></span>  
  
 <span data-ttu-id="357b7-128">此外，本节还指定了用于处理元数据的设置。</span><span class="sxs-lookup"><span data-stu-id="357b7-128">In addition, this section also specifies settings for processing metadata.</span></span>  
  
## <a name="example"></a><span data-ttu-id="357b7-129">示例</span><span class="sxs-lookup"><span data-stu-id="357b7-129">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="357b7-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="357b7-130">See also</span></span>
- <xref:System.ServiceModel.Configuration.ClientSection>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- [<span data-ttu-id="357b7-131">WCF 客户端配置</span><span class="sxs-lookup"><span data-stu-id="357b7-131">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="357b7-132">客户端</span><span class="sxs-lookup"><span data-stu-id="357b7-132">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
