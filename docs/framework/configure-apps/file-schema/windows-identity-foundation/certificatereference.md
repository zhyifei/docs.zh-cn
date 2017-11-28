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
ms.openlocfilehash: c8acf4b6d6e6e8a0fcf7d73139a1d2c5ea03f063
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="ltcertificatereferencegt"></a><span data-ttu-id="91567-102">&lt;certificateReference&gt;</span><span class="sxs-lookup"><span data-stu-id="91567-102">&lt;certificateReference&gt;</span></span>
<span data-ttu-id="91567-103">指定用于查找和验证的证书存储区中的 X.509 证书的设置。</span><span class="sxs-lookup"><span data-stu-id="91567-103">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>  
  
 <span data-ttu-id="91567-104">\<system.identityModel.services ></span><span class="sxs-lookup"><span data-stu-id="91567-104">\<system.identityModel.services></span></span>  
<span data-ttu-id="91567-105">\<federationConfiguration ></span><span class="sxs-lookup"><span data-stu-id="91567-105">\<federationConfiguration></span></span>  
<span data-ttu-id="91567-106">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="91567-106">\<serviceCertificate></span></span>  
<span data-ttu-id="91567-107">\<certificateReference ></span><span class="sxs-lookup"><span data-stu-id="91567-107">\<certificateReference></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91567-108">语法</span><span class="sxs-lookup"><span data-stu-id="91567-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="91567-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="91567-109">Attributes and Elements</span></span>  
 <span data-ttu-id="91567-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="91567-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="91567-111">特性</span><span class="sxs-lookup"><span data-stu-id="91567-111">Attributes</span></span>  
  
|<span data-ttu-id="91567-112">特性</span><span class="sxs-lookup"><span data-stu-id="91567-112">Attribute</span></span>|<span data-ttu-id="91567-113">描述</span><span class="sxs-lookup"><span data-stu-id="91567-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="91567-114">storeName</span><span class="sxs-lookup"><span data-stu-id="91567-114">storeName</span></span>|<span data-ttu-id="91567-115">X.509 证书存储区的名称。</span><span class="sxs-lookup"><span data-stu-id="91567-115">The name of the X.509 certificate store.</span></span> <span data-ttu-id="91567-116">默认值为"My"。</span><span class="sxs-lookup"><span data-stu-id="91567-116">The default is "My".</span></span> <span data-ttu-id="91567-117">可选。</span><span class="sxs-lookup"><span data-stu-id="91567-117">Optional.</span></span>|  
|<span data-ttu-id="91567-118">storeLocation</span><span class="sxs-lookup"><span data-stu-id="91567-118">storeLocation</span></span>|<span data-ttu-id="91567-119">A<xref:System.Security.Cryptography.X509Certificates.StoreLocation>值，该值指定 X.509 证书存储区的位置。</span><span class="sxs-lookup"><span data-stu-id="91567-119">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the location of the X.509 certificate store.</span></span> <span data-ttu-id="91567-120">默认值为"LocalMachine"。</span><span class="sxs-lookup"><span data-stu-id="91567-120">The default value is "LocalMachine".</span></span> <span data-ttu-id="91567-121">可选。</span><span class="sxs-lookup"><span data-stu-id="91567-121">Optional.</span></span>|  
|<span data-ttu-id="91567-122">x509FindType</span><span class="sxs-lookup"><span data-stu-id="91567-122">x509FindType</span></span>|<span data-ttu-id="91567-123"><xref:System.Security.Cryptography.X509Certificates.X509FindType>值，该值指定是要执行的搜索的类型。</span><span class="sxs-lookup"><span data-stu-id="91567-123">An <xref:System.Security.Cryptography.X509Certificates.X509FindType> value that specifies the type of search that is to be executed.</span></span> <span data-ttu-id="91567-124">默认值为"FindBySubjectDistinguishedName"。</span><span class="sxs-lookup"><span data-stu-id="91567-124">The default is "FindBySubjectDistinguishedName".</span></span> <span data-ttu-id="91567-125">可选。</span><span class="sxs-lookup"><span data-stu-id="91567-125">Optional.</span></span>|  
|<span data-ttu-id="91567-126">findValue</span><span class="sxs-lookup"><span data-stu-id="91567-126">findValue</span></span>|<span data-ttu-id="91567-127">要在 X.509 证书存储区中搜索的值。</span><span class="sxs-lookup"><span data-stu-id="91567-127">The value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="91567-128">可选。</span><span class="sxs-lookup"><span data-stu-id="91567-128">Optional.</span></span>|  
|<span data-ttu-id="91567-129">isChainIncluded</span><span class="sxs-lookup"><span data-stu-id="91567-129">isChainIncluded</span></span>|<span data-ttu-id="91567-130">指定是否应执行验证通过使用证书链。</span><span class="sxs-lookup"><span data-stu-id="91567-130">Specifies whether validation should be performed by using the certificate chain.</span></span> <span data-ttu-id="91567-131">默认值为"true";通过使用证书链执行验证。</span><span class="sxs-lookup"><span data-stu-id="91567-131">The default is "true"; validation is performed by using the certificate chain.</span></span> <span data-ttu-id="91567-132">可选。</span><span class="sxs-lookup"><span data-stu-id="91567-132">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="91567-133">子元素</span><span class="sxs-lookup"><span data-stu-id="91567-133">Child Elements</span></span>  
 <span data-ttu-id="91567-134">无</span><span class="sxs-lookup"><span data-stu-id="91567-134">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="91567-135">父元素</span><span class="sxs-lookup"><span data-stu-id="91567-135">Parent Elements</span></span>  
  
|<span data-ttu-id="91567-136">元素</span><span class="sxs-lookup"><span data-stu-id="91567-136">Element</span></span>|<span data-ttu-id="91567-137">描述</span><span class="sxs-lookup"><span data-stu-id="91567-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="91567-138">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="91567-138">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicecertificate.md)|<span data-ttu-id="91567-139">配置用来加密和解密令牌的证书。</span><span class="sxs-lookup"><span data-stu-id="91567-139">Configures the certificate that is used to encrypt and decrypt tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="91567-140">备注</span><span class="sxs-lookup"><span data-stu-id="91567-140">Remarks</span></span>  
 <span data-ttu-id="91567-141">`<certificateReference>`元素指定用于查找和验证的证书存储区中的 X.509 证书的设置。</span><span class="sxs-lookup"><span data-stu-id="91567-141">The `<certificateReference>` element specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span> <span data-ttu-id="91567-142">当指定的子元素为`<serviceCertficate>`元素，它指定用于加密和解密令牌的 X.509 证书的位置和验证设置。</span><span class="sxs-lookup"><span data-stu-id="91567-142">When it is specified as the child element of the `<serviceCertficate>` element, it specifies the location and verification settings of the X.509 certificate that is used to encrypt and decrypt tokens.</span></span> <span data-ttu-id="91567-143">`<certificateReference>`元素表示由<xref:System.ServiceModel.Configuration.CertificateReferenceElement>类。</span><span class="sxs-lookup"><span data-stu-id="91567-143">The `<certificateReference>` element is represented by the <xref:System.ServiceModel.Configuration.CertificateReferenceElement> class.</span></span>
