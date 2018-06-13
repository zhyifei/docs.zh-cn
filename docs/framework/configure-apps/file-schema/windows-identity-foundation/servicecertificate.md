---
title: '&lt;serviceCertificate&gt;'
ms.date: 03/30/2017
ms.assetid: 42c7f291-2ec3-43c5-8872-35897ff3c660
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: af59562dbf6c13970526f1665a9ba2c57c4f32ee
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32766772"
---
# <a name="ltservicecertificategt"></a>&lt;serviceCertificate&gt;
配置用于加密和解密令牌的 X.509 证书。  
  
 \<system.identityModel.services >  
\<federationConfiguration >  
\<serviceCertificate >  
  
## <a name="syntax"></a>语法  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <serviceCertificate>  
    </serviceCertificate>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
 无  
  
### <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<certificateReference >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatereference.md)|指定用于查找和验证的证书存储区中的 X.509 证书的设置。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<federationConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|包含配置的设置<xref:System.IdentityModel.Services.WSFederationAuthenticationModule>(WSFAM) 和<xref:System.IdentityModel.Services.SessionAuthenticationModule>(SAM)。|  
  
## <a name="example"></a>示例  
 下面的 XML 演示如何使用\<serviceCertificate > 元素。 XML 取自`CustomToken`示例。  
  
```xml  
<serviceCertificate>  
  <certificateReference x509FindType="FindBySubjectName" findValue="localhost" storeLocation="LocalMachine" storeName="My"/>  
</serviceCertificate>  
```
