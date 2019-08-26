---
title: <customCookieHandler>
ms.date: 03/30/2017
ms.assetid: a03b153d-5ec6-4915-9031-6f0c3fd348be
author: BrucePerlerMS
ms.openlocfilehash: ebf1f7f3de1b44dba63977bf524dea9af2690fb1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942783"
---
# <a name="customcookiehandler"></a>\<customCookieHandler>
设置自定义 cookie 处理程序类型。 仅当`mode` `<cookieHandler>`元素的属性为 "Custom" 时, 此元素才能存在。 自定义类型必须派生<xref:System.IdentityModel.Services.CookieHandler>自类。  
  
 \<system.identityModel.services>  
\<federationConfiguration>  
\<cookieHandler>  
\<customCookieHandler>  
  
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
|type|指定从<xref:System.IdentityModel.Services.CookieHandler>类派生的自定义类型。 有关如何指定`type`属性的详细信息, 请参阅[自定义类型引用](../windows-workflow-foundation/index.md)。|  
  
### <a name="child-elements"></a>子元素  
 无  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<cookieHandler>](cookiehandler.md)|<xref:System.IdentityModel.Services.CookieHandler> 配置用于读取<xref:System.IdentityModel.Services.SessionAuthenticationModule>和写入 cookie 的。|  
  
## <a name="remarks"></a>备注  
 如果通过将`mode` `<cookieHandler>`元素的属性设置为 "custom" 来指定自定义 cookie 处理程序, 则必须通过包含引用 cookie 处理程序类型的`<customCookieHandler>`子元素来指定自定义 cookie 处理程序的类型。 当特性设置为 "分块" `mode`或 "Default" 时, 不能指定此元素。 自定义 cookie 处理程序必须派生<xref:System.IdentityModel.Services.CookieHandler>自类。  
  
 元素由<xref:System.IdentityModel.Configuration.CustomTypeElement>类表示。 `<customCookieHandler>`  
  
## <a name="example"></a>示例  
 下面的示例将 SAM 配置为使用类型`MyNamespace.MyCustomCookieHandler`的自定义 cookie 处理程序。  
  
```xml  
<cookieHandler mode="Custom">  
    <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
</cookieHandler>  
```  
  
## <a name="see-also"></a>请参阅

- <xref:System.IdentityModel.Services.CookieHandler>
