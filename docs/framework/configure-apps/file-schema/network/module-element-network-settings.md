---
title: "&lt;模块&gt;元素 （网络设置）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#module
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/module
helpviewer_keywords:
- module element
- <module> element
ms.assetid: 10318725-9666-4d65-ab61-b94c64e59f13
caps.latest.revision: "14"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: a039f6ed985997c5557659abd299fe0fc7699a1b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltmodulegt-element-network-settings"></a>&lt;模块&gt;元素 （网络设置）
向应用程序添加新的代理模块。  
  
 \<configuration>  
\<system.net >  
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
  
|**特性**|**描述**|  
|-------------------|---------------------|  
|`type`|完全限定的类型名称 (由<xref:System.Type.FullName%2A>属性) 和程序集名称 (由<xref:System.Reflection.Assembly.FullName%2A>属性)，用逗号、 来实现该代理分隔。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|**元素**|**描述**|  
|-----------------|---------------------|  
|[defaultProxy](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|配置超文本传输协议 (HTTP) 代理服务器。|  
  
## <a name="remarks"></a>备注  
 `module`元素注册实现的代理类<xref:System.Net.IWebProxy>接口。 在注册代理类之后，该 `module` 可用于通过所支持的代理请求信息。  
  
 值`type`属性应为模块的类名称和名称的其相应的动态链接库 (DLL)。  
  
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
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Net.IWebProxy?displayProperty=nameWithType>  
 [网络设置架构](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
