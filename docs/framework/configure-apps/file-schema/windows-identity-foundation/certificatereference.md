---
title: <certificateReference>
ms.date: 03/30/2017
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
author: BrucePerlerMS
ms.openlocfilehash: da8ea128466457409334cd0b4ee3246a923f969a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69941935"
---
# <a name="certificatereference"></a><span data-ttu-id="8160d-101">\<certificateReference></span><span class="sxs-lookup"><span data-stu-id="8160d-101">\<certificateReference></span></span>
<span data-ttu-id="8160d-102">指定用于在证书存储中查找和验证 x.509 证书的设置。</span><span class="sxs-lookup"><span data-stu-id="8160d-102">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>  
  
 <span data-ttu-id="8160d-103">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="8160d-103">\<system.identityModel.services></span></span>  
<span data-ttu-id="8160d-104">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="8160d-104">\<federationConfiguration></span></span>  
<span data-ttu-id="8160d-105">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="8160d-105">\<serviceCertificate></span></span>  
<span data-ttu-id="8160d-106">\<certificateReference></span><span class="sxs-lookup"><span data-stu-id="8160d-106">\<certificateReference></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8160d-107">语法</span><span class="sxs-lookup"><span data-stu-id="8160d-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8160d-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="8160d-108">Attributes and Elements</span></span>  
 <span data-ttu-id="8160d-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="8160d-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8160d-110">特性</span><span class="sxs-lookup"><span data-stu-id="8160d-110">Attributes</span></span>  
  
|<span data-ttu-id="8160d-111">特性</span><span class="sxs-lookup"><span data-stu-id="8160d-111">Attribute</span></span>|<span data-ttu-id="8160d-112">描述</span><span class="sxs-lookup"><span data-stu-id="8160d-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8160d-113">storeName</span><span class="sxs-lookup"><span data-stu-id="8160d-113">storeName</span></span>|<span data-ttu-id="8160d-114">X.509 证书存储的名称。</span><span class="sxs-lookup"><span data-stu-id="8160d-114">The name of the X.509 certificate store.</span></span> <span data-ttu-id="8160d-115">默认值为 "My"。</span><span class="sxs-lookup"><span data-stu-id="8160d-115">The default is "My".</span></span> <span data-ttu-id="8160d-116">可选。</span><span class="sxs-lookup"><span data-stu-id="8160d-116">Optional.</span></span>|  
|<span data-ttu-id="8160d-117">storeLocation</span><span class="sxs-lookup"><span data-stu-id="8160d-117">storeLocation</span></span>|<span data-ttu-id="8160d-118">一个<xref:System.Security.Cryptography.X509Certificates.StoreLocation>值, 该值指定 x.509 证书存储区的位置。</span><span class="sxs-lookup"><span data-stu-id="8160d-118">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the location of the X.509 certificate store.</span></span> <span data-ttu-id="8160d-119">默认值为 "LocalMachine"。</span><span class="sxs-lookup"><span data-stu-id="8160d-119">The default value is "LocalMachine".</span></span> <span data-ttu-id="8160d-120">可选。</span><span class="sxs-lookup"><span data-stu-id="8160d-120">Optional.</span></span>|  
|<span data-ttu-id="8160d-121">x509FindType</span><span class="sxs-lookup"><span data-stu-id="8160d-121">x509FindType</span></span>|<span data-ttu-id="8160d-122">一个<xref:System.Security.Cryptography.X509Certificates.X509FindType>值, 该值指定要执行的搜索的类型。</span><span class="sxs-lookup"><span data-stu-id="8160d-122">An <xref:System.Security.Cryptography.X509Certificates.X509FindType> value that specifies the type of search that is to be executed.</span></span> <span data-ttu-id="8160d-123">默认值为 "FindBySubjectDistinguishedName"。</span><span class="sxs-lookup"><span data-stu-id="8160d-123">The default is "FindBySubjectDistinguishedName".</span></span> <span data-ttu-id="8160d-124">可选。</span><span class="sxs-lookup"><span data-stu-id="8160d-124">Optional.</span></span>|  
|<span data-ttu-id="8160d-125">findValue</span><span class="sxs-lookup"><span data-stu-id="8160d-125">findValue</span></span>|<span data-ttu-id="8160d-126">要在 X.509 证书存储区中搜索的值。</span><span class="sxs-lookup"><span data-stu-id="8160d-126">The value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="8160d-127">可选。</span><span class="sxs-lookup"><span data-stu-id="8160d-127">Optional.</span></span>|  
|<span data-ttu-id="8160d-128">isChainIncluded</span><span class="sxs-lookup"><span data-stu-id="8160d-128">isChainIncluded</span></span>|<span data-ttu-id="8160d-129">指定是否应通过使用证书链来执行验证。</span><span class="sxs-lookup"><span data-stu-id="8160d-129">Specifies whether validation should be performed by using the certificate chain.</span></span> <span data-ttu-id="8160d-130">默认值为 "true";验证是通过使用证书链来执行的。</span><span class="sxs-lookup"><span data-stu-id="8160d-130">The default is "true"; validation is performed by using the certificate chain.</span></span> <span data-ttu-id="8160d-131">可选。</span><span class="sxs-lookup"><span data-stu-id="8160d-131">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8160d-132">子元素</span><span class="sxs-lookup"><span data-stu-id="8160d-132">Child Elements</span></span>  
 <span data-ttu-id="8160d-133">无</span><span class="sxs-lookup"><span data-stu-id="8160d-133">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8160d-134">父元素</span><span class="sxs-lookup"><span data-stu-id="8160d-134">Parent Elements</span></span>  
  
|<span data-ttu-id="8160d-135">元素</span><span class="sxs-lookup"><span data-stu-id="8160d-135">Element</span></span>|<span data-ttu-id="8160d-136">描述</span><span class="sxs-lookup"><span data-stu-id="8160d-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8160d-137">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="8160d-137">\<serviceCertificate></span></span>](servicecertificate.md)|<span data-ttu-id="8160d-138">配置用于加密和解密令牌的证书。</span><span class="sxs-lookup"><span data-stu-id="8160d-138">Configures the certificate that is used to encrypt and decrypt tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8160d-139">备注</span><span class="sxs-lookup"><span data-stu-id="8160d-139">Remarks</span></span>  
 <span data-ttu-id="8160d-140">`<certificateReference>`元素指定用于在证书存储区中查找和验证 x.509 证书的设置。</span><span class="sxs-lookup"><span data-stu-id="8160d-140">The `<certificateReference>` element specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span> <span data-ttu-id="8160d-141">指定为`<serviceCertificate>`元素的子元素时, 它将指定用于加密和解密令牌的 x.509 证书的位置和验证设置。</span><span class="sxs-lookup"><span data-stu-id="8160d-141">When it is specified as the child element of the `<serviceCertificate>` element, it specifies the location and verification settings of the X.509 certificate that is used to encrypt and decrypt tokens.</span></span> <span data-ttu-id="8160d-142">元素由<xref:System.ServiceModel.Configuration.CertificateReferenceElement>类表示。 `<certificateReference>`</span><span class="sxs-lookup"><span data-stu-id="8160d-142">The `<certificateReference>` element is represented by the <xref:System.ServiceModel.Configuration.CertificateReferenceElement> class.</span></span>
