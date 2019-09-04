---
title: <certificateReference>
ms.date: 03/30/2017
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
author: BrucePerlerMS
ms.openlocfilehash: 782ca3344774b8412a18e3cf13bff5f969751ea3
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252146"
---
# <a name="certificatereference"></a><span data-ttu-id="7de3b-101">\<certificateReference></span><span class="sxs-lookup"><span data-stu-id="7de3b-101">\<certificateReference></span></span>
<span data-ttu-id="7de3b-102">指定用于在证书存储中查找和验证 x.509 证书的设置。</span><span class="sxs-lookup"><span data-stu-id="7de3b-102">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>  
  
<span data-ttu-id="7de3b-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="7de3b-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="7de3b-104">&nbsp;&nbsp;[ **\<System.identitymodel >** ](system-identitymodel-services.md)</span><span class="sxs-lookup"><span data-stu-id="7de3b-104">&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)</span></span>\
<span data-ttu-id="7de3b-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<federationConfiguration >** ](federationconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="7de3b-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)</span></span>\
<span data-ttu-id="7de3b-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceCertificate >** ](servicecertificate.md)</span><span class="sxs-lookup"><span data-stu-id="7de3b-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate.md)</span></span>\
<span data-ttu-id="7de3b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<certificateReference >**</span><span class="sxs-lookup"><span data-stu-id="7de3b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificateReference>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7de3b-108">语法</span><span class="sxs-lookup"><span data-stu-id="7de3b-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7de3b-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="7de3b-109">Attributes and Elements</span></span>  
 <span data-ttu-id="7de3b-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="7de3b-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7de3b-111">特性</span><span class="sxs-lookup"><span data-stu-id="7de3b-111">Attributes</span></span>  
  
|<span data-ttu-id="7de3b-112">特性</span><span class="sxs-lookup"><span data-stu-id="7de3b-112">Attribute</span></span>|<span data-ttu-id="7de3b-113">描述</span><span class="sxs-lookup"><span data-stu-id="7de3b-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7de3b-114">storeName</span><span class="sxs-lookup"><span data-stu-id="7de3b-114">storeName</span></span>|<span data-ttu-id="7de3b-115">X.509 证书存储的名称。</span><span class="sxs-lookup"><span data-stu-id="7de3b-115">The name of the X.509 certificate store.</span></span> <span data-ttu-id="7de3b-116">默认值为 "My"。</span><span class="sxs-lookup"><span data-stu-id="7de3b-116">The default is "My".</span></span> <span data-ttu-id="7de3b-117">可选。</span><span class="sxs-lookup"><span data-stu-id="7de3b-117">Optional.</span></span>|  
|<span data-ttu-id="7de3b-118">storeLocation</span><span class="sxs-lookup"><span data-stu-id="7de3b-118">storeLocation</span></span>|<span data-ttu-id="7de3b-119">一个<xref:System.Security.Cryptography.X509Certificates.StoreLocation>值，该值指定 x.509 证书存储区的位置。</span><span class="sxs-lookup"><span data-stu-id="7de3b-119">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the location of the X.509 certificate store.</span></span> <span data-ttu-id="7de3b-120">默认值为 "LocalMachine"。</span><span class="sxs-lookup"><span data-stu-id="7de3b-120">The default value is "LocalMachine".</span></span> <span data-ttu-id="7de3b-121">可选。</span><span class="sxs-lookup"><span data-stu-id="7de3b-121">Optional.</span></span>|  
|<span data-ttu-id="7de3b-122">x509FindType</span><span class="sxs-lookup"><span data-stu-id="7de3b-122">x509FindType</span></span>|<span data-ttu-id="7de3b-123">一个<xref:System.Security.Cryptography.X509Certificates.X509FindType>值，该值指定要执行的搜索的类型。</span><span class="sxs-lookup"><span data-stu-id="7de3b-123">An <xref:System.Security.Cryptography.X509Certificates.X509FindType> value that specifies the type of search that is to be executed.</span></span> <span data-ttu-id="7de3b-124">默认值为 "FindBySubjectDistinguishedName"。</span><span class="sxs-lookup"><span data-stu-id="7de3b-124">The default is "FindBySubjectDistinguishedName".</span></span> <span data-ttu-id="7de3b-125">可选。</span><span class="sxs-lookup"><span data-stu-id="7de3b-125">Optional.</span></span>|  
|<span data-ttu-id="7de3b-126">findValue</span><span class="sxs-lookup"><span data-stu-id="7de3b-126">findValue</span></span>|<span data-ttu-id="7de3b-127">要在 X.509 证书存储区中搜索的值。</span><span class="sxs-lookup"><span data-stu-id="7de3b-127">The value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="7de3b-128">可选。</span><span class="sxs-lookup"><span data-stu-id="7de3b-128">Optional.</span></span>|  
|<span data-ttu-id="7de3b-129">isChainIncluded</span><span class="sxs-lookup"><span data-stu-id="7de3b-129">isChainIncluded</span></span>|<span data-ttu-id="7de3b-130">指定是否应通过使用证书链来执行验证。</span><span class="sxs-lookup"><span data-stu-id="7de3b-130">Specifies whether validation should be performed by using the certificate chain.</span></span> <span data-ttu-id="7de3b-131">默认值为 "true";验证是通过使用证书链来执行的。</span><span class="sxs-lookup"><span data-stu-id="7de3b-131">The default is "true"; validation is performed by using the certificate chain.</span></span> <span data-ttu-id="7de3b-132">可选。</span><span class="sxs-lookup"><span data-stu-id="7de3b-132">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7de3b-133">子元素</span><span class="sxs-lookup"><span data-stu-id="7de3b-133">Child Elements</span></span>  
 <span data-ttu-id="7de3b-134">无</span><span class="sxs-lookup"><span data-stu-id="7de3b-134">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7de3b-135">父元素</span><span class="sxs-lookup"><span data-stu-id="7de3b-135">Parent Elements</span></span>  
  
|<span data-ttu-id="7de3b-136">元素</span><span class="sxs-lookup"><span data-stu-id="7de3b-136">Element</span></span>|<span data-ttu-id="7de3b-137">描述</span><span class="sxs-lookup"><span data-stu-id="7de3b-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7de3b-138">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="7de3b-138">\<serviceCertificate></span></span>](servicecertificate.md)|<span data-ttu-id="7de3b-139">配置用于加密和解密令牌的证书。</span><span class="sxs-lookup"><span data-stu-id="7de3b-139">Configures the certificate that is used to encrypt and decrypt tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7de3b-140">备注</span><span class="sxs-lookup"><span data-stu-id="7de3b-140">Remarks</span></span>  
 <span data-ttu-id="7de3b-141">`<certificateReference>`元素指定用于在证书存储区中查找和验证 x.509 证书的设置。</span><span class="sxs-lookup"><span data-stu-id="7de3b-141">The `<certificateReference>` element specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span> <span data-ttu-id="7de3b-142">指定为`<serviceCertificate>`元素的子元素时，它将指定用于加密和解密令牌的 x.509 证书的位置和验证设置。</span><span class="sxs-lookup"><span data-stu-id="7de3b-142">When it is specified as the child element of the `<serviceCertificate>` element, it specifies the location and verification settings of the X.509 certificate that is used to encrypt and decrypt tokens.</span></span> <span data-ttu-id="7de3b-143">元素由<xref:System.ServiceModel.Configuration.CertificateReferenceElement>类表示。 `<certificateReference>`</span><span class="sxs-lookup"><span data-stu-id="7de3b-143">The `<certificateReference>` element is represented by the <xref:System.ServiceModel.Configuration.CertificateReferenceElement> class.</span></span>
