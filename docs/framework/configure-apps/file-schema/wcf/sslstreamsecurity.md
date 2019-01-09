---
title: '&lt;sslStreamSecurity&gt;'
ms.date: 03/30/2017
ms.assetid: 430a378b-a742-4858-8a12-9f9b235fd627
ms.openlocfilehash: b081a577280f4f2a52ef3b5ece76f519f9701faa
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145102"
---
# <a name="ltsslstreamsecuritygt"></a><span data-ttu-id="75db8-102">&lt;sslStreamSecurity&gt;</span><span class="sxs-lookup"><span data-stu-id="75db8-102">&lt;sslStreamSecurity&gt;</span></span>
<span data-ttu-id="75db8-103">表示支持使用 SSL 流的通道安全的自定义绑定元素。</span><span class="sxs-lookup"><span data-stu-id="75db8-103">Represents a custom binding element that supports channel security using an SSL stream.</span></span>  
  
 <span data-ttu-id="75db8-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="75db8-104">\<system.serviceModel></span></span>  
<span data-ttu-id="75db8-105">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="75db8-105">\<bindings></span></span>  
<span data-ttu-id="75db8-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="75db8-106">\<customBinding></span></span>  
<span data-ttu-id="75db8-107">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="75db8-107">\<binding></span></span>  
<span data-ttu-id="75db8-108">\<sslStreamSecurity ></span><span class="sxs-lookup"><span data-stu-id="75db8-108">\<sslStreamSecurity></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75db8-109">语法</span><span class="sxs-lookup"><span data-stu-id="75db8-109">Syntax</span></span>  
  
```xml  
<sslStreamSecurity requireClientCertificate="Boolean"
                   sslProtocols="Ssl3|Tls|Tls11|Tls12" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="75db8-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="75db8-110">Attributes and Elements</span></span>  
 <span data-ttu-id="75db8-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="75db8-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="75db8-112">特性</span><span class="sxs-lookup"><span data-stu-id="75db8-112">Attributes</span></span>  
  
|<span data-ttu-id="75db8-113">特性</span><span class="sxs-lookup"><span data-stu-id="75db8-113">Attribute</span></span>|<span data-ttu-id="75db8-114">描述</span><span class="sxs-lookup"><span data-stu-id="75db8-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="75db8-115">requireClientCertificate</span><span class="sxs-lookup"><span data-stu-id="75db8-115">requireClientCertificate</span></span>|<span data-ttu-id="75db8-116">一个布尔值，指定此绑定是否需要客户端证书。</span><span class="sxs-lookup"><span data-stu-id="75db8-116">A Boolean value that specifies if a client certificate is required for this binding.</span></span> <span data-ttu-id="75db8-117">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="75db8-117">The default is `false`.</span></span>|  
|<span data-ttu-id="75db8-118">sslProtocols</span><span class="sxs-lookup"><span data-stu-id="75db8-118">sslProtocols</span></span>|<span data-ttu-id="75db8-119">指定支持哪些 SslProtocols 的 SslProtocols 枚举标志值。</span><span class="sxs-lookup"><span data-stu-id="75db8-119">A SslProtocols enum flag value that specifies which SslProtocols are supported.</span></span> <span data-ttu-id="75db8-120">默认值是 Ssl3&#124;Tls&#124;Tls11&#124;Tls12。</span><span class="sxs-lookup"><span data-stu-id="75db8-120">The default is Ssl3&#124;Tls&#124;Tls11&#124;Tls12.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="75db8-121">子元素</span><span class="sxs-lookup"><span data-stu-id="75db8-121">Child Elements</span></span>  
 <span data-ttu-id="75db8-122">无。</span><span class="sxs-lookup"><span data-stu-id="75db8-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="75db8-123">父元素</span><span class="sxs-lookup"><span data-stu-id="75db8-123">Parent Elements</span></span>  
  
|<span data-ttu-id="75db8-124">元素</span><span class="sxs-lookup"><span data-stu-id="75db8-124">Element</span></span>|<span data-ttu-id="75db8-125">描述</span><span class="sxs-lookup"><span data-stu-id="75db8-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="75db8-126">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="75db8-126">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="75db8-127">定义自定义绑定的所有绑定功能。</span><span class="sxs-lookup"><span data-stu-id="75db8-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="75db8-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="75db8-128">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>  
 [<span data-ttu-id="75db8-129">绑定</span><span class="sxs-lookup"><span data-stu-id="75db8-129">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="75db8-130">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="75db8-130">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="75db8-131">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="75db8-131">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="75db8-132">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="75db8-132">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
