---
title: <defaultCertificate> 元素
ms.date: 03/30/2017
ms.assetid: f1ddf364-9a00-45d3-b989-ff381c154ce6
ms.openlocfilehash: 2f1e17d6c6517e72c1a2ec8e001d857c0d2aa7af
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55275660"
---
# <a name="defaultcertificate-element"></a><span data-ttu-id="de173-102">\<defaultCertificate > 元素</span><span class="sxs-lookup"><span data-stu-id="de173-102">\<defaultCertificate> Element</span></span>
<span data-ttu-id="de173-103">指定在服务或 STS 未通过协商协议提供证书时要使用的 X.509 证书。</span><span class="sxs-lookup"><span data-stu-id="de173-103">Specifies an X.509 certificate to be used when a service or STS does not provide one via a negotiation protocol.</span></span>  
  
 <span data-ttu-id="de173-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="de173-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="de173-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="de173-105">\<behaviors></span></span>  
<span data-ttu-id="de173-106">endpointBehaviors 部分</span><span class="sxs-lookup"><span data-stu-id="de173-106">endpointBehaviors section</span></span>  
<span data-ttu-id="de173-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="de173-107">\<behavior></span></span>  
<span data-ttu-id="de173-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="de173-108">\<clientCredentials></span></span>  
<span data-ttu-id="de173-109">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="de173-109">\<serviceCertificate></span></span>  
<span data-ttu-id="de173-110">\<defaultCertificate></span><span class="sxs-lookup"><span data-stu-id="de173-110">\<defaultCertificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de173-111">语法</span><span class="sxs-lookup"><span data-stu-id="de173-111">Syntax</span></span>  
  
```xml  
<defaultCertificate findValue="String"
                    storeLocation=" CurrentUser/LocalMachine"
                    storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                    x509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialiNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="de173-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="de173-112">Attributes and Elements</span></span>  
 <span data-ttu-id="de173-113">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="de173-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="de173-114">特性</span><span class="sxs-lookup"><span data-stu-id="de173-114">Attributes</span></span>  
  
|<span data-ttu-id="de173-115">特性</span><span class="sxs-lookup"><span data-stu-id="de173-115">Attribute</span></span>|<span data-ttu-id="de173-116">描述</span><span class="sxs-lookup"><span data-stu-id="de173-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="de173-117">findValue</span><span class="sxs-lookup"><span data-stu-id="de173-117">findValue</span></span>|<span data-ttu-id="de173-118">字符串。</span><span class="sxs-lookup"><span data-stu-id="de173-118">String.</span></span> <span data-ttu-id="de173-119">要搜索的值。</span><span class="sxs-lookup"><span data-stu-id="de173-119">The value to search for.</span></span>|  
|<span data-ttu-id="de173-120">x509FindType</span><span class="sxs-lookup"><span data-stu-id="de173-120">x509FindType</span></span>|<span data-ttu-id="de173-121">枚举。</span><span class="sxs-lookup"><span data-stu-id="de173-121">Enumeration.</span></span> <span data-ttu-id="de173-122">要搜索的证书字段之一。</span><span class="sxs-lookup"><span data-stu-id="de173-122">One of the certificate fields to search.</span></span>|  
|<span data-ttu-id="de173-123">storeLocation</span><span class="sxs-lookup"><span data-stu-id="de173-123">storeLocation</span></span>|<span data-ttu-id="de173-124">枚举。</span><span class="sxs-lookup"><span data-stu-id="de173-124">Enumeration.</span></span> <span data-ttu-id="de173-125">要搜索的两个系统存储位置之一。</span><span class="sxs-lookup"><span data-stu-id="de173-125">One of the two system store locations to search.</span></span>|  
|<span data-ttu-id="de173-126">storeName</span><span class="sxs-lookup"><span data-stu-id="de173-126">storeName</span></span>|<span data-ttu-id="de173-127">枚举。</span><span class="sxs-lookup"><span data-stu-id="de173-127">Enumeration.</span></span> <span data-ttu-id="de173-128">要搜索的系统存储之一。</span><span class="sxs-lookup"><span data-stu-id="de173-128">One of the system stores to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="de173-129">findValue 属性</span><span class="sxs-lookup"><span data-stu-id="de173-129">findValue Attribute</span></span>  
  
|<span data-ttu-id="de173-130">值</span><span class="sxs-lookup"><span data-stu-id="de173-130">Value</span></span>|<span data-ttu-id="de173-131">描述</span><span class="sxs-lookup"><span data-stu-id="de173-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="de173-132">String</span><span class="sxs-lookup"><span data-stu-id="de173-132">String</span></span>|<span data-ttu-id="de173-133">值取决于搜索的字段（由 X509FindType 属性指定）。</span><span class="sxs-lookup"><span data-stu-id="de173-133">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="de173-134">例如，如果搜索指纹，则此值必须为十六进制数字字符串。</span><span class="sxs-lookup"><span data-stu-id="de173-134">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="de173-135">x509FindType 属性</span><span class="sxs-lookup"><span data-stu-id="de173-135">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="de173-136">值</span><span class="sxs-lookup"><span data-stu-id="de173-136">Value</span></span>|<span data-ttu-id="de173-137">描述</span><span class="sxs-lookup"><span data-stu-id="de173-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="de173-138">枚举</span><span class="sxs-lookup"><span data-stu-id="de173-138">Enumeration</span></span>|<span data-ttu-id="de173-139">值包括：FindByThumbprint、 FindBySubjectName、 FindBySubjectDistinguishedName、 FindByIssuerName、 FindByIssuerDistinguishedName、 FindBySerialNumber、 FindByTimeValid、 FindByTimeNotYetValid、 FindBySerialNumber、 FindByTimeExpired、 FindByTemplateNameFindByApplicationPolicy、 FindByCertificatePolicy、 FindByExtension、 FindByKeyUsage、 和 FindBySubjectKeyIdentifier。</span><span class="sxs-lookup"><span data-stu-id="de173-139">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="de173-140">storeLocation 属性</span><span class="sxs-lookup"><span data-stu-id="de173-140">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="de173-141">值</span><span class="sxs-lookup"><span data-stu-id="de173-141">Value</span></span>|<span data-ttu-id="de173-142">描述</span><span class="sxs-lookup"><span data-stu-id="de173-142">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="de173-143">枚举</span><span class="sxs-lookup"><span data-stu-id="de173-143">Enumeration</span></span>|<span data-ttu-id="de173-144">CurrentUser 或 LocalMachine。</span><span class="sxs-lookup"><span data-stu-id="de173-144">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="de173-145">storeName 属性</span><span class="sxs-lookup"><span data-stu-id="de173-145">storeName Attribute</span></span>  
  
|<span data-ttu-id="de173-146">值</span><span class="sxs-lookup"><span data-stu-id="de173-146">Value</span></span>|<span data-ttu-id="de173-147">描述</span><span class="sxs-lookup"><span data-stu-id="de173-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="de173-148">枚举</span><span class="sxs-lookup"><span data-stu-id="de173-148">Enumeration</span></span>|<span data-ttu-id="de173-149">值包括：AddressBook、 AuthRoot、 CertificateAuthority、 Disallowed、 My、 根、 TrustedPeople 和 TrustedPublisher。</span><span class="sxs-lookup"><span data-stu-id="de173-149">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="de173-150">子元素</span><span class="sxs-lookup"><span data-stu-id="de173-150">Child Elements</span></span>  
 <span data-ttu-id="de173-151">无。</span><span class="sxs-lookup"><span data-stu-id="de173-151">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="de173-152">父元素</span><span class="sxs-lookup"><span data-stu-id="de173-152">Parent Elements</span></span>  
  
|<span data-ttu-id="de173-153">元素</span><span class="sxs-lookup"><span data-stu-id="de173-153">Element</span></span>|<span data-ttu-id="de173-154">描述</span><span class="sxs-lookup"><span data-stu-id="de173-154">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="de173-155">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="de173-155">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="de173-156">指定客户端对服务进行身份验证时使用的证书。</span><span class="sxs-lookup"><span data-stu-id="de173-156">Specifies a certificate to use when authenticating a service to the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="de173-157">备注</span><span class="sxs-lookup"><span data-stu-id="de173-157">Remarks</span></span>  
 <span data-ttu-id="de173-158">对于使用基于证书的消息安全的绑定，此配置元素指定的证书用于加密发送给服务的消息，并期望服务用它来对客户端的应答进行签名。</span><span class="sxs-lookup"><span data-stu-id="de173-158">For bindings that use certificate-based message security, certificate specified by this configuration element is used to encrypt messages to the service and is expected to be used by the service for signing replies to the client.</span></span> <span data-ttu-id="de173-159">如果服务未指定任何证书，它只存储要使用的一个证书。</span><span class="sxs-lookup"><span data-stu-id="de173-159">It stores a single certificate to be used when no certificate is specified by a service.</span></span>  
  
## <a name="example"></a><span data-ttu-id="de173-160">示例</span><span class="sxs-lookup"><span data-stu-id="de173-160">Example</span></span>  
 <span data-ttu-id="de173-161">下面的示例指定证书用于 URI 以开头的终结点 `http://www.contoso.com` 和要使用其他不执行证书协商的所有终结点的证书。</span><span class="sxs-lookup"><span data-stu-id="de173-161">The following example specifies a certificate to use for endpoints whose URI begins with `http://www.contoso.com` and a certificate to use for all other endpoints that do not perform certificate negotiation.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="de173-162">请参阅</span><span class="sxs-lookup"><span data-stu-id="de173-162">See also</span></span>
- <xref:System.ServiceModel.Configuration.X509DefaultServiceCertificateElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.DefaultCertificate%2A>
- [<span data-ttu-id="de173-163">使用证书</span><span class="sxs-lookup"><span data-stu-id="de173-163">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="de173-164">\<authentication></span><span class="sxs-lookup"><span data-stu-id="de173-164">\<authentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md)
- [<span data-ttu-id="de173-165">保护客户端</span><span class="sxs-lookup"><span data-stu-id="de173-165">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
- [<span data-ttu-id="de173-166">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="de173-166">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
