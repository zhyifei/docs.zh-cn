---
title: <certificate> <clientCertificate>元素
ms.date: 03/30/2017
ms.assetid: 00297efb-a7f2-4e03-bc2b-943d545610fc
ms.openlocfilehash: 94241d022e8a97253100a67e2a779593861c093c
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55286450"
---
# <a name="certificate-of-clientcertificate-element"></a><span data-ttu-id="9b4ed-102">\<证书 > 的\<clientCertificate > 元素</span><span class="sxs-lookup"><span data-stu-id="9b4ed-102">\<certificate> of \<clientCertificate> Element</span></span>
<span data-ttu-id="9b4ed-103">指定用于对消息进行签名和加密的 X.509 证书。</span><span class="sxs-lookup"><span data-stu-id="9b4ed-103">Specifies an X.509 certificate used to sign and encrypt messages.</span></span>  
  
 <span data-ttu-id="9b4ed-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="9b4ed-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="9b4ed-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="9b4ed-105">\<behaviors></span></span>  
<span data-ttu-id="9b4ed-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="9b4ed-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="9b4ed-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="9b4ed-107">\<behavior></span></span>  
<span data-ttu-id="9b4ed-108">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="9b4ed-108">\<serviceCredentials></span></span>  
<span data-ttu-id="9b4ed-109">\<clientCertificate></span><span class="sxs-lookup"><span data-stu-id="9b4ed-109">\<clientCertificate></span></span>  
<span data-ttu-id="9b4ed-110">\<certificate></span><span class="sxs-lookup"><span data-stu-id="9b4ed-110">\<certificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b4ed-111">语法</span><span class="sxs-lookup"><span data-stu-id="9b4ed-111">Syntax</span></span>  
  
```xml  
<certificate findValue="String"
             storeLocation = "CurrentUser/LocalMachine"
             storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
             X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9b4ed-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="9b4ed-112">Attributes and Elements</span></span>  
 <span data-ttu-id="9b4ed-113">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="9b4ed-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9b4ed-114">特性</span><span class="sxs-lookup"><span data-stu-id="9b4ed-114">Attributes</span></span>  
  
|<span data-ttu-id="9b4ed-115">特性</span><span class="sxs-lookup"><span data-stu-id="9b4ed-115">Attribute</span></span>|<span data-ttu-id="9b4ed-116">描述</span><span class="sxs-lookup"><span data-stu-id="9b4ed-116">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="9b4ed-117">一个字符串，包含要在 X.509 证书存储中搜索的值。</span><span class="sxs-lookup"><span data-stu-id="9b4ed-117">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="9b4ed-118">此属性中包含的类型必须满足指定 X509FindType 的要求。</span><span class="sxs-lookup"><span data-stu-id="9b4ed-118">The type contained in the attribute must satisfy the requirements of the specified X509FindType.</span></span> <span data-ttu-id="9b4ed-119">默认值为一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="9b4ed-119">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="9b4ed-120">指定客户端可用于验证服务器证书的 X.509 证书存储的位置。</span><span class="sxs-lookup"><span data-stu-id="9b4ed-120">Specifies the location of the X.509 certificate store that the client uses to validate the server’s certificate against.</span></span> <span data-ttu-id="9b4ed-121">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="9b4ed-121">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="9b4ed-122">-LocalMachine： 分配给本地计算机的证书存储。</span><span class="sxs-lookup"><span data-stu-id="9b4ed-122">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="9b4ed-123">-CurrentUser： 分配给当前用户的证书存储。</span><span class="sxs-lookup"><span data-stu-id="9b4ed-123">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="9b4ed-124">默认值为 LocalMachine。</span><span class="sxs-lookup"><span data-stu-id="9b4ed-124">The default is LocalMachine.</span></span>|  
|`storeName`|<span data-ttu-id="9b4ed-125">指定要打开的 X.509 证书存储区的名称。</span><span class="sxs-lookup"><span data-stu-id="9b4ed-125">Specifies the name of the X.509 certificate store to open.</span></span> <span data-ttu-id="9b4ed-126">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="9b4ed-126">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="9b4ed-127">-通讯簿：其他用户的证书存储区。</span><span class="sxs-lookup"><span data-stu-id="9b4ed-127">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="9b4ed-128">-   AuthRoot:第三方证书颁发机构 (Ca) 证书存储区。</span><span class="sxs-lookup"><span data-stu-id="9b4ed-128">-   AuthRoot: Certificate store for third-party certification authorities (CAs).</span></span><br /><span data-ttu-id="9b4ed-129">-证书颁发机构：中间证书颁发机构 (Ca) 证书存储区。</span><span class="sxs-lookup"><span data-stu-id="9b4ed-129">-   CertificationAuthority: Certificate store for intermediate certification authorities (CAs).</span></span><br /><span data-ttu-id="9b4ed-130">-不允许：已吊销证书的证书存储区。</span><span class="sxs-lookup"><span data-stu-id="9b4ed-130">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="9b4ed-131">-我：个人证书的证书存储区。</span><span class="sxs-lookup"><span data-stu-id="9b4ed-131">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="9b4ed-132">根：受信任的根证书颁发机构 (Ca) 证书存储区。</span><span class="sxs-lookup"><span data-stu-id="9b4ed-132">-   Root: Certificate store for trusted root certification authorities (CAs).</span></span><br /><span data-ttu-id="9b4ed-133">-TrustedPeople:直接受信任的人和资源的证书存储区。</span><span class="sxs-lookup"><span data-stu-id="9b4ed-133">-   TrustedPeople: Certificate store for directly trusted people and resources.</span></span><br /><span data-ttu-id="9b4ed-134">-TrustedPublisher:直接受信任的发行者的证书存储区。</span><span class="sxs-lookup"><span data-stu-id="9b4ed-134">-   TrustedPublisher: Certificate store for directly trusted publishers.</span></span><br /><br /> <span data-ttu-id="9b4ed-135">默认值为 My。</span><span class="sxs-lookup"><span data-stu-id="9b4ed-135">The default is My.</span></span>|  
|`X509FindType`|<span data-ttu-id="9b4ed-136">定义要执行的 X.509 搜索的类型。</span><span class="sxs-lookup"><span data-stu-id="9b4ed-136">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="9b4ed-137">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="9b4ed-137">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="9b4ed-138">-FindByThumbPrint</span><span class="sxs-lookup"><span data-stu-id="9b4ed-138">-   FindByThumbPrint</span></span><br /><span data-ttu-id="9b4ed-139">-   FindBySubjectName</span><span class="sxs-lookup"><span data-stu-id="9b4ed-139">-   FindBySubjectName</span></span><br /><span data-ttu-id="9b4ed-140">-   FindBySubjectDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="9b4ed-140">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="9b4ed-141">-FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="9b4ed-141">-   FindByIssuerName</span></span><br /><span data-ttu-id="9b4ed-142">-FindByIssuerDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="9b4ed-142">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="9b4ed-143">-   FindBySerialNumber</span><span class="sxs-lookup"><span data-stu-id="9b4ed-143">-   FindBySerialNumber</span></span><br /><span data-ttu-id="9b4ed-144">-   FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="9b4ed-144">-   FindByTimeValid</span></span><br /><span data-ttu-id="9b4ed-145">-   FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="9b4ed-145">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="9b4ed-146">-FindByTemplateName</span><span class="sxs-lookup"><span data-stu-id="9b4ed-146">-   FindByTemplateName</span></span><br /><span data-ttu-id="9b4ed-147">-   FindByApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="9b4ed-147">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="9b4ed-148">-   FindByCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="9b4ed-148">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="9b4ed-149">-FindByExtension</span><span class="sxs-lookup"><span data-stu-id="9b4ed-149">-   FindByExtension</span></span><br /><span data-ttu-id="9b4ed-150">-FindByKeyUsage</span><span class="sxs-lookup"><span data-stu-id="9b4ed-150">-   FindByKeyUsage</span></span><br /><span data-ttu-id="9b4ed-151">-   FindBySubjectKeyIdentifier</span><span class="sxs-lookup"><span data-stu-id="9b4ed-151">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="9b4ed-152">`findValue` 属性中包含的类型必须满足指定 X509FindType 的要求。</span><span class="sxs-lookup"><span data-stu-id="9b4ed-152">The type contained in the `findValue` attribute must satisfy the requirements of the specified X509FindType.</span></span><br /><br /> <span data-ttu-id="9b4ed-153">默认值为 FindBySubjectDistinguishedName。</span><span class="sxs-lookup"><span data-stu-id="9b4ed-153">The default value is FindBySubjectDistinguishedName.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9b4ed-154">子元素</span><span class="sxs-lookup"><span data-stu-id="9b4ed-154">Child Elements</span></span>  
 <span data-ttu-id="9b4ed-155">无。</span><span class="sxs-lookup"><span data-stu-id="9b4ed-155">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9b4ed-156">父元素</span><span class="sxs-lookup"><span data-stu-id="9b4ed-156">Parent Elements</span></span>  
  
|<span data-ttu-id="9b4ed-157">元素</span><span class="sxs-lookup"><span data-stu-id="9b4ed-157">Element</span></span>|<span data-ttu-id="9b4ed-158">描述</span><span class="sxs-lookup"><span data-stu-id="9b4ed-158">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9b4ed-159">\<clientCertificate></span><span class="sxs-lookup"><span data-stu-id="9b4ed-159">\<clientCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md)||  
  
## <a name="remarks"></a><span data-ttu-id="9b4ed-160">备注</span><span class="sxs-lookup"><span data-stu-id="9b4ed-160">Remarks</span></span>  
 <span data-ttu-id="9b4ed-161">当服务必须事先拥有客户端的证书才能与该客户端进行安全通信时，可使用 `<certificate>` 元素。</span><span class="sxs-lookup"><span data-stu-id="9b4ed-161">The `<certificate>` element is used when the service must have the client's certificate in advance to communicate securely with the client.</span></span> <span data-ttu-id="9b4ed-162">使用双工通信模式时，会出现这种情况。</span><span class="sxs-lookup"><span data-stu-id="9b4ed-162">This occurs when using the duplex communication pattern.</span></span> <span data-ttu-id="9b4ed-163">在更为典型的请求/响应模式中，客户端会将其证书包含在请求中，服务将使用该证书对发送回客户端的响应进行加密和签名。</span><span class="sxs-lookup"><span data-stu-id="9b4ed-163">In the more typical request/response pattern, the client includes its certificate in the request, which the service uses to encrypt and sign its response back to the client.</span></span> <span data-ttu-id="9b4ed-164">但是，在双工通信模式中，服务没有来自客户端的请求，因此服务需要事先具有客户端的证书以确保发送到客户端的消息的安全。</span><span class="sxs-lookup"><span data-stu-id="9b4ed-164">In the duplex communication pattern, however, the service does not have a request from the client and therefore it needs the client's certificate in advance to secure the message to the client.</span></span> <span data-ttu-id="9b4ed-165">因此，您必须通过带外协商来获取客户端的证书，并使用此元素指定该证书。</span><span class="sxs-lookup"><span data-stu-id="9b4ed-165">Therefore you must obtain the client's certificate in an out-of-band negotiation, and specify the certificate using this element.</span></span> <span data-ttu-id="9b4ed-166">有关双工服务的详细信息，请参阅[如何：创建双工协定](../../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)。</span><span class="sxs-lookup"><span data-stu-id="9b4ed-166">For more information about duplex services, see [How to: Create a Duplex Contract](../../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9b4ed-167">示例</span><span class="sxs-lookup"><span data-stu-id="9b4ed-167">Example</span></span>  
 <span data-ttu-id="9b4ed-168">下面的代码指定如何在 `<authentication>` 元素中查找适当的 X.509 证书和自定义验证类型。</span><span class="sxs-lookup"><span data-stu-id="9b4ed-168">The following code specifies how to find an appropriate X.509 certificate and a custom validation type in the `<authentication>` element.</span></span>  
  
```xml  
<serviceBehaviors>
  <behavior name="myServiceBehavior">
    <clientCertificate>
      <certificate findValue="www.cohowinery.com"
                   storeLocation="CurrentUser"
                   storeName="TrustedPeople"
                   x509FindType="FindByIssuerName" />
      <authentication customCertificateValidatorType="MyTypes.Coho"
                      certificateValidationMode="Custom"
                      revocationMode="Offline"
                      includeWindowsGroups="false"
                      mapClientCertificateToWindowsAccount="true" />
    </clientCertificate>
  </behavior>
</serviceBehaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="9b4ed-169">请参阅</span><span class="sxs-lookup"><span data-stu-id="9b4ed-169">See also</span></span>
- <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential.Certificate%2A>
- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement.Certificate%2A>
- <xref:System.ServiceModel.Configuration.X509ClientCertificateCredentialsElement>
- [<span data-ttu-id="9b4ed-170">安全行为</span><span class="sxs-lookup"><span data-stu-id="9b4ed-170">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="9b4ed-171">如何：创建使用自定义证书验证程序的服务</span><span class="sxs-lookup"><span data-stu-id="9b4ed-171">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)
- [<span data-ttu-id="9b4ed-172">使用证书</span><span class="sxs-lookup"><span data-stu-id="9b4ed-172">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
