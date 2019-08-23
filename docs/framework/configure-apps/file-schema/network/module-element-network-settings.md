---
title: <module> 元素（网络设置）
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#module
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/module
helpviewer_keywords:
- module element
- <module> element
ms.assetid: 10318725-9666-4d65-ab61-b94c64e59f13
ms.openlocfilehash: 851a63b41dfb5d3b4058e1373148f48d47d9d6ae
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664072"
---
# <a name="module-element-network-settings"></a>\<module > 元素 (网络设置)
向应用程序添加新的代理模块。  
  
 \<configuration>  
\<system.net>  
\<defaultProxy >  
\<模块 >  
  
## <a name="syntax"></a>语法  
  
```xml  
<module   
  type="type_fullname, assembly_fullname"   
/>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|**特性**|**说明**|  
|-------------------|---------------------|  
|`type`|实现代理的由逗号分隔的完全限定<xref:System.Type.FullName%2A>的类型名称 (由属性指示) 和程序<xref:System.Reflection.Assembly.FullName%2A>集名称 (由属性指示)。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|**元素**|**说明**|  
|-----------------|---------------------|  
|[defaultProxy](defaultproxy-element-network-settings.md)|配置超文本传输协议 (HTTP) 代理服务器。|  
  
## <a name="remarks"></a>备注  
 元素注册用于<xref:System.Net.IWebProxy>实现接口的代理类。 `module` 在注册代理类之后，该 `module` 可用于通过所支持的代理请求信息。  
  
 `type`特性的值应为模块的类名称及其对应的动态链接库 (DLL) 的名称。  
  
## <a name="configuration-files"></a>配置文件  
 此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。  
  
## <a name="example"></a>示例  
 下面的示例注册自定义代理类。  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <module  
        type="Test.CustomWebProxy, TestProxy, Version=2.0.3600.0, Culture=neutral, PublicKeyToken=b23a5c561934e385"  
      />  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>请参阅

- <xref:System.Net.IWebProxy?displayProperty=nameWithType>
- [网络设置架构](index.md)
