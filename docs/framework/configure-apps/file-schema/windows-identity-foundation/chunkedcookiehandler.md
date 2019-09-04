---
title: <chunkedCookieHandler>
ms.date: 03/30/2017
ms.assetid: 7220de45-1d14-4aec-a29e-4a2ea8ac861f
author: BrucePerlerMS
ms.openlocfilehash: 6aad95033b99f1472284f838f3ede2e74ea8324c
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252111"
---
# <a name="chunkedcookiehandler"></a>\<chunkedCookieHandler>
<xref:System.IdentityModel.Services.ChunkedCookieHandler>配置。 仅当`mode` `<cookieHandler>`元素的属性为 "默认值" 或 "分块" 时，此元素才能存在。  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System.identitymodel >** ](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<federationConfiguration >** ](federationconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<cookieHandler >** ](cookiehandler.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<chunkedCookieHandler >**  
  
## <a name="syntax"></a>语法  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <cookieHandler mode="Chunked||Default" >  
      <chunkedCookieHandler size=xs:int >  
      </chunkedCookieHandler>  
    </cookieHandler>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|chunkSize|任何一个 HTTP cookie 的 HTTP cookie 数据的最大大小（字符数）。 调整块区大小时必须小心谨慎。 Web 浏览器对 cookie 和每个域允许的数量有不同的限制。 例如，原 Netscape 规范规定这些限制：300 cookie 总数、每个 cookie 标头4096个字节（包括元数据，而不仅仅是 cookie 值）和每个域20个 cookie。 默认值为2000。 必需。|  
  
### <a name="child-elements"></a>子元素  
 无  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<cookieHandler>](cookiehandler.md)|<xref:System.IdentityModel.Services.CookieHandler> 配置（SAM）用于读取<xref:System.IdentityModel.Services.SessionAuthenticationModule>和写入 cookie 的。|  
  
## <a name="remarks"></a>备注  
 <xref:System.IdentityModel.Services.ChunkedCookieHandler>通过`<cookieHandler>` `<chunkedCookieHandler>`将元素的属性设置为"默认值"或"分块"来指定时，可以指定cookie处理程序用于通过包括子元素来读取和写入cookie的块区大小，`mode`设置其`chunkSize`属性。 如果该`<chunkedCookieHandler>`元素不存在，则使用默认的块区大小（2000字节）。 当特性设置为 "Custom" `mode`时，不能指定此元素。  
  
 元素由<xref:System.IdentityModel.Services.ChunkedCookieHandlerElement>类表示。 `<chunkedCookieHandler>`  
  
## <a name="example"></a>示例  
 下面的示例配置一个分块 cookie 处理程序，该处理程序以3000字节的块写入 cookie。  
  
```xml  
<cookieHandler mode="Chunked">  
    <chunkedCookieHandler chunkSize=3000/>  
</cookieHandler>  
```  
  
## <a name="see-also"></a>请参阅

- <xref:System.IdentityModel.Services.ChunkedCookieHandler>
