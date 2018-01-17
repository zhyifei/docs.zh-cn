---
title: '&lt;securityTokenHandlers&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f11a631d-4094-4e11-bb03-4ede74b30281
caps.latest.revision: "5"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: de19fffdeae801163ec991ecf08d00b1286781d8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltsecuritytokenhandlersgt"></a>&lt;securityTokenHandlers&gt;
指定与终结点注册的安全令牌处理程序的集合。  
  
 \<system.identityModel >  
\<identityConfiguration >  
\<securityTokenHandlers >  
  
## <a name="syntax"></a>语法  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|name|指定令牌处理程序集合的名称。 由框架识别的唯一值是"ActAs"和"OnBehalfOf"。 如果使用的这些名称指定令牌处理程序集合，在处理 ActAs 或 OnBehalfOf 分别令牌时，将使用集合。|  
  
### <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|向令牌处理程序集合中添加的安全令牌处理程序。|  
|[\<clear>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/clear.md)|清除所有安全令牌处理程序从标记处理程序集合。|  
|[\<remove>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/remove.md)|从标记处理程序集合中移除的安全令牌处理程序。|  
|[\<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|提供配置令牌处理程序的集合。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|指定服务级别标识设置。|  
  
## <a name="remarks"></a>备注  
 你可以在服务配置中指定一个或多个安全令牌处理程序的命名的集合。 你可以通过使用指定集合的名称`name`属性。 该框架将处理的唯一名称是"ActAs"和"OnBehalfOf"。 如果处理程序存在这些集合中，它们由安全令牌服务 (STS) 而不是默认处理程序处理时`ActAs`和`OnBehalfOf`令牌。  
  
 默认情况下，使用以下处理程序类型填充集合： <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>， <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>， <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler>， <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler>， <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler>， <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>，和<xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler>。 你可以通过修改该集合`<add>`， `<remove>`，和`<clear>`元素。 你必须确保仅属于任何特定类型的单个处理程序集合中存在。 例如，如果你是派生的处理程序<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>类，或者您的处理程序或<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>可能单个集合，但不同时配置。  
  
 使用`<securityTokenHandlerConfiguration>`元素集合中指定的处理程序的配置设置。 通过此元素指定的设置会覆盖通过服务上指定的那些[ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)元素。 一些处理程序 （包括多个内置的处理程序类型） 可以支持通过的子元素的其他配置`<add>`元素。 上一个处理程序指定的设置重写指定集合或服务上的等效设置。
