---
title: "&lt;peer&gt; 的 &lt;certificate&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 48b69142-c957-4305-a042-c9d0c9a55c0e
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f46ebab92cbca616b06db5be6dc155a44558aa7e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltcertificategt-of-ltpeergt"></a><span data-ttu-id="ecfd1-102">&lt;peer&gt; 的 &lt;certificate&gt;</span><span class="sxs-lookup"><span data-stu-id="ecfd1-102">&lt;certificate&gt; of &lt;peer&gt;</span></span>
<span data-ttu-id="ecfd1-103">指定对等方使用的证书。</span><span class="sxs-lookup"><span data-stu-id="ecfd1-103">Specifies a certificate used by a peer.</span></span>  
  
 <span data-ttu-id="ecfd1-104">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="ecfd1-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="ecfd1-105">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="ecfd1-105">\<behaviors></span></span>  
<span data-ttu-id="ecfd1-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="ecfd1-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="ecfd1-107">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="ecfd1-107">\<behavior></span></span>  
<span data-ttu-id="ecfd1-108">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="ecfd1-108">\<serviceCredentials></span></span>  
<span data-ttu-id="ecfd1-109">\<对等 ></span><span class="sxs-lookup"><span data-stu-id="ecfd1-109">\<peer></span></span>  
<span data-ttu-id="ecfd1-110">\<证书 ></span><span class="sxs-lookup"><span data-stu-id="ecfd1-110">\<certificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecfd1-111">语法</span><span class="sxs-lookup"><span data-stu-id="ecfd1-111">Syntax</span></span>  
  
```xml  
<certificate findValue = "String"   
storeLocation = "CurrentUser/LocalMachine"  
storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ecfd1-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="ecfd1-112">Attributes and Elements</span></span>  
 <span data-ttu-id="ecfd1-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="ecfd1-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ecfd1-114">特性</span><span class="sxs-lookup"><span data-stu-id="ecfd1-114">Attributes</span></span>  
  
|<span data-ttu-id="ecfd1-115">特性</span><span class="sxs-lookup"><span data-stu-id="ecfd1-115">Attribute</span></span>|<span data-ttu-id="ecfd1-116">描述</span><span class="sxs-lookup"><span data-stu-id="ecfd1-116">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="ecfd1-117">一个字符串，包含要在 X.509 证书存储中搜索的值。</span><span class="sxs-lookup"><span data-stu-id="ecfd1-117">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="ecfd1-118">此属性中包含的类型必须满足指定 `x509FindType` 的要求。</span><span class="sxs-lookup"><span data-stu-id="ecfd1-118">The type contained in the attribute must satisfy the requirements of the specified `x509FindType`.</span></span> <span data-ttu-id="ecfd1-119">默认值为一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="ecfd1-119">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="ecfd1-120">指定客户端可用于验证对等方的证书的 X.509 证书存储的位置。</span><span class="sxs-lookup"><span data-stu-id="ecfd1-120">Specifies the location of the X.509 certificate store that the client uses to validate the peer's certificate against.</span></span> <span data-ttu-id="ecfd1-121">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="ecfd1-121">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="ecfd1-122">-LocalMachine： 分配给本地计算机的证书存储。</span><span class="sxs-lookup"><span data-stu-id="ecfd1-122">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="ecfd1-123">-CurrentUser： 分配给当前用户的证书存储。</span><span class="sxs-lookup"><span data-stu-id="ecfd1-123">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="ecfd1-124">默认值为 LocalMachine。</span><span class="sxs-lookup"><span data-stu-id="ecfd1-124">The default is LocalMachine.</span></span>|  
|`storeName`|<span data-ttu-id="ecfd1-125">指定要打开的 X.509 证书存储区的名称。</span><span class="sxs-lookup"><span data-stu-id="ecfd1-125">Specifies the name of the X.509 certificate store to open.</span></span> <span data-ttu-id="ecfd1-126">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="ecfd1-126">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="ecfd1-127">-AddressBook： 其他用户证书存储区。</span><span class="sxs-lookup"><span data-stu-id="ecfd1-127">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="ecfd1-128">-AuthRoot： 证书存储第三方证书颁发机构 (Ca)。</span><span class="sxs-lookup"><span data-stu-id="ecfd1-128">-   AuthRoot: Certificate store for third-party certificate authorities (CAs).</span></span><br /><span data-ttu-id="ecfd1-129">-CertificateAuthority： 中间证书颁发机构 (Ca) 证书存储区。</span><span class="sxs-lookup"><span data-stu-id="ecfd1-129">-   CertificateAuthority: Certificate store for intermediate certificate authorities (CAs).</span></span><br /><span data-ttu-id="ecfd1-130">-不允许： 证书吊销的证书存储。</span><span class="sxs-lookup"><span data-stu-id="ecfd1-130">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="ecfd1-131">-My： 个人证书的证书存储区。</span><span class="sxs-lookup"><span data-stu-id="ecfd1-131">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="ecfd1-132">-Root： 受信任的根证书颁发机构 (Ca) 证书存储区。</span><span class="sxs-lookup"><span data-stu-id="ecfd1-132">-   Root: Certificate store for trusted root certificate authorities (CAs).</span></span><br /><span data-ttu-id="ecfd1-133">-TrustedPeople： 直接受信任的人和资源的证书存储区。</span><span class="sxs-lookup"><span data-stu-id="ecfd1-133">-   TrustedPeople: Certificate store for directly-trusted people and resources.</span></span><br /><span data-ttu-id="ecfd1-134">-TrustedPublisher： 直接受信任发布者证书存储区。</span><span class="sxs-lookup"><span data-stu-id="ecfd1-134">-   TrustedPublisher: Certificate store for directly-trusted publishers.</span></span><br /><br /> <span data-ttu-id="ecfd1-135">默认值为 My。</span><span class="sxs-lookup"><span data-stu-id="ecfd1-135">The default is My.</span></span>|  
|`X509FindType`|<span data-ttu-id="ecfd1-136">定义要执行的 X.509 搜索的类型。</span><span class="sxs-lookup"><span data-stu-id="ecfd1-136">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="ecfd1-137">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="ecfd1-137">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="ecfd1-138">-FindByThumbPrint</span><span class="sxs-lookup"><span data-stu-id="ecfd1-138">-   FindByThumbPrint</span></span><br /><span data-ttu-id="ecfd1-139">-FindBySubjectName</span><span class="sxs-lookup"><span data-stu-id="ecfd1-139">-   FindBySubjectName</span></span><br /><span data-ttu-id="ecfd1-140">-FindBySubjectDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="ecfd1-140">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="ecfd1-141">-FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="ecfd1-141">-   FindByIssuerName</span></span><br /><span data-ttu-id="ecfd1-142">-FindByIssuerDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="ecfd1-142">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="ecfd1-143">-FindBySerialNumber</span><span class="sxs-lookup"><span data-stu-id="ecfd1-143">-   FindBySerialNumber</span></span><br /><span data-ttu-id="ecfd1-144">-FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="ecfd1-144">-   FindByTimeValid</span></span><br /><span data-ttu-id="ecfd1-145">-FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="ecfd1-145">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="ecfd1-146">-FindByTemplateName</span><span class="sxs-lookup"><span data-stu-id="ecfd1-146">-   FindByTemplateName</span></span><br /><span data-ttu-id="ecfd1-147">-FindByApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="ecfd1-147">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="ecfd1-148">-FindByCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="ecfd1-148">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="ecfd1-149">-FindByExtension</span><span class="sxs-lookup"><span data-stu-id="ecfd1-149">-   FindByExtension</span></span><br /><span data-ttu-id="ecfd1-150">-FindByKeyUsage</span><span class="sxs-lookup"><span data-stu-id="ecfd1-150">-   FindByKeyUsage</span></span><br /><span data-ttu-id="ecfd1-151">-和 FindBySubjectKeyIdentifier</span><span class="sxs-lookup"><span data-stu-id="ecfd1-151">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="ecfd1-152">`findValue` 属性中包含的类型必须满足指定 `X509FindType` 的要求。</span><span class="sxs-lookup"><span data-stu-id="ecfd1-152">The type contained in the `findValue` attribute must satisfy the requirements of the specified `X509FindType`.</span></span><br /><br /> <span data-ttu-id="ecfd1-153">默认值为 FindBySubjectDistinguishedName。</span><span class="sxs-lookup"><span data-stu-id="ecfd1-153">The default value is FindBySubjectDistinguishedName.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ecfd1-154">子元素</span><span class="sxs-lookup"><span data-stu-id="ecfd1-154">Child Elements</span></span>  
 <span data-ttu-id="ecfd1-155">无。</span><span class="sxs-lookup"><span data-stu-id="ecfd1-155">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ecfd1-156">父元素</span><span class="sxs-lookup"><span data-stu-id="ecfd1-156">Parent Elements</span></span>  
  
|<span data-ttu-id="ecfd1-157">元素</span><span class="sxs-lookup"><span data-stu-id="ecfd1-157">Element</span></span>|<span data-ttu-id="ecfd1-158">描述</span><span class="sxs-lookup"><span data-stu-id="ecfd1-158">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ecfd1-159">\<对等 ></span><span class="sxs-lookup"><span data-stu-id="ecfd1-159">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-servicecredentials.md)|<span data-ttu-id="ecfd1-160">指定对等节点的当前凭据。</span><span class="sxs-lookup"><span data-stu-id="ecfd1-160">Specifies the current credentials for a peer node.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ecfd1-161">备注</span><span class="sxs-lookup"><span data-stu-id="ecfd1-161">Remarks</span></span>  
 <span data-ttu-id="ecfd1-162">此配置元素包含对对等网格中的邻居进行身份验证时使用的 `X509Certificate2` 实例。</span><span class="sxs-lookup"><span data-stu-id="ecfd1-162">This configuration element contains an `X509Certificate2` instance used when authenticating neighbors in the peer mesh.</span></span>  
  
 <span data-ttu-id="ecfd1-163">有关对等编程的详细信息，请参阅[对等网络](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)。</span><span class="sxs-lookup"><span data-stu-id="ecfd1-163">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecfd1-164">请参阅</span><span class="sxs-lookup"><span data-stu-id="ecfd1-164">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement.Certificate%2A>  
 <xref:System.ServiceModel.Configuration.X509PeerCertificateElement>  
 <xref:System.ServiceModel.Security.PeerCredential.Certificate%2A>  
 <xref:System.ServiceModel.Security.PeerCredential>  
 [<span data-ttu-id="ecfd1-165">使用证书</span><span class="sxs-lookup"><span data-stu-id="ecfd1-165">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="ecfd1-166">对等网络</span><span class="sxs-lookup"><span data-stu-id="ecfd1-166">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [<span data-ttu-id="ecfd1-167">对等通道消息身份验证</span><span class="sxs-lookup"><span data-stu-id="ecfd1-167">Peer Channel Message Authentication</span></span>](http://msdn.microsoft.com/en-us/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [<span data-ttu-id="ecfd1-168">对等通道自定义身份验证</span><span class="sxs-lookup"><span data-stu-id="ecfd1-168">Peer Channel Custom Authentication</span></span>](http://msdn.microsoft.com/en-us/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [<span data-ttu-id="ecfd1-169">保护对等通道应用程序</span><span class="sxs-lookup"><span data-stu-id="ecfd1-169">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)  
 [<span data-ttu-id="ecfd1-170">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="ecfd1-170">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
