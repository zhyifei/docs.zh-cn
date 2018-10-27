---
title: '&lt;sslStreamSecurity&gt;'
ms.date: 03/30/2017
ms.assetid: 430a378b-a742-4858-8a12-9f9b235fd627
ms.openlocfilehash: ecc67c2b3972ccb5bc8a1fe9ae9b400292642d53
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2018
ms.locfileid: "50184486"
---
# <a name="ltsslstreamsecuritygt"></a><span data-ttu-id="4af97-102">&lt;sslStreamSecurity&gt;</span><span class="sxs-lookup"><span data-stu-id="4af97-102">&lt;sslStreamSecurity&gt;</span></span>
<span data-ttu-id="4af97-103">表示支持使用 SSL 流的通道安全的自定义绑定元素。</span><span class="sxs-lookup"><span data-stu-id="4af97-103">Represents a custom binding element that supports channel security using an SSL stream.</span></span>  
  
 <span data-ttu-id="4af97-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="4af97-104">\<system.serviceModel></span></span>  
<span data-ttu-id="4af97-105">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="4af97-105">\<bindings></span></span>  
<span data-ttu-id="4af97-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="4af97-106">\<customBinding></span></span>  
<span data-ttu-id="4af97-107">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="4af97-107">\<binding></span></span>  
<span data-ttu-id="4af97-108">\<sslStreamSecurity ></span><span class="sxs-lookup"><span data-stu-id="4af97-108">\<sslStreamSecurity></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4af97-109">语法</span><span class="sxs-lookup"><span data-stu-id="4af97-109">Syntax</span></span>  
  
```xml  
<sslStreamSecurity requireClientCertificate="Boolean"      sslProtocols="Ssl3|Tls|Tls11|Tls12" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4af97-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="4af97-110">Attributes and Elements</span></span>  
 <span data-ttu-id="4af97-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="4af97-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4af97-112">特性</span><span class="sxs-lookup"><span data-stu-id="4af97-112">Attributes</span></span>  
  
|<span data-ttu-id="4af97-113">特性</span><span class="sxs-lookup"><span data-stu-id="4af97-113">Attribute</span></span>|<span data-ttu-id="4af97-114">描述</span><span class="sxs-lookup"><span data-stu-id="4af97-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4af97-115">requireClientCertificate</span><span class="sxs-lookup"><span data-stu-id="4af97-115">requireClientCertificate</span></span>|<span data-ttu-id="4af97-116">一个布尔值，指定此绑定是否需要客户端证书。</span><span class="sxs-lookup"><span data-stu-id="4af97-116">A Boolean value that specifies if a client certificate is required for this binding.</span></span> <span data-ttu-id="4af97-117">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="4af97-117">The default is `false`.</span></span>|  
|<span data-ttu-id="4af97-118">sslProtocols</span><span class="sxs-lookup"><span data-stu-id="4af97-118">sslProtocols</span></span>|<span data-ttu-id="4af97-119">指定支持哪些 SslProtocols 的 SslProtocols 枚举标志值。</span><span class="sxs-lookup"><span data-stu-id="4af97-119">A SslProtocols enum flag value that specifies which SslProtocols are supported.</span></span> <span data-ttu-id="4af97-120">默认值是 Ssl3&#124;Tls&#124;Tls11&#124;Tls12。</span><span class="sxs-lookup"><span data-stu-id="4af97-120">The default is Ssl3&#124;Tls&#124;Tls11&#124;Tls12.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4af97-121">子元素</span><span class="sxs-lookup"><span data-stu-id="4af97-121">Child Elements</span></span>  
 <span data-ttu-id="4af97-122">无。</span><span class="sxs-lookup"><span data-stu-id="4af97-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4af97-123">父元素</span><span class="sxs-lookup"><span data-stu-id="4af97-123">Parent Elements</span></span>  
  
|<span data-ttu-id="4af97-124">元素</span><span class="sxs-lookup"><span data-stu-id="4af97-124">Element</span></span>|<span data-ttu-id="4af97-125">描述</span><span class="sxs-lookup"><span data-stu-id="4af97-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4af97-126">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="4af97-126">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="4af97-127">定义自定义绑定的所有绑定功能。</span><span class="sxs-lookup"><span data-stu-id="4af97-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4af97-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="4af97-128">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>  
 [<span data-ttu-id="4af97-129">绑定</span><span class="sxs-lookup"><span data-stu-id="4af97-129">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="4af97-130">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="4af97-130">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="4af97-131">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="4af97-131">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="4af97-132">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="4af97-132">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
