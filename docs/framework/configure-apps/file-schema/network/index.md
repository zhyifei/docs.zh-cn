---
title: "网络设置架构 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "配置设置 [.NET Framework], 网络"
  - "连接 [.NET Framework], 网络配置元素"
  - "元素 [.NET Framework], 网络配置元素"
  - "Internet, 网络配置元素"
  - "网络配置元素"
  - "网络资源, 网络配置元素"
  - "网络设置"
  - "接收数据, 网络配置元素"
  - "发送数据, 网络配置元素"
ms.assetid: f1de5a0f-76c5-4833-819f-5222b8146340
caps.latest.revision: 14
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 14
---
# 网络设置架构
网络设置指定 .NET Framework 与网络的连接方式。  下表描述 [\<system.Net\> 元素（网络设置）](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md) 下的每一子级配置元素的功能。  
  
|元素|说明|  
|--------|--------|  
|[\<authenticationModules\> 元素（网络设置）](../../../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md)|指定用于对 Internet 请求进行身份验证的模块。|  
|[\<connectionManagement\> 元素（网络设置）](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|指定与 Internet 宿主的连接的最大数目。|  
|[\<defaultProxy\> 元素（网络设置）](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|指定用于对 Internet 的 HTTP 请求的代理服务器。|  
|[\<mailSettings\> 元素（网络设置）](../../../../../docs/framework/configure-apps/file-schema/network/mailsettings-element-network-settings.md)|包含邮件发送选项的设置。|  
|[\<requestCaching\> 元素（网络设置）](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|指定用于从 Internet 宿主中请求信息的模块。|  
|[\<requestCaching\> 元素（网络设置）](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|配置 <xref:System.Net?displayProperty=fullName> 命名空间的基本网络选项。|  
|[\<webRequestModules\> 元素（网络设置）](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|指定用于从 Internet 宿主中请求信息的模块。|  
  
 Uri设置指定用于指定 .NET Framework 如何处理使用统一资源标识符 \(URI\) 表示的 Web 地址。  下表描述在 [\<uri\> 元素（URI 设置）](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md) 下的每一子级配置元素的功能。  
  
|元素|说明|  
|--------|--------|  
|[\<idn\> 元素（Uri 设置）](../../../../../docs/framework/configure-apps/file-schema/network/idn-element-uri-settings.md)|指定是否对域名应用国际化域名 \(IDN\) 分析。|  
|[\<iriParsing\> 元素（Uri 设置）](../../../../../docs/framework/configure-apps/file-schema/network/iriparsing-element-uri-settings.md)|指定是否对 <xref:System.Uri> 应用国际化资源标识符 \(IRI\) 分析以及是否应该应用 IRI 分析规则。|  
|[\<schemeSettings\> 元素（Uri 设置）](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|指定如何针对特定方案分析 <xref:System.Uri>。|  
  
## 请参阅  
 [配置 Internet 应用程序](../../../../../docs/framework/network-programming/configuring-internet-applications.md)   
 [配置文件架构](../../../../../docs/framework/configure-apps/file-schema/index.md)