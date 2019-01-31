---
title: <certificateReference>
ms.date: 03/30/2017
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
author: BrucePerlerMS
ms.openlocfilehash: 6c9c77f96ff6032de43d9b5a257bc0796a19b858
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55269336"
---
# <a name="certificatereference"></a><span data-ttu-id="d9144-101">\<certificateReference></span><span class="sxs-lookup"><span data-stu-id="d9144-101">\<certificateReference></span></span>
<span data-ttu-id="d9144-102">指定用于查找和验证的证书存储区中的 X.509 证书的设置。</span><span class="sxs-lookup"><span data-stu-id="d9144-102">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>  
  
 <span data-ttu-id="d9144-103">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="d9144-103">\<system.identityModel.services></span></span>  
<span data-ttu-id="d9144-104">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="d9144-104">\<federationConfiguration></span></span>  
<span data-ttu-id="d9144-105">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="d9144-105">\<serviceCertificate></span></span>  
<span data-ttu-id="d9144-106">\<certificateReference></span><span class="sxs-lookup"><span data-stu-id="d9144-106">\<certificateReference></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9144-107">语法</span><span class="sxs-lookup"><span data-stu-id="d9144-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d9144-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d9144-108">Attributes and Elements</span></span>  
 <span data-ttu-id="d9144-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="d9144-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d9144-110">特性</span><span class="sxs-lookup"><span data-stu-id="d9144-110">Attributes</span></span>  
  
|<span data-ttu-id="d9144-111">特性</span><span class="sxs-lookup"><span data-stu-id="d9144-111">Attribute</span></span>|<span data-ttu-id="d9144-112">描述</span><span class="sxs-lookup"><span data-stu-id="d9144-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d9144-113">storeName</span><span class="sxs-lookup"><span data-stu-id="d9144-113">storeName</span></span>|<span data-ttu-id="d9144-114">X.509 证书存储区的名称。</span><span class="sxs-lookup"><span data-stu-id="d9144-114">The name of the X.509 certificate store.</span></span> <span data-ttu-id="d9144-115">默认值为"My"。</span><span class="sxs-lookup"><span data-stu-id="d9144-115">The default is "My".</span></span> <span data-ttu-id="d9144-116">可选。</span><span class="sxs-lookup"><span data-stu-id="d9144-116">Optional.</span></span>|  
|<span data-ttu-id="d9144-117">storeLocation</span><span class="sxs-lookup"><span data-stu-id="d9144-117">storeLocation</span></span>|<span data-ttu-id="d9144-118">一个<xref:System.Security.Cryptography.X509Certificates.StoreLocation>值，该值指定的 X.509 证书存储区位置。</span><span class="sxs-lookup"><span data-stu-id="d9144-118">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the location of the X.509 certificate store.</span></span> <span data-ttu-id="d9144-119">默认值为"LocalMachine"。</span><span class="sxs-lookup"><span data-stu-id="d9144-119">The default value is "LocalMachine".</span></span> <span data-ttu-id="d9144-120">可选。</span><span class="sxs-lookup"><span data-stu-id="d9144-120">Optional.</span></span>|  
|<span data-ttu-id="d9144-121">x509FindType</span><span class="sxs-lookup"><span data-stu-id="d9144-121">x509FindType</span></span>|<span data-ttu-id="d9144-122"><xref:System.Security.Cryptography.X509Certificates.X509FindType>值，该值指定要执行的搜索的类型。</span><span class="sxs-lookup"><span data-stu-id="d9144-122">An <xref:System.Security.Cryptography.X509Certificates.X509FindType> value that specifies the type of search that is to be executed.</span></span> <span data-ttu-id="d9144-123">默认值是"FindBySubjectDistinguishedName"。</span><span class="sxs-lookup"><span data-stu-id="d9144-123">The default is "FindBySubjectDistinguishedName".</span></span> <span data-ttu-id="d9144-124">可选。</span><span class="sxs-lookup"><span data-stu-id="d9144-124">Optional.</span></span>|  
|<span data-ttu-id="d9144-125">findValue</span><span class="sxs-lookup"><span data-stu-id="d9144-125">findValue</span></span>|<span data-ttu-id="d9144-126">要在 X.509 证书存储区中搜索的值。</span><span class="sxs-lookup"><span data-stu-id="d9144-126">The value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="d9144-127">可选。</span><span class="sxs-lookup"><span data-stu-id="d9144-127">Optional.</span></span>|  
|<span data-ttu-id="d9144-128">isChainIncluded</span><span class="sxs-lookup"><span data-stu-id="d9144-128">isChainIncluded</span></span>|<span data-ttu-id="d9144-129">指定是否应使用的证书链执行验证。</span><span class="sxs-lookup"><span data-stu-id="d9144-129">Specifies whether validation should be performed by using the certificate chain.</span></span> <span data-ttu-id="d9144-130">默认值为"true";通过使用证书链执行验证。</span><span class="sxs-lookup"><span data-stu-id="d9144-130">The default is "true"; validation is performed by using the certificate chain.</span></span> <span data-ttu-id="d9144-131">可选。</span><span class="sxs-lookup"><span data-stu-id="d9144-131">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d9144-132">子元素</span><span class="sxs-lookup"><span data-stu-id="d9144-132">Child Elements</span></span>  
 <span data-ttu-id="d9144-133">无</span><span class="sxs-lookup"><span data-stu-id="d9144-133">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d9144-134">父元素</span><span class="sxs-lookup"><span data-stu-id="d9144-134">Parent Elements</span></span>  
  
|<span data-ttu-id="d9144-135">元素</span><span class="sxs-lookup"><span data-stu-id="d9144-135">Element</span></span>|<span data-ttu-id="d9144-136">描述</span><span class="sxs-lookup"><span data-stu-id="d9144-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d9144-137">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="d9144-137">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicecertificate.md)|<span data-ttu-id="d9144-138">配置用于加密和解密令牌的证书。</span><span class="sxs-lookup"><span data-stu-id="d9144-138">Configures the certificate that is used to encrypt and decrypt tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d9144-139">备注</span><span class="sxs-lookup"><span data-stu-id="d9144-139">Remarks</span></span>  
 <span data-ttu-id="d9144-140">`<certificateReference>`元素指定用于查找和验证的证书存储区中的 X.509 证书的设置。</span><span class="sxs-lookup"><span data-stu-id="d9144-140">The `<certificateReference>` element specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span> <span data-ttu-id="d9144-141">当指定的子元素为`<serviceCertficate>`元素，它指定用于加密和解密令牌的 X.509 证书的位置和验证设置。</span><span class="sxs-lookup"><span data-stu-id="d9144-141">When it is specified as the child element of the `<serviceCertficate>` element, it specifies the location and verification settings of the X.509 certificate that is used to encrypt and decrypt tokens.</span></span> <span data-ttu-id="d9144-142">`<certificateReference>`元素表示由<xref:System.ServiceModel.Configuration.CertificateReferenceElement>类。</span><span class="sxs-lookup"><span data-stu-id="d9144-142">The `<certificateReference>` element is represented by the <xref:System.ServiceModel.Configuration.CertificateReferenceElement> class.</span></span>
