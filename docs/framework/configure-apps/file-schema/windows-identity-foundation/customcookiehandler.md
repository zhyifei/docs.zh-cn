---
title: '&lt;customCookieHandler&gt;'
ms.date: 03/30/2017
ms.assetid: a03b153d-5ec6-4915-9031-6f0c3fd348be
author: BrucePerlerMS
ms.openlocfilehash: 51ca91de5c77727f5f5506118461d19354f12c14
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2018
ms.locfileid: "48836415"
---
# <a name="ltcustomcookiehandlergt"></a>&lt;customCookieHandler&gt;
设置自定义 cookie 处理程序类型。 此元素仅可能存在如果`mode`属性的`<cookieHandler>`元素是"自定义"。 自定义的类型必须派生自<xref:System.IdentityModel.Services.CookieHandler>类。  
  
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
|类型|指定派生的自定义类型<xref:System.IdentityModel.Services.CookieHandler>类。 有关如何指定详细信息`type`属性，请参阅[自定义类型引用](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md)。|  
  
### <a name="child-elements"></a>子元素  
 无  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<cookieHandler >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|配置<xref:System.IdentityModel.Services.CookieHandler>的<xref:System.IdentityModel.Services.SessionAuthenticationModule>用于读取和写入 cookie。|  
  
## <a name="remarks"></a>备注  
 通过设置指定自定义 cookie 处理程序时`mode`的属性`<cookieHandler>`元素为"Custom"，必须指定自定义 cookie 处理程序的类型，通过包括`<customCookieHandler>`引用 cookie 处理程序类型的子元素。 不能为此元素时指定`mode`属性设置为"Chunked"或"Default"。 自定义 cookie 处理程序必须派生自<xref:System.IdentityModel.Services.CookieHandler>类。  
  
 `<customCookieHandler>`元素表示由<xref:System.IdentityModel.Configuration.CustomTypeElement>类。  
  
## <a name="example"></a>示例  
 下面的示例配置 SAM 使用的类型的自定义 cookie 处理程序`MyNamespace.MyCustomCookieHandler`。  
  
```xml  
<cookieHandler mode="Custom">  
    <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
</cookieHandler>  
```  
  
## <a name="see-also"></a>请参阅  
 <xref:System.IdentityModel.Services.CookieHandler>
