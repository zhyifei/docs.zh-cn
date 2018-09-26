---
title: '&lt;ws2007HttpBinding&gt; 的 &lt;security&gt;'
ms.date: 03/30/2017
ms.assetid: fdda0ff7-b462-4e26-af52-e87ddab71945
author: BrucePerlerMS
ms.openlocfilehash: 6eb7497990abb29693921d601b222a3b7e87bf6c
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2018
ms.locfileid: "47196585"
---
# <a name="ltsecuritygt-of-ltws2007httpbindinggt"></a><span data-ttu-id="872b4-102">&lt;ws2007HttpBinding&gt; 的 &lt;security&gt;</span><span class="sxs-lookup"><span data-stu-id="872b4-102">&lt;security&gt; of &lt;ws2007HttpBinding&gt;</span></span>
<span data-ttu-id="872b4-103">表示与一起使用的安全设置[ \<ws2007HttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md)元素。</span><span class="sxs-lookup"><span data-stu-id="872b4-103">Represents the security settings used with the [\<ws2007HttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md) element.</span></span>  
  
 <span data-ttu-id="872b4-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="872b4-104">\<system.serviceModel></span></span>  
<span data-ttu-id="872b4-105">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="872b4-105">\<bindings></span></span>  
<span data-ttu-id="872b4-106">\<ws2007HttpBinding></span><span class="sxs-lookup"><span data-stu-id="872b4-106">\<ws2007HttpBinding></span></span>  
<span data-ttu-id="872b4-107">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="872b4-107">\<binding></span></span>  
<span data-ttu-id="872b4-108">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="872b4-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="872b4-109">语法</span><span class="sxs-lookup"><span data-stu-id="872b4-109">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
    <bindings>  
        <ws2007HttpBinding>  
            <binding name = "string">  
              <security mode="None/Message/Transport/TransportWithMessageCredential">  
                  <transport>  
                  </transport>  
                  <message>  
                  </message>  
              </security  
        </ws2007HttpBinding>  
    </bindings>  
</system.ServiceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="872b4-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="872b4-110">Attributes and Elements</span></span>  
 <span data-ttu-id="872b4-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="872b4-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="872b4-112">特性</span><span class="sxs-lookup"><span data-stu-id="872b4-112">Attributes</span></span>  
  
|<span data-ttu-id="872b4-113">特性</span><span class="sxs-lookup"><span data-stu-id="872b4-113">Attribute</span></span>|<span data-ttu-id="872b4-114">描述</span><span class="sxs-lookup"><span data-stu-id="872b4-114">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="872b4-115">-可选。</span><span class="sxs-lookup"><span data-stu-id="872b4-115">-   Optional.</span></span> <span data-ttu-id="872b4-116">指定所应用的安全类型。</span><span class="sxs-lookup"><span data-stu-id="872b4-116">Specifies the type of security that is applied.</span></span> <span data-ttu-id="872b4-117">默认值为 `Message`。</span><span class="sxs-lookup"><span data-stu-id="872b4-117">The default is `Message`.</span></span><br /><br /> <span data-ttu-id="872b4-118">此属性的类型为 <xref:System.ServiceModel.SecurityMode>。</span><span class="sxs-lookup"><span data-stu-id="872b4-118">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="872b4-119">Mode 属性</span><span class="sxs-lookup"><span data-stu-id="872b4-119">Mode Attribute</span></span>  
  
|<span data-ttu-id="872b4-120">值</span><span class="sxs-lookup"><span data-stu-id="872b4-120">Value</span></span>|<span data-ttu-id="872b4-121">描述</span><span class="sxs-lookup"><span data-stu-id="872b4-121">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="872b4-122">禁用安全性。</span><span class="sxs-lookup"><span data-stu-id="872b4-122">Security is disabled.</span></span>|  
|`Transport`|<span data-ttu-id="872b4-123">使用 HTTPS 提供安全性。</span><span class="sxs-lookup"><span data-stu-id="872b4-123">Security is provided using HTTPS.</span></span> <span data-ttu-id="872b4-124">此服务必须使用安全套接字层 (SSL) 证书进行配置。</span><span class="sxs-lookup"><span data-stu-id="872b4-124">The service must be configured with Secure Sockets Layer (SSL) certificates.</span></span> <span data-ttu-id="872b4-125">消息使用 HTTPS 获得全面保护，而且客户端使用服务的 SSL 证书对服务进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="872b4-125">The message is entirely secured using HTTPS and the service is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="872b4-126">客户端身份验证通过`ClientCredentials`的属性[\<传输 >](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-ws2007httpbinding.md)元素。</span><span class="sxs-lookup"><span data-stu-id="872b4-126">The client authentication is controlled through the `ClientCredentials` attribute of the [\<transport>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-ws2007httpbinding.md) element.</span></span>|  
|`Message`|<span data-ttu-id="872b4-127">使用 SOAP 消息安全提供安全性。</span><span class="sxs-lookup"><span data-stu-id="872b4-127">Security is provided using SOAP message security.</span></span> <span data-ttu-id="872b4-128">默认情况下，将对 SOAP 正文进行加密和签名。</span><span class="sxs-lookup"><span data-stu-id="872b4-128">By default, the SOAP body is encrypted and signed.</span></span> <span data-ttu-id="872b4-129">此模式提供了各种各样的功能，例如服务凭据在带外客户端是否可用、要使用的算法套件以及通过 <xref:System.ServiceModel.Security.SecurityMessageProperty> 要应用于消息正文的保护级别。</span><span class="sxs-lookup"><span data-stu-id="872b4-129">This mode offers a variety of features, such as whether the service credentials are available at the client out of band, the algorithm suite to use, and what level of protection to apply to the message body through the <xref:System.ServiceModel.Security.SecurityMessageProperty>.</span></span> <span data-ttu-id="872b4-130">每个会话将执行一次客户端身份验证，身份验证的结果在会话过程中将进行缓存。</span><span class="sxs-lookup"><span data-stu-id="872b4-130">Client authentication is performed once for each session and the results of authentication are cached for the duration of the session.</span></span>|  
|`TransportWithMessageCredential`|<span data-ttu-id="872b4-131">在此模式下，HTTPS 将提供完整性、保密性和服务器身份验证，SOAP 消息安全将提供客户端身份验证。</span><span class="sxs-lookup"><span data-stu-id="872b4-131">In this mode, HTTPS provides integrity, confidentiality, and server authentication, and SOAP message security provides client authentication.</span></span> <span data-ttu-id="872b4-132">默认情况下，每个会话将执行一次客户端身份验证，身份验证的结果在会话过程中将进行缓存。</span><span class="sxs-lookup"><span data-stu-id="872b4-132">By default, client authentication is performed once for each session and the results of authentication are cached for the duration of the session.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="872b4-133">子元素</span><span class="sxs-lookup"><span data-stu-id="872b4-133">Child Elements</span></span>  
  
|<span data-ttu-id="872b4-134">元素</span><span class="sxs-lookup"><span data-stu-id="872b4-134">Element</span></span>|<span data-ttu-id="872b4-135">描述</span><span class="sxs-lookup"><span data-stu-id="872b4-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="872b4-136">\<transport></span><span class="sxs-lookup"><span data-stu-id="872b4-136">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-ws2007httpbinding.md)|<span data-ttu-id="872b4-137">定义传输安全设置。</span><span class="sxs-lookup"><span data-stu-id="872b4-137">Defines the transport security settings.</span></span> <span data-ttu-id="872b4-138">此元素与 <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> 类型相对应。</span><span class="sxs-lookup"><span data-stu-id="872b4-138">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span> <span data-ttu-id="872b4-139">仅在将模式设置为“Transport”时才应用这些设置。</span><span class="sxs-lookup"><span data-stu-id="872b4-139">These settings are applied only when the mode is set to Transport.</span></span>|  
|[<span data-ttu-id="872b4-140">\<message></span><span class="sxs-lookup"><span data-stu-id="872b4-140">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-ws2007httpbinding.md)|<span data-ttu-id="872b4-141">定义消息的安全设置。</span><span class="sxs-lookup"><span data-stu-id="872b4-141">Defines the security settings for the message.</span></span> <span data-ttu-id="872b4-142">此元素与 <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> 类型相对应。</span><span class="sxs-lookup"><span data-stu-id="872b4-142">This element corresponds to the <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> type.</span></span> <span data-ttu-id="872b4-143">将模式设置为“Transport”时，不应用这些设置。</span><span class="sxs-lookup"><span data-stu-id="872b4-143">These settings are not applied when the mode is set to Transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="872b4-144">父元素</span><span class="sxs-lookup"><span data-stu-id="872b4-144">Parent Elements</span></span>  
  
|<span data-ttu-id="872b4-145">元素</span><span class="sxs-lookup"><span data-stu-id="872b4-145">Element</span></span>|<span data-ttu-id="872b4-146">描述</span><span class="sxs-lookup"><span data-stu-id="872b4-146">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="872b4-147">\<ws2007HttpBinding></span><span class="sxs-lookup"><span data-stu-id="872b4-147">\<ws2007HttpBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md)|<span data-ttu-id="872b4-148">HTTP 传输应用程序的安全绑定。</span><span class="sxs-lookup"><span data-stu-id="872b4-148">A secure binding for HTTP transport applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="872b4-149">备注</span><span class="sxs-lookup"><span data-stu-id="872b4-149">Remarks</span></span>  
 <span data-ttu-id="872b4-150">此元素专用于与实现 WS-\* 规范的服务进行互操作。</span><span class="sxs-lookup"><span data-stu-id="872b4-150">This element is designed for interoperation with services that implement WS-\* specifications.</span></span> <span data-ttu-id="872b4-151">此绑定的传输安全为 HTTP 上的安全套接字层 (SSL)，即 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="872b4-151">The transport security for this binding is Secure Sockets Layer (SSL) over HTTP, or HTTPS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="872b4-152">请参阅</span><span class="sxs-lookup"><span data-stu-id="872b4-152">See Also</span></span>  
 <xref:System.ServiceModel.WSHttpSecurity>  
 <xref:System.ServiceModel.WSHttpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.WSHttpBindingElement.Security%2A>  
 <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>  
 <xref:System.ServiceModel.BasicHttpSecurity>  
 [<span data-ttu-id="872b4-153">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="872b4-153">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="872b4-154">绑定</span><span class="sxs-lookup"><span data-stu-id="872b4-154">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="872b4-155">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="872b4-155">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="872b4-156">使用绑定来配置 Windows Communication Foundation 服务和客户端</span><span class="sxs-lookup"><span data-stu-id="872b4-156">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="872b4-157">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="872b4-157">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
