---
title: '&lt;chunkedCookieHandler&gt;'
ms.date: 03/30/2017
ms.assetid: 7220de45-1d14-4aec-a29e-4a2ea8ac861f
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 193b783e44fe4386d3575e180dc5baa6a7f9a8be
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32758368"
---
# <a name="ltchunkedcookiehandlergt"></a>&lt;chunkedCookieHandler&gt;
配置<xref:System.IdentityModel.Services.ChunkedCookieHandler>。 此元素仅可呈现如果`mode`属性`<cookieHandler>`元素是"默认"块"。  
  
 \<system.identityModel.services >  
\<federationConfiguration >  
\<cookieHandler >  
\<chunkedCookieHandler >  
  
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
|chunkSize|最大大小，以字符为单位的任何一个的 HTTP cookie 的 HTTP cookie 数据。 你必须调整块区大小时请小心。 Web 浏览器 cookie 和号允许每个域的大小具有不同的限制。 例如，原始的 Netscape 规范规定这些限制： 总 300 cookie，每个 cookie 标头 （包括元数据，而不仅仅是 cookie 值），4096 个字节和每个域的 20 cookie。 默认值为 2000年。 必须的。|  
  
### <a name="child-elements"></a>子元素  
 无  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<cookieHandler >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|配置<xref:System.IdentityModel.Services.CookieHandler>， <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) 用于读取和写入 cookie。|  
  
## <a name="remarks"></a>备注  
 当指定<xref:System.IdentityModel.Services.ChunkedCookieHandler>通过设置`mode`属性`<cookieHandler>`到"默认"或"Chunked"的元素，可以指定的 cookie 处理使用来读取和写入 cookie 包括块区大小`<chunkedCookieHandler>`子元素和设置其`chunkSize`属性。 如果`<chunkedCookieHandler>`元素不存在，则使用默认块区大小的 2000 个字节。 此元素不能为时指定`mode`属性设置为"Custom"。  
  
 `<chunkedCookieHandler>`元素表示由<xref:System.IdentityModel.Services.ChunkedCookieHandlerElement>类。  
  
## <a name="example"></a>示例  
 下面的示例配置中的 3000 个字节块写入 cookie 分块的 cookie 处理程序。  
  
```xml  
<cookieHandler mode="Chunked">  
    <chunkedCookieHandler chunkSize=3000/>  
</cookieHandler>  
```  
  
## <a name="see-also"></a>请参阅  
 <xref:System.IdentityModel.Services.ChunkedCookieHandler>
