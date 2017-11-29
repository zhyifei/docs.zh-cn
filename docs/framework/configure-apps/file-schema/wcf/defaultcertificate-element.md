---
title: "&lt;defaultCertificate&gt; 元素"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f1ddf364-9a00-45d3-b989-ff381c154ce6
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4424b8b5e0389c0a0395550fddb71ac34e0fb987
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltdefaultcertificategt-element"></a><span data-ttu-id="d6a65-102">&lt;defaultCertificate&gt; 元素</span><span class="sxs-lookup"><span data-stu-id="d6a65-102">&lt;defaultCertificate&gt; Element</span></span>
<span data-ttu-id="d6a65-103">指定在服务或 STS 未通过协商协议提供证书时要使用的 X.509 证书。</span><span class="sxs-lookup"><span data-stu-id="d6a65-103">Specifies an X.509 certificate to be used when a service or STS does not provide one via a negotiation protocol.</span></span>  
  
 <span data-ttu-id="d6a65-104">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="d6a65-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="d6a65-105">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="d6a65-105">\<behaviors></span></span>  
<span data-ttu-id="d6a65-106">endpointBehaviors 部分</span><span class="sxs-lookup"><span data-stu-id="d6a65-106">endpointBehaviors section</span></span>  
<span data-ttu-id="d6a65-107">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="d6a65-107">\<behavior></span></span>  
<span data-ttu-id="d6a65-108">\<c a t e ></span><span class="sxs-lookup"><span data-stu-id="d6a65-108">\<clientCredentials></span></span>  
<span data-ttu-id="d6a65-109">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="d6a65-109">\<serviceCertificate></span></span>  
<span data-ttu-id="d6a65-110">\<defaultCertificate ></span><span class="sxs-lookup"><span data-stu-id="d6a65-110">\<defaultCertificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6a65-111">语法</span><span class="sxs-lookup"><span data-stu-id="d6a65-111">Syntax</span></span>  
  
```xml  
<defaultCertificate findValue="String"   
storeLocation=" CurrentUser/LocalMachine"  
storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"   
x509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialiNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d6a65-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d6a65-112">Attributes and Elements</span></span>  
 <span data-ttu-id="d6a65-113">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="d6a65-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d6a65-114">特性</span><span class="sxs-lookup"><span data-stu-id="d6a65-114">Attributes</span></span>  
  
|<span data-ttu-id="d6a65-115">特性</span><span class="sxs-lookup"><span data-stu-id="d6a65-115">Attribute</span></span>|<span data-ttu-id="d6a65-116">描述</span><span class="sxs-lookup"><span data-stu-id="d6a65-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d6a65-117">findValue</span><span class="sxs-lookup"><span data-stu-id="d6a65-117">findValue</span></span>|<span data-ttu-id="d6a65-118">字符串。</span><span class="sxs-lookup"><span data-stu-id="d6a65-118">String.</span></span> <span data-ttu-id="d6a65-119">要搜索的值。</span><span class="sxs-lookup"><span data-stu-id="d6a65-119">The value to search for.</span></span>|  
|<span data-ttu-id="d6a65-120">x509FindType</span><span class="sxs-lookup"><span data-stu-id="d6a65-120">x509FindType</span></span>|<span data-ttu-id="d6a65-121">枚举。</span><span class="sxs-lookup"><span data-stu-id="d6a65-121">Enumeration.</span></span> <span data-ttu-id="d6a65-122">要搜索的证书字段之一。</span><span class="sxs-lookup"><span data-stu-id="d6a65-122">One of the certificate fields to search.</span></span>|  
|<span data-ttu-id="d6a65-123">storeLocation</span><span class="sxs-lookup"><span data-stu-id="d6a65-123">storeLocation</span></span>|<span data-ttu-id="d6a65-124">枚举。</span><span class="sxs-lookup"><span data-stu-id="d6a65-124">Enumeration.</span></span> <span data-ttu-id="d6a65-125">要搜索的两个系统存储位置之一。</span><span class="sxs-lookup"><span data-stu-id="d6a65-125">One of the two system store locations to search.</span></span>|  
|<span data-ttu-id="d6a65-126">storeName</span><span class="sxs-lookup"><span data-stu-id="d6a65-126">storeName</span></span>|<span data-ttu-id="d6a65-127">枚举。</span><span class="sxs-lookup"><span data-stu-id="d6a65-127">Enumeration.</span></span> <span data-ttu-id="d6a65-128">要搜索的系统存储之一。</span><span class="sxs-lookup"><span data-stu-id="d6a65-128">One of the system stores to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="d6a65-129">findValue 属性</span><span class="sxs-lookup"><span data-stu-id="d6a65-129">findValue Attribute</span></span>  
  
|<span data-ttu-id="d6a65-130">值</span><span class="sxs-lookup"><span data-stu-id="d6a65-130">Value</span></span>|<span data-ttu-id="d6a65-131">描述</span><span class="sxs-lookup"><span data-stu-id="d6a65-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d6a65-132">String</span><span class="sxs-lookup"><span data-stu-id="d6a65-132">String</span></span>|<span data-ttu-id="d6a65-133">值取决于搜索的字段（由 X509FindType 属性指定）。</span><span class="sxs-lookup"><span data-stu-id="d6a65-133">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="d6a65-134">例如，如果搜索指纹，则此值必须为十六进制数字字符串。</span><span class="sxs-lookup"><span data-stu-id="d6a65-134">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="d6a65-135">x509FindType 属性</span><span class="sxs-lookup"><span data-stu-id="d6a65-135">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="d6a65-136">值</span><span class="sxs-lookup"><span data-stu-id="d6a65-136">Value</span></span>|<span data-ttu-id="d6a65-137">描述</span><span class="sxs-lookup"><span data-stu-id="d6a65-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d6a65-138">枚举</span><span class="sxs-lookup"><span data-stu-id="d6a65-138">Enumeration</span></span>|<span data-ttu-id="d6a65-139">值包括：FindByThumbprint、FindBySubjectName、FindBySubjectDistinguishedName、FindByIssuerName、FindByIssuerDistinguishedName、FindBySerialNumber、FindByTimeValid、FindByTimeNotYetValid、FindBySerialNumber、FindByTimeExpired、FindByTemplateName、FindByApplicationPolicy、FindByCertificatePolicy、FindByExtension、FindByKeyUsage 和 FindBySubjectKeyIdentifier。</span><span class="sxs-lookup"><span data-stu-id="d6a65-139">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="d6a65-140">storeLocation 属性</span><span class="sxs-lookup"><span data-stu-id="d6a65-140">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="d6a65-141">值</span><span class="sxs-lookup"><span data-stu-id="d6a65-141">Value</span></span>|<span data-ttu-id="d6a65-142">描述</span><span class="sxs-lookup"><span data-stu-id="d6a65-142">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d6a65-143">枚举</span><span class="sxs-lookup"><span data-stu-id="d6a65-143">Enumeration</span></span>|<span data-ttu-id="d6a65-144">CurrentUser 或 LocalMachine。</span><span class="sxs-lookup"><span data-stu-id="d6a65-144">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="d6a65-145">storeName 属性</span><span class="sxs-lookup"><span data-stu-id="d6a65-145">storeName Attribute</span></span>  
  
|<span data-ttu-id="d6a65-146">值</span><span class="sxs-lookup"><span data-stu-id="d6a65-146">Value</span></span>|<span data-ttu-id="d6a65-147">描述</span><span class="sxs-lookup"><span data-stu-id="d6a65-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d6a65-148">枚举</span><span class="sxs-lookup"><span data-stu-id="d6a65-148">Enumeration</span></span>|<span data-ttu-id="d6a65-149">值包括：AddressBook、AuthRoot、CertificateAuthority、Disallowed、My、Root、TrustedPeople 和 TrustedPublisher。</span><span class="sxs-lookup"><span data-stu-id="d6a65-149">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d6a65-150">子元素</span><span class="sxs-lookup"><span data-stu-id="d6a65-150">Child Elements</span></span>  
 <span data-ttu-id="d6a65-151">无。</span><span class="sxs-lookup"><span data-stu-id="d6a65-151">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d6a65-152">父元素</span><span class="sxs-lookup"><span data-stu-id="d6a65-152">Parent Elements</span></span>  
  
|<span data-ttu-id="d6a65-153">元素</span><span class="sxs-lookup"><span data-stu-id="d6a65-153">Element</span></span>|<span data-ttu-id="d6a65-154">描述</span><span class="sxs-lookup"><span data-stu-id="d6a65-154">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d6a65-155">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="d6a65-155">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="d6a65-156">指定客户端对服务进行身份验证时使用的证书。</span><span class="sxs-lookup"><span data-stu-id="d6a65-156">Specifies a certificate to use when authenticating a service to the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d6a65-157">备注</span><span class="sxs-lookup"><span data-stu-id="d6a65-157">Remarks</span></span>  
 <span data-ttu-id="d6a65-158">对于使用基于证书的消息安全的绑定，此配置元素指定的证书用于加密发送给服务的消息，并期望服务用它来对客户端的应答进行签名。</span><span class="sxs-lookup"><span data-stu-id="d6a65-158">For bindings that use certificate-based message security, certificate specified by this configuration element is used to encrypt messages to the service and is expected to be used by the service for signing replies to the client.</span></span> <span data-ttu-id="d6a65-159">如果服务未指定任何证书，它只存储要使用的一个证书。</span><span class="sxs-lookup"><span data-stu-id="d6a65-159">It stores a single certificate to be used when no certificate is specified by a service.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d6a65-160">示例</span><span class="sxs-lookup"><span data-stu-id="d6a65-160">Example</span></span>  
 <span data-ttu-id="d6a65-161">下面的示例指定了两个证书，一个证书用于 URI 以 http://www.contoso.com 开头的终结点，另一个证书用于不执行证书协商的所有其他终结点。</span><span class="sxs-lookup"><span data-stu-id="d6a65-161">The following example specifies a certificate to use for endpoints whose URI begins with http://www.contoso.com and a certificate to use for all other endpoints that do not perform certificate negotiation.</span></span>  
  
```xml  
<serviceCertificate>  
  <defaultCertificate findValue="www.contoso.com"   
                      storeLocation="LocalMachine"  
                      storeName="TrustedPeople"   
                      x509FindType="FindByIssuerDistinguishedName" />  
  <scopedCertificates>  
     <add targetUri="http://www.contoso.com"   
          findValue="www.contoso.com" storeLocation="LocalMachine"  
                  storeName="Root" x509FindType="FindByIssuerName" />  
  </scopedCertificates>  
  <authentication revocationMode="Online"   
   trustedStoreLocation="LocalMachine" />  
</serviceCertificate>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d6a65-162">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d6a65-162">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.X509DefaultServiceCertificateElement>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.DefaultCertificate%2A>  
 [<span data-ttu-id="d6a65-163">使用证书</span><span class="sxs-lookup"><span data-stu-id="d6a65-163">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="d6a65-164">\<身份验证 ></span><span class="sxs-lookup"><span data-stu-id="d6a65-164">\<authentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md)  
 [<span data-ttu-id="d6a65-165">保护客户端</span><span class="sxs-lookup"><span data-stu-id="d6a65-165">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="d6a65-166">保护服务和客户端</span><span class="sxs-lookup"><span data-stu-id="d6a65-166">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
