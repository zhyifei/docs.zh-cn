---
title: <sslStreamSecurity>
ms.date: 03/30/2017
ms.assetid: 430a378b-a742-4858-8a12-9f9b235fd627
ms.openlocfilehash: 67ec30b2bf3c322b949700789ce942e4281b77a4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59204440"
---
# <a name="sslstreamsecurity"></a><span data-ttu-id="0000a-101">\<sslStreamSecurity></span><span class="sxs-lookup"><span data-stu-id="0000a-101">\<sslStreamSecurity></span></span>
<span data-ttu-id="0000a-102">表示一个自定义绑定元素，它支持使用 SSL 流的通道安全。</span><span class="sxs-lookup"><span data-stu-id="0000a-102">Represents a custom binding element that supports channel security using an SSL stream.</span></span>  
  
 <span data-ttu-id="0000a-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="0000a-103">\<system.serviceModel></span></span>  
<span data-ttu-id="0000a-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="0000a-104">\<bindings></span></span>  
<span data-ttu-id="0000a-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="0000a-105">\<customBinding></span></span>  
<span data-ttu-id="0000a-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="0000a-106">\<binding></span></span>  
<span data-ttu-id="0000a-107">\<sslStreamSecurity></span><span class="sxs-lookup"><span data-stu-id="0000a-107">\<sslStreamSecurity></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0000a-108">语法</span><span class="sxs-lookup"><span data-stu-id="0000a-108">Syntax</span></span>  
  
```xml  
<sslStreamSecurity requireClientCertificate="Boolean"
                   sslProtocols="Ssl3|Tls|Tls11|Tls12" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0000a-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="0000a-109">Attributes and Elements</span></span>  
 <span data-ttu-id="0000a-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="0000a-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0000a-111">特性</span><span class="sxs-lookup"><span data-stu-id="0000a-111">Attributes</span></span>  
  
|<span data-ttu-id="0000a-112">特性</span><span class="sxs-lookup"><span data-stu-id="0000a-112">Attribute</span></span>|<span data-ttu-id="0000a-113">描述</span><span class="sxs-lookup"><span data-stu-id="0000a-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0000a-114">requireClientCertificate</span><span class="sxs-lookup"><span data-stu-id="0000a-114">requireClientCertificate</span></span>|<span data-ttu-id="0000a-115">一个布尔值，指定此绑定是否需要客户端证书。</span><span class="sxs-lookup"><span data-stu-id="0000a-115">A Boolean value that specifies if a client certificate is required for this binding.</span></span> <span data-ttu-id="0000a-116">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="0000a-116">The default is `false`.</span></span>|  
|<span data-ttu-id="0000a-117">sslProtocols</span><span class="sxs-lookup"><span data-stu-id="0000a-117">sslProtocols</span></span>|<span data-ttu-id="0000a-118">指定支持哪些 SslProtocols 的 SslProtocols 枚举标志值。</span><span class="sxs-lookup"><span data-stu-id="0000a-118">A SslProtocols enum flag value that specifies which SslProtocols are supported.</span></span> <span data-ttu-id="0000a-119">默认值是 Ssl3&#124;Tls&#124;Tls11&#124;Tls12。</span><span class="sxs-lookup"><span data-stu-id="0000a-119">The default is Ssl3&#124;Tls&#124;Tls11&#124;Tls12.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0000a-120">子元素</span><span class="sxs-lookup"><span data-stu-id="0000a-120">Child Elements</span></span>  
 <span data-ttu-id="0000a-121">无。</span><span class="sxs-lookup"><span data-stu-id="0000a-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0000a-122">父元素</span><span class="sxs-lookup"><span data-stu-id="0000a-122">Parent Elements</span></span>  
  
|<span data-ttu-id="0000a-123">元素</span><span class="sxs-lookup"><span data-stu-id="0000a-123">Element</span></span>|<span data-ttu-id="0000a-124">描述</span><span class="sxs-lookup"><span data-stu-id="0000a-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0000a-125">\<binding></span><span class="sxs-lookup"><span data-stu-id="0000a-125">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="0000a-126">定义自定义绑定的所有绑定功能。</span><span class="sxs-lookup"><span data-stu-id="0000a-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0000a-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="0000a-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>
- [<span data-ttu-id="0000a-128">绑定</span><span class="sxs-lookup"><span data-stu-id="0000a-128">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="0000a-129">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="0000a-129">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="0000a-130">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="0000a-130">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="0000a-131">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="0000a-131">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
