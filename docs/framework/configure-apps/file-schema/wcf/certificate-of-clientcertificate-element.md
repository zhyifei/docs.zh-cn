---
title: <certificate>of <clientCertificate>元素
ms.date: 03/30/2017
ms.assetid: 00297efb-a7f2-4e03-bc2b-943d545610fc
ms.openlocfilehash: d0c4ef9d3657d2dfa787feb3576beda09d1997a3
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400536"
---
# <a name="certificate-of-clientcertificate-element"></a><span data-ttu-id="1db1f-102">\<clientCertificate > 元素\<的证书 ></span><span class="sxs-lookup"><span data-stu-id="1db1f-102">\<certificate> of \<clientCertificate> Element</span></span>
<span data-ttu-id="1db1f-103">指定用于对消息进行签名和加密的 X.509 证书。</span><span class="sxs-lookup"><span data-stu-id="1db1f-103">Specifies an X.509 certificate used to sign and encrypt messages.</span></span>  
  
<span data-ttu-id="1db1f-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="1db1f-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="1db1f-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="1db1f-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="1db1f-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="1db1f-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="1db1f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="1db1f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="1db1f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="1db1f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="1db1f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceCredentials >** ](servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="1db1f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)</span></span>\
<span data-ttu-id="1db1f-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<clientCertificate >** ](clientcertificate-of-servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="1db1f-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCertificate>**](clientcertificate-of-servicecredentials.md)</span></span>\
<span data-ttu-id="1db1f-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<证书 >**</span><span class="sxs-lookup"><span data-stu-id="1db1f-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificate>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1db1f-112">语法</span><span class="sxs-lookup"><span data-stu-id="1db1f-112">Syntax</span></span>  
  
```xml  
<certificate findValue="String"
             storeLocation = "CurrentUser/LocalMachine"
             storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
             X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1db1f-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="1db1f-113">Attributes and Elements</span></span>  
 <span data-ttu-id="1db1f-114">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="1db1f-114">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1db1f-115">特性</span><span class="sxs-lookup"><span data-stu-id="1db1f-115">Attributes</span></span>  
  
|<span data-ttu-id="1db1f-116">特性</span><span class="sxs-lookup"><span data-stu-id="1db1f-116">Attribute</span></span>|<span data-ttu-id="1db1f-117">描述</span><span class="sxs-lookup"><span data-stu-id="1db1f-117">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="1db1f-118">一个字符串，包含要在 X.509 证书存储中搜索的值。</span><span class="sxs-lookup"><span data-stu-id="1db1f-118">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="1db1f-119">此属性中包含的类型必须满足指定 X509FindType 的要求。</span><span class="sxs-lookup"><span data-stu-id="1db1f-119">The type contained in the attribute must satisfy the requirements of the specified X509FindType.</span></span> <span data-ttu-id="1db1f-120">默认值为一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="1db1f-120">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="1db1f-121">指定客户端可用于验证服务器证书的 X.509 证书存储的位置。</span><span class="sxs-lookup"><span data-stu-id="1db1f-121">Specifies the location of the X.509 certificate store that the client uses to validate the server’s certificate against.</span></span> <span data-ttu-id="1db1f-122">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="1db1f-122">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="1db1f-123">-LocalMachine：分配给本地计算机的证书存储区。</span><span class="sxs-lookup"><span data-stu-id="1db1f-123">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="1db1f-124">-CurrentUser：分配给当前用户的证书存储区。</span><span class="sxs-lookup"><span data-stu-id="1db1f-124">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="1db1f-125">默认值为 LocalMachine。</span><span class="sxs-lookup"><span data-stu-id="1db1f-125">The default is LocalMachine.</span></span>|  
|`storeName`|<span data-ttu-id="1db1f-126">指定要打开的 X.509 证书存储区的名称。</span><span class="sxs-lookup"><span data-stu-id="1db1f-126">Specifies the name of the X.509 certificate store to open.</span></span> <span data-ttu-id="1db1f-127">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="1db1f-127">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="1db1f-128">通讯簿其他用户的证书存储区。</span><span class="sxs-lookup"><span data-stu-id="1db1f-128">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="1db1f-129">AuthRoot第三方证书颁发机构（Ca）的证书存储区。</span><span class="sxs-lookup"><span data-stu-id="1db1f-129">-   AuthRoot: Certificate store for third-party certification authorities (CAs).</span></span><br /><span data-ttu-id="1db1f-130">证书颁发机构中间证书颁发机构（Ca）的证书存储区。</span><span class="sxs-lookup"><span data-stu-id="1db1f-130">-   CertificationAuthority: Certificate store for intermediate certification authorities (CAs).</span></span><br /><span data-ttu-id="1db1f-131">禁用吊销的证书的证书存储区。</span><span class="sxs-lookup"><span data-stu-id="1db1f-131">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="1db1f-132">记住个人证书的证书存储区。</span><span class="sxs-lookup"><span data-stu-id="1db1f-132">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="1db1f-133">Root受信任的根证书颁发机构（Ca）的证书存储区。</span><span class="sxs-lookup"><span data-stu-id="1db1f-133">-   Root: Certificate store for trusted root certification authorities (CAs).</span></span><br /><span data-ttu-id="1db1f-134">TrustedPeople直接受信任的人和资源的证书存储区。</span><span class="sxs-lookup"><span data-stu-id="1db1f-134">-   TrustedPeople: Certificate store for directly trusted people and resources.</span></span><br /><span data-ttu-id="1db1f-135">TrustedPublisher直接受信任的发布者的证书存储区。</span><span class="sxs-lookup"><span data-stu-id="1db1f-135">-   TrustedPublisher: Certificate store for directly trusted publishers.</span></span><br /><br /> <span data-ttu-id="1db1f-136">默认值为 My。</span><span class="sxs-lookup"><span data-stu-id="1db1f-136">The default is My.</span></span>|  
|`X509FindType`|<span data-ttu-id="1db1f-137">定义要执行的 X.509 搜索的类型。</span><span class="sxs-lookup"><span data-stu-id="1db1f-137">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="1db1f-138">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="1db1f-138">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="1db1f-139">-FindByThumbPrint</span><span class="sxs-lookup"><span data-stu-id="1db1f-139">-   FindByThumbPrint</span></span><br /><span data-ttu-id="1db1f-140">-   FindBySubjectName</span><span class="sxs-lookup"><span data-stu-id="1db1f-140">-   FindBySubjectName</span></span><br /><span data-ttu-id="1db1f-141">-FindBySubjectDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="1db1f-141">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="1db1f-142">- FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="1db1f-142">-   FindByIssuerName</span></span><br /><span data-ttu-id="1db1f-143">- FindByIssuerDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="1db1f-143">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="1db1f-144">-FindBySerialNumber</span><span class="sxs-lookup"><span data-stu-id="1db1f-144">-   FindBySerialNumber</span></span><br /><span data-ttu-id="1db1f-145">-   FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="1db1f-145">-   FindByTimeValid</span></span><br /><span data-ttu-id="1db1f-146">-   FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="1db1f-146">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="1db1f-147">- FindByTemplateName</span><span class="sxs-lookup"><span data-stu-id="1db1f-147">-   FindByTemplateName</span></span><br /><span data-ttu-id="1db1f-148">-   FindByApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="1db1f-148">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="1db1f-149">-   FindByCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="1db1f-149">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="1db1f-150">- FindByExtension</span><span class="sxs-lookup"><span data-stu-id="1db1f-150">-   FindByExtension</span></span><br /><span data-ttu-id="1db1f-151">- FindByKeyUsage</span><span class="sxs-lookup"><span data-stu-id="1db1f-151">-   FindByKeyUsage</span></span><br /><span data-ttu-id="1db1f-152">-   FindBySubjectKeyIdentifier</span><span class="sxs-lookup"><span data-stu-id="1db1f-152">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="1db1f-153">`findValue` 属性中包含的类型必须满足指定 X509FindType 的要求。</span><span class="sxs-lookup"><span data-stu-id="1db1f-153">The type contained in the `findValue` attribute must satisfy the requirements of the specified X509FindType.</span></span><br /><br /> <span data-ttu-id="1db1f-154">默认值为 FindBySubjectDistinguishedName。</span><span class="sxs-lookup"><span data-stu-id="1db1f-154">The default value is FindBySubjectDistinguishedName.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1db1f-155">子元素</span><span class="sxs-lookup"><span data-stu-id="1db1f-155">Child Elements</span></span>  
 <span data-ttu-id="1db1f-156">无。</span><span class="sxs-lookup"><span data-stu-id="1db1f-156">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1db1f-157">父元素</span><span class="sxs-lookup"><span data-stu-id="1db1f-157">Parent Elements</span></span>  
  
|<span data-ttu-id="1db1f-158">元素</span><span class="sxs-lookup"><span data-stu-id="1db1f-158">Element</span></span>|<span data-ttu-id="1db1f-159">描述</span><span class="sxs-lookup"><span data-stu-id="1db1f-159">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1db1f-160">\<clientCertificate></span><span class="sxs-lookup"><span data-stu-id="1db1f-160">\<clientCertificate></span></span>](clientcertificate-of-servicecredentials.md)||  
  
## <a name="remarks"></a><span data-ttu-id="1db1f-161">备注</span><span class="sxs-lookup"><span data-stu-id="1db1f-161">Remarks</span></span>  
 <span data-ttu-id="1db1f-162">当服务必须事先拥有客户端的证书才能与该客户端进行安全通信时，可使用 `<certificate>` 元素。</span><span class="sxs-lookup"><span data-stu-id="1db1f-162">The `<certificate>` element is used when the service must have the client's certificate in advance to communicate securely with the client.</span></span> <span data-ttu-id="1db1f-163">使用双工通信模式时，会出现这种情况。</span><span class="sxs-lookup"><span data-stu-id="1db1f-163">This occurs when using the duplex communication pattern.</span></span> <span data-ttu-id="1db1f-164">在更为典型的请求/响应模式中，客户端会将其证书包含在请求中，服务将使用该证书对发送回客户端的响应进行加密和签名。</span><span class="sxs-lookup"><span data-stu-id="1db1f-164">In the more typical request/response pattern, the client includes its certificate in the request, which the service uses to encrypt and sign its response back to the client.</span></span> <span data-ttu-id="1db1f-165">但是，在双工通信模式中，服务没有来自客户端的请求，因此服务需要事先具有客户端的证书以确保发送到客户端的消息的安全。</span><span class="sxs-lookup"><span data-stu-id="1db1f-165">In the duplex communication pattern, however, the service does not have a request from the client and therefore it needs the client's certificate in advance to secure the message to the client.</span></span> <span data-ttu-id="1db1f-166">因此，您必须通过带外协商来获取客户端的证书，并使用此元素指定该证书。</span><span class="sxs-lookup"><span data-stu-id="1db1f-166">Therefore you must obtain the client's certificate in an out-of-band negotiation, and specify the certificate using this element.</span></span> <span data-ttu-id="1db1f-167">有关双工服务的详细信息， [请参阅如何：创建双工协定](../../../wcf/feature-details/how-to-create-a-duplex-contract.md)。</span><span class="sxs-lookup"><span data-stu-id="1db1f-167">For more information about duplex services, see [How to: Create a Duplex Contract](../../../wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1db1f-168">示例</span><span class="sxs-lookup"><span data-stu-id="1db1f-168">Example</span></span>  
 <span data-ttu-id="1db1f-169">下面的代码指定如何在 `<authentication>` 元素中查找适当的 X.509 证书和自定义验证类型。</span><span class="sxs-lookup"><span data-stu-id="1db1f-169">The following code specifies how to find an appropriate X.509 certificate and a custom validation type in the `<authentication>` element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1db1f-170">请参阅</span><span class="sxs-lookup"><span data-stu-id="1db1f-170">See also</span></span>

- <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential.Certificate%2A>
- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement.Certificate%2A>
- <xref:System.ServiceModel.Configuration.X509ClientCertificateCredentialsElement>
- [<span data-ttu-id="1db1f-171">安全行为</span><span class="sxs-lookup"><span data-stu-id="1db1f-171">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="1db1f-172">如何：创建使用自定义证书验证程序的服务</span><span class="sxs-lookup"><span data-stu-id="1db1f-172">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)
- [<span data-ttu-id="1db1f-173">使用证书</span><span class="sxs-lookup"><span data-stu-id="1db1f-173">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
