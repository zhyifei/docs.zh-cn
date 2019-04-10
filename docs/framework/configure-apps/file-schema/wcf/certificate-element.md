---
title: <certificate> 元素
ms.date: 03/30/2017
ms.assetid: 9b3d9233-ef35-477a-bf5d-efd1e80a52f4
ms.openlocfilehash: eea8130911ca3780a6e4e753c17877e58c50b139
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59164263"
---
# <a name="certificate-element"></a><span data-ttu-id="e2178-102">\<证书 > 元素</span><span class="sxs-lookup"><span data-stu-id="e2178-102">\<certificate> Element</span></span>
<span data-ttu-id="e2178-103">指定要用于为对等客户端的消息进行签名和加密的 X.509 证书。</span><span class="sxs-lookup"><span data-stu-id="e2178-103">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer clients.</span></span>  
  
 <span data-ttu-id="e2178-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e2178-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="e2178-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="e2178-105">\<behaviors></span></span>  
<span data-ttu-id="e2178-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="e2178-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="e2178-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="e2178-107">\<behavior></span></span>  
<span data-ttu-id="e2178-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="e2178-108">\<clientCredentials></span></span>  
<span data-ttu-id="e2178-109">\<peer></span><span class="sxs-lookup"><span data-stu-id="e2178-109">\<peer></span></span>  
<span data-ttu-id="e2178-110">\<certificate></span><span class="sxs-lookup"><span data-stu-id="e2178-110">\<certificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2178-111">语法</span><span class="sxs-lookup"><span data-stu-id="e2178-111">Syntax</span></span>  
  
```xml  
<certificate findValue="String"
             storeLocation="LocalMachine/CurrentUser"
             storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
             X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e2178-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="e2178-112">Attributes and Elements</span></span>  
 <span data-ttu-id="e2178-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="e2178-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e2178-114">特性</span><span class="sxs-lookup"><span data-stu-id="e2178-114">Attributes</span></span>  
  
|<span data-ttu-id="e2178-115">特性</span><span class="sxs-lookup"><span data-stu-id="e2178-115">Attribute</span></span>|<span data-ttu-id="e2178-116">描述</span><span class="sxs-lookup"><span data-stu-id="e2178-116">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="e2178-117">一个字符串，包含要在 X.509 证书存储中搜索的值。</span><span class="sxs-lookup"><span data-stu-id="e2178-117">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="e2178-118">此属性中包含的类型必须满足指定 `x509FindType` 的要求。</span><span class="sxs-lookup"><span data-stu-id="e2178-118">The type contained in the attribute must satisfy the requirements of the specified `x509FindType`.</span></span> <span data-ttu-id="e2178-119">默认值为一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="e2178-119">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="e2178-120">指定客户端可用于验证对等方的证书的 X.509 证书存储的位置。</span><span class="sxs-lookup"><span data-stu-id="e2178-120">Specifies the location of the X.509 certificate store that the client uses to validate the peer's certificate against.</span></span> <span data-ttu-id="e2178-121">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="e2178-121">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="e2178-122">-LocalMachine： 分配给本地计算机的证书存储。</span><span class="sxs-lookup"><span data-stu-id="e2178-122">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="e2178-123">-CurrentUser： 分配给当前用户的证书存储。</span><span class="sxs-lookup"><span data-stu-id="e2178-123">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="e2178-124">默认值为 LocalMachine。</span><span class="sxs-lookup"><span data-stu-id="e2178-124">The default is LocalMachine.</span></span>|  
|`storeName`|<span data-ttu-id="e2178-125">指定要打开的 X.509 证书存储区的名称。</span><span class="sxs-lookup"><span data-stu-id="e2178-125">Specifies the name of the X.509 certificate store to open.</span></span> <span data-ttu-id="e2178-126">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="e2178-126">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="e2178-127">-通讯簿：其他用户的证书存储区。</span><span class="sxs-lookup"><span data-stu-id="e2178-127">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="e2178-128">-   AuthRoot:第三方证书颁发机构 (Ca) 证书存储区。</span><span class="sxs-lookup"><span data-stu-id="e2178-128">-   AuthRoot: Certificate store for third-party certification authorities (CAs).</span></span><br /><span data-ttu-id="e2178-129">-CertificateAuthority:中间证书颁发机构 (Ca) 证书存储区。</span><span class="sxs-lookup"><span data-stu-id="e2178-129">-   CertificateAuthority: Certificate store for intermediate certification authorities (CAs).</span></span><br /><span data-ttu-id="e2178-130">-不允许：已吊销证书的证书存储区。</span><span class="sxs-lookup"><span data-stu-id="e2178-130">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="e2178-131">-我：个人证书的证书存储区。</span><span class="sxs-lookup"><span data-stu-id="e2178-131">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="e2178-132">根：受信任的根证书颁发机构 (Ca) 证书存储区。</span><span class="sxs-lookup"><span data-stu-id="e2178-132">-   Root: Certificate store for trusted root certification authorities (CAs).</span></span><br /><span data-ttu-id="e2178-133">-TrustedPeople:直接受信任的人和资源的证书存储区。</span><span class="sxs-lookup"><span data-stu-id="e2178-133">-   TrustedPeople: Certificate store for directly-trusted people and resources.</span></span><br /><span data-ttu-id="e2178-134">-TrustedPublisher:直接受信任发布者的证书存储区。</span><span class="sxs-lookup"><span data-stu-id="e2178-134">-   TrustedPublisher: Certificate store for directly-trusted publishers.</span></span><br /><br /> <span data-ttu-id="e2178-135">默认值为 My。</span><span class="sxs-lookup"><span data-stu-id="e2178-135">The default is My.</span></span>|  
|`X509FindType`|<span data-ttu-id="e2178-136">定义要执行的 X.509 搜索的类型。</span><span class="sxs-lookup"><span data-stu-id="e2178-136">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="e2178-137">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="e2178-137">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="e2178-138">-FindByThumbPrint</span><span class="sxs-lookup"><span data-stu-id="e2178-138">-   FindByThumbPrint</span></span><br /><span data-ttu-id="e2178-139">-   FindBySubjectName</span><span class="sxs-lookup"><span data-stu-id="e2178-139">-   FindBySubjectName</span></span><br /><span data-ttu-id="e2178-140">-   FindBySubjectDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="e2178-140">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="e2178-141">-FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="e2178-141">-   FindByIssuerName</span></span><br /><span data-ttu-id="e2178-142">-FindByIssuerDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="e2178-142">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="e2178-143">-   FindBySerialNumber</span><span class="sxs-lookup"><span data-stu-id="e2178-143">-   FindBySerialNumber</span></span><br /><span data-ttu-id="e2178-144">-   FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="e2178-144">-   FindByTimeValid</span></span><br /><span data-ttu-id="e2178-145">-   FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="e2178-145">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="e2178-146">-FindByTemplateName</span><span class="sxs-lookup"><span data-stu-id="e2178-146">-   FindByTemplateName</span></span><br /><span data-ttu-id="e2178-147">-   FindByApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="e2178-147">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="e2178-148">-   FindByCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="e2178-148">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="e2178-149">-FindByExtension</span><span class="sxs-lookup"><span data-stu-id="e2178-149">-   FindByExtension</span></span><br /><span data-ttu-id="e2178-150">-FindByKeyUsage</span><span class="sxs-lookup"><span data-stu-id="e2178-150">-   FindByKeyUsage</span></span><br /><span data-ttu-id="e2178-151">-   FindBySubjectKeyIdentifier</span><span class="sxs-lookup"><span data-stu-id="e2178-151">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="e2178-152">`findValue` 属性中包含的类型必须满足指定 `X509FindType` 的要求。</span><span class="sxs-lookup"><span data-stu-id="e2178-152">The type contained in the `findValue` attribute must satisfy the requirements of the specified `X509FindType`.</span></span><br /><br /> <span data-ttu-id="e2178-153">默认值为 FindBySubjectDistinguishedName。</span><span class="sxs-lookup"><span data-stu-id="e2178-153">The default value is FindBySubjectDistinguishedName.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e2178-154">子元素</span><span class="sxs-lookup"><span data-stu-id="e2178-154">Child Elements</span></span>  
 <span data-ttu-id="e2178-155">无。</span><span class="sxs-lookup"><span data-stu-id="e2178-155">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e2178-156">父元素</span><span class="sxs-lookup"><span data-stu-id="e2178-156">Parent Elements</span></span>  
  
|<span data-ttu-id="e2178-157">元素</span><span class="sxs-lookup"><span data-stu-id="e2178-157">Element</span></span>|<span data-ttu-id="e2178-158">描述</span><span class="sxs-lookup"><span data-stu-id="e2178-158">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e2178-159">\<peer></span><span class="sxs-lookup"><span data-stu-id="e2178-159">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-clientcredentials-element.md)|<span data-ttu-id="e2178-160">指定在向对等客户端进行身份验证时使用的凭据。</span><span class="sxs-lookup"><span data-stu-id="e2178-160">Specifies credentials used when authenticating peer-to-peer clients.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e2178-161">备注</span><span class="sxs-lookup"><span data-stu-id="e2178-161">Remarks</span></span>  
 <span data-ttu-id="e2178-162">此配置元素包含对对等网格中的邻居进行身份验证时使用的 X509Certificate2 实例。</span><span class="sxs-lookup"><span data-stu-id="e2178-162">This configuration element contains a X509Certificate2 instance used when authenticating neighbors in the peer mesh.</span></span>  
  
 <span data-ttu-id="e2178-163">有关对等编程的详细信息，请参阅[对等网络](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)。</span><span class="sxs-lookup"><span data-stu-id="e2178-163">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e2178-164">示例</span><span class="sxs-lookup"><span data-stu-id="e2178-164">Example</span></span>  
 <span data-ttu-id="e2178-165">下面的代码指定如何查找在对等方案中使用的证书。</span><span class="sxs-lookup"><span data-stu-id="e2178-165">The following code specifies how to find the certificate used in a peer-to-peer scenario.</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="MyEndpointBehavior">
      <clientCredentials>
        <peer>
          <certificate findValue="www.contoso.com"
                       storeLocation="LocalMachine"
                       x509FindType="FindByIssuerName" />
        </peer>
      </clientCredentials>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="e2178-166">请参阅</span><span class="sxs-lookup"><span data-stu-id="e2178-166">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.Certificate%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateElement>
- <xref:System.ServiceModel.Security.PeerCredential.Certificate%2A>
- [<span data-ttu-id="e2178-167">使用证书</span><span class="sxs-lookup"><span data-stu-id="e2178-167">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="e2178-168">对等网络</span><span class="sxs-lookup"><span data-stu-id="e2178-168">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)
- [<span data-ttu-id="e2178-169">对等通道消息身份验证</span><span class="sxs-lookup"><span data-stu-id="e2178-169">Peer Channel Message Authentication</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))
- [<span data-ttu-id="e2178-170">对等通道自定义身份验证</span><span class="sxs-lookup"><span data-stu-id="e2178-170">Peer Channel Custom Authentication</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))
- [<span data-ttu-id="e2178-171">保护对等通道应用程序</span><span class="sxs-lookup"><span data-stu-id="e2178-171">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
