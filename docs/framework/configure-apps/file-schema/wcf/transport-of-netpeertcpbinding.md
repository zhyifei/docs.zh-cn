---
title: <transport> 的 <netPeerTcpBinding>
ms.date: 03/30/2017
ms.assetid: c44d86d2-1160-44d7-9c7a-297b12eccc7f
ms.openlocfilehash: 08be5d752f8422ebe6442b295195f21b16a274c0
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399317"
---
# <a name="transport-of-netpeertcpbinding"></a><span data-ttu-id="ea46b-102">\<netPeerTcpBinding > 的\<传输 ></span><span class="sxs-lookup"><span data-stu-id="ea46b-102">\<transport> of \<netPeerTcpBinding></span></span>
<span data-ttu-id="ea46b-103">指定使用[ \<netPeerTcpBinding >](netpeertcpbinding.md)时的传输级安全性设置。</span><span class="sxs-lookup"><span data-stu-id="ea46b-103">Specifies settings for transport level security when using the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>  
  
<span data-ttu-id="ea46b-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ea46b-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ea46b-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="ea46b-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="ea46b-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<绑定 >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="ea46b-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="ea46b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netPeerTcpBinding >** ](netpeertcpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="ea46b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netPeerTcpBinding>**](netpeertcpbinding.md)</span></span>\
<span data-ttu-id="ea46b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<绑定 >** </span><span class="sxs-lookup"><span data-stu-id="ea46b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="ea46b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<安全 >** ](security-of-netpeerbinding.md)</span><span class="sxs-lookup"><span data-stu-id="ea46b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-netpeerbinding.md)</span></span>\
<span data-ttu-id="ea46b-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<传输 >**</span><span class="sxs-lookup"><span data-stu-id="ea46b-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea46b-111">语法</span><span class="sxs-lookup"><span data-stu-id="ea46b-111">Syntax</span></span>  
  
```xml  
<netPeerTcpBinding>
  <binding>
    <security>
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerTcpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ea46b-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="ea46b-112">Attributes and Elements</span></span>  
 <span data-ttu-id="ea46b-113">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="ea46b-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ea46b-114">特性</span><span class="sxs-lookup"><span data-stu-id="ea46b-114">Attributes</span></span>  
  
|<span data-ttu-id="ea46b-115">特性</span><span class="sxs-lookup"><span data-stu-id="ea46b-115">Attribute</span></span>|<span data-ttu-id="ea46b-116">描述</span><span class="sxs-lookup"><span data-stu-id="ea46b-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ea46b-117">credentialType</span><span class="sxs-lookup"><span data-stu-id="ea46b-117">credentialType</span></span>|<span data-ttu-id="ea46b-118">可选。</span><span class="sxs-lookup"><span data-stu-id="ea46b-118">Optional.</span></span> <span data-ttu-id="ea46b-119">指定用于验证通过对等传输发送的消息的凭据的类型。</span><span class="sxs-lookup"><span data-stu-id="ea46b-119">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="ea46b-120">此属性的类型为 <xref:System.ServiceModel.PeerTransportCredentialType>。</span><span class="sxs-lookup"><span data-stu-id="ea46b-120">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="ea46b-121">credentialType 属性</span><span class="sxs-lookup"><span data-stu-id="ea46b-121">credentialType Attribute</span></span>  
  
|<span data-ttu-id="ea46b-122">值</span><span class="sxs-lookup"><span data-stu-id="ea46b-122">Value</span></span>|<span data-ttu-id="ea46b-123">描述</span><span class="sxs-lookup"><span data-stu-id="ea46b-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ea46b-124">证书</span><span class="sxs-lookup"><span data-stu-id="ea46b-124">Certificate</span></span>|<span data-ttu-id="ea46b-125">对等通道传输的身份验证需要 X509 证书。</span><span class="sxs-lookup"><span data-stu-id="ea46b-125">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="ea46b-126">Password</span><span class="sxs-lookup"><span data-stu-id="ea46b-126">Password</span></span>|<span data-ttu-id="ea46b-127">对等通道传输的身份验证需要正确的密码。</span><span class="sxs-lookup"><span data-stu-id="ea46b-127">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ea46b-128">子元素</span><span class="sxs-lookup"><span data-stu-id="ea46b-128">Child Elements</span></span>  
 <span data-ttu-id="ea46b-129">无</span><span class="sxs-lookup"><span data-stu-id="ea46b-129">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ea46b-130">父元素</span><span class="sxs-lookup"><span data-stu-id="ea46b-130">Parent Elements</span></span>  
  
|<span data-ttu-id="ea46b-131">元素</span><span class="sxs-lookup"><span data-stu-id="ea46b-131">Element</span></span>|<span data-ttu-id="ea46b-132">描述</span><span class="sxs-lookup"><span data-stu-id="ea46b-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ea46b-133">\<security></span><span class="sxs-lookup"><span data-stu-id="ea46b-133">\<security></span></span>](security-of-netpeerbinding.md)|<span data-ttu-id="ea46b-134">定义[ \<netPeerTcpBinding >](netpeertcpbinding.md)的安全设置。</span><span class="sxs-lookup"><span data-stu-id="ea46b-134">Defines the security settings for the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ea46b-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="ea46b-135">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>
- <xref:System.ServiceModel.Configuration.PeerSecurityElement.Transport%2A>
- <xref:System.ServiceModel.PeerTransportSecuritySettings>
- [<span data-ttu-id="ea46b-136">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="ea46b-136">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="ea46b-137">绑定</span><span class="sxs-lookup"><span data-stu-id="ea46b-137">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="ea46b-138">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="ea46b-138">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="ea46b-139">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="ea46b-139">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="ea46b-140">\<binding></span><span class="sxs-lookup"><span data-stu-id="ea46b-140">\<binding></span></span>](../../../misc/binding.md)
