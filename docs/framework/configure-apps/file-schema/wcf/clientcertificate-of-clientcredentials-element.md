---
title: "&lt;clientCredentials&gt; 的 &lt;clientCertificate&gt; 元素"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3b3fa000-3434-4142-a178-11903bdd2c5d
caps.latest.revision: "14"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 961e745f15b4c7b7ae489a8b2b3128c1a64c6eab
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltclientcertificategt-of-ltclientcredentialsgt-element"></a>&lt;clientCredentials&gt; 的 &lt;clientCertificate&gt; 元素
定义用于针对服务进行客户端身份验证的 X.509 证书。  
  
 \<系统。ServiceModel >  
\<行为 >  
\<endpointBehaviors >  
\<行为 >  
\<c a t e >  
\<t i a l >  
  
## <a name="syntax"></a>语法  
  
```xml  
<clientCertificate findValue="String"   
    storeLocation="LocalMachine/CurrentUser"  
    storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"  
/>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 以下几节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|`findValue`|一个字符串，包含要在 X.509 证书存储中搜索的值。 此属性中包含的类型必须满足 `X509FindType` 属性值的要求。 默认值为一个空字符串。|  
|`storeLocation`|指定客户端用于向服务验证自身身份的 X.509 证书的位置。 包括以下有效值：<br /><br /> -LocalMachine： 分配给本地计算机的证书存储。<br />-CurrentUser： 分配给当前用户的证书存储。<br /><br /> 默认值为 LocalMachine。 此属性的类型为 <xref:System.Security.Cryptography.X509Certificates.StoreLocation>。|  
|`storeName`|指定要搜索的 X.509 证书存储的名称。 包括以下有效值：<br /><br /> -AddressBook： 其他用户证书存储区。<br />-AuthRoot： 证书存储第三方证书颁发机构 (Ca)。<br />-CertificateAuthority： 中间证书颁发机构 (Ca) 证书存储区。<br />-不允许： 证书吊销的证书存储。<br />-My： 个人证书的证书存储区。<br />-Root： 受信任的根证书颁发机构 (Ca) 证书存储区。<br />-TrustedPeople： 直接受信任的人和资源的证书存储区。<br />-TrustedPublisher： 直接受信任的发行者的证书存储区。<br /><br /> 默认值为 My。 此属性的类型为 <xref:System.Security.Cryptography.X509Certificates.StoreName>。|  
|X509FindType|定义要执行的 X.509 搜索的类型。 `findValue` 属性中包含的类型必须满足此属性的要求。 包括以下有效值：<br /><br /> -FindByThumbPrint<br />-FindBySubjectName<br />-FindBySubjectDistinguishedName<br />-FindByIssuerName<br />-FindByIssuerDistinguishedName<br />-FindBySerialNumber<br />-FindByTimeValid<br />-FindByTimeNotYetValid<br />-FindByTemplateName<br />-FindByApplicationPolicy<br />-FindByCertificatePolicy<br />-FindByExtension<br />-FindByKeyUsage<br />-和 FindBySubjectKeyIdentifier<br /><br /> 默认值为 FindBySubjectDistinguishedName。 此属性的类型为 <xref:System.Security.Cryptography.X509Certificates.X509FindType>。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<c a t e >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|指定用于向服务验证客户端身份的凭据。|  
  
## <a name="remarks"></a>备注  
 此配置元素指定用于对具有此元素的客户端进行身份验证的证书。 [!INCLUDE[crdefault](../../../../../includes/crdefault-md.md)][如何： 指定客户端凭据值](../../../../../docs/framework/wcf/how-to-specify-client-credential-values.md)。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement.ClientCertificate%2A>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Description.ClientCredentials.ClientCertificate%2A>  
 <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>  
 <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>  
 [安全行为](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [如何：指定客户端凭据值](../../../../../docs/framework/wcf/how-to-specify-client-credential-values.md)  
 [保护客户端](../../../../../docs/framework/wcf/securing-clients.md)  
 [使用证书](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [保护服务和客户端](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
