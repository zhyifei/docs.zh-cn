---
title: '&lt;compositeDuplex&gt;'
ms.date: 03/30/2017
ms.assetid: 725004d1-ce88-4405-a220-78e89844f81f
ms.openlocfilehash: 4b84b4f2816dc68b7dcee784d957189728e5a4b2
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2019
ms.locfileid: "54149041"
---
# <a name="ltcompositeduplexgt"></a><span data-ttu-id="09410-102">&lt;compositeDuplex&gt;</span><span class="sxs-lookup"><span data-stu-id="09410-102">&lt;compositeDuplex&gt;</span></span>
<span data-ttu-id="09410-103">定义绑定元素，客户端在必须公开一个终结点以使服务可以将消息发送回客户端时使用此元素。</span><span class="sxs-lookup"><span data-stu-id="09410-103">Defines the binding element that is used when the client must expose an endpoint for the service to send messages back to the client.</span></span>  
  
 <span data-ttu-id="09410-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="09410-104">\<system.serviceModel></span></span>  
<span data-ttu-id="09410-105">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="09410-105">\<bindings></span></span>  
<span data-ttu-id="09410-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="09410-106">\<customBinding></span></span>  
<span data-ttu-id="09410-107">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="09410-107">\<binding></span></span>  
<span data-ttu-id="09410-108">\<compositeDuplex ></span><span class="sxs-lookup"><span data-stu-id="09410-108">\<compositeDuplex></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09410-109">语法</span><span class="sxs-lookup"><span data-stu-id="09410-109">Syntax</span></span>  
  
```xml  
<compositeDuplex clientBaseAddress="URI" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="09410-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="09410-110">Attributes and Elements</span></span>  
 <span data-ttu-id="09410-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="09410-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="09410-112">特性</span><span class="sxs-lookup"><span data-stu-id="09410-112">Attributes</span></span>  
  
|<span data-ttu-id="09410-113">特性</span><span class="sxs-lookup"><span data-stu-id="09410-113">Attribute</span></span>|<span data-ttu-id="09410-114">描述</span><span class="sxs-lookup"><span data-stu-id="09410-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="09410-115">clientBaseAddress</span><span class="sxs-lookup"><span data-stu-id="09410-115">clientBaseAddress</span></span>|<span data-ttu-id="09410-116">一个在双工模式下设置反向通道地址的 URI。</span><span class="sxs-lookup"><span data-stu-id="09410-116">A URI that sets the address of the back channel in duplex mode.</span></span> <span data-ttu-id="09410-117">服务使用该地址与客户端进行联系和建立连接。</span><span class="sxs-lookup"><span data-stu-id="09410-117">The service uses this address to make contact and establish a connection with the client.</span></span><br /><br /> <span data-ttu-id="09410-118">如果此属性未设置，默认地址"`full qualified name+default port\TemporaryIndigoAddress\guid`"生成。</span><span class="sxs-lookup"><span data-stu-id="09410-118">If this attribute is not set, a default address "`full qualified name+default port\TemporaryIndigoAddress\guid`" is generated.</span></span> <span data-ttu-id="09410-119">默认值为 `null`。</span><span class="sxs-lookup"><span data-stu-id="09410-119">The default is `null`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="09410-120">子元素</span><span class="sxs-lookup"><span data-stu-id="09410-120">Child Elements</span></span>  
 <span data-ttu-id="09410-121">无</span><span class="sxs-lookup"><span data-stu-id="09410-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="09410-122">父元素</span><span class="sxs-lookup"><span data-stu-id="09410-122">Parent Elements</span></span>  
  
|<span data-ttu-id="09410-123">元素</span><span class="sxs-lookup"><span data-stu-id="09410-123">Element</span></span>|<span data-ttu-id="09410-124">描述</span><span class="sxs-lookup"><span data-stu-id="09410-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="09410-125">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="09410-125">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="09410-126">定义自定义绑定的所有绑定功能。</span><span class="sxs-lookup"><span data-stu-id="09410-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="09410-127">备注</span><span class="sxs-lookup"><span data-stu-id="09410-127">Remarks</span></span>  
 <span data-ttu-id="09410-128">此配置元素与本身不允许进行双工通信的传输（例如，HTTP）一起使用。</span><span class="sxs-lookup"><span data-stu-id="09410-128">This configuration element is used with transports that do not allow duplex communications natively, for example, HTTP.</span></span> <span data-ttu-id="09410-129">与此相反，TCP 本身允许进行双工通信，并且不要求服务在将消息发送回客户端时使用此绑定元素。</span><span class="sxs-lookup"><span data-stu-id="09410-129">TCP, by contrast, allows duplex communications natively, and does not require the use of this binding element for the service to send messages back to a client.</span></span>  
  
 <span data-ttu-id="09410-130">客户端必须公开一个地址，以便服务进行联系和建立连接。</span><span class="sxs-lookup"><span data-stu-id="09410-130">The client must expose an address for the service to make contact and establish a connection.</span></span> <span data-ttu-id="09410-131">此客户端地址由 `clientBaseAddress` 属性提供。</span><span class="sxs-lookup"><span data-stu-id="09410-131">This client address is provided by the `clientBaseAddress` attribute.</span></span> <span data-ttu-id="09410-132">请注意，如果用户未显式设置 ClientBaseAddress，则 Windows Communication Foundation (WCF) 将自动生成一个 ClientBaseAddress。</span><span class="sxs-lookup"><span data-stu-id="09410-132">Note that Windows Communication Foundation (WCF) auto-generates a ClientBaseAddress if one is not explicitly set by the user.</span></span>  
  
## <a name="example"></a><span data-ttu-id="09410-133">示例</span><span class="sxs-lookup"><span data-stu-id="09410-133">Example</span></span>  
  
```xml  
<compositeDuplex clientBaseAddress="http://www.contoso.com" />
```  
  
## <a name="see-also"></a><span data-ttu-id="09410-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="09410-134">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.CompositeDuplexElement>  
 <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="09410-135">绑定</span><span class="sxs-lookup"><span data-stu-id="09410-135">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="09410-136">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="09410-136">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="09410-137">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="09410-137">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="09410-138">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="09410-138">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
