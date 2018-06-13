---
title: '&lt;客户端&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.ServiceModel/client
- http://schemas.microsoft.com/.NetConfiguration/v2.0#client
ms.assetid: bf0f7031-76c8-4e7e-a6c6-9ad9119134be
ms.openlocfilehash: b8a006d3dee4149569b3f5b573d9d765504b0d65
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32752632"
---
# <a name="ltclientgt"></a><span data-ttu-id="6591d-102">&lt;客户端&gt;</span><span class="sxs-lookup"><span data-stu-id="6591d-102">&lt;client&gt;</span></span>
<span data-ttu-id="6591d-103">`client` 元素定义客户端可以连接的终结点的列表。</span><span class="sxs-lookup"><span data-stu-id="6591d-103">The `client` element defines a list of endpoints that a client can connect to.</span></span>  
  
 <span data-ttu-id="6591d-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="6591d-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="6591d-105">\<客户端 ></span><span class="sxs-lookup"><span data-stu-id="6591d-105">\<client></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6591d-106">语法</span><span class="sxs-lookup"><span data-stu-id="6591d-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6591d-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="6591d-107">Attributes and Elements</span></span>  
 <span data-ttu-id="6591d-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="6591d-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6591d-109">特性</span><span class="sxs-lookup"><span data-stu-id="6591d-109">Attributes</span></span>  
 <span data-ttu-id="6591d-110">无</span><span class="sxs-lookup"><span data-stu-id="6591d-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6591d-111">子元素</span><span class="sxs-lookup"><span data-stu-id="6591d-111">Child Elements</span></span>  
  
|<span data-ttu-id="6591d-112">元素</span><span class="sxs-lookup"><span data-stu-id="6591d-112">Element</span></span>|<span data-ttu-id="6591d-113">描述</span><span class="sxs-lookup"><span data-stu-id="6591d-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6591d-114">\<终结点 ></span><span class="sxs-lookup"><span data-stu-id="6591d-114">\<endpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-of-client.md)|<span data-ttu-id="6591d-115">包含终结点元素集合，这些元素指定此客户端可连接到的终结点。</span><span class="sxs-lookup"><span data-stu-id="6591d-115">Contains a collection of endpoint elements, that specify the endpoints that this client can connect to.</span></span>|  
|[<span data-ttu-id="6591d-116">\<元数据 ></span><span class="sxs-lookup"><span data-stu-id="6591d-116">\<metadata></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md)|<span data-ttu-id="6591d-117">包含用于处理元数据的设置。</span><span class="sxs-lookup"><span data-stu-id="6591d-117">Contains settings for processing metadata.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6591d-118">父元素</span><span class="sxs-lookup"><span data-stu-id="6591d-118">Parent Elements</span></span>  
  
|<span data-ttu-id="6591d-119">元素</span><span class="sxs-lookup"><span data-stu-id="6591d-119">Element</span></span>|<span data-ttu-id="6591d-120">描述</span><span class="sxs-lookup"><span data-stu-id="6591d-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6591d-121">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="6591d-121">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="6591d-122">所有 Windows Communication Foundation (WCF) 配置元素的根元素。</span><span class="sxs-lookup"><span data-stu-id="6591d-122">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6591d-123">备注</span><span class="sxs-lookup"><span data-stu-id="6591d-123">Remarks</span></span>  
 <span data-ttu-id="6591d-124">`client` 节定义客户端可以连接的终结点的列表。</span><span class="sxs-lookup"><span data-stu-id="6591d-124">The `client` section defines a list of endpoints that a client can connect to.</span></span> <span data-ttu-id="6591d-125">客户端节中列出的每个终结点都定义了它自己的绑定、行为和协定。</span><span class="sxs-lookup"><span data-stu-id="6591d-125">Each endpoint listed in the client section defines its own binding, behavior, and contract.</span></span> <span data-ttu-id="6591d-126">它由 `name` 和 `contract` 属性共同进行唯一标识。</span><span class="sxs-lookup"><span data-stu-id="6591d-126">It is uniquely identified by the combination of the `name` and `contract` attributes.</span></span> <span data-ttu-id="6591d-127">客户端代码指定要连接到该客户端实现的服务终结点的 `name`。</span><span class="sxs-lookup"><span data-stu-id="6591d-127">The client code specifies the `name` to connect to an endpoint for the service that the client implements.</span></span> <span data-ttu-id="6591d-128">如果省略 `name` 属性，则该终结点将作为其实现的协定的默认终结点。</span><span class="sxs-lookup"><span data-stu-id="6591d-128">If the `name` attribute is omitted, the endpoint acts as the default endpoint for the contract it implements.</span></span>  
  
 <span data-ttu-id="6591d-129">此外，本节还指定了用于处理元数据的设置。</span><span class="sxs-lookup"><span data-stu-id="6591d-129">In addition, this section also specifies settings for processing metadata.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6591d-130">示例</span><span class="sxs-lookup"><span data-stu-id="6591d-130">Example</span></span>  
  
```xml  
<client>  
    <endpoint address="/HelloWorld/"  
              bindingConfiguration="usingDefaults"  
              name="MyBinding"  
              binding="customBinding"  
              contract="HelloWorld">  
    <addressProperties actingAs="http://www.microsoft.com/TestActor"  
             identityData="BasicReadWrite" identityType="Spn" isAddressPrivate="false">  
    </endpoint>  
</client>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6591d-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="6591d-131">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ClientSection>  
 <xref:System.ServiceModel.Configuration.MetadataElement>  
 [<span data-ttu-id="6591d-132">WCF 客户端配置</span><span class="sxs-lookup"><span data-stu-id="6591d-132">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)  
 [<span data-ttu-id="6591d-133">客户端</span><span class="sxs-lookup"><span data-stu-id="6591d-133">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
