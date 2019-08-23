---
title: <transport> 的 <ws2007HttpBinding>
ms.date: 03/30/2017
ms.assetid: 692befa3-8b0b-4ec5-b601-755874e98eb0
ms.openlocfilehash: ce8b2acb7d87b094958e20ca0b6cca9fc8266a8d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69911986"
---
# <a name="transport-of-ws2007httpbinding"></a><span data-ttu-id="b33b1-102">\<ws2007HttpBinding > 的\<传输 ></span><span class="sxs-lookup"><span data-stu-id="b33b1-102">\<transport> of \<ws2007HttpBinding></span></span>
<span data-ttu-id="b33b1-103">定义 HTTP 传输的身份验证设置。</span><span class="sxs-lookup"><span data-stu-id="b33b1-103">Defines authentication settings for the HTTP transport.</span></span>  
  
 <span data-ttu-id="b33b1-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="b33b1-104">\<system.serviceModel></span></span>  
<span data-ttu-id="b33b1-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="b33b1-105">\<bindings></span></span>  
<span data-ttu-id="b33b1-106">\<ws2007HttpBinding></span><span class="sxs-lookup"><span data-stu-id="b33b1-106">\<ws2007HttpBinding></span></span>  
<span data-ttu-id="b33b1-107">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="b33b1-107">\<binding></span></span>  
<span data-ttu-id="b33b1-108">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="b33b1-108">\<security></span></span>  
<span data-ttu-id="b33b1-109">\<transport></span><span class="sxs-lookup"><span data-stu-id="b33b1-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b33b1-110">语法</span><span class="sxs-lookup"><span data-stu-id="b33b1-110">Syntax</span></span>  
  
```xml  
<transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
           proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
           realm="string" />
```  
  
## <a name="type"></a><span data-ttu-id="b33b1-111">类型</span><span class="sxs-lookup"><span data-stu-id="b33b1-111">Type</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b33b1-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="b33b1-112">Attributes and Elements</span></span>  
 <span data-ttu-id="b33b1-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="b33b1-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b33b1-114">特性</span><span class="sxs-lookup"><span data-stu-id="b33b1-114">Attributes</span></span>  
  
|<span data-ttu-id="b33b1-115">特性</span><span class="sxs-lookup"><span data-stu-id="b33b1-115">Attribute</span></span>|<span data-ttu-id="b33b1-116">描述</span><span class="sxs-lookup"><span data-stu-id="b33b1-116">Description</span></span>|  
|---------------|-----------------|  
|`clientCredentialType`|<span data-ttu-id="b33b1-117">指定用于向服务证明客户端身份的凭据。</span><span class="sxs-lookup"><span data-stu-id="b33b1-117">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="b33b1-118">此属性的类型为 <xref:System.ServiceModel.HttpClientCredentialType>。</span><span class="sxs-lookup"><span data-stu-id="b33b1-118">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|`proxyCredentialType`|<span data-ttu-id="b33b1-119">指定用于向域代理证明客户端身份的凭据。</span><span class="sxs-lookup"><span data-stu-id="b33b1-119">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="b33b1-120">此属性的类型为 <xref:System.ServiceModel.HttpProxyCredentialType>。</span><span class="sxs-lookup"><span data-stu-id="b33b1-120">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|`realm`|<span data-ttu-id="b33b1-121">摘要式或基本身份验证的身份验证领域。</span><span class="sxs-lookup"><span data-stu-id="b33b1-121">The authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="b33b1-122">默认值为一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="b33b1-122">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="b33b1-123">身份验证领域至少指定执行身份验证的主机的名称。</span><span class="sxs-lookup"><span data-stu-id="b33b1-123">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="b33b1-124">它还可以指定具有访问权限的用户集合。</span><span class="sxs-lookup"><span data-stu-id="b33b1-124">It can also specify a collection of users who have access.</span></span> <span data-ttu-id="b33b1-125">用户可以查询身份验证领域，以确定多个可能的用户名和密码中哪一个可以使用。</span><span class="sxs-lookup"><span data-stu-id="b33b1-125">A user can query the authentication realm to determine which one of the several possible usernames and passwords can be used.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="b33b1-126">clientCredentialType 属性</span><span class="sxs-lookup"><span data-stu-id="b33b1-126">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="b33b1-127">值</span><span class="sxs-lookup"><span data-stu-id="b33b1-127">Value</span></span>|<span data-ttu-id="b33b1-128">描述</span><span class="sxs-lookup"><span data-stu-id="b33b1-128">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b33b1-129">无</span><span class="sxs-lookup"><span data-stu-id="b33b1-129">None</span></span>|<span data-ttu-id="b33b1-130">禁用安全性。</span><span class="sxs-lookup"><span data-stu-id="b33b1-130">Security is disabled.</span></span>|  
|<span data-ttu-id="b33b1-131">基本</span><span class="sxs-lookup"><span data-stu-id="b33b1-131">Basic</span></span>|<span data-ttu-id="b33b1-132">使用基本身份验证。</span><span class="sxs-lookup"><span data-stu-id="b33b1-132">Uses basic authentication.</span></span>|  
|<span data-ttu-id="b33b1-133">摘要</span><span class="sxs-lookup"><span data-stu-id="b33b1-133">Digest</span></span>|<span data-ttu-id="b33b1-134">使用摘要式身份验证。</span><span class="sxs-lookup"><span data-stu-id="b33b1-134">Uses digest authentication.</span></span>|  
|<span data-ttu-id="b33b1-135">Ntlm</span><span class="sxs-lookup"><span data-stu-id="b33b1-135">Ntlm</span></span>|<span data-ttu-id="b33b1-136">对 Windows 域使用 NTLM 身份验证作为回退。</span><span class="sxs-lookup"><span data-stu-id="b33b1-136">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="b33b1-137">Windows</span><span class="sxs-lookup"><span data-stu-id="b33b1-137">Windows</span></span>|<span data-ttu-id="b33b1-138">使用集成 Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="b33b1-138">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="b33b1-139">证书</span><span class="sxs-lookup"><span data-stu-id="b33b1-139">Certificate</span></span>|<span data-ttu-id="b33b1-140">使用 X.509 证书对客户端进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="b33b1-140">Uses X.509 certificates to authenticate the client.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="b33b1-141">proxyCredentialType 属性</span><span class="sxs-lookup"><span data-stu-id="b33b1-141">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="b33b1-142">值</span><span class="sxs-lookup"><span data-stu-id="b33b1-142">Value</span></span>|<span data-ttu-id="b33b1-143">描述</span><span class="sxs-lookup"><span data-stu-id="b33b1-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b33b1-144">无</span><span class="sxs-lookup"><span data-stu-id="b33b1-144">None</span></span>|<span data-ttu-id="b33b1-145">禁用安全性。</span><span class="sxs-lookup"><span data-stu-id="b33b1-145">Security is disabled.</span></span>|  
|<span data-ttu-id="b33b1-146">基本</span><span class="sxs-lookup"><span data-stu-id="b33b1-146">Basic</span></span>|<span data-ttu-id="b33b1-147">使用基本身份验证。</span><span class="sxs-lookup"><span data-stu-id="b33b1-147">Uses basic authentication.</span></span>|  
|<span data-ttu-id="b33b1-148">摘要</span><span class="sxs-lookup"><span data-stu-id="b33b1-148">Digest</span></span>|<span data-ttu-id="b33b1-149">使用摘要式身份验证。</span><span class="sxs-lookup"><span data-stu-id="b33b1-149">Uses digest authentication.</span></span>|  
|<span data-ttu-id="b33b1-150">Ntlm</span><span class="sxs-lookup"><span data-stu-id="b33b1-150">Ntlm</span></span>|<span data-ttu-id="b33b1-151">对 Windows 域使用 NTLM 作为回退。</span><span class="sxs-lookup"><span data-stu-id="b33b1-151">Uses NTLM as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="b33b1-152">Windows</span><span class="sxs-lookup"><span data-stu-id="b33b1-152">Windows</span></span>|<span data-ttu-id="b33b1-153">使用集成 Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="b33b1-153">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="b33b1-154">证书</span><span class="sxs-lookup"><span data-stu-id="b33b1-154">Certificate</span></span>|<span data-ttu-id="b33b1-155">使用 X.509 证书对客户端进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="b33b1-155">Uses X.509 certificates to authenticate the client.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b33b1-156">子元素</span><span class="sxs-lookup"><span data-stu-id="b33b1-156">Child Elements</span></span>  
 <span data-ttu-id="b33b1-157">无</span><span class="sxs-lookup"><span data-stu-id="b33b1-157">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b33b1-158">父元素</span><span class="sxs-lookup"><span data-stu-id="b33b1-158">Parent Elements</span></span>  
  
|<span data-ttu-id="b33b1-159">元素</span><span class="sxs-lookup"><span data-stu-id="b33b1-159">Element</span></span>|<span data-ttu-id="b33b1-160">描述</span><span class="sxs-lookup"><span data-stu-id="b33b1-160">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b33b1-161">\<security></span><span class="sxs-lookup"><span data-stu-id="b33b1-161">\<security></span></span>](security-of-ws2007httpbinding.md)|<span data-ttu-id="b33b1-162">表示[ \<ws2007HttpBinding >](ws2007httpbinding.md)元素的安全功能。</span><span class="sxs-lookup"><span data-stu-id="b33b1-162">Represents the security capabilities of the [\<ws2007HttpBinding>](ws2007httpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b33b1-163">请参阅</span><span class="sxs-lookup"><span data-stu-id="b33b1-163">See also</span></span>

- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.WSHttpTransportSecurityElement>
- [<span data-ttu-id="b33b1-164">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="b33b1-164">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="b33b1-165">绑定</span><span class="sxs-lookup"><span data-stu-id="b33b1-165">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="b33b1-166">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="b33b1-166">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="b33b1-167">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="b33b1-167">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="b33b1-168">\<binding></span><span class="sxs-lookup"><span data-stu-id="b33b1-168">\<binding></span></span>](../../../misc/binding.md)
