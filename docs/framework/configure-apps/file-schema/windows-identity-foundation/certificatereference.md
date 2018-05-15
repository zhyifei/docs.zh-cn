---
title: '&lt;certificateReference&gt;'
ms.date: 03/30/2017
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: e0f9a826a4c8d292346d9efee7970a82b88fb612
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltcertificatereferencegt"></a><span data-ttu-id="7cbde-102">&lt;certificateReference&gt;</span><span class="sxs-lookup"><span data-stu-id="7cbde-102">&lt;certificateReference&gt;</span></span>
<span data-ttu-id="7cbde-103">指定用于查找和验证的证书存储区中的 X.509 证书的设置。</span><span class="sxs-lookup"><span data-stu-id="7cbde-103">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>  
  
 <span data-ttu-id="7cbde-104">\<system.identityModel.services ></span><span class="sxs-lookup"><span data-stu-id="7cbde-104">\<system.identityModel.services></span></span>  
<span data-ttu-id="7cbde-105">\<federationConfiguration ></span><span class="sxs-lookup"><span data-stu-id="7cbde-105">\<federationConfiguration></span></span>  
<span data-ttu-id="7cbde-106">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="7cbde-106">\<serviceCertificate></span></span>  
<span data-ttu-id="7cbde-107">\<certificateReference ></span><span class="sxs-lookup"><span data-stu-id="7cbde-107">\<certificateReference></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7cbde-108">语法</span><span class="sxs-lookup"><span data-stu-id="7cbde-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7cbde-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="7cbde-109">Attributes and Elements</span></span>  
 <span data-ttu-id="7cbde-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="7cbde-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7cbde-111">特性</span><span class="sxs-lookup"><span data-stu-id="7cbde-111">Attributes</span></span>  
  
|<span data-ttu-id="7cbde-112">特性</span><span class="sxs-lookup"><span data-stu-id="7cbde-112">Attribute</span></span>|<span data-ttu-id="7cbde-113">描述</span><span class="sxs-lookup"><span data-stu-id="7cbde-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7cbde-114">storeName</span><span class="sxs-lookup"><span data-stu-id="7cbde-114">storeName</span></span>|<span data-ttu-id="7cbde-115">X.509 证书存储区的名称。</span><span class="sxs-lookup"><span data-stu-id="7cbde-115">The name of the X.509 certificate store.</span></span> <span data-ttu-id="7cbde-116">默认值为"My"。</span><span class="sxs-lookup"><span data-stu-id="7cbde-116">The default is "My".</span></span> <span data-ttu-id="7cbde-117">可选。</span><span class="sxs-lookup"><span data-stu-id="7cbde-117">Optional.</span></span>|  
|<span data-ttu-id="7cbde-118">storeLocation</span><span class="sxs-lookup"><span data-stu-id="7cbde-118">storeLocation</span></span>|<span data-ttu-id="7cbde-119">A<xref:System.Security.Cryptography.X509Certificates.StoreLocation>值，该值指定 X.509 证书存储区的位置。</span><span class="sxs-lookup"><span data-stu-id="7cbde-119">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the location of the X.509 certificate store.</span></span> <span data-ttu-id="7cbde-120">默认值为"LocalMachine"。</span><span class="sxs-lookup"><span data-stu-id="7cbde-120">The default value is "LocalMachine".</span></span> <span data-ttu-id="7cbde-121">可选。</span><span class="sxs-lookup"><span data-stu-id="7cbde-121">Optional.</span></span>|  
|<span data-ttu-id="7cbde-122">x509FindType</span><span class="sxs-lookup"><span data-stu-id="7cbde-122">x509FindType</span></span>|<span data-ttu-id="7cbde-123"><xref:System.Security.Cryptography.X509Certificates.X509FindType>值，该值指定是要执行的搜索的类型。</span><span class="sxs-lookup"><span data-stu-id="7cbde-123">An <xref:System.Security.Cryptography.X509Certificates.X509FindType> value that specifies the type of search that is to be executed.</span></span> <span data-ttu-id="7cbde-124">默认值为"FindBySubjectDistinguishedName"。</span><span class="sxs-lookup"><span data-stu-id="7cbde-124">The default is "FindBySubjectDistinguishedName".</span></span> <span data-ttu-id="7cbde-125">可选。</span><span class="sxs-lookup"><span data-stu-id="7cbde-125">Optional.</span></span>|  
|<span data-ttu-id="7cbde-126">findValue</span><span class="sxs-lookup"><span data-stu-id="7cbde-126">findValue</span></span>|<span data-ttu-id="7cbde-127">要在 X.509 证书存储区中搜索的值。</span><span class="sxs-lookup"><span data-stu-id="7cbde-127">The value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="7cbde-128">可选。</span><span class="sxs-lookup"><span data-stu-id="7cbde-128">Optional.</span></span>|  
|<span data-ttu-id="7cbde-129">isChainIncluded</span><span class="sxs-lookup"><span data-stu-id="7cbde-129">isChainIncluded</span></span>|<span data-ttu-id="7cbde-130">指定是否应执行验证通过使用证书链。</span><span class="sxs-lookup"><span data-stu-id="7cbde-130">Specifies whether validation should be performed by using the certificate chain.</span></span> <span data-ttu-id="7cbde-131">默认值为"true";通过使用证书链执行验证。</span><span class="sxs-lookup"><span data-stu-id="7cbde-131">The default is "true"; validation is performed by using the certificate chain.</span></span> <span data-ttu-id="7cbde-132">可选。</span><span class="sxs-lookup"><span data-stu-id="7cbde-132">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7cbde-133">子元素</span><span class="sxs-lookup"><span data-stu-id="7cbde-133">Child Elements</span></span>  
 <span data-ttu-id="7cbde-134">无</span><span class="sxs-lookup"><span data-stu-id="7cbde-134">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7cbde-135">父元素</span><span class="sxs-lookup"><span data-stu-id="7cbde-135">Parent Elements</span></span>  
  
|<span data-ttu-id="7cbde-136">元素</span><span class="sxs-lookup"><span data-stu-id="7cbde-136">Element</span></span>|<span data-ttu-id="7cbde-137">描述</span><span class="sxs-lookup"><span data-stu-id="7cbde-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7cbde-138">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="7cbde-138">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicecertificate.md)|<span data-ttu-id="7cbde-139">配置用来加密和解密令牌的证书。</span><span class="sxs-lookup"><span data-stu-id="7cbde-139">Configures the certificate that is used to encrypt and decrypt tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7cbde-140">备注</span><span class="sxs-lookup"><span data-stu-id="7cbde-140">Remarks</span></span>  
 <span data-ttu-id="7cbde-141">`<certificateReference>`元素指定用于查找和验证的证书存储区中的 X.509 证书的设置。</span><span class="sxs-lookup"><span data-stu-id="7cbde-141">The `<certificateReference>` element specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span> <span data-ttu-id="7cbde-142">当指定的子元素为`<serviceCertficate>`元素，它指定用于加密和解密令牌的 X.509 证书的位置和验证设置。</span><span class="sxs-lookup"><span data-stu-id="7cbde-142">When it is specified as the child element of the `<serviceCertficate>` element, it specifies the location and verification settings of the X.509 certificate that is used to encrypt and decrypt tokens.</span></span> <span data-ttu-id="7cbde-143">`<certificateReference>`元素表示由<xref:System.ServiceModel.Configuration.CertificateReferenceElement>类。</span><span class="sxs-lookup"><span data-stu-id="7cbde-143">The `<certificateReference>` element is represented by the <xref:System.ServiceModel.Configuration.CertificateReferenceElement> class.</span></span>
