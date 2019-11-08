---
title: <transport> 的 <ws2007HttpBinding>
ms.date: 03/30/2017
ms.assetid: 692befa3-8b0b-4ec5-b601-755874e98eb0
ms.openlocfilehash: 0cd20c607b0c4ddd3ecfd806d38ba63b4a5c5a25
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2019
ms.locfileid: "73732761"
---
# <a name="transport-of-ws2007httpbinding"></a><span data-ttu-id="9cb41-102">\<ws2007HttpBinding 的 \<传输 > ></span><span class="sxs-lookup"><span data-stu-id="9cb41-102">\<transport> of \<ws2007HttpBinding></span></span>
<span data-ttu-id="9cb41-103">定义 HTTP 传输的身份验证设置。</span><span class="sxs-lookup"><span data-stu-id="9cb41-103">Defines authentication settings for the HTTP transport.</span></span>  
  
<span data-ttu-id="9cb41-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9cb41-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9cb41-105">\<system &nbsp; &nbsp;[ **>** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="9cb41-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="9cb41-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<绑定**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="9cb41-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="9cb41-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<ws2007HttpBinding >** ](ws2007httpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="9cb41-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007HttpBinding>**](ws2007httpbinding.md)</span></span>\
<span data-ttu-id="9cb41-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<绑定 >** </span><span class="sxs-lookup"><span data-stu-id="9cb41-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="9cb41-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](security-of-ws2007httpbinding.md) ></span><span class="sxs-lookup"><span data-stu-id="9cb41-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-ws2007httpbinding.md)</span></span>\
<span data-ttu-id="9cb41-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<传输 >**</span><span class="sxs-lookup"><span data-stu-id="9cb41-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9cb41-111">语法</span><span class="sxs-lookup"><span data-stu-id="9cb41-111">Syntax</span></span>  
  
```xml  
<transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
           proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
           realm="string" />
```  
  
## <a name="type"></a><span data-ttu-id="9cb41-112">键入</span><span class="sxs-lookup"><span data-stu-id="9cb41-112">Type</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9cb41-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="9cb41-113">Attributes and Elements</span></span>  
 <span data-ttu-id="9cb41-114">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="9cb41-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9cb41-115">特性</span><span class="sxs-lookup"><span data-stu-id="9cb41-115">Attributes</span></span>  
  
|<span data-ttu-id="9cb41-116">特性</span><span class="sxs-lookup"><span data-stu-id="9cb41-116">Attribute</span></span>|<span data-ttu-id="9cb41-117">描述</span><span class="sxs-lookup"><span data-stu-id="9cb41-117">Description</span></span>|  
|---------------|-----------------|  
|`clientCredentialType`|<span data-ttu-id="9cb41-118">指定用于向服务证明客户端身份的凭据。</span><span class="sxs-lookup"><span data-stu-id="9cb41-118">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="9cb41-119">此属性的类型为 <xref:System.ServiceModel.HttpClientCredentialType>。</span><span class="sxs-lookup"><span data-stu-id="9cb41-119">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|`proxyCredentialType`|<span data-ttu-id="9cb41-120">指定用于向域代理证明客户端身份的凭据。</span><span class="sxs-lookup"><span data-stu-id="9cb41-120">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="9cb41-121">此属性的类型为 <xref:System.ServiceModel.HttpProxyCredentialType>。</span><span class="sxs-lookup"><span data-stu-id="9cb41-121">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|`realm`|<span data-ttu-id="9cb41-122">摘要式或基本身份验证的身份验证领域。</span><span class="sxs-lookup"><span data-stu-id="9cb41-122">The authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="9cb41-123">默认值为一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="9cb41-123">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="9cb41-124">身份验证领域至少指定执行身份验证的主机的名称。</span><span class="sxs-lookup"><span data-stu-id="9cb41-124">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="9cb41-125">它还可以指定具有访问权限的用户集合。</span><span class="sxs-lookup"><span data-stu-id="9cb41-125">It can also specify a collection of users who have access.</span></span> <span data-ttu-id="9cb41-126">用户可以查询身份验证领域，以确定多个可能的用户名和密码中哪一个可以使用。</span><span class="sxs-lookup"><span data-stu-id="9cb41-126">A user can query the authentication realm to determine which one of the several possible usernames and passwords can be used.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="9cb41-127">clientCredentialType 属性</span><span class="sxs-lookup"><span data-stu-id="9cb41-127">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="9cb41-128">“值”</span><span class="sxs-lookup"><span data-stu-id="9cb41-128">Value</span></span>|<span data-ttu-id="9cb41-129">描述</span><span class="sxs-lookup"><span data-stu-id="9cb41-129">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9cb41-130">None</span><span class="sxs-lookup"><span data-stu-id="9cb41-130">None</span></span>|<span data-ttu-id="9cb41-131">禁用安全性。</span><span class="sxs-lookup"><span data-stu-id="9cb41-131">Security is disabled.</span></span>|  
|<span data-ttu-id="9cb41-132">Basic</span><span class="sxs-lookup"><span data-stu-id="9cb41-132">Basic</span></span>|<span data-ttu-id="9cb41-133">使用基本身份验证。</span><span class="sxs-lookup"><span data-stu-id="9cb41-133">Uses basic authentication.</span></span>|  
|<span data-ttu-id="9cb41-134">摘要</span><span class="sxs-lookup"><span data-stu-id="9cb41-134">Digest</span></span>|<span data-ttu-id="9cb41-135">使用摘要式身份验证。</span><span class="sxs-lookup"><span data-stu-id="9cb41-135">Uses digest authentication.</span></span>|  
|<span data-ttu-id="9cb41-136">Ntlm</span><span class="sxs-lookup"><span data-stu-id="9cb41-136">Ntlm</span></span>|<span data-ttu-id="9cb41-137">对 Windows 域使用 NTLM 身份验证作为回退。</span><span class="sxs-lookup"><span data-stu-id="9cb41-137">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="9cb41-138">Windows</span><span class="sxs-lookup"><span data-stu-id="9cb41-138">Windows</span></span>|<span data-ttu-id="9cb41-139">使用集成 Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="9cb41-139">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="9cb41-140">证书</span><span class="sxs-lookup"><span data-stu-id="9cb41-140">Certificate</span></span>|<span data-ttu-id="9cb41-141">使用 X.509 证书对客户端进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="9cb41-141">Uses X.509 certificates to authenticate the client.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="9cb41-142">proxyCredentialType 属性</span><span class="sxs-lookup"><span data-stu-id="9cb41-142">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="9cb41-143">“值”</span><span class="sxs-lookup"><span data-stu-id="9cb41-143">Value</span></span>|<span data-ttu-id="9cb41-144">描述</span><span class="sxs-lookup"><span data-stu-id="9cb41-144">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9cb41-145">None</span><span class="sxs-lookup"><span data-stu-id="9cb41-145">None</span></span>|<span data-ttu-id="9cb41-146">禁用安全性。</span><span class="sxs-lookup"><span data-stu-id="9cb41-146">Security is disabled.</span></span>|  
|<span data-ttu-id="9cb41-147">Basic</span><span class="sxs-lookup"><span data-stu-id="9cb41-147">Basic</span></span>|<span data-ttu-id="9cb41-148">使用基本身份验证。</span><span class="sxs-lookup"><span data-stu-id="9cb41-148">Uses basic authentication.</span></span>|  
|<span data-ttu-id="9cb41-149">摘要</span><span class="sxs-lookup"><span data-stu-id="9cb41-149">Digest</span></span>|<span data-ttu-id="9cb41-150">使用摘要式身份验证。</span><span class="sxs-lookup"><span data-stu-id="9cb41-150">Uses digest authentication.</span></span>|  
|<span data-ttu-id="9cb41-151">Ntlm</span><span class="sxs-lookup"><span data-stu-id="9cb41-151">Ntlm</span></span>|<span data-ttu-id="9cb41-152">对 Windows 域使用 NTLM 作为回退。</span><span class="sxs-lookup"><span data-stu-id="9cb41-152">Uses NTLM as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="9cb41-153">Windows</span><span class="sxs-lookup"><span data-stu-id="9cb41-153">Windows</span></span>|<span data-ttu-id="9cb41-154">使用集成 Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="9cb41-154">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="9cb41-155">证书</span><span class="sxs-lookup"><span data-stu-id="9cb41-155">Certificate</span></span>|<span data-ttu-id="9cb41-156">使用 X.509 证书对客户端进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="9cb41-156">Uses X.509 certificates to authenticate the client.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9cb41-157">子元素</span><span class="sxs-lookup"><span data-stu-id="9cb41-157">Child Elements</span></span>  
 <span data-ttu-id="9cb41-158">None</span><span class="sxs-lookup"><span data-stu-id="9cb41-158">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9cb41-159">父元素</span><span class="sxs-lookup"><span data-stu-id="9cb41-159">Parent Elements</span></span>  
  
|<span data-ttu-id="9cb41-160">元素</span><span class="sxs-lookup"><span data-stu-id="9cb41-160">Element</span></span>|<span data-ttu-id="9cb41-161">描述</span><span class="sxs-lookup"><span data-stu-id="9cb41-161">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9cb41-162">\<security ></span><span class="sxs-lookup"><span data-stu-id="9cb41-162">\<security></span></span>](security-of-ws2007httpbinding.md)|<span data-ttu-id="9cb41-163">表示[\<ws2007HttpBinding >](ws2007httpbinding.md)元素的安全功能。</span><span class="sxs-lookup"><span data-stu-id="9cb41-163">Represents the security capabilities of the [\<ws2007HttpBinding>](ws2007httpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9cb41-164">请参阅</span><span class="sxs-lookup"><span data-stu-id="9cb41-164">See also</span></span>

- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.WSHttpTransportSecurityElement>
- [<span data-ttu-id="9cb41-165">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="9cb41-165">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="9cb41-166">绑定</span><span class="sxs-lookup"><span data-stu-id="9cb41-166">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="9cb41-167">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="9cb41-167">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="9cb41-168">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="9cb41-168">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="9cb41-169">\<binding ></span><span class="sxs-lookup"><span data-stu-id="9cb41-169">\<binding></span></span>](bindings.md)
