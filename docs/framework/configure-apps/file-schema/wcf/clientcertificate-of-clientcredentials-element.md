---
title: "&lt;clientCredentials&gt; 的 &lt;clientCertificate&gt; 元素"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3b3fa000-3434-4142-a178-11903bdd2c5d
caps.latest.revision: "14"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 961e745f15b4c7b7ae489a8b2b3128c1a64c6eab
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltclientcertificategt-of-ltclientcredentialsgt-element"></a><span data-ttu-id="edf75-102">&lt;clientCredentials&gt; 的 &lt;clientCertificate&gt; 元素</span><span class="sxs-lookup"><span data-stu-id="edf75-102">&lt;clientCertificate&gt; of &lt;clientCredentials&gt; Element</span></span>
<span data-ttu-id="edf75-103">定义用于针对服务进行客户端身份验证的 X.509 证书。</span><span class="sxs-lookup"><span data-stu-id="edf75-103">Defines an X.509 certificate used to authenticate a client to a service.</span></span>  
  
 <span data-ttu-id="edf75-104">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="edf75-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="edf75-105">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="edf75-105">\<behaviors></span></span>  
<span data-ttu-id="edf75-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="edf75-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="edf75-107">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="edf75-107">\<behavior></span></span>  
<span data-ttu-id="edf75-108">\<c a t e ></span><span class="sxs-lookup"><span data-stu-id="edf75-108">\<clientCredentials></span></span>  
<span data-ttu-id="edf75-109">\<t i a l ></span><span class="sxs-lookup"><span data-stu-id="edf75-109">\<clientCertificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="edf75-110">语法</span><span class="sxs-lookup"><span data-stu-id="edf75-110">Syntax</span></span>  
  
```xml  
<clientCertificate findValue="String"   
    storeLocation="LocalMachine/CurrentUser"  
    storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="edf75-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="edf75-111">Attributes and Elements</span></span>  
 <span data-ttu-id="edf75-112">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="edf75-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="edf75-113">特性</span><span class="sxs-lookup"><span data-stu-id="edf75-113">Attributes</span></span>  
  
|<span data-ttu-id="edf75-114">特性</span><span class="sxs-lookup"><span data-stu-id="edf75-114">Attribute</span></span>|<span data-ttu-id="edf75-115">描述</span><span class="sxs-lookup"><span data-stu-id="edf75-115">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="edf75-116">一个字符串，包含要在 X.509 证书存储中搜索的值。</span><span class="sxs-lookup"><span data-stu-id="edf75-116">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="edf75-117">此属性中包含的类型必须满足 `X509FindType` 属性值的要求。</span><span class="sxs-lookup"><span data-stu-id="edf75-117">The type contained in the attribute must satisfy the requirements of the `X509FindType` attribute value.</span></span> <span data-ttu-id="edf75-118">默认值为一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="edf75-118">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="edf75-119">指定客户端用于向服务验证自身身份的 X.509 证书的位置。</span><span class="sxs-lookup"><span data-stu-id="edf75-119">Specifies the location of the X.509 certificate that the client uses to authenticate itself to the service.</span></span> <span data-ttu-id="edf75-120">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="edf75-120">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="edf75-121">-LocalMachine： 分配给本地计算机的证书存储。</span><span class="sxs-lookup"><span data-stu-id="edf75-121">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="edf75-122">-CurrentUser： 分配给当前用户的证书存储。</span><span class="sxs-lookup"><span data-stu-id="edf75-122">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="edf75-123">默认值为 LocalMachine。</span><span class="sxs-lookup"><span data-stu-id="edf75-123">The default is LocalMachine.</span></span> <span data-ttu-id="edf75-124">此属性的类型为 <xref:System.Security.Cryptography.X509Certificates.StoreLocation>。</span><span class="sxs-lookup"><span data-stu-id="edf75-124">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span></span>|  
|`storeName`|<span data-ttu-id="edf75-125">指定要搜索的 X.509 证书存储的名称。</span><span class="sxs-lookup"><span data-stu-id="edf75-125">Specifies the name of the X.509 certificate store to search.</span></span> <span data-ttu-id="edf75-126">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="edf75-126">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="edf75-127">-AddressBook： 其他用户证书存储区。</span><span class="sxs-lookup"><span data-stu-id="edf75-127">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="edf75-128">-AuthRoot： 证书存储第三方证书颁发机构 (Ca)。</span><span class="sxs-lookup"><span data-stu-id="edf75-128">-   AuthRoot: Certificate store for third-party certificate authorities (CAs).</span></span><br /><span data-ttu-id="edf75-129">-CertificateAuthority： 中间证书颁发机构 (Ca) 证书存储区。</span><span class="sxs-lookup"><span data-stu-id="edf75-129">-   CertificateAuthority: Certificate store for intermediate certificate authorities (CAs).</span></span><br /><span data-ttu-id="edf75-130">-不允许： 证书吊销的证书存储。</span><span class="sxs-lookup"><span data-stu-id="edf75-130">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="edf75-131">-My： 个人证书的证书存储区。</span><span class="sxs-lookup"><span data-stu-id="edf75-131">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="edf75-132">-Root： 受信任的根证书颁发机构 (Ca) 证书存储区。</span><span class="sxs-lookup"><span data-stu-id="edf75-132">-   Root: Certificate store for trusted root certificate authorities (CAs).</span></span><br /><span data-ttu-id="edf75-133">-TrustedPeople： 直接受信任的人和资源的证书存储区。</span><span class="sxs-lookup"><span data-stu-id="edf75-133">-   TrustedPeople: Certificate store for directly trusted people and resources.</span></span><br /><span data-ttu-id="edf75-134">-TrustedPublisher： 直接受信任的发行者的证书存储区。</span><span class="sxs-lookup"><span data-stu-id="edf75-134">-   TrustedPublisher: Certificate store for directly trusted publishers.</span></span><br /><br /> <span data-ttu-id="edf75-135">默认值为 My。</span><span class="sxs-lookup"><span data-stu-id="edf75-135">The default is My.</span></span> <span data-ttu-id="edf75-136">此属性的类型为 <xref:System.Security.Cryptography.X509Certificates.StoreName>。</span><span class="sxs-lookup"><span data-stu-id="edf75-136">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.StoreName>.</span></span>|  
|<span data-ttu-id="edf75-137">X509FindType</span><span class="sxs-lookup"><span data-stu-id="edf75-137">X509FindType</span></span>|<span data-ttu-id="edf75-138">定义要执行的 X.509 搜索的类型。</span><span class="sxs-lookup"><span data-stu-id="edf75-138">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="edf75-139">`findValue` 属性中包含的类型必须满足此属性的要求。</span><span class="sxs-lookup"><span data-stu-id="edf75-139">The type contained in the `findValue` attribute must satisfy the requirements of this attribute.</span></span> <span data-ttu-id="edf75-140">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="edf75-140">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="edf75-141">-FindByThumbPrint</span><span class="sxs-lookup"><span data-stu-id="edf75-141">-   FindByThumbPrint</span></span><br /><span data-ttu-id="edf75-142">-FindBySubjectName</span><span class="sxs-lookup"><span data-stu-id="edf75-142">-   FindBySubjectName</span></span><br /><span data-ttu-id="edf75-143">-FindBySubjectDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="edf75-143">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="edf75-144">-FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="edf75-144">-   FindByIssuerName</span></span><br /><span data-ttu-id="edf75-145">-FindByIssuerDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="edf75-145">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="edf75-146">-FindBySerialNumber</span><span class="sxs-lookup"><span data-stu-id="edf75-146">-   FindBySerialNumber</span></span><br /><span data-ttu-id="edf75-147">-FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="edf75-147">-   FindByTimeValid</span></span><br /><span data-ttu-id="edf75-148">-FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="edf75-148">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="edf75-149">-FindByTemplateName</span><span class="sxs-lookup"><span data-stu-id="edf75-149">-   FindByTemplateName</span></span><br /><span data-ttu-id="edf75-150">-FindByApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="edf75-150">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="edf75-151">-FindByCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="edf75-151">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="edf75-152">-FindByExtension</span><span class="sxs-lookup"><span data-stu-id="edf75-152">-   FindByExtension</span></span><br /><span data-ttu-id="edf75-153">-FindByKeyUsage</span><span class="sxs-lookup"><span data-stu-id="edf75-153">-   FindByKeyUsage</span></span><br /><span data-ttu-id="edf75-154">-和 FindBySubjectKeyIdentifier</span><span class="sxs-lookup"><span data-stu-id="edf75-154">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="edf75-155">默认值为 FindBySubjectDistinguishedName。</span><span class="sxs-lookup"><span data-stu-id="edf75-155">The default value is FindBySubjectDistinguishedName.</span></span> <span data-ttu-id="edf75-156">此属性的类型为 <xref:System.Security.Cryptography.X509Certificates.X509FindType>。</span><span class="sxs-lookup"><span data-stu-id="edf75-156">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.X509FindType>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="edf75-157">子元素</span><span class="sxs-lookup"><span data-stu-id="edf75-157">Child Elements</span></span>  
 <span data-ttu-id="edf75-158">无。</span><span class="sxs-lookup"><span data-stu-id="edf75-158">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="edf75-159">父元素</span><span class="sxs-lookup"><span data-stu-id="edf75-159">Parent Elements</span></span>  
  
|<span data-ttu-id="edf75-160">元素</span><span class="sxs-lookup"><span data-stu-id="edf75-160">Element</span></span>|<span data-ttu-id="edf75-161">描述</span><span class="sxs-lookup"><span data-stu-id="edf75-161">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="edf75-162">\<c a t e ></span><span class="sxs-lookup"><span data-stu-id="edf75-162">\<clientCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|<span data-ttu-id="edf75-163">指定用于向服务验证客户端身份的凭据。</span><span class="sxs-lookup"><span data-stu-id="edf75-163">Specifies the credentials used to authenticate the client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="edf75-164">备注</span><span class="sxs-lookup"><span data-stu-id="edf75-164">Remarks</span></span>  
 <span data-ttu-id="edf75-165">此配置元素指定用于对具有此元素的客户端进行身份验证的证书。</span><span class="sxs-lookup"><span data-stu-id="edf75-165">This configuration element specifies the certificate used to authenticate the client with this element.</span></span> [!INCLUDE[crdefault](../../../../../includes/crdefault-md.md)]<span data-ttu-id="edf75-166">[如何： 指定客户端凭据值](../../../../../docs/framework/wcf/how-to-specify-client-credential-values.md)。</span><span class="sxs-lookup"><span data-stu-id="edf75-166"> [How to: Specify Client Credential Values](../../../../../docs/framework/wcf/how-to-specify-client-credential-values.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edf75-167">另请参阅</span><span class="sxs-lookup"><span data-stu-id="edf75-167">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement.ClientCertificate%2A>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Description.ClientCredentials.ClientCertificate%2A>  
 <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>  
 <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>  
 [<span data-ttu-id="edf75-168">安全行为</span><span class="sxs-lookup"><span data-stu-id="edf75-168">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="edf75-169">如何：指定客户端凭据值</span><span class="sxs-lookup"><span data-stu-id="edf75-169">How to: Specify Client Credential Values</span></span>](../../../../../docs/framework/wcf/how-to-specify-client-credential-values.md)  
 [<span data-ttu-id="edf75-170">保护客户端</span><span class="sxs-lookup"><span data-stu-id="edf75-170">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="edf75-171">使用证书</span><span class="sxs-lookup"><span data-stu-id="edf75-171">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="edf75-172">保护服务和客户端</span><span class="sxs-lookup"><span data-stu-id="edf75-172">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
