---
title: <security> 的 <netHttpBinding>
ms.date: 03/30/2017
ms.assetid: dc41f6f7-cabc-4a64-9fa0-ceabf861b348
ms.openlocfilehash: f2750036aa4d3fbe41062ad041e50ff3a4be32b5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61670555"
---
# <a name="security-of-nethttpbinding"></a><span data-ttu-id="56660-102">\<安全 > 的\<netHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="56660-102">\<security> of \<netHttpBinding></span></span>

<span data-ttu-id="56660-103">定义的安全功能[ \<basicHttpBinding >](basichttpbinding.md)。</span><span class="sxs-lookup"><span data-stu-id="56660-103">Defines the security capabilities of the [\<basicHttpBinding>](basichttpbinding.md).</span></span>

<span data-ttu-id="56660-104">\<system.ServiceModel>\\</span><span class="sxs-lookup"><span data-stu-id="56660-104">\<system.ServiceModel>\\</span></span>
<span data-ttu-id="56660-105">\<bindings>\\</span><span class="sxs-lookup"><span data-stu-id="56660-105">\<bindings>\\</span></span>
<span data-ttu-id="56660-106">\<netHttpBinding>\\</span><span class="sxs-lookup"><span data-stu-id="56660-106">\<netHttpBinding>\\</span></span>
<span data-ttu-id="56660-107">\<binding>\\</span><span class="sxs-lookup"><span data-stu-id="56660-107">\<binding>\\</span></span>
<span data-ttu-id="56660-108">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="56660-108">\<security></span></span>

## <a name="syntax"></a><span data-ttu-id="56660-109">语法</span><span class="sxs-lookup"><span data-stu-id="56660-109">Syntax</span></span>

```xml
<security mode="Message/None/Transport/TransportWithCredential">
  <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
             realm="string" />
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />
</security>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="56660-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="56660-110">Attributes and elements</span></span>

<span data-ttu-id="56660-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="56660-111">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="56660-112">特性</span><span class="sxs-lookup"><span data-stu-id="56660-112">Attributes</span></span>

|<span data-ttu-id="56660-113">特性</span><span class="sxs-lookup"><span data-stu-id="56660-113">Attribute</span></span>|<span data-ttu-id="56660-114">描述</span><span class="sxs-lookup"><span data-stu-id="56660-114">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="56660-115">mode</span><span class="sxs-lookup"><span data-stu-id="56660-115">mode</span></span>|<span data-ttu-id="56660-116">可选。</span><span class="sxs-lookup"><span data-stu-id="56660-116">Optional.</span></span> <span data-ttu-id="56660-117">指定所使用的安全类型。</span><span class="sxs-lookup"><span data-stu-id="56660-117">Specifies the type of security that is used.</span></span> <span data-ttu-id="56660-118">默认值为 `None`。</span><span class="sxs-lookup"><span data-stu-id="56660-118">The default is `None`.</span></span> <span data-ttu-id="56660-119">此属性的类型为 <xref:System.ServiceModel.BasicHttpSecurityMode>。</span><span class="sxs-lookup"><span data-stu-id="56660-119">This attribute is of type <xref:System.ServiceModel.BasicHttpSecurityMode>.</span></span>|

## <a name="mode-attribute"></a><span data-ttu-id="56660-120">mode 属性</span><span class="sxs-lookup"><span data-stu-id="56660-120">mode attribute</span></span>

|<span data-ttu-id="56660-121">“值”</span><span class="sxs-lookup"><span data-stu-id="56660-121">Value</span></span>|<span data-ttu-id="56660-122">描述</span><span class="sxs-lookup"><span data-stu-id="56660-122">Description</span></span>|
|-----------|-----------------|
|<span data-ttu-id="56660-123">None</span><span class="sxs-lookup"><span data-stu-id="56660-123">None</span></span>|<span data-ttu-id="56660-124">的在传输过程中不是安全消息数。</span><span class="sxs-lookup"><span data-stu-id="56660-124">-   Messages are not secured during transfer.</span></span>|
|<span data-ttu-id="56660-125">传输</span><span class="sxs-lookup"><span data-stu-id="56660-125">Transport</span></span>|<span data-ttu-id="56660-126">使用 HTTPS 传输提供安全性。</span><span class="sxs-lookup"><span data-stu-id="56660-126">Security is provided using HTTPS transport.</span></span> <span data-ttu-id="56660-127">用 HTTPS 保证 SOAP 消息的安全。</span><span class="sxs-lookup"><span data-stu-id="56660-127">The SOAP messages are secured using HTTPS.</span></span> <span data-ttu-id="56660-128">使用服务的 X.509 证书向客户端对服务进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="56660-128">The service is authenticated to the client using the service's X.509 certificate.</span></span> <span data-ttu-id="56660-129">使用所提供的 ClientCredentialType 对客户端进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="56660-129">The client is authenticated using the ClientCredentialType supplied.</span></span>|
|<span data-ttu-id="56660-130">消息</span><span class="sxs-lookup"><span data-stu-id="56660-130">Message</span></span>|<span data-ttu-id="56660-131">使用 SOAP 消息安全提供安全性。</span><span class="sxs-lookup"><span data-stu-id="56660-131">Security is provided using SOAP message security.</span></span> <span data-ttu-id="56660-132">默认情况下，将对正文进行加密和签名。</span><span class="sxs-lookup"><span data-stu-id="56660-132">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="56660-133">对于此绑定，系统要求向带外客户端提供服务器证书。</span><span class="sxs-lookup"><span data-stu-id="56660-133">For this binding, the system requires that the server certificate be provided to the client out of band.</span></span> <span data-ttu-id="56660-134">此绑定仅有的有效 `ClientCredentialType` 为 `Certificate`。</span><span class="sxs-lookup"><span data-stu-id="56660-134">The only valid `ClientCredentialType` for this binding is `Certificate`.</span></span>|
|<span data-ttu-id="56660-135">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="56660-135">TransportWithMessageCredential</span></span>|<span data-ttu-id="56660-136">完整性、保密性和服务器身份验证由传输安全来提供。</span><span class="sxs-lookup"><span data-stu-id="56660-136">Integrity, confidentiality and server authentication are provided by transport security.</span></span> <span data-ttu-id="56660-137">客户端身份验证采用 SOAP 消息安全方式提供。</span><span class="sxs-lookup"><span data-stu-id="56660-137">Client authentication is provided by means of SOAP message security.</span></span> <span data-ttu-id="56660-138">如果要使用用户名/密码对用户进行身份验证，并且存在用于保护消息传输的现有 HTTP 部署，则适用此模式。</span><span class="sxs-lookup"><span data-stu-id="56660-138">This mode is relevant when the user is authenticating using username/password and there is an existing HTTP deployment for securing message transfer.</span></span>|
|<span data-ttu-id="56660-139">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="56660-139">TransportCredentialOnly</span></span>|<span data-ttu-id="56660-140">此模式并不提供消息的完整性和保密性，</span><span class="sxs-lookup"><span data-stu-id="56660-140">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="56660-141">而是提供基于 http 的客户端身份验证。</span><span class="sxs-lookup"><span data-stu-id="56660-141">It provides http-based client authentication.</span></span> <span data-ttu-id="56660-142">使用此模式时应当小心。</span><span class="sxs-lookup"><span data-stu-id="56660-142">This mode should be used with caution.</span></span> <span data-ttu-id="56660-143">它应在其中通过其他方式 （如 IPSec) 提供传输安全和 WCF 基础结构提供仅客户端身份验证的环境中使用。</span><span class="sxs-lookup"><span data-stu-id="56660-143">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="56660-144">子元素</span><span class="sxs-lookup"><span data-stu-id="56660-144">Child elements</span></span>

|<span data-ttu-id="56660-145">元素</span><span class="sxs-lookup"><span data-stu-id="56660-145">Element</span></span>|<span data-ttu-id="56660-146">描述</span><span class="sxs-lookup"><span data-stu-id="56660-146">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="56660-147">\<transport></span><span class="sxs-lookup"><span data-stu-id="56660-147">\<transport></span></span>](transport-of-nethttpbinding.md)|<span data-ttu-id="56660-148">定义基本 HTTP 服务的传输安全设置。</span><span class="sxs-lookup"><span data-stu-id="56660-148">Defines the transport security settings for a basic HTTP service.</span></span> <span data-ttu-id="56660-149">此元素与 <xref:System.ServiceModel.HttpTransportSecurity> 相对应。</span><span class="sxs-lookup"><span data-stu-id="56660-149">This element corresponds to <xref:System.ServiceModel.HttpTransportSecurity>.</span></span>|
|[<span data-ttu-id="56660-150">\<message></span><span class="sxs-lookup"><span data-stu-id="56660-150">\<message></span></span>](message-of-nethttpbinding.md)|<span data-ttu-id="56660-151">定义基本 HTTP 服务的消息安全设置。</span><span class="sxs-lookup"><span data-stu-id="56660-151">Defines the message security settings for a basic HTTP service.</span></span> <span data-ttu-id="56660-152">此元素与 <xref:System.ServiceModel.BasicHttpMessageSecurity> 相对应。</span><span class="sxs-lookup"><span data-stu-id="56660-152">This element corresponds to <xref:System.ServiceModel.BasicHttpMessageSecurity>.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="56660-153">父元素</span><span class="sxs-lookup"><span data-stu-id="56660-153">Parent elements</span></span>

|<span data-ttu-id="56660-154">元素</span><span class="sxs-lookup"><span data-stu-id="56660-154">Element</span></span>|<span data-ttu-id="56660-155">描述</span><span class="sxs-lookup"><span data-stu-id="56660-155">Description</span></span>|
|-------------|-----------------|
|<span data-ttu-id="56660-156">绑定</span><span class="sxs-lookup"><span data-stu-id="56660-156">binding</span></span>|<span data-ttu-id="56660-157">绑定元素[ \<basicHttpBinding >](basichttpbinding.md)。</span><span class="sxs-lookup"><span data-stu-id="56660-157">The binding element of the [\<basicHttpBinding>](basichttpbinding.md).</span></span>|

## <a name="remarks"></a><span data-ttu-id="56660-158">备注</span><span class="sxs-lookup"><span data-stu-id="56660-158">Remarks</span></span>

 <span data-ttu-id="56660-159">默认情况下，不会对 SOAP 消息进行保护，也不会对客户端进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="56660-159">By default, the SOAP message is not secured and the client is not authenticated.</span></span> <span data-ttu-id="56660-160">使用此元素，您可以配置 `netHttpBinding` 元素的其他安全设置。</span><span class="sxs-lookup"><span data-stu-id="56660-160">This element enables you to configure additional security settings for the `netHttpBinding` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="56660-161">请参阅</span><span class="sxs-lookup"><span data-stu-id="56660-161">See also</span></span>

- <xref:System.ServiceModel.NetHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetHttpBindingElement.Security%2A>  
- [<span data-ttu-id="56660-162">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="56660-162">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="56660-163">选择凭据类型</span><span class="sxs-lookup"><span data-stu-id="56660-163">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="56660-164">绑定</span><span class="sxs-lookup"><span data-stu-id="56660-164">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="56660-165">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="56660-165">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="56660-166">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="56660-166">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="56660-167">\<binding></span><span class="sxs-lookup"><span data-stu-id="56660-167">\<binding></span></span>](../../../misc/binding.md)
