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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: eeb4c1b010e2d446303e780966668fc8a6f5ddb7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltdefaultcertificategt-element"></a><span data-ttu-id="3ed47-102">&lt;defaultCertificate&gt; 元素</span><span class="sxs-lookup"><span data-stu-id="3ed47-102">&lt;defaultCertificate&gt; Element</span></span>
<span data-ttu-id="3ed47-103">指定在服务或 STS 未通过协商协议提供证书时要使用的 X.509 证书。</span><span class="sxs-lookup"><span data-stu-id="3ed47-103">Specifies an X.509 certificate to be used when a service or STS does not provide one via a negotiation protocol.</span></span>  
  
 <span data-ttu-id="3ed47-104">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="3ed47-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="3ed47-105">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="3ed47-105">\<behaviors></span></span>  
<span data-ttu-id="3ed47-106">endpointBehaviors 部分</span><span class="sxs-lookup"><span data-stu-id="3ed47-106">endpointBehaviors section</span></span>  
<span data-ttu-id="3ed47-107">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="3ed47-107">\<behavior></span></span>  
<span data-ttu-id="3ed47-108">\<c a t e ></span><span class="sxs-lookup"><span data-stu-id="3ed47-108">\<clientCredentials></span></span>  
<span data-ttu-id="3ed47-109">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="3ed47-109">\<serviceCertificate></span></span>  
<span data-ttu-id="3ed47-110">\<defaultCertificate ></span><span class="sxs-lookup"><span data-stu-id="3ed47-110">\<defaultCertificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ed47-111">语法</span><span class="sxs-lookup"><span data-stu-id="3ed47-111">Syntax</span></span>  
  
```xml  
<defaultCertificate findValue="String"   
storeLocation=" CurrentUser/LocalMachine"  
storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"   
x509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialiNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3ed47-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="3ed47-112">Attributes and Elements</span></span>  
 <span data-ttu-id="3ed47-113">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="3ed47-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3ed47-114">特性</span><span class="sxs-lookup"><span data-stu-id="3ed47-114">Attributes</span></span>  
  
|<span data-ttu-id="3ed47-115">特性</span><span class="sxs-lookup"><span data-stu-id="3ed47-115">Attribute</span></span>|<span data-ttu-id="3ed47-116">描述</span><span class="sxs-lookup"><span data-stu-id="3ed47-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3ed47-117">findValue</span><span class="sxs-lookup"><span data-stu-id="3ed47-117">findValue</span></span>|<span data-ttu-id="3ed47-118">字符串。</span><span class="sxs-lookup"><span data-stu-id="3ed47-118">String.</span></span> <span data-ttu-id="3ed47-119">要搜索的值。</span><span class="sxs-lookup"><span data-stu-id="3ed47-119">The value to search for.</span></span>|  
|<span data-ttu-id="3ed47-120">x509FindType</span><span class="sxs-lookup"><span data-stu-id="3ed47-120">x509FindType</span></span>|<span data-ttu-id="3ed47-121">枚举。</span><span class="sxs-lookup"><span data-stu-id="3ed47-121">Enumeration.</span></span> <span data-ttu-id="3ed47-122">要搜索的证书字段之一。</span><span class="sxs-lookup"><span data-stu-id="3ed47-122">One of the certificate fields to search.</span></span>|  
|<span data-ttu-id="3ed47-123">storeLocation</span><span class="sxs-lookup"><span data-stu-id="3ed47-123">storeLocation</span></span>|<span data-ttu-id="3ed47-124">枚举。</span><span class="sxs-lookup"><span data-stu-id="3ed47-124">Enumeration.</span></span> <span data-ttu-id="3ed47-125">要搜索的两个系统存储位置之一。</span><span class="sxs-lookup"><span data-stu-id="3ed47-125">One of the two system store locations to search.</span></span>|  
|<span data-ttu-id="3ed47-126">storeName</span><span class="sxs-lookup"><span data-stu-id="3ed47-126">storeName</span></span>|<span data-ttu-id="3ed47-127">枚举。</span><span class="sxs-lookup"><span data-stu-id="3ed47-127">Enumeration.</span></span> <span data-ttu-id="3ed47-128">要搜索的系统存储之一。</span><span class="sxs-lookup"><span data-stu-id="3ed47-128">One of the system stores to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="3ed47-129">findValue 属性</span><span class="sxs-lookup"><span data-stu-id="3ed47-129">findValue Attribute</span></span>  
  
|<span data-ttu-id="3ed47-130">值</span><span class="sxs-lookup"><span data-stu-id="3ed47-130">Value</span></span>|<span data-ttu-id="3ed47-131">描述</span><span class="sxs-lookup"><span data-stu-id="3ed47-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3ed47-132">String</span><span class="sxs-lookup"><span data-stu-id="3ed47-132">String</span></span>|<span data-ttu-id="3ed47-133">值取决于搜索的字段（由 X509FindType 属性指定）。</span><span class="sxs-lookup"><span data-stu-id="3ed47-133">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="3ed47-134">例如，如果搜索指纹，则此值必须为十六进制数字字符串。</span><span class="sxs-lookup"><span data-stu-id="3ed47-134">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="3ed47-135">x509FindType 属性</span><span class="sxs-lookup"><span data-stu-id="3ed47-135">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="3ed47-136">值</span><span class="sxs-lookup"><span data-stu-id="3ed47-136">Value</span></span>|<span data-ttu-id="3ed47-137">描述</span><span class="sxs-lookup"><span data-stu-id="3ed47-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3ed47-138">枚举</span><span class="sxs-lookup"><span data-stu-id="3ed47-138">Enumeration</span></span>|<span data-ttu-id="3ed47-139">值包括：FindByThumbprint、FindBySubjectName、FindBySubjectDistinguishedName、FindByIssuerName、FindByIssuerDistinguishedName、FindBySerialNumber、FindByTimeValid、FindByTimeNotYetValid、FindBySerialNumber、FindByTimeExpired、FindByTemplateName、FindByApplicationPolicy、FindByCertificatePolicy、FindByExtension、FindByKeyUsage 和 FindBySubjectKeyIdentifier。</span><span class="sxs-lookup"><span data-stu-id="3ed47-139">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="3ed47-140">storeLocation 属性</span><span class="sxs-lookup"><span data-stu-id="3ed47-140">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="3ed47-141">值</span><span class="sxs-lookup"><span data-stu-id="3ed47-141">Value</span></span>|<span data-ttu-id="3ed47-142">描述</span><span class="sxs-lookup"><span data-stu-id="3ed47-142">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3ed47-143">枚举</span><span class="sxs-lookup"><span data-stu-id="3ed47-143">Enumeration</span></span>|<span data-ttu-id="3ed47-144">CurrentUser 或 LocalMachine。</span><span class="sxs-lookup"><span data-stu-id="3ed47-144">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="3ed47-145">storeName 属性</span><span class="sxs-lookup"><span data-stu-id="3ed47-145">storeName Attribute</span></span>  
  
|<span data-ttu-id="3ed47-146">值</span><span class="sxs-lookup"><span data-stu-id="3ed47-146">Value</span></span>|<span data-ttu-id="3ed47-147">描述</span><span class="sxs-lookup"><span data-stu-id="3ed47-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3ed47-148">枚举</span><span class="sxs-lookup"><span data-stu-id="3ed47-148">Enumeration</span></span>|<span data-ttu-id="3ed47-149">值包括：AddressBook、AuthRoot、CertificateAuthority、Disallowed、My、Root、TrustedPeople 和 TrustedPublisher。</span><span class="sxs-lookup"><span data-stu-id="3ed47-149">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3ed47-150">子元素</span><span class="sxs-lookup"><span data-stu-id="3ed47-150">Child Elements</span></span>  
 <span data-ttu-id="3ed47-151">无。</span><span class="sxs-lookup"><span data-stu-id="3ed47-151">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3ed47-152">父元素</span><span class="sxs-lookup"><span data-stu-id="3ed47-152">Parent Elements</span></span>  
  
|<span data-ttu-id="3ed47-153">元素</span><span class="sxs-lookup"><span data-stu-id="3ed47-153">Element</span></span>|<span data-ttu-id="3ed47-154">描述</span><span class="sxs-lookup"><span data-stu-id="3ed47-154">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3ed47-155">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="3ed47-155">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="3ed47-156">指定客户端对服务进行身份验证时使用的证书。</span><span class="sxs-lookup"><span data-stu-id="3ed47-156">Specifies a certificate to use when authenticating a service to the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3ed47-157">备注</span><span class="sxs-lookup"><span data-stu-id="3ed47-157">Remarks</span></span>  
 <span data-ttu-id="3ed47-158">对于使用基于证书的消息安全的绑定，此配置元素指定的证书用于加密发送给服务的消息，并期望服务用它来对客户端的应答进行签名。</span><span class="sxs-lookup"><span data-stu-id="3ed47-158">For bindings that use certificate-based message security, certificate specified by this configuration element is used to encrypt messages to the service and is expected to be used by the service for signing replies to the client.</span></span> <span data-ttu-id="3ed47-159">如果服务未指定任何证书，它只存储要使用的一个证书。</span><span class="sxs-lookup"><span data-stu-id="3ed47-159">It stores a single certificate to be used when no certificate is specified by a service.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3ed47-160">示例</span><span class="sxs-lookup"><span data-stu-id="3ed47-160">Example</span></span>  
 <span data-ttu-id="3ed47-161">下面的示例指定了两个证书，一个证书用于 URI 以 http://www.contoso.com 开头的终结点，另一个证书用于不执行证书协商的所有其他终结点。</span><span class="sxs-lookup"><span data-stu-id="3ed47-161">The following example specifies a certificate to use for endpoints whose URI begins with http://www.contoso.com and a certificate to use for all other endpoints that do not perform certificate negotiation.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3ed47-162">请参阅</span><span class="sxs-lookup"><span data-stu-id="3ed47-162">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.X509DefaultServiceCertificateElement>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.DefaultCertificate%2A>  
 [<span data-ttu-id="3ed47-163">使用证书</span><span class="sxs-lookup"><span data-stu-id="3ed47-163">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="3ed47-164">\<身份验证 ></span><span class="sxs-lookup"><span data-stu-id="3ed47-164">\<authentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md)  
 [<span data-ttu-id="3ed47-165">保护客户端</span><span class="sxs-lookup"><span data-stu-id="3ed47-165">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="3ed47-166">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="3ed47-166">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
