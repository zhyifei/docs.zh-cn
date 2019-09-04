---
title: <cookieHandler>
ms.date: 03/30/2017
ms.assetid: bfdc127f-8d94-4566-8bef-f583c6ae7398
author: BrucePerlerMS
ms.openlocfilehash: 853dc9817d080e59ac7a792576eda862bd0b1f1d
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252031"
---
# <a name="cookiehandler"></a>\<cookieHandler>
<xref:System.IdentityModel.Services.CookieHandler> 配置（SAM）用于读取<xref:System.IdentityModel.Services.SessionAuthenticationModule>和写入 cookie 的。  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System.identitymodel >** ](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<federationConfiguration >** ](federationconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<cookieHandler >**  
  
## <a name="syntax"></a>语法  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <cookieHandler name=xs:string  
        path=Path  
        mode="Chunked||Custom||Default"  
        persistentSessionLifetime=xs:string  
        hideFromScript=xs:boolean  
        requireSSL=xs:boolean  
        domain=xs:string  
      <chunkedCookieHandler size=xs:int />  
      <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
    </cookieHandler>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|NAME|指定写入的任何 cookie 的基名称。 默认值为 "FedAuth"。|  
|path|指定写入的任何 cookie 的路径值。 默认值为 "HttpRuntime. AppDomainAppVirtualPath"。|  
|mode|<xref:System.IdentityModel.Services.CookieHandlerMode>值之一，它指定 SAM 使用的 cookie 处理程序的类型。 可以使用以下值：<br /><br /> -"Default"-与 "分块" 相同。<br />-"分块"-使用<xref:System.IdentityModel.Services.ChunkedCookieHandler>类的实例。 此 cookie 处理程序可确保各个 cookie 不会超过设置的最大大小。 它通过将一个逻辑 cookie "分块" 为多个网络中的多个 cookie 来实现这一点。<br />-"Custom"-使用派生<xref:System.IdentityModel.Services.CookieHandler>自的自定义类的实例。 派生类由`<customCookieHandler>`子元素引用。<br /><br /> 默认值为 "Default"。|  
|persistentSessionLifetime|指定持久会话的生存期。 如果为零，则始终使用暂时性会话。 默认值为 "0:0:0"，该值指定暂时性会话。 最大值为 "365:0:0"，该值指定的会话为365天。 应根据以下限制指定值： `<xs:pattern value="([0-9.]+:){0,1}([0-9]+:){0,1}[0-9.]+" />`，其中最左端的值指定天，中间值（如果有）指定小时，最右侧的值（如果有）指定分钟。|  
|requireSsl|指定是否为写入的任何 cookie 发出 "Secure" 标志。 如果设置了此值，则只能通过 HTTPS 使用登录会话 cookie。 默认值为“true”。|  
|hideFromScript|控制是否为写入的任何 cookie 发出 "HttpOnly" 标志。 某些 web 浏览器通过保持客户端脚本访问 cookie 值来服从此标志。 默认值为“true”。|  
|域|写入的任何 cookie 的域值。 默认值为 ""。|  
  
### <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<chunkedCookieHandler>](chunkedcookiehandler.md)|<xref:System.IdentityModel.Services.ChunkedCookieHandler>配置。 仅当`mode` `<cookieHandler>`元素的属性为 "默认值" 或 "分块" 时，此元素才能存在。|  
|[\<customCookieHandler>](customcookiehandler.md)|设置自定义 cookie 处理程序类型。 如果`mode` `<cookieHandler>`元素的属性为 "Custom"，则此元素必须存在。 此`mode`属性的任何其他值不能出现此情况。 自定义类型必须派生<xref:System.IdentityModel.Services.CookieHandler>自类。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<federationConfiguration>](federationconfiguration.md)|包含配置<xref:System.IdentityModel.Services.WSFederationAuthenticationModule> （WSFAM） <xref:System.IdentityModel.Services.SessionAuthenticationModule>和（SAM）的设置。|  
  
## <a name="remarks"></a>备注  
 <xref:System.IdentityModel.Services.CookieHandler>负责在 HTTP 协议级别读取和写入原始 cookie。 可以配置<xref:System.IdentityModel.Services.ChunkedCookieHandler> <xref:System.IdentityModel.Services.CookieHandler>从类派生的或自定义 cookie 处理程序。  
  
 若要配置分块 cookie 处理程序，请将 mode 属性设置为 "分块" 或 "Default"。 默认块区大小为2000个字节，但您可以选择通过包括`<chunkedCookieHandler>`子元素来指定不同的区块大小。  
  
 若要配置自定义 cookie 处理程序，请将 mode 属性设置为 "Custom"。 还必须指定`<customCookieHandler>`引用自定义处理程序的类型的子元素。  
  
 元素由<xref:System.IdentityModel.Services.CookieHandlerElement>类表示。 `<cookieHandler>` 在配置中指定的 cookie 处理程序可通过<xref:System.IdentityModel.Services.Configuration.FederationConfiguration.CookieHandler%2A> <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType>属性上设置的<xref:System.IdentityModel.Services.Configuration.FederationConfiguration>对象的属性获得。  
  
## <a name="example"></a>示例  
 下面的 XML 显示了`<cookieHandler>`一个元素。 在此示例中，由于`mode`未指定属性，SAM 将使用默认的 cookie 处理程序。 这是<xref:System.IdentityModel.Services.ChunkedCookieHandler>类的实例。 由于未指定子元素，将使用默认的块区大小。 `<chunkedCookieHandler>` 不需要 HTTPS，因为`requireSsl`已设置`false`属性。  
  
> [!WARNING]
> 在此示例中，无需 HTTPS 即可写入会话 cookie。 这是因为`<cookieHandler>`元素`requireSsl`上的特性设置为。 `false` 对于大多数生产环境，不建议使用此设置，因为这可能会带来安全风险。  
  
```xml  
<cookieHandler requireSsl="false" />  
```  
  
## <a name="see-also"></a>请参阅

- <xref:System.IdentityModel.Services.CookieHandler>
- <xref:System.IdentityModel.Services.ChunkedCookieHandler>
- <xref:System.IdentityModel.Services.SessionAuthenticationModule>
