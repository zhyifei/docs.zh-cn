---
title: '&lt;idn&gt;元素 （Uri 设置）'
ms.date: 03/30/2017
ms.assetid: 16c8e869-1791-4cf5-9244-3d3c738f60ec
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 17f68fbb92797928be911e530232e8638793687f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32742567"
---
# <a name="ltidngt-element-uri-settings"></a>&lt;idn&gt;元素 （Uri 设置）
指定是否国际化域名 (IDN) 分析将应用于域的名称。  
  
## <a name="schema-hierarchy"></a>架构层次结构  
 [\<configuration> 元素](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [\<Uri > 元素 （Uri 设置）](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)  
  
 [\<idn >](../../../../../docs/framework/configure-apps/file-schema/network/idn-element-uri-settings.md)  
  
## <a name="syntax"></a>语法  
  
```xml  
<idn  
  enabled="All|AllExceptIntranet|None"  
/>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|**元素**|**说明**|  
|-----------------|---------------------|  
|`enabled`|指定是否国际化域名 (IDN) 分析应用到一个域名称的默认值为 none。|  
  
### <a name="child-elements"></a>子元素  
 无  
  
### <a name="parent-elements"></a>父元素  
  
|**元素**|**说明**|  
|-----------------|---------------------|  
|[Uri](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)|包含指定.NET Framework 如何处理使用统一资源标识符 (Uri) 表示的 web 地址的设置。|  
  
## <a name="remarks"></a>备注  
 现有<xref:System.Uri>已在.NET Framework 3.5 扩展类。 3.0 SP1 和 2.0 SP1 中的对国际资源标识符 (IRI) 和国际化域名 (IDN) 的支持。 当前用户将不会看到从.NET Framework 2.0 行为的任何更改，除非专门允许 IRI 和 IDN 支持。 这确保了 NET Framework 以前版本的应用程序兼容性。  
  
 若要启用对 IRI 的支持，以下两项更改是必需的：  
  
1.  将以下行添加到.NET Framework 2.0 目录下的 machine.config 文件  
  
    ```xml  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2.  指定是否要国际化域名 (IDN) 分析应用到的域名以及是否应应用 IRI 分析规则。 这可以在 machine.config 或应用配置文件中完成。  
  
 有用于 IDN 具体取决于使用的 DNS 服务器的三个可能的值：  
  
-   启用 idn = All  
  
     此值会将任何 Unicode 域名称转换为其 Punycode 等效项 （IDN 名称）。  
  
-   启用 idn = AllExceptIntranet  
  
     此值会将所有 Unicode 域名而不是基于本地 Intranet 使用 Punycode 等效 （IDN 名称）。 在这种情况下来处理本地 Intranet 上的国际名称，用于 Intranet DNS 服务器应支持 Unicode 名称解析。  
  
-   启用 idn = None  
  
     此值不会将转换使用 Punycode 任何 Unicode 域名。 这是默认值，这是与.NET Framework 2.0 行为一致。  
  
 启用 IDN 可以将域名中所有 Unicode 标签转换成标签的 Punycode 等同项。 Punycode 名称只包含 ASCII 字符，并且始终以 xn-- 前缀开头。 这样是为了支持 Internet 上的 DNS 服务器，因为大部分 DNS 服务器仅支持 ASCII 字符（参见 RFC 3940）。  
  
### <a name="configuration-files"></a>配置文件  
 此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。  
  
## <a name="example"></a>示例  
  
### <a name="description"></a>描述  
 下面的示例演示使用的配置<xref:System.Uri>类，以支持 IRI 分析和 IDN 名称。  
  
### <a name="code"></a>代码  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Configuration.IdnElement?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection?displayProperty=nameWithType>  
 [网络设置架构](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
