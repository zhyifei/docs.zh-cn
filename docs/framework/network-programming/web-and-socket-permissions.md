---
title: "Web 和套接字权限 | Microsoft Docs"
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
helpviewer_keywords: 
  - "网络"
  - "位置 [.NET Framework]，接受"
  - "套接字，权限"
  - "网络，权限"
  - "Internet，权限"
  - "网络资源"
  - "SocketPermission 类，关于 SocketPermission 类"
  - "位置 [.NET Framework]，连接"
  - "WebPermission 类，关于 WebPermission 类"
  - "权限 [.NET Framework]，套接字"
  - "安全性 [.NET Framework]，Internet"
  - "位置 [.NET Framework]，授予"
ms.assetid: d51ad8cb-03ae-4a51-bfcd-cfcf6b98afa9
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# Web 和套接字权限
使用 <xref:System.Net> 命名空间 <xref:System.Net.WebPermission> 和 <xref:System.Net.SocketPermission> 选件类提供应用程序的Internet安全性。  **WebPermission** 选件类控制应用程序的权限请求来自URI的数据或服务URI到Internet。  **SocketPermission** 选件类控制应用程序的权限由使用 <xref:System.Net.Sockets.Socket> 接受数据有关本地或端口与远程计算机使用传输协议在另一个地址，基于套接字的主机、端口号和传输协议。  
  
 哪些权限选件类使用取决于您的应用程序类型。  使用 <xref:System.Net.WebRequest> 及其后代的应用程序应使用 **WebPermission** 选件类管理权限。  使用存储级访问的应用程序应使用 **SocketPermission** 选件类管理权限。  
  
 **WebPermission** 和 **SocketPermission** 定义两个权限:接受并连接。  接受向应用程序授予响应来自对方的传入连接。  连接向应用程序授予首次与另一方的连接。  
  
 对于 **SocketPermission** 实例，接受意味着应用程序可以接受在本地传输地址的传入连接;连接意味着应用程序可以连接到某个远程的\(或本地\)传输地址。  
  
 对于 **WebPermission** 实例，接受意味着应用程序可以对the world导出 **WebPermission** 控件的URI;连接意味着应用程序可以URI的访问\(它是远程或本地\)。  
  
## 请参阅  
 [安全性](../../../docs/standard/security/index.md)   
 [网络编程中的安全性](../../../docs/framework/network-programming/security-in-network-programming.md)