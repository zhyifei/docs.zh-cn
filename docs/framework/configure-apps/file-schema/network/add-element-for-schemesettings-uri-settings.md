---
title: '&lt;添加&gt;schemeSettings （Uri 设置） 的元素'
ms.date: 03/30/2017
ms.assetid: 594a7b3b-af23-4cfa-b616-0b2dddb1a705
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: bd8033b07b29066633e5217645f3ee06937179da
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltaddgt-element-for-schemesettings-uri-settings"></a>&lt;添加&gt;schemeSettings （Uri 设置） 的元素
添加方案名称方案设置。  
  
 \<configuration>  
\<uri >  
\<schemeSettings >  
\<add>  
  
## <a name="syntax"></a>语法  
  
```xml  
<add
  name="http|https"
  genericUriParserOptions="DontUnescapePathDotsAndSlashes"
/>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 以下几节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|name|此设置适用于方案名称。 只有受支持的值名称 ="http"和名称 ="https"。|  
  
## <a name="attribute-name-attribute"></a>{属性名称}属性  
  
|值|描述|  
|-----------|-----------------|  
|genericUriParserOptions|有关此方案的分析器选项。 仅支持的值是 genericUriParserOptions ="DontUnescapePathDotsAndSlashes"。|  
  
### <a name="child-elements"></a>子元素  
 无  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<schemeSettings> 元素（Uri 设置）](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|指定如何分析特定方案的 <xref:System.Uri>。|  
  
## <a name="remarks"></a>备注  
 默认情况下，<xref:System.Uri?displayProperty=nameWithType>类取消转义百分号编码在执行路径压缩前的路径分隔符。 这实现为一种安全机制免受攻击如下所示：  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 如果此 URI 获取传递给模块不处理百分号编码字符正确，则可能导致服务器正在执行的以下命令：  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 为此，<xref:System.Uri?displayProperty=nameWithType>类第一个取消转义路径分隔符，然后将应用路径压缩。 将传递到的恶意 URL 上面的结果<xref:System.Uri?displayProperty=nameWithType>类构造函数会产生以下 URI:  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 SchemeSettings 配置选项用于特定方案的不取消转义百分比编码的路径分隔符，可以修改此默认行为。  
  
## <a name="configuration-files"></a>配置文件  
 此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。  
  
## <a name="example"></a>示例  
 下面的示例演示使用的配置<xref:System.Uri>类，以支持非转义 http 方案的百分比编码路径分隔符。  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>  
 <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>  
 <xref:System.GenericUriParserOptions?displayProperty=nameWithType>  
 <xref:System.Uri?displayProperty=nameWithType>  
 [网络设置架构](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
