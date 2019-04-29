---
title: <compositeDuplex>
ms.date: 03/30/2017
ms.assetid: 725004d1-ce88-4405-a220-78e89844f81f
ms.openlocfilehash: 1e5ecc2b937aa0cdb159a6cbd1222fe6d4af79fb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704174"
---
# <a name="compositeduplex"></a><span data-ttu-id="e1f85-101">\<compositeDuplex></span><span class="sxs-lookup"><span data-stu-id="e1f85-101">\<compositeDuplex></span></span>
<span data-ttu-id="e1f85-102">定义绑定元素，客户端在必须公开一个终结点以使服务可以将消息发送回客户端时使用此元素。</span><span class="sxs-lookup"><span data-stu-id="e1f85-102">Defines the binding element that is used when the client must expose an endpoint for the service to send messages back to the client.</span></span>  
  
 <span data-ttu-id="e1f85-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="e1f85-103">\<system.serviceModel></span></span>  
<span data-ttu-id="e1f85-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="e1f85-104">\<bindings></span></span>  
<span data-ttu-id="e1f85-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="e1f85-105">\<customBinding></span></span>  
<span data-ttu-id="e1f85-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="e1f85-106">\<binding></span></span>  
<span data-ttu-id="e1f85-107">\<compositeDuplex></span><span class="sxs-lookup"><span data-stu-id="e1f85-107">\<compositeDuplex></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1f85-108">语法</span><span class="sxs-lookup"><span data-stu-id="e1f85-108">Syntax</span></span>  
  
```xml  
<compositeDuplex clientBaseAddress="URI" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e1f85-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="e1f85-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e1f85-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="e1f85-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e1f85-111">特性</span><span class="sxs-lookup"><span data-stu-id="e1f85-111">Attributes</span></span>  
  
|<span data-ttu-id="e1f85-112">特性</span><span class="sxs-lookup"><span data-stu-id="e1f85-112">Attribute</span></span>|<span data-ttu-id="e1f85-113">描述</span><span class="sxs-lookup"><span data-stu-id="e1f85-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e1f85-114">clientBaseAddress</span><span class="sxs-lookup"><span data-stu-id="e1f85-114">clientBaseAddress</span></span>|<span data-ttu-id="e1f85-115">一个在双工模式下设置反向通道地址的 URI。</span><span class="sxs-lookup"><span data-stu-id="e1f85-115">A URI that sets the address of the back channel in duplex mode.</span></span> <span data-ttu-id="e1f85-116">服务使用该地址与客户端进行联系和建立连接。</span><span class="sxs-lookup"><span data-stu-id="e1f85-116">The service uses this address to make contact and establish a connection with the client.</span></span><br /><br /> <span data-ttu-id="e1f85-117">如果此属性未设置，默认地址"`full qualified name+default port\TemporaryIndigoAddress\guid`"生成。</span><span class="sxs-lookup"><span data-stu-id="e1f85-117">If this attribute is not set, a default address "`full qualified name+default port\TemporaryIndigoAddress\guid`" is generated.</span></span> <span data-ttu-id="e1f85-118">默认值为 `null`。</span><span class="sxs-lookup"><span data-stu-id="e1f85-118">The default is `null`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e1f85-119">子元素</span><span class="sxs-lookup"><span data-stu-id="e1f85-119">Child Elements</span></span>  
 <span data-ttu-id="e1f85-120">None</span><span class="sxs-lookup"><span data-stu-id="e1f85-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e1f85-121">父元素</span><span class="sxs-lookup"><span data-stu-id="e1f85-121">Parent Elements</span></span>  
  
|<span data-ttu-id="e1f85-122">元素</span><span class="sxs-lookup"><span data-stu-id="e1f85-122">Element</span></span>|<span data-ttu-id="e1f85-123">描述</span><span class="sxs-lookup"><span data-stu-id="e1f85-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e1f85-124">\<binding></span><span class="sxs-lookup"><span data-stu-id="e1f85-124">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="e1f85-125">定义自定义绑定的所有绑定功能。</span><span class="sxs-lookup"><span data-stu-id="e1f85-125">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e1f85-126">备注</span><span class="sxs-lookup"><span data-stu-id="e1f85-126">Remarks</span></span>  
 <span data-ttu-id="e1f85-127">此配置元素与本身不允许进行双工通信的传输（例如，HTTP）一起使用。</span><span class="sxs-lookup"><span data-stu-id="e1f85-127">This configuration element is used with transports that do not allow duplex communications natively, for example, HTTP.</span></span> <span data-ttu-id="e1f85-128">与此相反，TCP 本身允许进行双工通信，并且不要求服务在将消息发送回客户端时使用此绑定元素。</span><span class="sxs-lookup"><span data-stu-id="e1f85-128">TCP, by contrast, allows duplex communications natively, and does not require the use of this binding element for the service to send messages back to a client.</span></span>  
  
 <span data-ttu-id="e1f85-129">客户端必须公开一个地址，以便服务进行联系和建立连接。</span><span class="sxs-lookup"><span data-stu-id="e1f85-129">The client must expose an address for the service to make contact and establish a connection.</span></span> <span data-ttu-id="e1f85-130">此客户端地址由 `clientBaseAddress` 属性提供。</span><span class="sxs-lookup"><span data-stu-id="e1f85-130">This client address is provided by the `clientBaseAddress` attribute.</span></span> <span data-ttu-id="e1f85-131">请注意，如果用户未显式设置 ClientBaseAddress，则 Windows Communication Foundation (WCF) 将自动生成一个 ClientBaseAddress。</span><span class="sxs-lookup"><span data-stu-id="e1f85-131">Note that Windows Communication Foundation (WCF) auto-generates a ClientBaseAddress if one is not explicitly set by the user.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e1f85-132">示例</span><span class="sxs-lookup"><span data-stu-id="e1f85-132">Example</span></span>  
  
```xml  
<compositeDuplex clientBaseAddress="http://www.contoso.com" />
```  
  
## <a name="see-also"></a><span data-ttu-id="e1f85-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="e1f85-133">See also</span></span>

- <xref:System.ServiceModel.Configuration.CompositeDuplexElement>
- <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="e1f85-134">绑定</span><span class="sxs-lookup"><span data-stu-id="e1f85-134">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="e1f85-135">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="e1f85-135">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="e1f85-136">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="e1f85-136">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="e1f85-137">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="e1f85-137">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
