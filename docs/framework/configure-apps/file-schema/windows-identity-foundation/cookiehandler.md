---
title: '&lt;cookieHandler&gt;'
ms.date: 03/30/2017
ms.assetid: bfdc127f-8d94-4566-8bef-f583c6ae7398
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 7fcdf1e89c3b68daa36ee80fe7234737c61a5a3c
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32758134"
---
# <a name="ltcookiehandlergt"></a>&lt;cookieHandler&gt;
配置<xref:System.IdentityModel.Services.CookieHandler>， <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) 用于读取和写入 cookie。  
  
 \<system.identityModel.services >  
\<federationConfiguration >  
\<cookieHandler >  
  
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
|name|指定任何已编写 cookie 的基名称。 默认值为"FedAuth"。|  
|path|指定任何已编写 cookie 的路径值。 默认值为"HttpRuntime.AppDomainAppVirtualPath"。|  
|mode|之一<xref:System.IdentityModel.Services.CookieHandlerMode>指定 SAM 所用的 cookie 处理程序的类型的值。 可以使用以下值：<br /><br /> -"默认"-"Chunked"相同。<br />-"分块"-使用的是实例<xref:System.IdentityModel.Services.ChunkedCookieHandler>类。 此 cookie 处理程序可确保各个 cookie 不能超过集的最大大小。 通过可能"分块"一个逻辑 cookie，为多个 cookie 上在线完成此操作。<br />-"Custom"-使用派生自的自定义类的实例<xref:System.IdentityModel.Services.CookieHandler>。 派生的类引用的`<customCookieHandler>`子元素。<br /><br /> 默认值为"Default"。|  
|persistentSessionLifetime|指定持久性会话的生存期。 如果为零，始终使用临时会话。 默认值为"0:0:0"，指定的临时会话。 最大值为"365:0:0"，指定的 365 天内的会话。 应根据以下限制指定的值： `<xs:pattern value="([0-9.]+:){0,1}([0-9]+:){0,1}[0-9.]+" />`，其中最左侧的值指定天数、 中间值 （如果有） 指定小时数，并最右侧的值 （如果有） 指定的分钟数。|  
|RequireSsl|指定是否有任何已编写 cookie 发出"安全"标志。 如果设置此值，在登录会话 cookie 将仅可通过 HTTPS。 默认值为“true”。|  
|hideFromScript|控制是否有任何已编写 cookie 发出"HttpOnly"标志。 某些 web 浏览器通过阻止客户端脚本访问的 cookie 值接受此标志。 默认值为“true”。|  
|域|任何已编写 cookie 域值。 默认值为 ""。|  
  
### <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<chunkedCookieHandler >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/chunkedcookiehandler.md)|配置<xref:System.IdentityModel.Services.ChunkedCookieHandler>。 此元素仅可呈现如果`mode`属性`<cookieHandler>`元素是"默认"块"。|  
|[\<customCookieHandler >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/customcookiehandler.md)|设置自定义 cookie 处理程序类型。 此元素必须存在如果`mode`属性`<cookieHandler>`元素是"自定义"。 它不能出现的任何其他值`mode`属性。 自定义的类型必须派生自<xref:System.IdentityModel.Services.CookieHandler>类。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<federationConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|包含配置的设置<xref:System.IdentityModel.Services.WSFederationAuthenticationModule>(WSFAM) 和<xref:System.IdentityModel.Services.SessionAuthenticationModule>(SAM)。|  
  
## <a name="remarks"></a>备注  
 <xref:System.IdentityModel.Services.CookieHandler>负责读取和写入原始 cookie 在 HTTP 协议级别。 你可以配置任一<xref:System.IdentityModel.Services.ChunkedCookieHandler>或从派生自定义 cookie 处理程序<xref:System.IdentityModel.Services.CookieHandler>类。  
  
 若要配置分块的 cookie 处理程序，将模式特性设置为"Chunked"或"默认"。 默认块区大小为 2000 个字节，但您可以通过包括 （可选） 指定的不同区块大小`<chunkedCookieHandler>`子元素。  
  
 若要配置自定义 cookie 处理程序，将模式特性设置为"Custom"。 你还必须指定`<customCookieHandler>`引用自定义处理程序的类型的子元素。  
  
 `<cookieHandler>`元素表示由<xref:System.IdentityModel.Services.CookieHandlerElement>类。 已在配置中指定该 cookie 处理程序可从<xref:System.IdentityModel.Services.Configuration.FederationConfiguration.CookieHandler%2A>属性<xref:System.IdentityModel.Services.Configuration.FederationConfiguration>对象上设置<xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType>属性。  
  
## <a name="example"></a>示例  
 下面的 XML 演示`<cookieHandler>`元素。 在此示例中，因为`mode`未指定属性时，将通过 SAM 使用默认 cookie 处理程序。 这是实例<xref:System.IdentityModel.Services.ChunkedCookieHandler>类。 因为`<chunkedCookieHandler>`未指定子元素时，将使用默认块区大小。 HTTPS 不是所需因为`requireSsl`特性设置`false`。  
  
> [!WARNING]
>  在此示例中，不需要 HTTPS 编写会话 cookie。 这是因为`requireSsl`属性`<cookieHandler>`元素设置为`false`。 对于大多数生产环境不被建议此设置，因为它可能存在安全风险。  
  
```xml  
<cookieHandler requireSsl="false" />  
```  
  
## <a name="see-also"></a>请参阅  
 <xref:System.IdentityModel.Services.CookieHandler>  
 <xref:System.IdentityModel.Services.ChunkedCookieHandler>  
 <xref:System.IdentityModel.Services.SessionAuthenticationModule>
