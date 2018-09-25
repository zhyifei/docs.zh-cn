---
title: '&lt;sslStreamSecurity&gt;'
ms.date: 03/30/2017
ms.assetid: 430a378b-a742-4858-8a12-9f9b235fd627
author: BrucePerlerMS
ms.openlocfilehash: 6eacf1833ecf980696d75c5dbcaaba3ba6403d92
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "47087445"
---
# <a name="ltsslstreamsecuritygt"></a><span data-ttu-id="372da-102">&lt;sslStreamSecurity&gt;</span><span class="sxs-lookup"><span data-stu-id="372da-102">&lt;sslStreamSecurity&gt;</span></span>
<span data-ttu-id="372da-103">表示支持使用 SSL 流的通道安全的自定义绑定元素。</span><span class="sxs-lookup"><span data-stu-id="372da-103">Represents a custom binding element that supports channel security using an SSL stream.</span></span>  
  
 <span data-ttu-id="372da-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="372da-104">\<system.serviceModel></span></span>  
<span data-ttu-id="372da-105">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="372da-105">\<bindings></span></span>  
<span data-ttu-id="372da-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="372da-106">\<customBinding></span></span>  
<span data-ttu-id="372da-107">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="372da-107">\<binding></span></span>  
<span data-ttu-id="372da-108">\<sslStreamSecurity ></span><span class="sxs-lookup"><span data-stu-id="372da-108">\<sslStreamSecurity></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="372da-109">语法</span><span class="sxs-lookup"><span data-stu-id="372da-109">Syntax</span></span>  
  
```xml  
<sslStreamSecurity requireClientCertificate="Boolean"      sslProtocols="Ssl3|Tls|Tls11|Tls12" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="372da-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="372da-110">Attributes and Elements</span></span>  
 <span data-ttu-id="372da-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="372da-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="372da-112">特性</span><span class="sxs-lookup"><span data-stu-id="372da-112">Attributes</span></span>  
  
|<span data-ttu-id="372da-113">特性</span><span class="sxs-lookup"><span data-stu-id="372da-113">Attribute</span></span>|<span data-ttu-id="372da-114">描述</span><span class="sxs-lookup"><span data-stu-id="372da-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="372da-115">requireClientCertificate</span><span class="sxs-lookup"><span data-stu-id="372da-115">requireClientCertificate</span></span>|<span data-ttu-id="372da-116">一个布尔值，指定此绑定是否需要客户端证书。</span><span class="sxs-lookup"><span data-stu-id="372da-116">A Boolean value that specifies if a client certificate is required for this binding.</span></span> <span data-ttu-id="372da-117">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="372da-117">The default is `false`.</span></span>|  
|<span data-ttu-id="372da-118">sslProtocols</span><span class="sxs-lookup"><span data-stu-id="372da-118">sslProtocols</span></span>|<span data-ttu-id="372da-119">指定支持哪些 SslProtocols 的 SslProtocols 枚举标志值。</span><span class="sxs-lookup"><span data-stu-id="372da-119">A SslProtocols enum flag value that specifies which SslProtocols are supported.</span></span> <span data-ttu-id="372da-120">默认值是 Ssl3&#124;Tls&#124;Tls11&#124;Tls12。</span><span class="sxs-lookup"><span data-stu-id="372da-120">The default is Ssl3&#124;Tls&#124;Tls11&#124;Tls12.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="372da-121">子元素</span><span class="sxs-lookup"><span data-stu-id="372da-121">Child Elements</span></span>  
 <span data-ttu-id="372da-122">无。</span><span class="sxs-lookup"><span data-stu-id="372da-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="372da-123">父元素</span><span class="sxs-lookup"><span data-stu-id="372da-123">Parent Elements</span></span>  
  
|<span data-ttu-id="372da-124">元素</span><span class="sxs-lookup"><span data-stu-id="372da-124">Element</span></span>|<span data-ttu-id="372da-125">描述</span><span class="sxs-lookup"><span data-stu-id="372da-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="372da-126">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="372da-126">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="372da-127">定义自定义绑定的所有绑定功能。</span><span class="sxs-lookup"><span data-stu-id="372da-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="372da-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="372da-128">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>  
 [<span data-ttu-id="372da-129">绑定</span><span class="sxs-lookup"><span data-stu-id="372da-129">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="372da-130">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="372da-130">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="372da-131">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="372da-131">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="372da-132">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="372da-132">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
