---
title: '&lt;certificateValidator&gt;'
ms.date: 03/30/2017
ms.assetid: 86161897-c20f-4ad8-9d7f-050c247251bf
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: a4663b0c3a2a6965a977a1d551c47de7e13d144b
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32766889"
---
# <a name="ltcertificatevalidatorgt"></a>&lt;certificateValidator&gt;
指定证书验证的自定义类型。 仅当使用此类型`certificateValidationMode`属性[ \<certificateValidation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)元素设置为"Custom"。  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<certificateValidation >  
\<certificateValidator >  
  
## <a name="syntax"></a>语法  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <certificateValidation>  
      <certificateValidator type=xs:string>  
      </certificateValidator>  
    </certificateValidation>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|类型|指定自定义类型派生自<xref:System.IdentityModel.Selectors.X509CertificateValidator>类。 设置`certificateValidationMode`属性[ \<certificateValidation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)为"Custom"以使用此类型的元素。 有关如何指定详细信息`type`属性，请参阅[自定义类型引用](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md)。 可选。|  
  
### <a name="child-elements"></a>子元素  
 无  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<certificateValidation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)|控制令牌处理程序用来验证证书的设置。|  
  
## <a name="example"></a>示例  
  
```xml  
<certificateValidation certificateValidationMode="Custom"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine">  
    <certificateValidator type="MyNamespace.CustomValidator, MyAssembly" />    
</certificateValidation>        
```
