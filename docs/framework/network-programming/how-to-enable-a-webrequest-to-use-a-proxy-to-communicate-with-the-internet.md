---
title: "如何：使 WebRequest 能够使用代理以与 Internet 通信 | Microsoft Docs"
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
ms.assetid: 63c0ef2c-44b5-4c54-9804-ba0b9b001ac7
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# 如何：使 WebRequest 能够使用代理以与 Internet 通信
此示例创建将使所有 <xref:System.Net.WebRequest> 使用代理与Internet通信的全局代理实例。  此示例假定，该代理服务器名为 `webproxy` ，它位于端口80通信，标准HTTP端口。  
  
## 示例  
  
```csharp  
WebProxy proxyObject = new WebProxy("http://webproxy:80/");  
GlobalProxySelection.Select = proxyObject;  
```  
  
```vb  
Dim proxyObject As WebProxy = New WebProxy("http://webproxy:80/")  
GlobalProxySelection.Select = proxyObject  
```  
  
## 编译代码  
 此示例需要：  
  
-   对 **System.Net** 命名空间。  
  
## 请参阅  
 [使用应用程序协议](../../../docs/framework/network-programming/using-application-protocols.md)   
 [通过代理访问 Internet](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)