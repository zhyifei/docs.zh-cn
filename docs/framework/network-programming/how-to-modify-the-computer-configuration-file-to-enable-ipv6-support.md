---
title: "如何：修改计算机配置文件以启用 IPv6 支持 | Microsoft Docs"
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
ms.assetid: 5611b677-b9cc-43b8-a434-60e18d89aada
caps.latest.revision: 18
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 18
---
# 如何：修改计算机配置文件以启用 IPv6 支持
下面的代码示例演示如何修改计算机配置文件， *machine.config*，启用IPv6支持。  *machine.config* 文件在安装 Windows 的内容的 *%Windir%\\Microsoft.NET\\Framework* 文件夹中。  具有在计算机在.NET Framework的每个版本的 *%Windir%\\Microsoft.NET\\Framework* 下安装的文件夹的一个单独的 *machine.config* 文件\(例如，*C:\\WINDOWS\\Microsoft.NET\\Framework\\v2.0.50727\\machine.config*\)。  
  
 这些设置应用程序的配置文件还使，在计算机配置文件的优先级。  
  
 为.NET Framework版本1.1和早期版本中， **ipv6 enabled** 配置开关的值指定 <xref:System.Net.Dns?displayProperty=fullName> 选件类的成员是否返回 IPv6 地址。  
  
 对于.NET Framework 2.0版和更高版本，因此，如果Windows支持IPv6，然后 <xref:System.Net.Dns?displayProperty=fullName> 选件类的所有成员\(例如， <xref:System.Net.Dns.GetHostEntry%2A?displayProperty=fullName> 方法\)，将返回IPv6具有一个限制的地址。  <xref:System.Net.Dns?displayProperty=fullName> 选件类的过时成员\(例如， <xref:System.Net.Dns.Resolve%2A?displayProperty=fullName> 方法\)将读取并识别在配置文件中的值。  
  
> [!NOTE]
>  默认情况下为.NET Framework 2.0版和更高版本， IPv6启用。  默认情况下为.NET Framework版本1.1和早期版本中， IPv6被禁用。  
  
## 示例  
  
```  
<system.net>  
    …………  
    <settings>  
        …………  
        <ipv6 enabled="true"/>   
    ……………  
    </settings>  
    ………………  
<system.net>  
```  
  
## 请参阅  
 [IPv6 寻址](../../../docs/framework/network-programming/ipv6-addressing.md)   
 [网络设置架构](../../../docs/framework/configure-apps/file-schema/network/index.md)   
 [\<ipv6\> 元素（网络设置）](../../../docs/framework/configure-apps/file-schema/network/ipv6-element-network-settings.md)