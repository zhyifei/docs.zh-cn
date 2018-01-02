---
title: "&lt;客户端&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.ServiceModel/client
- http://schemas.microsoft.com/.NetConfiguration/v2.0#client
ms.assetid: bf0f7031-76c8-4e7e-a6c6-9ad9119134be
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a7d52d74c36ea1b1d722d781f554f8cc6691d53e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltclientgt"></a><span data-ttu-id="8956a-102">&lt;客户端&gt;</span><span class="sxs-lookup"><span data-stu-id="8956a-102">&lt;client&gt;</span></span>
<span data-ttu-id="8956a-103">`client` 元素定义客户端可以连接的终结点的列表。</span><span class="sxs-lookup"><span data-stu-id="8956a-103">The `client` element defines a list of endpoints that a client can connect to.</span></span>  
  
 <span data-ttu-id="8956a-104">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="8956a-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="8956a-105">\<客户端 ></span><span class="sxs-lookup"><span data-stu-id="8956a-105">\<client></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8956a-106">语法</span><span class="sxs-lookup"><span data-stu-id="8956a-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8956a-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="8956a-107">Attributes and Elements</span></span>  
 <span data-ttu-id="8956a-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="8956a-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8956a-109">特性</span><span class="sxs-lookup"><span data-stu-id="8956a-109">Attributes</span></span>  
 <span data-ttu-id="8956a-110">无</span><span class="sxs-lookup"><span data-stu-id="8956a-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8956a-111">子元素</span><span class="sxs-lookup"><span data-stu-id="8956a-111">Child Elements</span></span>  
  
|<span data-ttu-id="8956a-112">元素</span><span class="sxs-lookup"><span data-stu-id="8956a-112">Element</span></span>|<span data-ttu-id="8956a-113">描述</span><span class="sxs-lookup"><span data-stu-id="8956a-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8956a-114">\<终结点 ></span><span class="sxs-lookup"><span data-stu-id="8956a-114">\<endpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-of-client.md)|<span data-ttu-id="8956a-115">包含终结点元素集合，这些元素指定此客户端可连接到的终结点。</span><span class="sxs-lookup"><span data-stu-id="8956a-115">Contains a collection of endpoint elements, that specify the endpoints that this client can connect to.</span></span>|  
|[<span data-ttu-id="8956a-116">\<元数据 ></span><span class="sxs-lookup"><span data-stu-id="8956a-116">\<metadata></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md)|<span data-ttu-id="8956a-117">包含用于处理元数据的设置。</span><span class="sxs-lookup"><span data-stu-id="8956a-117">Contains settings for processing metadata.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8956a-118">父元素</span><span class="sxs-lookup"><span data-stu-id="8956a-118">Parent Elements</span></span>  
  
|<span data-ttu-id="8956a-119">元素</span><span class="sxs-lookup"><span data-stu-id="8956a-119">Element</span></span>|<span data-ttu-id="8956a-120">描述</span><span class="sxs-lookup"><span data-stu-id="8956a-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8956a-121">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="8956a-121">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="8956a-122">所有 Windows Communication Foundation (WCF) 配置元素的根元素。</span><span class="sxs-lookup"><span data-stu-id="8956a-122">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8956a-123">备注</span><span class="sxs-lookup"><span data-stu-id="8956a-123">Remarks</span></span>  
 <span data-ttu-id="8956a-124">`client` 节定义客户端可以连接的终结点的列表。</span><span class="sxs-lookup"><span data-stu-id="8956a-124">The `client` section defines a list of endpoints that a client can connect to.</span></span> <span data-ttu-id="8956a-125">客户端节中列出的每个终结点都定义了它自己的绑定、行为和协定。</span><span class="sxs-lookup"><span data-stu-id="8956a-125">Each endpoint listed in the client section defines its own binding, behavior, and contract.</span></span> <span data-ttu-id="8956a-126">它由 `name` 和 `contract` 属性共同进行唯一标识。</span><span class="sxs-lookup"><span data-stu-id="8956a-126">It is uniquely identified by the combination of the `name` and `contract` attributes.</span></span> <span data-ttu-id="8956a-127">客户端代码指定要连接到该客户端实现的服务终结点的 `name`。</span><span class="sxs-lookup"><span data-stu-id="8956a-127">The client code specifies the `name` to connect to an endpoint for the service that the client implements.</span></span> <span data-ttu-id="8956a-128">如果省略 `name` 属性，则该终结点将作为其实现的协定的默认终结点。</span><span class="sxs-lookup"><span data-stu-id="8956a-128">If the `name` attribute is omitted, the endpoint acts as the default endpoint for the contract it implements.</span></span>  
  
 <span data-ttu-id="8956a-129">此外，本节还指定了用于处理元数据的设置。</span><span class="sxs-lookup"><span data-stu-id="8956a-129">In addition, this section also specifies settings for processing metadata.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8956a-130">示例</span><span class="sxs-lookup"><span data-stu-id="8956a-130">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8956a-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="8956a-131">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ClientSection>  
 <xref:System.ServiceModel.Configuration.MetadataElement>  
 [<span data-ttu-id="8956a-132">WCF 客户端配置</span><span class="sxs-lookup"><span data-stu-id="8956a-132">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)  
 [<span data-ttu-id="8956a-133">客户端</span><span class="sxs-lookup"><span data-stu-id="8956a-133">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
