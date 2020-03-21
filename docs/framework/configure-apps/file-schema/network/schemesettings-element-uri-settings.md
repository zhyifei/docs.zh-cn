---
title: <schemeSettings> 元素（Uri 设置）
ms.date: 03/30/2017
ms.assetid: 0ae45c6e-8c4c-4c0d-8b9f-a93824648890
ms.openlocfilehash: c745c90bb61b9ee393687d7f6db4fd11565c7dc7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154642"
---
# <a name="schemesettings-element-uri-settings"></a>\<schemeSettings> 元素（Uri 设置）
指定如何分析特定方案的 <xref:System.Uri>。  
  
[**\<配置>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<乌里>**](uri-element-uri-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<方案设置>**  
  
## <a name="syntax"></a>语法  
  
```xml  
<schemeSettings>
</schemeSettings>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>属性  
 无  
  
### <a name="child-elements"></a>子元素  
  
|**元素**|**说明**|  
|-----------------|---------------------|  
|[添加](add-element-for-schemesettings-uri-settings.md)|添加方案名称的方案设置。|  
|[清楚](clear-element-for-schemesettings-uri-settings.md)|清除所有现有方案设置。|  
|[删除](remove-element-for-schemesettings-uri-settings.md)|删除方案名称的方案设置。|  
  
### <a name="parent-elements"></a>父元素  
  
|**元素**|**说明**|  
|-----------------|---------------------|  
|[Uri](uri-element-uri-settings.md)|包含指定 .NET 框架如何处理使用统一资源标识符 （URI） 表示的 Web 地址的设置。|  
  
## <a name="remarks"></a>备注  
 默认情况下，<xref:System.Uri?displayProperty=nameWithType>类取消转义百分比编码的路径分隔符，然后再执行路径压缩。 这是作为针对以下攻击的安全机制实现的：  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 如果此 URI 传递给未正确处理编码百分比的模块，则可能导致服务器执行以下命令：  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 因此，<xref:System.Uri?displayProperty=nameWithType>类首先取消转义路径分隔符，然后应用路径压缩。 将上述恶意 URL 传递给<xref:System.Uri?displayProperty=nameWithType>类构造函数的结果会导致以下 URI：  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 可以使用方案设置配置选项修改此默认行为，以不取消转义百分比编码路径分隔符。  
  
## <a name="configuration-files"></a>配置文件  
 此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。  
  
## <a name="example"></a>示例  
 下面的示例显示了<xref:System.Uri>类用于支持不为 http 方案提供百分比编码的路径分隔符的配置。  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="element-information"></a>元素信息  
  
|||
|-|-|  
|命名空间|系统|  
|架构名称||  
|验证文件||  
|可以为空||  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [网络设置架构](index.md)
