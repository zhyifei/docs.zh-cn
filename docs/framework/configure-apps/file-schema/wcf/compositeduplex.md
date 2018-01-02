---
title: '&lt;compositeDuplex&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 725004d1-ce88-4405-a220-78e89844f81f
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 80c8f3954cccbce8e93ab9d8c516fdfd6c7bff10
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltcompositeduplexgt"></a><span data-ttu-id="26d49-102">&lt;compositeDuplex&gt;</span><span class="sxs-lookup"><span data-stu-id="26d49-102">&lt;compositeDuplex&gt;</span></span>
<span data-ttu-id="26d49-103">定义绑定元素，客户端在必须公开一个终结点以使服务可以将消息发送回客户端时使用此元素。</span><span class="sxs-lookup"><span data-stu-id="26d49-103">Defines the binding element that is used when the client must expose an endpoint for the service to send messages back to the client.</span></span>  
  
 <span data-ttu-id="26d49-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="26d49-104">\<system.serviceModel></span></span>  
<span data-ttu-id="26d49-105">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="26d49-105">\<bindings></span></span>  
<span data-ttu-id="26d49-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="26d49-106">\<customBinding></span></span>  
<span data-ttu-id="26d49-107">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="26d49-107">\<binding></span></span>  
<span data-ttu-id="26d49-108">\<compositeDuplex ></span><span class="sxs-lookup"><span data-stu-id="26d49-108">\<compositeDuplex></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26d49-109">语法</span><span class="sxs-lookup"><span data-stu-id="26d49-109">Syntax</span></span>  
  
```xml  
<compositeDuplex clientBaseAddress="URI" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="26d49-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="26d49-110">Attributes and Elements</span></span>  
 <span data-ttu-id="26d49-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="26d49-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="26d49-112">特性</span><span class="sxs-lookup"><span data-stu-id="26d49-112">Attributes</span></span>  
  
|<span data-ttu-id="26d49-113">特性</span><span class="sxs-lookup"><span data-stu-id="26d49-113">Attribute</span></span>|<span data-ttu-id="26d49-114">描述</span><span class="sxs-lookup"><span data-stu-id="26d49-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="26d49-115">clientBaseAddress</span><span class="sxs-lookup"><span data-stu-id="26d49-115">clientBaseAddress</span></span>|<span data-ttu-id="26d49-116">一个在双工模式下设置反向通道地址的 URI。</span><span class="sxs-lookup"><span data-stu-id="26d49-116">A URI that sets the address of the back channel in duplex mode.</span></span> <span data-ttu-id="26d49-117">服务使用该地址与客户端进行联系和建立连接。</span><span class="sxs-lookup"><span data-stu-id="26d49-117">The service uses this address to make contact and establish a connection with the client.</span></span><br /><br /> <span data-ttu-id="26d49-118">如果此属性未设置，默认地址"`full qualified name+default port\TemporaryIndigoAddress\guid`"生成。</span><span class="sxs-lookup"><span data-stu-id="26d49-118">If this attribute is not set, a default address "`full qualified name+default port\TemporaryIndigoAddress\guid`" is generated.</span></span> <span data-ttu-id="26d49-119">默认值为 `null`。</span><span class="sxs-lookup"><span data-stu-id="26d49-119">The default is `null`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="26d49-120">子元素</span><span class="sxs-lookup"><span data-stu-id="26d49-120">Child Elements</span></span>  
 <span data-ttu-id="26d49-121">无</span><span class="sxs-lookup"><span data-stu-id="26d49-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="26d49-122">父元素</span><span class="sxs-lookup"><span data-stu-id="26d49-122">Parent Elements</span></span>  
  
|<span data-ttu-id="26d49-123">元素</span><span class="sxs-lookup"><span data-stu-id="26d49-123">Element</span></span>|<span data-ttu-id="26d49-124">描述</span><span class="sxs-lookup"><span data-stu-id="26d49-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="26d49-125">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="26d49-125">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="26d49-126">定义自定义绑定的所有绑定功能。</span><span class="sxs-lookup"><span data-stu-id="26d49-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="26d49-127">备注</span><span class="sxs-lookup"><span data-stu-id="26d49-127">Remarks</span></span>  
 <span data-ttu-id="26d49-128">此配置元素与本身不允许进行双工通信的传输（例如，HTTP）一起使用。</span><span class="sxs-lookup"><span data-stu-id="26d49-128">This configuration element is used with transports that do not allow duplex communications natively, for example, HTTP.</span></span> <span data-ttu-id="26d49-129">与此相反，TCP 本身允许进行双工通信，并且不要求服务在将消息发送回客户端时使用此绑定元素。</span><span class="sxs-lookup"><span data-stu-id="26d49-129">TCP, by contrast, allows duplex communications natively, and does not require the use of this binding element for the service to send messages back to a client.</span></span>  
  
 <span data-ttu-id="26d49-130">客户端必须公开一个地址，以便服务进行联系和建立连接。</span><span class="sxs-lookup"><span data-stu-id="26d49-130">The client must expose an address for the service to make contact and establish a connection.</span></span> <span data-ttu-id="26d49-131">此客户端地址由 `clientBaseAddress` 属性提供。</span><span class="sxs-lookup"><span data-stu-id="26d49-131">This client address is provided by the `clientBaseAddress` attribute.</span></span> <span data-ttu-id="26d49-132">请注意，如果用户未显式设置 ClientBaseAddress，则 Windows Communication Foundation (WCF) 将自动生成一个 ClientBaseAddress。</span><span class="sxs-lookup"><span data-stu-id="26d49-132">Note that Windows Communication Foundation (WCF) auto-generates a ClientBaseAddress if one is not explicitly set by the user.</span></span>  
  
## <a name="example"></a><span data-ttu-id="26d49-133">示例</span><span class="sxs-lookup"><span data-stu-id="26d49-133">Example</span></span>  
  
```xml  
<compositeDuplex clientBaseAddress="http://www.contoso.com" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="26d49-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="26d49-134">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.CompositeDuplexElement>  
 <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="26d49-135">绑定</span><span class="sxs-lookup"><span data-stu-id="26d49-135">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="26d49-136">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="26d49-136">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="26d49-137">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="26d49-137">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="26d49-138">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="26d49-138">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
