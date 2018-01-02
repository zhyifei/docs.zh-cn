---
title: "&lt;serviceCredentials&gt; 的 &lt;serviceCertificate&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 597ae6d5-4938-4950-9f5e-b2280e816182
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e5b6baca250e4fadc2a66bb0fe83b076522f82ee
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltservicecertificategt-of-ltservicecredentialsgt"></a><span data-ttu-id="3cb90-102">&lt;serviceCredentials&gt; 的 &lt;serviceCertificate&gt;</span><span class="sxs-lookup"><span data-stu-id="3cb90-102">&lt;serviceCertificate&gt; of &lt;serviceCredentials&gt;</span></span>
<span data-ttu-id="3cb90-103">指定一个 X.509 证书，以供服务用来向使用 Message 安全模式的客户端证明自己的身份。</span><span class="sxs-lookup"><span data-stu-id="3cb90-103">Specify an X.509 certificate that will be used to authenticate the service to clients using Message security mode.</span></span>  
  
 <span data-ttu-id="3cb90-104">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="3cb90-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="3cb90-105">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="3cb90-105">\<behaviors></span></span>  
<span data-ttu-id="3cb90-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="3cb90-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="3cb90-107">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="3cb90-107">\<behavior></span></span>  
<span data-ttu-id="3cb90-108">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="3cb90-108">\<serviceCredentials></span></span>  
<span data-ttu-id="3cb90-109">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="3cb90-109">\<serviceCertificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3cb90-110">语法</span><span class="sxs-lookup"><span data-stu-id="3cb90-110">Syntax</span></span>  
  
```xml  
<serviceCertificate findValue="String"   
    storeLocation="LocalMachine/CurrentUser"  
    storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3cb90-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="3cb90-111">Attributes and Elements</span></span>  
 <span data-ttu-id="3cb90-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="3cb90-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3cb90-113">特性</span><span class="sxs-lookup"><span data-stu-id="3cb90-113">Attributes</span></span>  
  
|<span data-ttu-id="3cb90-114">特性</span><span class="sxs-lookup"><span data-stu-id="3cb90-114">Attribute</span></span>|<span data-ttu-id="3cb90-115">描述</span><span class="sxs-lookup"><span data-stu-id="3cb90-115">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="3cb90-116">一个字符串，包含要在 X.509 证书存储中搜索的值。</span><span class="sxs-lookup"><span data-stu-id="3cb90-116">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="3cb90-117">此属性中包含的类型必须满足指定 X509FindType 的要求。</span><span class="sxs-lookup"><span data-stu-id="3cb90-117">The type contained in the attribute must satisfy the requirements of the specified X509FindType.</span></span> <span data-ttu-id="3cb90-118">默认值为一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="3cb90-118">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="3cb90-119">指定客户端可用于验证服务器证书的 X.509 证书存储的位置。</span><span class="sxs-lookup"><span data-stu-id="3cb90-119">Specifies the location of the X.509 certificate store that the client uses to validate the server’s certificate against.</span></span> <span data-ttu-id="3cb90-120">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="3cb90-120">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="3cb90-121">-LocalMachine： 分配给本地计算机的证书存储。</span><span class="sxs-lookup"><span data-stu-id="3cb90-121">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="3cb90-122">-CurrentUser： 分配给当前用户的证书存储。</span><span class="sxs-lookup"><span data-stu-id="3cb90-122">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="3cb90-123">默认值为 LocalMachine。</span><span class="sxs-lookup"><span data-stu-id="3cb90-123">The default is LocalMachine.</span></span>|  
|`storeName`|<span data-ttu-id="3cb90-124">指定要打开的 X.509 证书存储区的名称。</span><span class="sxs-lookup"><span data-stu-id="3cb90-124">Specifies the name of the X.509 certificate store to open.</span></span> <span data-ttu-id="3cb90-125">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="3cb90-125">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="3cb90-126">-AddressBook： 其他用户证书存储区。</span><span class="sxs-lookup"><span data-stu-id="3cb90-126">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="3cb90-127">-AuthRoot： 证书存储第三方证书颁发机构 (Ca)。</span><span class="sxs-lookup"><span data-stu-id="3cb90-127">-   AuthRoot: Certificate store for third-party certification authorities (CAs).</span></span><br /><span data-ttu-id="3cb90-128">-CertificatAuthority： 中间证书颁发机构 (Ca) 证书存储区。</span><span class="sxs-lookup"><span data-stu-id="3cb90-128">-   CertificatAuthority: Certificate store for intermediate certification authorities (CAs).</span></span><br /><span data-ttu-id="3cb90-129">-不允许： 证书吊销的证书存储。</span><span class="sxs-lookup"><span data-stu-id="3cb90-129">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="3cb90-130">-My： 个人证书的证书存储区。</span><span class="sxs-lookup"><span data-stu-id="3cb90-130">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="3cb90-131">-Root： 受信任的根证书颁发机构 (Ca) 证书存储区。</span><span class="sxs-lookup"><span data-stu-id="3cb90-131">-   Root: Certificate store for trusted root certification authorities (CAs).</span></span><br /><span data-ttu-id="3cb90-132">-TrustedPeople： 直接受信任的人和资源的证书存储区。</span><span class="sxs-lookup"><span data-stu-id="3cb90-132">-   TrustedPeople: Certificate store for directly trusted people and resources.</span></span><br /><span data-ttu-id="3cb90-133">-TrustedPublisher： 直接受信任的发行者的证书存储区。</span><span class="sxs-lookup"><span data-stu-id="3cb90-133">-   TrustedPublisher: Certificate store for directly trusted publishers.</span></span><br /><br /> <span data-ttu-id="3cb90-134">默认值为 My。</span><span class="sxs-lookup"><span data-stu-id="3cb90-134">The default is My.</span></span>|  
|`x509FindType`|<span data-ttu-id="3cb90-135">定义要执行的 X.509 搜索的类型。</span><span class="sxs-lookup"><span data-stu-id="3cb90-135">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="3cb90-136">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="3cb90-136">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="3cb90-137">-FindByThumbprint</span><span class="sxs-lookup"><span data-stu-id="3cb90-137">-   FindByThumbprint</span></span><br /><span data-ttu-id="3cb90-138">-FindBySubjectName</span><span class="sxs-lookup"><span data-stu-id="3cb90-138">-   FindBySubjectName</span></span><br /><span data-ttu-id="3cb90-139">-FindBySubjectDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="3cb90-139">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="3cb90-140">-FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="3cb90-140">-   FindByIssuerName</span></span><br /><span data-ttu-id="3cb90-141">-FindByIssuerDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="3cb90-141">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="3cb90-142">-FindBySerialNumber</span><span class="sxs-lookup"><span data-stu-id="3cb90-142">-   FindBySerialNumber</span></span><br /><span data-ttu-id="3cb90-143">-FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="3cb90-143">-   FindByTimeValid</span></span><br /><span data-ttu-id="3cb90-144">-FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="3cb90-144">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="3cb90-145">-FindByTemplateName</span><span class="sxs-lookup"><span data-stu-id="3cb90-145">-   FindByTemplateName</span></span><br /><span data-ttu-id="3cb90-146">-FindByApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="3cb90-146">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="3cb90-147">-FindByCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="3cb90-147">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="3cb90-148">-FindByExtension</span><span class="sxs-lookup"><span data-stu-id="3cb90-148">-   FindByExtension</span></span><br /><span data-ttu-id="3cb90-149">-FindByKeyUsage</span><span class="sxs-lookup"><span data-stu-id="3cb90-149">-   FindByKeyUsage</span></span><br /><span data-ttu-id="3cb90-150">-和 FindBySubjectKeyIdentifier</span><span class="sxs-lookup"><span data-stu-id="3cb90-150">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="3cb90-151">`findValue` 属性中包含的类型必须满足指定 X509FindType 的要求。</span><span class="sxs-lookup"><span data-stu-id="3cb90-151">The type contained in the `findValue` attribute must satisfy the requirements of the specified X509FindType.</span></span><br /><br /> <span data-ttu-id="3cb90-152">默认值为 FindBySubjectDistinguishedName。</span><span class="sxs-lookup"><span data-stu-id="3cb90-152">The default value is FindBySubjectDistinguishedName.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3cb90-153">子元素</span><span class="sxs-lookup"><span data-stu-id="3cb90-153">Child Elements</span></span>  
 <span data-ttu-id="3cb90-154">无</span><span class="sxs-lookup"><span data-stu-id="3cb90-154">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3cb90-155">父元素</span><span class="sxs-lookup"><span data-stu-id="3cb90-155">Parent Elements</span></span>  
  
|<span data-ttu-id="3cb90-156">元素</span><span class="sxs-lookup"><span data-stu-id="3cb90-156">Element</span></span>|<span data-ttu-id="3cb90-157">描述</span><span class="sxs-lookup"><span data-stu-id="3cb90-157">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3cb90-158">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="3cb90-158">\<serviceCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|<span data-ttu-id="3cb90-159">指定要用于对服务进行身份验证的凭据以及与客户端凭据验证相关的设置。</span><span class="sxs-lookup"><span data-stu-id="3cb90-159">Specifies the credential to be used in authenticating the service, and the client credential validation related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3cb90-160">备注</span><span class="sxs-lookup"><span data-stu-id="3cb90-160">Remarks</span></span>  
 <span data-ttu-id="3cb90-161">使用此元素可指定一个 X.509 证书，以供服务用来向使用 Message 安全模式的客户端证明自己的身份。</span><span class="sxs-lookup"><span data-stu-id="3cb90-161">Use this element to specify an X.509 certificate that will be used to authenticate the service to clients using Message security mode.</span></span> <span data-ttu-id="3cb90-162">如果您使用的是将会定期续订的证书，则证书的指纹将会变更。</span><span class="sxs-lookup"><span data-stu-id="3cb90-162">If you are using a certificate that will be periodically renewed, then its thumbprint will change.</span></span> <span data-ttu-id="3cb90-163">在此情况下，请使用主题名称作为 `x509FindType`，因为可以使用同一主题名称来重新颁发该证书。</span><span class="sxs-lookup"><span data-stu-id="3cb90-163">In that case, use the subject name as the `x509FindType` because the certificate can be reissued with the same subject name.</span></span>  
  
 [!INCLUDE[crabout](../../../../../includes/crabout-md.md)]<span data-ttu-id="3cb90-164">使用了元素，请参阅[如何： 指定客户端凭据值](../../../../../docs/framework/wcf/how-to-specify-client-credential-values.md)。</span><span class="sxs-lookup"><span data-stu-id="3cb90-164"> using the element, see [How to: Specify Client Credential Values](../../../../../docs/framework/wcf/how-to-specify-client-credential-values.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cb90-165">请参阅</span><span class="sxs-lookup"><span data-stu-id="3cb90-165">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>  
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.ServiceCertificate%2A>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential>  
 <xref:System.ServiceModel.Description.ServiceCredentials.ServiceCertificate%2A>  
 [<span data-ttu-id="3cb90-166">如何：指定客户端凭据值</span><span class="sxs-lookup"><span data-stu-id="3cb90-166">How to: Specify Client Credential Values</span></span>](../../../../../docs/framework/wcf/how-to-specify-client-credential-values.md)  
 [<span data-ttu-id="3cb90-167">安全行为</span><span class="sxs-lookup"><span data-stu-id="3cb90-167">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
