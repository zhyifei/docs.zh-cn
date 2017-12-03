---
title: "&lt;标识&gt;的&lt; certificateReference&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ac359c65-c22d-42d2-97de-db53b77cebdb
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 27bcccab90c4627f2c9a1d241af3b1833ae13a18
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="ltcertificatereferencegt-for-ltidentitygt"></a><span data-ttu-id="eb642-102">&lt;标识&gt;的&lt; certificateReference&gt;</span><span class="sxs-lookup"><span data-stu-id="eb642-102">&lt;certificateReference&gt; for &lt;identity&gt;</span></span>
<span data-ttu-id="eb642-103">指定 X.509 证书验证的设置。</span><span class="sxs-lookup"><span data-stu-id="eb642-103">Specifies settings for X.509 certificate validation.</span></span> <span data-ttu-id="eb642-104">通过此标识连接到终结点的安全 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 将验证由服务器提供的声明是否包含一个用于构造此标识的标识声明。</span><span class="sxs-lookup"><span data-stu-id="eb642-104">A secure [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] client that connects to an endpoint with this identity verifies that the claims presented by the server contain the identity claim used to construct this identity.</span></span>  
  
 <span data-ttu-id="eb642-105">\<标识 ></span><span class="sxs-lookup"><span data-stu-id="eb642-105">\<identity></span></span>  
<span data-ttu-id="eb642-106">\<certificateReference ></span><span class="sxs-lookup"><span data-stu-id="eb642-106">\<certificateReference></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb642-107">语法</span><span class="sxs-lookup"><span data-stu-id="eb642-107">Syntax</span></span>  
  
```xml  
<certificateReference   
        findValue="String"   
    isChainIncluded="Boolean"  
    storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"storeName="  
  
    storeLocation="LocalMachine/CurrentUser"  
  
X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"  
</certificateReference>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eb642-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="eb642-108">Attributes and Elements</span></span>  
 <span data-ttu-id="eb642-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="eb642-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eb642-110">特性</span><span class="sxs-lookup"><span data-stu-id="eb642-110">Attributes</span></span>  
  
|<span data-ttu-id="eb642-111">特性</span><span class="sxs-lookup"><span data-stu-id="eb642-111">Attribute</span></span>|<span data-ttu-id="eb642-112">描述</span><span class="sxs-lookup"><span data-stu-id="eb642-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="eb642-113">findValue</span><span class="sxs-lookup"><span data-stu-id="eb642-113">findValue</span></span>|<span data-ttu-id="eb642-114">指定要在 X.509 证书存储中搜索的值。</span><span class="sxs-lookup"><span data-stu-id="eb642-114">Specifies the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="eb642-115">此属性中包含的类型必须满足指定的 `X509FindType` 值的要求。</span><span class="sxs-lookup"><span data-stu-id="eb642-115">The type contained in this attribute must satisfy the requirements of the specified `X509FindType` value.</span></span> <span data-ttu-id="eb642-116">默认值为一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="eb642-116">The default is an empty string.</span></span>|  
|<span data-ttu-id="eb642-117">isChainIncluded</span><span class="sxs-lookup"><span data-stu-id="eb642-117">isChainIncluded</span></span>|<span data-ttu-id="eb642-118">一个布尔值，指定是否使用证书链来执行验证。</span><span class="sxs-lookup"><span data-stu-id="eb642-118">A Boolean value that specifies if the validation is done using a certificate chain.</span></span>|  
|<span data-ttu-id="eb642-119">storeLocation</span><span class="sxs-lookup"><span data-stu-id="eb642-119">storeLocation</span></span>|<span data-ttu-id="eb642-120">指定客户端可用于验证服务器证书的证书存储的位置。</span><span class="sxs-lookup"><span data-stu-id="eb642-120">Specifies the location of the certificate store that the client can use to validate the server’s certificate.</span></span><br /><br /> <span data-ttu-id="eb642-121">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="eb642-121">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="eb642-122">-LocalMachine： 分配到本地计算机的证书存储。</span><span class="sxs-lookup"><span data-stu-id="eb642-122">-   LocalMachine: The cert store assigned to the local machine.</span></span><br /><span data-ttu-id="eb642-123">-CurrentUser： 分配给当前用户的证书存储。</span><span class="sxs-lookup"><span data-stu-id="eb642-123">-   CurrentUser: The cert store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="eb642-124">默认值为 LocalMachine。</span><span class="sxs-lookup"><span data-stu-id="eb642-124">The default value is LocalMachine.</span></span><br /><br /> <span data-ttu-id="eb642-125">此属性的类型为 <xref:System.Security.Cryptography.X509Certificates.StoreLocation>。</span><span class="sxs-lookup"><span data-stu-id="eb642-125">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span></span>|  
|<span data-ttu-id="eb642-126">storeName</span><span class="sxs-lookup"><span data-stu-id="eb642-126">storeName</span></span>|<span data-ttu-id="eb642-127">指定要打开的 X.509 证书存储区的名称。</span><span class="sxs-lookup"><span data-stu-id="eb642-127">Specifies the name of the X.509 certificate store to open.</span></span><br /><br /> <span data-ttu-id="eb642-128">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="eb642-128">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="eb642-129">-AddressBook： 其他用户证书存储区。</span><span class="sxs-lookup"><span data-stu-id="eb642-129">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="eb642-130">-AuthRoot： 证书存储第三方证书颁发机构 (Ca)。</span><span class="sxs-lookup"><span data-stu-id="eb642-130">-   AuthRoot: Certificate store for third-party certification authorities (CAs).</span></span><br /><span data-ttu-id="eb642-131">-CertificateAuthority： 中间 Ca 证书存储区。</span><span class="sxs-lookup"><span data-stu-id="eb642-131">-   CertificateAuthority: Certificate store for intermediate CAs.</span></span><br /><span data-ttu-id="eb642-132">-不允许： 证书吊销的证书存储。</span><span class="sxs-lookup"><span data-stu-id="eb642-132">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="eb642-133">-My： 个人证书的证书存储区。</span><span class="sxs-lookup"><span data-stu-id="eb642-133">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="eb642-134">-Root： 受信任的根 Ca 证书存储区。</span><span class="sxs-lookup"><span data-stu-id="eb642-134">-   Root: Certificate store for trusted root CAs.</span></span><br /><span data-ttu-id="eb642-135">-TrustedPeople： 直接受信任的人和资源的证书存储区。</span><span class="sxs-lookup"><span data-stu-id="eb642-135">-   TrustedPeople: Certificate store for directly trusted people and resources.</span></span><br /><span data-ttu-id="eb642-136">-TrustedPublisher： 直接受信任的发行者的证书存储区。</span><span class="sxs-lookup"><span data-stu-id="eb642-136">-   TrustedPublisher: Certificate store for directly trusted publishers.</span></span><br /><br /> <span data-ttu-id="eb642-137">默认值为 My。</span><span class="sxs-lookup"><span data-stu-id="eb642-137">The default value is My.</span></span><br /><br /> <span data-ttu-id="eb642-138">此属性的类型为 <xref:System.Security.Cryptography.X509Certificates.StoreName>。</span><span class="sxs-lookup"><span data-stu-id="eb642-138">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.StoreName>.</span></span>|  
|<span data-ttu-id="eb642-139">X509FindType</span><span class="sxs-lookup"><span data-stu-id="eb642-139">X509FindType</span></span>|<span data-ttu-id="eb642-140">指定要执行的 X.509 搜索的类型。</span><span class="sxs-lookup"><span data-stu-id="eb642-140">Specifies the type of X.509 search to be executed.</span></span> <span data-ttu-id="eb642-141">`findValue` 属性中包含的类型必须满足指定 X509FindType 的要求。</span><span class="sxs-lookup"><span data-stu-id="eb642-141">The type contained in the `findValue` attribute must satisfy the requirements of the specified X509FindType.</span></span><br /><br /> <span data-ttu-id="eb642-142">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="eb642-142">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="eb642-143">-FindByThumbPrint</span><span class="sxs-lookup"><span data-stu-id="eb642-143">-   FindByThumbPrint</span></span><br /><span data-ttu-id="eb642-144">-FindBySubjectName</span><span class="sxs-lookup"><span data-stu-id="eb642-144">-   FindBySubjectName</span></span><br /><span data-ttu-id="eb642-145">-FindBySubjectDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="eb642-145">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="eb642-146">-FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="eb642-146">-   FindByIssuerName</span></span><br /><span data-ttu-id="eb642-147">-FindByIssuerDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="eb642-147">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="eb642-148">-FindBySerialNumber</span><span class="sxs-lookup"><span data-stu-id="eb642-148">-   FindBySerialNumber</span></span><br /><span data-ttu-id="eb642-149">-FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="eb642-149">-   FindByTimeValid</span></span><br /><span data-ttu-id="eb642-150">-FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="eb642-150">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="eb642-151">-FindByTemplateName</span><span class="sxs-lookup"><span data-stu-id="eb642-151">-   FindByTemplateName</span></span><br /><span data-ttu-id="eb642-152">-FindByApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="eb642-152">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="eb642-153">-FindByCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="eb642-153">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="eb642-154">-FindByExtension</span><span class="sxs-lookup"><span data-stu-id="eb642-154">-   FindByExtension</span></span><br /><span data-ttu-id="eb642-155">-FindByKeyUsage</span><span class="sxs-lookup"><span data-stu-id="eb642-155">-   FindByKeyUsage</span></span><br /><span data-ttu-id="eb642-156">-和 FindBySubjectKeyIdentifier</span><span class="sxs-lookup"><span data-stu-id="eb642-156">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="eb642-157">默认值为 FindBySubjectDistinguishedName。</span><span class="sxs-lookup"><span data-stu-id="eb642-157">The default value is FindBySubjectDistinguishedName.</span></span><br /><br /> <span data-ttu-id="eb642-158">此属性的类型为 <xref:System.Security.Cryptography.X509Certificates.X509FindType>。</span><span class="sxs-lookup"><span data-stu-id="eb642-158">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.X509FindType>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="eb642-159">子元素</span><span class="sxs-lookup"><span data-stu-id="eb642-159">Child Elements</span></span>  
 <span data-ttu-id="eb642-160">无。</span><span class="sxs-lookup"><span data-stu-id="eb642-160">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="eb642-161">父元素</span><span class="sxs-lookup"><span data-stu-id="eb642-161">Parent Elements</span></span>  
  
|<span data-ttu-id="eb642-162">元素</span><span class="sxs-lookup"><span data-stu-id="eb642-162">Element</span></span>|<span data-ttu-id="eb642-163">描述</span><span class="sxs-lookup"><span data-stu-id="eb642-163">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eb642-164">\<标识 ></span><span class="sxs-lookup"><span data-stu-id="eb642-164">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="eb642-165">指定一些设置，与某个终结点交换消息的其他终结点可以使用这些设置对该终结点进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="eb642-165">Specifies settings that enable the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="eb642-166">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eb642-166">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.CertificateReferenceElement>  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>
