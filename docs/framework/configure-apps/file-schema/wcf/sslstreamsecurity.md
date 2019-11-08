---
title: <sslStreamSecurity>
ms.date: 03/30/2017
ms.assetid: 430a378b-a742-4858-8a12-9f9b235fd627
ms.openlocfilehash: c5c7ec2b18143ff4d71540a60e24b8225ca4db16
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738590"
---
# <a name="sslstreamsecurity"></a><span data-ttu-id="28cd4-101">\<Custombinding> sslstreamsecurity> ></span><span class="sxs-lookup"><span data-stu-id="28cd4-101">\<sslStreamSecurity></span></span>
<span data-ttu-id="28cd4-102">表示一个自定义绑定元素，它支持使用 SSL 流的通道安全。</span><span class="sxs-lookup"><span data-stu-id="28cd4-102">Represents a custom binding element that supports channel security using an SSL stream.</span></span>  
  
<span data-ttu-id="28cd4-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="28cd4-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="28cd4-104">\<system &nbsp; &nbsp;[ **>** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="28cd4-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="28cd4-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<绑定**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="28cd4-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="28cd4-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="28cd4-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="28cd4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<绑定 >** </span><span class="sxs-lookup"><span data-stu-id="28cd4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="28cd4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<custombinding> sslstreamsecurity> >**</span><span class="sxs-lookup"><span data-stu-id="28cd4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sslStreamSecurity>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28cd4-109">语法</span><span class="sxs-lookup"><span data-stu-id="28cd4-109">Syntax</span></span>  
  
```xml  
<sslStreamSecurity requireClientCertificate="Boolean"
                   sslProtocols="Ssl3|Tls|Tls11|Tls12" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="28cd4-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="28cd4-110">Attributes and Elements</span></span>  
 <span data-ttu-id="28cd4-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="28cd4-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="28cd4-112">特性</span><span class="sxs-lookup"><span data-stu-id="28cd4-112">Attributes</span></span>  
  
|<span data-ttu-id="28cd4-113">特性</span><span class="sxs-lookup"><span data-stu-id="28cd4-113">Attribute</span></span>|<span data-ttu-id="28cd4-114">描述</span><span class="sxs-lookup"><span data-stu-id="28cd4-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="28cd4-115">requireClientCertificate</span><span class="sxs-lookup"><span data-stu-id="28cd4-115">requireClientCertificate</span></span>|<span data-ttu-id="28cd4-116">一个布尔值，指定此绑定是否需要客户端证书。</span><span class="sxs-lookup"><span data-stu-id="28cd4-116">A Boolean value that specifies if a client certificate is required for this binding.</span></span> <span data-ttu-id="28cd4-117">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="28cd4-117">The default is `false`.</span></span>|  
|<span data-ttu-id="28cd4-118">sslProtocols</span><span class="sxs-lookup"><span data-stu-id="28cd4-118">sslProtocols</span></span>|<span data-ttu-id="28cd4-119">指定支持哪些 SslProtocols 的 SslProtocols 枚举标志值。</span><span class="sxs-lookup"><span data-stu-id="28cd4-119">A SslProtocols enum flag value that specifies which SslProtocols are supported.</span></span> <span data-ttu-id="28cd4-120">默认值为 Ssl3&#124;Tls&#124;Tls11&#124;Tls12。</span><span class="sxs-lookup"><span data-stu-id="28cd4-120">The default is Ssl3&#124;Tls&#124;Tls11&#124;Tls12.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="28cd4-121">子元素</span><span class="sxs-lookup"><span data-stu-id="28cd4-121">Child Elements</span></span>  
 <span data-ttu-id="28cd4-122">无。</span><span class="sxs-lookup"><span data-stu-id="28cd4-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="28cd4-123">父元素</span><span class="sxs-lookup"><span data-stu-id="28cd4-123">Parent Elements</span></span>  
  
|<span data-ttu-id="28cd4-124">元素</span><span class="sxs-lookup"><span data-stu-id="28cd4-124">Element</span></span>|<span data-ttu-id="28cd4-125">描述</span><span class="sxs-lookup"><span data-stu-id="28cd4-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="28cd4-126">\<binding ></span><span class="sxs-lookup"><span data-stu-id="28cd4-126">\<binding></span></span>](bindings.md)|<span data-ttu-id="28cd4-127">定义自定义绑定的所有绑定功能。</span><span class="sxs-lookup"><span data-stu-id="28cd4-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="28cd4-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="28cd4-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>
- [<span data-ttu-id="28cd4-129">绑定</span><span class="sxs-lookup"><span data-stu-id="28cd4-129">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="28cd4-130">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="28cd4-130">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="28cd4-131">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="28cd4-131">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="28cd4-132">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="28cd4-132">\<customBinding></span></span>](custombinding.md)
