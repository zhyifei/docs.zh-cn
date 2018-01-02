---
title: '&lt;certificateReference&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
caps.latest.revision: "4"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: fd0d4742a162000d438851cef9c00e21368b7ba1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltcertificatereferencegt"></a><span data-ttu-id="366d9-102">&lt;certificateReference&gt;</span><span class="sxs-lookup"><span data-stu-id="366d9-102">&lt;certificateReference&gt;</span></span>
<span data-ttu-id="366d9-103">指定用于查找和验证的证书存储区中的 X.509 证书的设置。</span><span class="sxs-lookup"><span data-stu-id="366d9-103">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>  
  
 <span data-ttu-id="366d9-104">\<system.identityModel.services ></span><span class="sxs-lookup"><span data-stu-id="366d9-104">\<system.identityModel.services></span></span>  
<span data-ttu-id="366d9-105">\<federationConfiguration ></span><span class="sxs-lookup"><span data-stu-id="366d9-105">\<federationConfiguration></span></span>  
<span data-ttu-id="366d9-106">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="366d9-106">\<serviceCertificate></span></span>  
<span data-ttu-id="366d9-107">\<certificateReference ></span><span class="sxs-lookup"><span data-stu-id="366d9-107">\<certificateReference></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="366d9-108">语法</span><span class="sxs-lookup"><span data-stu-id="366d9-108">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <serviceCertificate>  
      <certificateReference   
        storeName="AddressBook||AuthRoot||CertificateAuthority||Disallowed||My||Root||TrustedPeople||TrustedPublisher"  
        storeLocation="CurrentUser||LocalMachine"  
        x509FindType="FindByThumbprint||FindBySubjectName||FindBySubjectDistinguishedName||FindByIssuerName||FindByIssuerDistinguishedName||FindBySerialNumber||FindByTimeValid||FindByTimeNotYetValid||FindByTimeExpired||FindByTemplateName||FindByApplicationPolicy||FindByCertificatePolicy||FindByExtension||FindByKeyUsage||FindBySubjectKeyIdentifier"  
        findValue=xs:String  
        isChainIncluded=xs:Boolean >  
      </certificateReference>  
    </serviceCertificate>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="366d9-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="366d9-109">Attributes and Elements</span></span>  
 <span data-ttu-id="366d9-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="366d9-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="366d9-111">特性</span><span class="sxs-lookup"><span data-stu-id="366d9-111">Attributes</span></span>  
  
|<span data-ttu-id="366d9-112">特性</span><span class="sxs-lookup"><span data-stu-id="366d9-112">Attribute</span></span>|<span data-ttu-id="366d9-113">描述</span><span class="sxs-lookup"><span data-stu-id="366d9-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="366d9-114">storeName</span><span class="sxs-lookup"><span data-stu-id="366d9-114">storeName</span></span>|<span data-ttu-id="366d9-115">X.509 证书存储区的名称。</span><span class="sxs-lookup"><span data-stu-id="366d9-115">The name of the X.509 certificate store.</span></span> <span data-ttu-id="366d9-116">默认值为"My"。</span><span class="sxs-lookup"><span data-stu-id="366d9-116">The default is "My".</span></span> <span data-ttu-id="366d9-117">可选。</span><span class="sxs-lookup"><span data-stu-id="366d9-117">Optional.</span></span>|  
|<span data-ttu-id="366d9-118">storeLocation</span><span class="sxs-lookup"><span data-stu-id="366d9-118">storeLocation</span></span>|<span data-ttu-id="366d9-119">A<xref:System.Security.Cryptography.X509Certificates.StoreLocation>值，该值指定 X.509 证书存储区的位置。</span><span class="sxs-lookup"><span data-stu-id="366d9-119">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the location of the X.509 certificate store.</span></span> <span data-ttu-id="366d9-120">默认值为"LocalMachine"。</span><span class="sxs-lookup"><span data-stu-id="366d9-120">The default value is "LocalMachine".</span></span> <span data-ttu-id="366d9-121">可选。</span><span class="sxs-lookup"><span data-stu-id="366d9-121">Optional.</span></span>|  
|<span data-ttu-id="366d9-122">x509FindType</span><span class="sxs-lookup"><span data-stu-id="366d9-122">x509FindType</span></span>|<span data-ttu-id="366d9-123"><xref:System.Security.Cryptography.X509Certificates.X509FindType>值，该值指定是要执行的搜索的类型。</span><span class="sxs-lookup"><span data-stu-id="366d9-123">An <xref:System.Security.Cryptography.X509Certificates.X509FindType> value that specifies the type of search that is to be executed.</span></span> <span data-ttu-id="366d9-124">默认值为"FindBySubjectDistinguishedName"。</span><span class="sxs-lookup"><span data-stu-id="366d9-124">The default is "FindBySubjectDistinguishedName".</span></span> <span data-ttu-id="366d9-125">可选。</span><span class="sxs-lookup"><span data-stu-id="366d9-125">Optional.</span></span>|  
|<span data-ttu-id="366d9-126">findValue</span><span class="sxs-lookup"><span data-stu-id="366d9-126">findValue</span></span>|<span data-ttu-id="366d9-127">要在 X.509 证书存储区中搜索的值。</span><span class="sxs-lookup"><span data-stu-id="366d9-127">The value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="366d9-128">可选。</span><span class="sxs-lookup"><span data-stu-id="366d9-128">Optional.</span></span>|  
|<span data-ttu-id="366d9-129">isChainIncluded</span><span class="sxs-lookup"><span data-stu-id="366d9-129">isChainIncluded</span></span>|<span data-ttu-id="366d9-130">指定是否应执行验证通过使用证书链。</span><span class="sxs-lookup"><span data-stu-id="366d9-130">Specifies whether validation should be performed by using the certificate chain.</span></span> <span data-ttu-id="366d9-131">默认值为"true";通过使用证书链执行验证。</span><span class="sxs-lookup"><span data-stu-id="366d9-131">The default is "true"; validation is performed by using the certificate chain.</span></span> <span data-ttu-id="366d9-132">可选。</span><span class="sxs-lookup"><span data-stu-id="366d9-132">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="366d9-133">子元素</span><span class="sxs-lookup"><span data-stu-id="366d9-133">Child Elements</span></span>  
 <span data-ttu-id="366d9-134">无</span><span class="sxs-lookup"><span data-stu-id="366d9-134">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="366d9-135">父元素</span><span class="sxs-lookup"><span data-stu-id="366d9-135">Parent Elements</span></span>  
  
|<span data-ttu-id="366d9-136">元素</span><span class="sxs-lookup"><span data-stu-id="366d9-136">Element</span></span>|<span data-ttu-id="366d9-137">描述</span><span class="sxs-lookup"><span data-stu-id="366d9-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="366d9-138">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="366d9-138">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicecertificate.md)|<span data-ttu-id="366d9-139">配置用来加密和解密令牌的证书。</span><span class="sxs-lookup"><span data-stu-id="366d9-139">Configures the certificate that is used to encrypt and decrypt tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="366d9-140">备注</span><span class="sxs-lookup"><span data-stu-id="366d9-140">Remarks</span></span>  
 <span data-ttu-id="366d9-141">`<certificateReference>`元素指定用于查找和验证的证书存储区中的 X.509 证书的设置。</span><span class="sxs-lookup"><span data-stu-id="366d9-141">The `<certificateReference>` element specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span> <span data-ttu-id="366d9-142">当指定的子元素为`<serviceCertficate>`元素，它指定用于加密和解密令牌的 X.509 证书的位置和验证设置。</span><span class="sxs-lookup"><span data-stu-id="366d9-142">When it is specified as the child element of the `<serviceCertficate>` element, it specifies the location and verification settings of the X.509 certificate that is used to encrypt and decrypt tokens.</span></span> <span data-ttu-id="366d9-143">`<certificateReference>`元素表示由<xref:System.ServiceModel.Configuration.CertificateReferenceElement>类。</span><span class="sxs-lookup"><span data-stu-id="366d9-143">The `<certificateReference>` element is represented by the <xref:System.ServiceModel.Configuration.CertificateReferenceElement> class.</span></span>
