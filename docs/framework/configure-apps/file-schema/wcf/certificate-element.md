---
title: <certificate> 元素
ms.date: 03/30/2017
ms.assetid: 9b3d9233-ef35-477a-bf5d-efd1e80a52f4
ms.openlocfilehash: e28e7d16073a56f3b6126439644bfff86c9af18b
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400555"
---
# <a name="certificate-element"></a><span data-ttu-id="43e60-102">\<证书 > 元素</span><span class="sxs-lookup"><span data-stu-id="43e60-102">\<certificate> Element</span></span>
<span data-ttu-id="43e60-103">指定要用于为对等客户端的消息进行签名和加密的 X.509 证书。</span><span class="sxs-lookup"><span data-stu-id="43e60-103">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer clients.</span></span>  
  
<span data-ttu-id="43e60-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="43e60-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="43e60-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="43e60-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="43e60-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="43e60-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="43e60-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="43e60-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="43e60-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="43e60-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="43e60-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<clientCredentials >** ](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="43e60-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="43e60-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<对等 >** ](peer-of-clientcredentials-element.md)</span><span class="sxs-lookup"><span data-stu-id="43e60-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peer>**](peer-of-clientcredentials-element.md)</span></span>\
<span data-ttu-id="43e60-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<证书 >**</span><span class="sxs-lookup"><span data-stu-id="43e60-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificate>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43e60-112">语法</span><span class="sxs-lookup"><span data-stu-id="43e60-112">Syntax</span></span>  
  
```xml  
<certificate findValue="String"
             storeLocation="LocalMachine/CurrentUser"
             storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
             X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="43e60-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="43e60-113">Attributes and Elements</span></span>  
 <span data-ttu-id="43e60-114">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="43e60-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="43e60-115">特性</span><span class="sxs-lookup"><span data-stu-id="43e60-115">Attributes</span></span>  
  
|<span data-ttu-id="43e60-116">特性</span><span class="sxs-lookup"><span data-stu-id="43e60-116">Attribute</span></span>|<span data-ttu-id="43e60-117">描述</span><span class="sxs-lookup"><span data-stu-id="43e60-117">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="43e60-118">一个字符串，包含要在 X.509 证书存储中搜索的值。</span><span class="sxs-lookup"><span data-stu-id="43e60-118">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="43e60-119">此属性中包含的类型必须满足指定 `x509FindType` 的要求。</span><span class="sxs-lookup"><span data-stu-id="43e60-119">The type contained in the attribute must satisfy the requirements of the specified `x509FindType`.</span></span> <span data-ttu-id="43e60-120">默认值为一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="43e60-120">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="43e60-121">指定客户端可用于验证对等方的证书的 X.509 证书存储的位置。</span><span class="sxs-lookup"><span data-stu-id="43e60-121">Specifies the location of the X.509 certificate store that the client uses to validate the peer's certificate against.</span></span> <span data-ttu-id="43e60-122">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="43e60-122">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="43e60-123">-LocalMachine：分配给本地计算机的证书存储区。</span><span class="sxs-lookup"><span data-stu-id="43e60-123">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="43e60-124">-CurrentUser：分配给当前用户的证书存储区。</span><span class="sxs-lookup"><span data-stu-id="43e60-124">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="43e60-125">默认值为 LocalMachine。</span><span class="sxs-lookup"><span data-stu-id="43e60-125">The default is LocalMachine.</span></span>|  
|`storeName`|<span data-ttu-id="43e60-126">指定要打开的 X.509 证书存储区的名称。</span><span class="sxs-lookup"><span data-stu-id="43e60-126">Specifies the name of the X.509 certificate store to open.</span></span> <span data-ttu-id="43e60-127">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="43e60-127">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="43e60-128">通讯簿其他用户的证书存储区。</span><span class="sxs-lookup"><span data-stu-id="43e60-128">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="43e60-129">AuthRoot第三方证书颁发机构（Ca）的证书存储区。</span><span class="sxs-lookup"><span data-stu-id="43e60-129">-   AuthRoot: Certificate store for third-party certification authorities (CAs).</span></span><br /><span data-ttu-id="43e60-130">CertificateAuthority中间证书颁发机构（Ca）的证书存储区。</span><span class="sxs-lookup"><span data-stu-id="43e60-130">-   CertificateAuthority: Certificate store for intermediate certification authorities (CAs).</span></span><br /><span data-ttu-id="43e60-131">禁用吊销的证书的证书存储区。</span><span class="sxs-lookup"><span data-stu-id="43e60-131">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="43e60-132">记住个人证书的证书存储区。</span><span class="sxs-lookup"><span data-stu-id="43e60-132">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="43e60-133">Root受信任的根证书颁发机构（Ca）的证书存储区。</span><span class="sxs-lookup"><span data-stu-id="43e60-133">-   Root: Certificate store for trusted root certification authorities (CAs).</span></span><br /><span data-ttu-id="43e60-134">TrustedPeople直接受信任的人和资源的证书存储区。</span><span class="sxs-lookup"><span data-stu-id="43e60-134">-   TrustedPeople: Certificate store for directly-trusted people and resources.</span></span><br /><span data-ttu-id="43e60-135">TrustedPublisher直接受信任的发布者的证书存储区。</span><span class="sxs-lookup"><span data-stu-id="43e60-135">-   TrustedPublisher: Certificate store for directly-trusted publishers.</span></span><br /><br /> <span data-ttu-id="43e60-136">默认值为 My。</span><span class="sxs-lookup"><span data-stu-id="43e60-136">The default is My.</span></span>|  
|`X509FindType`|<span data-ttu-id="43e60-137">定义要执行的 X.509 搜索的类型。</span><span class="sxs-lookup"><span data-stu-id="43e60-137">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="43e60-138">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="43e60-138">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="43e60-139">-FindByThumbPrint</span><span class="sxs-lookup"><span data-stu-id="43e60-139">-   FindByThumbPrint</span></span><br /><span data-ttu-id="43e60-140">-   FindBySubjectName</span><span class="sxs-lookup"><span data-stu-id="43e60-140">-   FindBySubjectName</span></span><br /><span data-ttu-id="43e60-141">-FindBySubjectDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="43e60-141">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="43e60-142">- FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="43e60-142">-   FindByIssuerName</span></span><br /><span data-ttu-id="43e60-143">- FindByIssuerDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="43e60-143">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="43e60-144">-FindBySerialNumber</span><span class="sxs-lookup"><span data-stu-id="43e60-144">-   FindBySerialNumber</span></span><br /><span data-ttu-id="43e60-145">-   FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="43e60-145">-   FindByTimeValid</span></span><br /><span data-ttu-id="43e60-146">-   FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="43e60-146">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="43e60-147">- FindByTemplateName</span><span class="sxs-lookup"><span data-stu-id="43e60-147">-   FindByTemplateName</span></span><br /><span data-ttu-id="43e60-148">-   FindByApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="43e60-148">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="43e60-149">-   FindByCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="43e60-149">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="43e60-150">- FindByExtension</span><span class="sxs-lookup"><span data-stu-id="43e60-150">-   FindByExtension</span></span><br /><span data-ttu-id="43e60-151">- FindByKeyUsage</span><span class="sxs-lookup"><span data-stu-id="43e60-151">-   FindByKeyUsage</span></span><br /><span data-ttu-id="43e60-152">-   FindBySubjectKeyIdentifier</span><span class="sxs-lookup"><span data-stu-id="43e60-152">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="43e60-153">`findValue` 属性中包含的类型必须满足指定 `X509FindType` 的要求。</span><span class="sxs-lookup"><span data-stu-id="43e60-153">The type contained in the `findValue` attribute must satisfy the requirements of the specified `X509FindType`.</span></span><br /><br /> <span data-ttu-id="43e60-154">默认值为 FindBySubjectDistinguishedName。</span><span class="sxs-lookup"><span data-stu-id="43e60-154">The default value is FindBySubjectDistinguishedName.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="43e60-155">子元素</span><span class="sxs-lookup"><span data-stu-id="43e60-155">Child Elements</span></span>  
 <span data-ttu-id="43e60-156">无。</span><span class="sxs-lookup"><span data-stu-id="43e60-156">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="43e60-157">父元素</span><span class="sxs-lookup"><span data-stu-id="43e60-157">Parent Elements</span></span>  
  
|<span data-ttu-id="43e60-158">元素</span><span class="sxs-lookup"><span data-stu-id="43e60-158">Element</span></span>|<span data-ttu-id="43e60-159">描述</span><span class="sxs-lookup"><span data-stu-id="43e60-159">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="43e60-160">\<peer></span><span class="sxs-lookup"><span data-stu-id="43e60-160">\<peer></span></span>](peer-of-clientcredentials-element.md)|<span data-ttu-id="43e60-161">指定在向对等客户端进行身份验证时使用的凭据。</span><span class="sxs-lookup"><span data-stu-id="43e60-161">Specifies credentials used when authenticating peer-to-peer clients.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="43e60-162">备注</span><span class="sxs-lookup"><span data-stu-id="43e60-162">Remarks</span></span>  
 <span data-ttu-id="43e60-163">此配置元素包含对对等网格中的邻居进行身份验证时使用的 X509Certificate2 实例。</span><span class="sxs-lookup"><span data-stu-id="43e60-163">This configuration element contains a X509Certificate2 instance used when authenticating neighbors in the peer mesh.</span></span>  
  
 <span data-ttu-id="43e60-164">有关对等编程的详细信息，请参阅对等[网络](../../../wcf/feature-details/peer-to-peer-networking.md)。</span><span class="sxs-lookup"><span data-stu-id="43e60-164">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="43e60-165">示例</span><span class="sxs-lookup"><span data-stu-id="43e60-165">Example</span></span>  
 <span data-ttu-id="43e60-166">下面的代码指定如何查找在对等方案中使用的证书。</span><span class="sxs-lookup"><span data-stu-id="43e60-166">The following code specifies how to find the certificate used in a peer-to-peer scenario.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="43e60-167">请参阅</span><span class="sxs-lookup"><span data-stu-id="43e60-167">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.Certificate%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateElement>
- <xref:System.ServiceModel.Security.PeerCredential.Certificate%2A>
- [<span data-ttu-id="43e60-168">使用证书</span><span class="sxs-lookup"><span data-stu-id="43e60-168">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="43e60-169">对等网络</span><span class="sxs-lookup"><span data-stu-id="43e60-169">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="43e60-170">[对等通道消息身份验证](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="43e60-170">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="43e60-171">[对等通道自定义身份验证](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="43e60-171">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="43e60-172">保护对等通道应用程序</span><span class="sxs-lookup"><span data-stu-id="43e60-172">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
