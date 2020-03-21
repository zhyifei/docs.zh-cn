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
# <a name="certificatereference"></a>\<证书参考>
指定用于在证书存储中查找和验证 X.509 证书的设置。  
  
[**\<配置>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<系统.身份模型.服务>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<联合配置>**](federationconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<服务证书>**](servicecertificate.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<证书参考>**  
  
## <a name="syntax"></a>语法  
  
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
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>属性  
  
|Attribute|说明|  
|---------------|-----------------|  
|storeName|X.509 证书存储区的名称。 默认值为"我的"。 可选。|  
|storeLocation|指定<xref:System.Security.Cryptography.X509Certificates.StoreLocation>X.509 证书存储的位置的值。 默认值为"本地计算机"。 可选。|  
|x509FindType|指定<xref:System.Security.Cryptography.X509Certificates.X509FindType>要执行的搜索类型的值。 默认值为"查找主题分辨名称"。 可选。|  
|findValue|要在 X.509 证书存储区中搜索的值。 可选。|  
|isChainIncluded|指定是否应使用证书链执行验证。 默认值为"true";默认值为"true"，为"true"，为"true";为验证是使用证书链执行的。 可选。|  
  
### <a name="child-elements"></a>子元素  
 无  
  
### <a name="parent-elements"></a>父元素  
  
|元素|说明|  
|-------------|-----------------|  
|[\<服务证书>](servicecertificate.md)|配置用于加密和解密令牌的证书。|  
  
## <a name="remarks"></a>备注  
 该`<certificateReference>`元素指定用于在证书存储中查找和验证 X.509 证书的设置。 当它指定为`<serviceCertificate>`元素的子元素时，它指定用于加密和解密令牌的 X.509 证书的位置和验证设置。 元素`<certificateReference>`由类<xref:System.ServiceModel.Configuration.CertificateReferenceElement>表示。
