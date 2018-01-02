---
title: '&lt;customCookieHandler&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a03b153d-5ec6-4915-9031-6f0c3fd348be
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 61b128d5856fd8e35516949b637177dc38a17164
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltcustomcookiehandlergt"></a>&lt;customCookieHandler&gt;
设置自定义 cookie 处理程序类型。 此元素仅可呈现如果`mode`属性`<cookieHandler>`元素是"自定义"。 自定义的类型必须派生自<xref:System.IdentityModel.Services.CookieHandler>类。  
  
 \<system.identityModel.services >  
\<federationConfiguration >  
\<cookieHandler >  
\<customCookieHandler >  
  
## <a name="syntax"></a>语法  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <cookieHandler mode="Custom">  
      <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" >  
      </customCookieHandler>  
    </cookieHandler>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|类型|指定自定义类型派生自<xref:System.IdentityModel.Services.CookieHandler>类。 有关如何指定详细信息`type`属性，请参阅[自定义类型引用](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md)。|  
  
### <a name="child-elements"></a>子元素  
 无  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<cookieHandler >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|配置<xref:System.IdentityModel.Services.CookieHandler>，<xref:System.IdentityModel.Services.SessionAuthenticationModule>用于读取和写入 cookie。|  
  
## <a name="remarks"></a>备注  
 当你通过设置指定的自定义 cookie 处理`mode`属性`<cookieHandler>`元素为"Custom"，必须指定自定义 cookie 处理程序的类型，通过包括`<customCookieHandler>`引用该 cookie 处理程序类型的子元素。 此元素不能为时指定`mode`属性设置为"Chunked"或"默认"。 自定义 cookie 处理程序必须派生自<xref:System.IdentityModel.Services.CookieHandler>类。  
  
 `<customCookieHandler>`元素表示由<xref:System.IdentityModel.Configuration.CustomTypeElement>类。  
  
## <a name="example"></a>示例  
 下面的示例将配置 SAM 若要使用的类型的自定义 cookie 处理`MyNamespace.MyCustomCookieHandler`。  
  
```xml  
<cookieHandler mode="Custom">  
    <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
</cookieHandler>  
```  
  
## <a name="see-also"></a>请参阅  
 <xref:System.IdentityModel.Services.CookieHandler>
