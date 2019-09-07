---
title: <defaultCertificate> 元素
ms.date: 03/30/2017
ms.assetid: f1ddf364-9a00-45d3-b989-ff381c154ce6
ms.openlocfilehash: cce236bf80fa00f01a3b5f4680d975f83fde0c16
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400417"
---
# <a name="defaultcertificate-element"></a><span data-ttu-id="101fe-102">\<defaultCertificate > 元素</span><span class="sxs-lookup"><span data-stu-id="101fe-102">\<defaultCertificate> Element</span></span>
<span data-ttu-id="101fe-103">指定在服务或 STS 未通过协商协议提供证书时要使用的 X.509 证书。</span><span class="sxs-lookup"><span data-stu-id="101fe-103">Specifies an X.509 certificate to be used when a service or STS does not provide one via a negotiation protocol.</span></span>  
  
<span data-ttu-id="101fe-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="101fe-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="101fe-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="101fe-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="101fe-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="101fe-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="101fe-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="101fe-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="101fe-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="101fe-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="101fe-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<clientCredentials >** ](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="101fe-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="101fe-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceCertificate >** ](servicecertificate-of-clientcredentials-element.md)</span><span class="sxs-lookup"><span data-stu-id="101fe-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate-of-clientcredentials-element.md)</span></span>\
<span data-ttu-id="101fe-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<defaultCertificate >**</span><span class="sxs-lookup"><span data-stu-id="101fe-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultCertificate>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="101fe-112">语法</span><span class="sxs-lookup"><span data-stu-id="101fe-112">Syntax</span></span>  
  
```xml  
<defaultCertificate findValue="String"
                    storeLocation=" CurrentUser/LocalMachine"
                    storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                    x509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialiNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="101fe-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="101fe-113">Attributes and Elements</span></span>  
 <span data-ttu-id="101fe-114">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="101fe-114">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="101fe-115">特性</span><span class="sxs-lookup"><span data-stu-id="101fe-115">Attributes</span></span>  
  
|<span data-ttu-id="101fe-116">特性</span><span class="sxs-lookup"><span data-stu-id="101fe-116">Attribute</span></span>|<span data-ttu-id="101fe-117">描述</span><span class="sxs-lookup"><span data-stu-id="101fe-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="101fe-118">findValue</span><span class="sxs-lookup"><span data-stu-id="101fe-118">findValue</span></span>|<span data-ttu-id="101fe-119">字符串。</span><span class="sxs-lookup"><span data-stu-id="101fe-119">String.</span></span> <span data-ttu-id="101fe-120">要搜索的值。</span><span class="sxs-lookup"><span data-stu-id="101fe-120">The value to search for.</span></span>|  
|<span data-ttu-id="101fe-121">x509FindType</span><span class="sxs-lookup"><span data-stu-id="101fe-121">x509FindType</span></span>|<span data-ttu-id="101fe-122">枚举。</span><span class="sxs-lookup"><span data-stu-id="101fe-122">Enumeration.</span></span> <span data-ttu-id="101fe-123">要搜索的证书字段之一。</span><span class="sxs-lookup"><span data-stu-id="101fe-123">One of the certificate fields to search.</span></span>|  
|<span data-ttu-id="101fe-124">storeLocation</span><span class="sxs-lookup"><span data-stu-id="101fe-124">storeLocation</span></span>|<span data-ttu-id="101fe-125">枚举。</span><span class="sxs-lookup"><span data-stu-id="101fe-125">Enumeration.</span></span> <span data-ttu-id="101fe-126">要搜索的两个系统存储位置之一。</span><span class="sxs-lookup"><span data-stu-id="101fe-126">One of the two system store locations to search.</span></span>|  
|<span data-ttu-id="101fe-127">storeName</span><span class="sxs-lookup"><span data-stu-id="101fe-127">storeName</span></span>|<span data-ttu-id="101fe-128">枚举。</span><span class="sxs-lookup"><span data-stu-id="101fe-128">Enumeration.</span></span> <span data-ttu-id="101fe-129">要搜索的系统存储之一。</span><span class="sxs-lookup"><span data-stu-id="101fe-129">One of the system stores to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="101fe-130">findValue 属性</span><span class="sxs-lookup"><span data-stu-id="101fe-130">findValue Attribute</span></span>  
  
|<span data-ttu-id="101fe-131">值</span><span class="sxs-lookup"><span data-stu-id="101fe-131">Value</span></span>|<span data-ttu-id="101fe-132">描述</span><span class="sxs-lookup"><span data-stu-id="101fe-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="101fe-133">String</span><span class="sxs-lookup"><span data-stu-id="101fe-133">String</span></span>|<span data-ttu-id="101fe-134">值取决于搜索的字段（由 X509FindType 属性指定）。</span><span class="sxs-lookup"><span data-stu-id="101fe-134">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="101fe-135">例如，如果搜索指纹，则此值必须为十六进制数字字符串。</span><span class="sxs-lookup"><span data-stu-id="101fe-135">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="101fe-136">x509FindType 属性</span><span class="sxs-lookup"><span data-stu-id="101fe-136">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="101fe-137">值</span><span class="sxs-lookup"><span data-stu-id="101fe-137">Value</span></span>|<span data-ttu-id="101fe-138">描述</span><span class="sxs-lookup"><span data-stu-id="101fe-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="101fe-139">枚举</span><span class="sxs-lookup"><span data-stu-id="101fe-139">Enumeration</span></span>|<span data-ttu-id="101fe-140">值包括：FindByThumbprint、Findbysubjectname)、FindBySubjectDistinguishedName、FindByIssuerName、FindByIssuerDistinguishedName、FindBySerialNumber、FindByTimeValid、FindByTimeNotYetValid、FindBySerialNumber、FindByTimeExpired、FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span><span class="sxs-lookup"><span data-stu-id="101fe-140">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="101fe-141">storeLocation 属性</span><span class="sxs-lookup"><span data-stu-id="101fe-141">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="101fe-142">值</span><span class="sxs-lookup"><span data-stu-id="101fe-142">Value</span></span>|<span data-ttu-id="101fe-143">描述</span><span class="sxs-lookup"><span data-stu-id="101fe-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="101fe-144">枚举</span><span class="sxs-lookup"><span data-stu-id="101fe-144">Enumeration</span></span>|<span data-ttu-id="101fe-145">CurrentUser 或 LocalMachine。</span><span class="sxs-lookup"><span data-stu-id="101fe-145">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="101fe-146">storeName 属性</span><span class="sxs-lookup"><span data-stu-id="101fe-146">storeName Attribute</span></span>  
  
|<span data-ttu-id="101fe-147">值</span><span class="sxs-lookup"><span data-stu-id="101fe-147">Value</span></span>|<span data-ttu-id="101fe-148">描述</span><span class="sxs-lookup"><span data-stu-id="101fe-148">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="101fe-149">枚举</span><span class="sxs-lookup"><span data-stu-id="101fe-149">Enumeration</span></span>|<span data-ttu-id="101fe-150">值包括：通讯簿、AuthRoot、CertificateAuthority、不允许、My、Root、TrustedPeople 和 TrustedPublisher。</span><span class="sxs-lookup"><span data-stu-id="101fe-150">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="101fe-151">子元素</span><span class="sxs-lookup"><span data-stu-id="101fe-151">Child Elements</span></span>  
 <span data-ttu-id="101fe-152">无。</span><span class="sxs-lookup"><span data-stu-id="101fe-152">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="101fe-153">父元素</span><span class="sxs-lookup"><span data-stu-id="101fe-153">Parent Elements</span></span>  
  
|<span data-ttu-id="101fe-154">元素</span><span class="sxs-lookup"><span data-stu-id="101fe-154">Element</span></span>|<span data-ttu-id="101fe-155">描述</span><span class="sxs-lookup"><span data-stu-id="101fe-155">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="101fe-156">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="101fe-156">\<serviceCertificate></span></span>](servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="101fe-157">指定客户端对服务进行身份验证时使用的证书。</span><span class="sxs-lookup"><span data-stu-id="101fe-157">Specifies a certificate to use when authenticating a service to the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="101fe-158">备注</span><span class="sxs-lookup"><span data-stu-id="101fe-158">Remarks</span></span>  
 <span data-ttu-id="101fe-159">对于使用基于证书的消息安全的绑定，此配置元素指定的证书用于加密发送给服务的消息，并期望服务用它来对客户端的应答进行签名。</span><span class="sxs-lookup"><span data-stu-id="101fe-159">For bindings that use certificate-based message security, certificate specified by this configuration element is used to encrypt messages to the service and is expected to be used by the service for signing replies to the client.</span></span> <span data-ttu-id="101fe-160">如果服务未指定任何证书，它只存储要使用的一个证书。</span><span class="sxs-lookup"><span data-stu-id="101fe-160">It stores a single certificate to be used when no certificate is specified by a service.</span></span>  
  
## <a name="example"></a><span data-ttu-id="101fe-161">示例</span><span class="sxs-lookup"><span data-stu-id="101fe-161">Example</span></span>  
 <span data-ttu-id="101fe-162">下面的示例指定证书用于 URI 以开头的终结点 `http://www.contoso.com` 和要使用其他不执行证书协商的所有终结点的证书。</span><span class="sxs-lookup"><span data-stu-id="101fe-162">The following example specifies a certificate to use for endpoints whose URI begins with `http://www.contoso.com` and a certificate to use for all other endpoints that do not perform certificate negotiation.</span></span>  
  
```xml  
<serviceCertificate>
  <defaultCertificate findValue="www.contoso.com"
                      storeLocation="LocalMachine"
                      storeName="TrustedPeople"
                      x509FindType="FindByIssuerDistinguishedName" />
  <scopedCertificates>
    <add targetUri="http://www.contoso.com"
         findValue="www.contoso.com"
         storeLocation="LocalMachine"
         storeName="Root"
         x509FindType="FindByIssuerName" />
  </scopedCertificates>
  <authentication revocationMode="Online"
                  trustedStoreLocation="LocalMachine" />
</serviceCertificate>
```  
  
## <a name="see-also"></a><span data-ttu-id="101fe-163">请参阅</span><span class="sxs-lookup"><span data-stu-id="101fe-163">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509DefaultServiceCertificateElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.DefaultCertificate%2A>
- [<span data-ttu-id="101fe-164">使用证书</span><span class="sxs-lookup"><span data-stu-id="101fe-164">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="101fe-165">\<authentication></span><span class="sxs-lookup"><span data-stu-id="101fe-165">\<authentication></span></span>](authentication-of-clientcertificate-element.md)
- [<span data-ttu-id="101fe-166">保护客户端</span><span class="sxs-lookup"><span data-stu-id="101fe-166">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="101fe-167">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="101fe-167">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
