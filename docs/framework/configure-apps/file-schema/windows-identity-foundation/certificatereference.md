---
title: <certificateReference>
ms.date: 03/30/2017
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
author: BrucePerlerMS
ms.openlocfilehash: 47d432a84d070476ddffd9b98a4ba46d8163bdc3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152809"
---
# <a name="certificatereference"></a><span data-ttu-id="b8f6a-101">\<证书参考></span><span class="sxs-lookup"><span data-stu-id="b8f6a-101">\<certificateReference></span></span>
<span data-ttu-id="b8f6a-102">指定用于在证书存储中查找和验证 X.509 证书的设置。</span><span class="sxs-lookup"><span data-stu-id="b8f6a-102">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>  
  
<span data-ttu-id="b8f6a-103">[**\<配置>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b8f6a-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b8f6a-104">&nbsp;&nbsp;[**\<系统.身份模型.服务>**](system-identitymodel-services.md)</span><span class="sxs-lookup"><span data-stu-id="b8f6a-104">&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)</span></span>\
<span data-ttu-id="b8f6a-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<联合配置>**](federationconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="b8f6a-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)</span></span>\
<span data-ttu-id="b8f6a-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<服务证书>**](servicecertificate.md)</span><span class="sxs-lookup"><span data-stu-id="b8f6a-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate.md)</span></span>\
<span data-ttu-id="b8f6a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<证书参考>**</span><span class="sxs-lookup"><span data-stu-id="b8f6a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificateReference>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8f6a-108">语法</span><span class="sxs-lookup"><span data-stu-id="b8f6a-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b8f6a-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="b8f6a-109">Attributes and Elements</span></span>  
 <span data-ttu-id="b8f6a-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="b8f6a-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b8f6a-111">属性</span><span class="sxs-lookup"><span data-stu-id="b8f6a-111">Attributes</span></span>  
  
|<span data-ttu-id="b8f6a-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="b8f6a-112">Attribute</span></span>|<span data-ttu-id="b8f6a-113">说明</span><span class="sxs-lookup"><span data-stu-id="b8f6a-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b8f6a-114">storeName</span><span class="sxs-lookup"><span data-stu-id="b8f6a-114">storeName</span></span>|<span data-ttu-id="b8f6a-115">X.509 证书存储区的名称。</span><span class="sxs-lookup"><span data-stu-id="b8f6a-115">The name of the X.509 certificate store.</span></span> <span data-ttu-id="b8f6a-116">默认值为"我的"。</span><span class="sxs-lookup"><span data-stu-id="b8f6a-116">The default is "My".</span></span> <span data-ttu-id="b8f6a-117">可选。</span><span class="sxs-lookup"><span data-stu-id="b8f6a-117">Optional.</span></span>|  
|<span data-ttu-id="b8f6a-118">storeLocation</span><span class="sxs-lookup"><span data-stu-id="b8f6a-118">storeLocation</span></span>|<span data-ttu-id="b8f6a-119">指定<xref:System.Security.Cryptography.X509Certificates.StoreLocation>X.509 证书存储的位置的值。</span><span class="sxs-lookup"><span data-stu-id="b8f6a-119">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the location of the X.509 certificate store.</span></span> <span data-ttu-id="b8f6a-120">默认值为"本地计算机"。</span><span class="sxs-lookup"><span data-stu-id="b8f6a-120">The default value is "LocalMachine".</span></span> <span data-ttu-id="b8f6a-121">可选。</span><span class="sxs-lookup"><span data-stu-id="b8f6a-121">Optional.</span></span>|  
|<span data-ttu-id="b8f6a-122">x509FindType</span><span class="sxs-lookup"><span data-stu-id="b8f6a-122">x509FindType</span></span>|<span data-ttu-id="b8f6a-123">指定<xref:System.Security.Cryptography.X509Certificates.X509FindType>要执行的搜索类型的值。</span><span class="sxs-lookup"><span data-stu-id="b8f6a-123">An <xref:System.Security.Cryptography.X509Certificates.X509FindType> value that specifies the type of search that is to be executed.</span></span> <span data-ttu-id="b8f6a-124">默认值为"查找主题分辨名称"。</span><span class="sxs-lookup"><span data-stu-id="b8f6a-124">The default is "FindBySubjectDistinguishedName".</span></span> <span data-ttu-id="b8f6a-125">可选。</span><span class="sxs-lookup"><span data-stu-id="b8f6a-125">Optional.</span></span>|  
|<span data-ttu-id="b8f6a-126">findValue</span><span class="sxs-lookup"><span data-stu-id="b8f6a-126">findValue</span></span>|<span data-ttu-id="b8f6a-127">要在 X.509 证书存储区中搜索的值。</span><span class="sxs-lookup"><span data-stu-id="b8f6a-127">The value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="b8f6a-128">可选。</span><span class="sxs-lookup"><span data-stu-id="b8f6a-128">Optional.</span></span>|  
|<span data-ttu-id="b8f6a-129">isChainIncluded</span><span class="sxs-lookup"><span data-stu-id="b8f6a-129">isChainIncluded</span></span>|<span data-ttu-id="b8f6a-130">指定是否应使用证书链执行验证。</span><span class="sxs-lookup"><span data-stu-id="b8f6a-130">Specifies whether validation should be performed by using the certificate chain.</span></span> <span data-ttu-id="b8f6a-131">默认值为"true";默认值为"true"，为"true"，为"true";为验证是使用证书链执行的。</span><span class="sxs-lookup"><span data-stu-id="b8f6a-131">The default is "true"; validation is performed by using the certificate chain.</span></span> <span data-ttu-id="b8f6a-132">可选。</span><span class="sxs-lookup"><span data-stu-id="b8f6a-132">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b8f6a-133">子元素</span><span class="sxs-lookup"><span data-stu-id="b8f6a-133">Child Elements</span></span>  
 <span data-ttu-id="b8f6a-134">无</span><span class="sxs-lookup"><span data-stu-id="b8f6a-134">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b8f6a-135">父元素</span><span class="sxs-lookup"><span data-stu-id="b8f6a-135">Parent Elements</span></span>  
  
|<span data-ttu-id="b8f6a-136">元素</span><span class="sxs-lookup"><span data-stu-id="b8f6a-136">Element</span></span>|<span data-ttu-id="b8f6a-137">说明</span><span class="sxs-lookup"><span data-stu-id="b8f6a-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b8f6a-138">\<服务证书></span><span class="sxs-lookup"><span data-stu-id="b8f6a-138">\<serviceCertificate></span></span>](servicecertificate.md)|<span data-ttu-id="b8f6a-139">配置用于加密和解密令牌的证书。</span><span class="sxs-lookup"><span data-stu-id="b8f6a-139">Configures the certificate that is used to encrypt and decrypt tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b8f6a-140">备注</span><span class="sxs-lookup"><span data-stu-id="b8f6a-140">Remarks</span></span>  
 <span data-ttu-id="b8f6a-141">该`<certificateReference>`元素指定用于在证书存储中查找和验证 X.509 证书的设置。</span><span class="sxs-lookup"><span data-stu-id="b8f6a-141">The `<certificateReference>` element specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span> <span data-ttu-id="b8f6a-142">当它指定为`<serviceCertificate>`元素的子元素时，它指定用于加密和解密令牌的 X.509 证书的位置和验证设置。</span><span class="sxs-lookup"><span data-stu-id="b8f6a-142">When it is specified as the child element of the `<serviceCertificate>` element, it specifies the location and verification settings of the X.509 certificate that is used to encrypt and decrypt tokens.</span></span> <span data-ttu-id="b8f6a-143">元素`<certificateReference>`由类<xref:System.ServiceModel.Configuration.CertificateReferenceElement>表示。</span><span class="sxs-lookup"><span data-stu-id="b8f6a-143">The `<certificateReference>` element is represented by the <xref:System.ServiceModel.Configuration.CertificateReferenceElement> class.</span></span>
