---
title: <security> 的 <netHttpBinding>
ms.date: 03/30/2017
ms.assetid: dc41f6f7-cabc-4a64-9fa0-ceabf861b348
ms.openlocfilehash: 97c52fa4f062ed0c65d5b1a8ca47a1439ab04cf5
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2019
ms.locfileid: "73736491"
---
# <a name="security-of-nethttpbinding"></a><span data-ttu-id="98f07-102">\<netHttpBinding 的安全 > \<</span><span class="sxs-lookup"><span data-stu-id="98f07-102">\<security> of \<netHttpBinding></span></span>

<span data-ttu-id="98f07-103">定义[\<netHttpBinding >](nethttpbinding.md)的安全功能。</span><span class="sxs-lookup"><span data-stu-id="98f07-103">Defines the security capabilities of the [\<netHttpBinding>](nethttpbinding.md).</span></span>

<span data-ttu-id="98f07-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="98f07-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="98f07-105">\<system &nbsp; &nbsp;[ **>** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="98f07-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="98f07-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<绑定**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="98f07-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="98f07-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netHttpBinding >** ](nethttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="98f07-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netHttpBinding>**](nethttpbinding.md)</span></span>\
<span data-ttu-id="98f07-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<绑定 >** </span><span class="sxs-lookup"><span data-stu-id="98f07-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="98f07-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<** ></span><span class="sxs-lookup"><span data-stu-id="98f07-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="98f07-110">语法</span><span class="sxs-lookup"><span data-stu-id="98f07-110">Syntax</span></span>

```xml
<security mode="Message/None/Transport/TransportWithCredential">
  <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
             realm="string" />
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />
</security>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="98f07-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="98f07-111">Attributes and elements</span></span>

<span data-ttu-id="98f07-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="98f07-112">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="98f07-113">特性</span><span class="sxs-lookup"><span data-stu-id="98f07-113">Attributes</span></span>

|<span data-ttu-id="98f07-114">特性</span><span class="sxs-lookup"><span data-stu-id="98f07-114">Attribute</span></span>|<span data-ttu-id="98f07-115">描述</span><span class="sxs-lookup"><span data-stu-id="98f07-115">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="98f07-116">mode</span><span class="sxs-lookup"><span data-stu-id="98f07-116">mode</span></span>|<span data-ttu-id="98f07-117">可选。</span><span class="sxs-lookup"><span data-stu-id="98f07-117">Optional.</span></span> <span data-ttu-id="98f07-118">指定所使用的安全类型。</span><span class="sxs-lookup"><span data-stu-id="98f07-118">Specifies the type of security that is used.</span></span> <span data-ttu-id="98f07-119">默认值为 `None`。</span><span class="sxs-lookup"><span data-stu-id="98f07-119">The default is `None`.</span></span> <span data-ttu-id="98f07-120">此属性的类型为 <xref:System.ServiceModel.BasicHttpSecurityMode>。</span><span class="sxs-lookup"><span data-stu-id="98f07-120">This attribute is of type <xref:System.ServiceModel.BasicHttpSecurityMode>.</span></span>|

## <a name="mode-attribute"></a><span data-ttu-id="98f07-121">mode 特性</span><span class="sxs-lookup"><span data-stu-id="98f07-121">mode attribute</span></span>

|<span data-ttu-id="98f07-122">“值”</span><span class="sxs-lookup"><span data-stu-id="98f07-122">Value</span></span>|<span data-ttu-id="98f07-123">描述</span><span class="sxs-lookup"><span data-stu-id="98f07-123">Description</span></span>|
|-----------|-----------------|
|<span data-ttu-id="98f07-124">None</span><span class="sxs-lookup"><span data-stu-id="98f07-124">None</span></span>|<span data-ttu-id="98f07-125">-传输过程中消息不受保护。</span><span class="sxs-lookup"><span data-stu-id="98f07-125">-   Messages are not secured during transfer.</span></span>|
|<span data-ttu-id="98f07-126">传输</span><span class="sxs-lookup"><span data-stu-id="98f07-126">Transport</span></span>|<span data-ttu-id="98f07-127">使用 HTTPS 传输提供安全性。</span><span class="sxs-lookup"><span data-stu-id="98f07-127">Security is provided using HTTPS transport.</span></span> <span data-ttu-id="98f07-128">用 HTTPS 保证 SOAP 消息的安全。</span><span class="sxs-lookup"><span data-stu-id="98f07-128">The SOAP messages are secured using HTTPS.</span></span> <span data-ttu-id="98f07-129">使用服务的 X.509 证书向客户端对服务进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="98f07-129">The service is authenticated to the client using the service's X.509 certificate.</span></span> <span data-ttu-id="98f07-130">使用所提供的 ClientCredentialType 对客户端进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="98f07-130">The client is authenticated using the ClientCredentialType supplied.</span></span>|
|<span data-ttu-id="98f07-131">消息</span><span class="sxs-lookup"><span data-stu-id="98f07-131">Message</span></span>|<span data-ttu-id="98f07-132">使用 SOAP 消息安全提供安全性。</span><span class="sxs-lookup"><span data-stu-id="98f07-132">Security is provided using SOAP message security.</span></span> <span data-ttu-id="98f07-133">默认情况下，将对正文进行加密和签名。</span><span class="sxs-lookup"><span data-stu-id="98f07-133">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="98f07-134">对于此绑定，系统要求向带外客户端提供服务器证书。</span><span class="sxs-lookup"><span data-stu-id="98f07-134">For this binding, the system requires that the server certificate be provided to the client out of band.</span></span> <span data-ttu-id="98f07-135">此绑定仅有的有效 `ClientCredentialType` 为 `Certificate`。</span><span class="sxs-lookup"><span data-stu-id="98f07-135">The only valid `ClientCredentialType` for this binding is `Certificate`.</span></span>|
|<span data-ttu-id="98f07-136">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="98f07-136">TransportWithMessageCredential</span></span>|<span data-ttu-id="98f07-137">完整性、保密性和服务器身份验证由传输安全来提供。</span><span class="sxs-lookup"><span data-stu-id="98f07-137">Integrity, confidentiality and server authentication are provided by transport security.</span></span> <span data-ttu-id="98f07-138">客户端身份验证采用 SOAP 消息安全方式提供。</span><span class="sxs-lookup"><span data-stu-id="98f07-138">Client authentication is provided by means of SOAP message security.</span></span> <span data-ttu-id="98f07-139">如果要使用用户名/密码对用户进行身份验证，并且存在用于保护消息传输的现有 HTTP 部署，则适用此模式。</span><span class="sxs-lookup"><span data-stu-id="98f07-139">This mode is relevant when the user is authenticating using username/password and there is an existing HTTP deployment for securing message transfer.</span></span>|
|<span data-ttu-id="98f07-140">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="98f07-140">TransportCredentialOnly</span></span>|<span data-ttu-id="98f07-141">此模式并不提供消息的完整性和保密性，</span><span class="sxs-lookup"><span data-stu-id="98f07-141">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="98f07-142">而是提供基于 http 的客户端身份验证。</span><span class="sxs-lookup"><span data-stu-id="98f07-142">It provides http-based client authentication.</span></span> <span data-ttu-id="98f07-143">使用此模式时应当小心。</span><span class="sxs-lookup"><span data-stu-id="98f07-143">This mode should be used with caution.</span></span> <span data-ttu-id="98f07-144">在通过其他方式（如 IPSec）提供传输安全，并且 WCF 基础结构仅提供客户端身份验证的环境中，应使用此方法。</span><span class="sxs-lookup"><span data-stu-id="98f07-144">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="98f07-145">子元素</span><span class="sxs-lookup"><span data-stu-id="98f07-145">Child elements</span></span>

|<span data-ttu-id="98f07-146">元素</span><span class="sxs-lookup"><span data-stu-id="98f07-146">Element</span></span>|<span data-ttu-id="98f07-147">描述</span><span class="sxs-lookup"><span data-stu-id="98f07-147">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="98f07-148">\<传输 ></span><span class="sxs-lookup"><span data-stu-id="98f07-148">\<transport></span></span>](transport-of-nethttpbinding.md)|<span data-ttu-id="98f07-149">定义基本 HTTP 服务的传输安全设置。</span><span class="sxs-lookup"><span data-stu-id="98f07-149">Defines the transport security settings for a basic HTTP service.</span></span> <span data-ttu-id="98f07-150">此元素与 <xref:System.ServiceModel.HttpTransportSecurity> 相对应。</span><span class="sxs-lookup"><span data-stu-id="98f07-150">This element corresponds to <xref:System.ServiceModel.HttpTransportSecurity>.</span></span>|
|[<span data-ttu-id="98f07-151">\<message ></span><span class="sxs-lookup"><span data-stu-id="98f07-151">\<message></span></span>](message-of-nethttpbinding.md)|<span data-ttu-id="98f07-152">定义基本 HTTP 服务的消息安全设置。</span><span class="sxs-lookup"><span data-stu-id="98f07-152">Defines the message security settings for a basic HTTP service.</span></span> <span data-ttu-id="98f07-153">此元素与 <xref:System.ServiceModel.BasicHttpMessageSecurity> 相对应。</span><span class="sxs-lookup"><span data-stu-id="98f07-153">This element corresponds to <xref:System.ServiceModel.BasicHttpMessageSecurity>.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="98f07-154">父元素</span><span class="sxs-lookup"><span data-stu-id="98f07-154">Parent elements</span></span>

|<span data-ttu-id="98f07-155">元素</span><span class="sxs-lookup"><span data-stu-id="98f07-155">Element</span></span>|<span data-ttu-id="98f07-156">描述</span><span class="sxs-lookup"><span data-stu-id="98f07-156">Description</span></span>|
|-------------|-----------------|
|<span data-ttu-id="98f07-157">绑定</span><span class="sxs-lookup"><span data-stu-id="98f07-157">binding</span></span>|<span data-ttu-id="98f07-158">[\<basicHttpBinding >](basichttpbinding.md)的绑定元素。</span><span class="sxs-lookup"><span data-stu-id="98f07-158">The binding element of the [\<basicHttpBinding>](basichttpbinding.md).</span></span>|

## <a name="remarks"></a><span data-ttu-id="98f07-159">备注</span><span class="sxs-lookup"><span data-stu-id="98f07-159">Remarks</span></span>

 <span data-ttu-id="98f07-160">默认情况下，不会对 SOAP 消息进行保护，也不会对客户端进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="98f07-160">By default, the SOAP message is not secured and the client is not authenticated.</span></span> <span data-ttu-id="98f07-161">使用此元素，您可以配置 `netHttpBinding` 元素的其他安全设置。</span><span class="sxs-lookup"><span data-stu-id="98f07-161">This element enables you to configure additional security settings for the `netHttpBinding` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="98f07-162">请参阅</span><span class="sxs-lookup"><span data-stu-id="98f07-162">See also</span></span>

- <xref:System.ServiceModel.NetHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetHttpBindingElement.Security%2A>  
- [<span data-ttu-id="98f07-163">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="98f07-163">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="98f07-164">选择凭据类型</span><span class="sxs-lookup"><span data-stu-id="98f07-164">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="98f07-165">绑定</span><span class="sxs-lookup"><span data-stu-id="98f07-165">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="98f07-166">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="98f07-166">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="98f07-167">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="98f07-167">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="98f07-168">\<binding ></span><span class="sxs-lookup"><span data-stu-id="98f07-168">\<binding></span></span>](bindings.md)
