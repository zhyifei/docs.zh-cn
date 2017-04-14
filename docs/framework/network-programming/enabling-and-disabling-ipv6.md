---
title: "启用和禁用 IPv6 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: 6408d3ef-c9ba-49d9-b15e-fe74bd3ef031
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# 启用和禁用 IPv6
若要使用IPv6协议，请确保您运行支持IPv6操作系统的版本并确保正确释放操作系统和网络连接选件类。  
  
## 配置步骤  
 下表列出了各种配置  
  
|IPv6启用的操作系统?|IPv6启用网络连接选件类?|描述|  
|------------------|--------------------|--------|  
|否|否|可以分析 IPv6 地址。|  
|否|是|可以分析 IPv6 地址。|  
|是|否|使用名称转换方法未标记为过时，可以分析 IPv6 地址和解决 IPv6 地址。|  
|是|是|使用任何方法包含这些清单过时，可以分析和解析 IPv6 地址。|  
  
 请注意启用IPv6为System.Net命名空间中的任何选件类支持，您必须修改计算机配置文件或配置文件应用程序的。  应用程序的配置文件在计算机配置文件的优先级。  
  
 向示例说明如何修改计算机配置文件， *machine.config*，启用Ipv6支持看到， [如何:修改计算机配置文件启用Ipv6支持](../../../docs/framework/network-programming/how-to-modify-the-computer-configuration-file-to-enable-ipv6-support.md)。  另外，请确保IPv6支持操作系统上启用。  
  
 .NET Framework具有如下设置的配置开关在配置文件  
  
```  
<system.net>…  
    <settings>…  
        <ipv6 enabled="true"/>…  
    </settings>…  
</system.net>  
```  
  
 为.NET Framework版本1.1和早期版本中， **ipv6 enabled** 配置开关的值指定 <xref:System.Net.Dns?displayProperty=fullName> 选件类的成员是否返回 IPv6 地址。  
  
 对于.NET Framework <xref:System.Net.Dns?displayProperty=fullName> 选件类的2.0版和更高版本，因此，如果Windows支持IPv6，然后成员， \(例如， <xref:System.Net.Dns.GetHostEntry%2A?displayProperty=fullName> 方法\)，将返回IPv6具有一个限制的地址。  DNS <xref:System.Net.Dns?displayProperty=fullName> 的过时成员\(例如， <xref:System.Net.Dns.Resolve%2A?displayProperty=fullName> 方法\)将读取并识别在配置文件中的值ipv6启用设置的。  
  
## 请参阅  
 [Internet 协议版本 6](../../../docs/framework/network-programming/internet-protocol-version-6.md)   
 [套接字](../../../docs/framework/network-programming/sockets.md)   
 [网络设置架构](../../../docs/framework/configure-apps/file-schema/network/index.md)   
 [\<ipv6\> 元素（网络设置）](../../../docs/framework/configure-apps/file-schema/network/ipv6-element-network-settings.md)