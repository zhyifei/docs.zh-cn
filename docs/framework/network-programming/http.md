---
title: "HTTP | Microsoft Docs"
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
  - "协议，HTTP"
  - "发送数据，HTTP"
  - "HttpWebResponse 类，发送和接收数据"
  - "HTTP"
  - "接收数据，HTTP"
  - "应用程序协议，HTTP"
  - "Internet，HTTP"
  - "网络资源，HTTP"
  - "HTTP，关于 HTTP"
  - "HttpWebRequest 类，发送和接收数据"
ms.assetid: 985fe5d8-eb71-4024-b361-41fbdc1618d8
caps.latest.revision: 10
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 8
---
# HTTP
.NET Framework提供全面的HTTP协议支持，构成多数人所有Internet通信，与<xref:System.Net.HttpWebRequest> 和 <xref:System.Net.HttpWebResponse> 选件类。  这些选件类，从派生 <xref:System.Net.WebRequest> 和 <xref:System.Net.WebResponse>，返回默认情况下，只要该静态方法 <xref:System.Net.WebRequest.Create%2A?displayProperty=fullName> 从“HTTP”或“https启动”遇到URI。  在大多数情况下， **WebRequest** 和 **WebResponse** 选件类提供所有需要发出请求，，但是，如果需要对作为属性公开的HTTP特定功能的访问，可以强制转换这些选件类。 **HttpWebRequest** 或 **HttpWebResponse**。  
  
 **HttpWebRequest** 和 **HttpWebResponse** 封装一个标准HTTP请求和响应事务并提供对常见HTTP标头。  这些选件类还支持大多数HTTP 1.1功能，包括流水线处理?，发送和接收以增加的数据，身份验证， preauthentication，加密，代理支持，服务器证书验证和连接管理。  可以存储自定义通过属性没有提供的标头和标头并将 **标头** 属性访问。  
  
 ，然后才能通过URI到 **WebRequest.Create** 方法之前，**HttpWebRequest** 是 **WebRequest** 使用的默认选件类，并不需要注册。  
  
 可以使应用程序遵循HTTP通过设置 <xref:System.Net.HttpWebRequest.AllowAutoRedirect%2A> 属性自动重定向到 **true** \(默认值\)。  应用程序请求重定向，并且， **HttpWebResponse**[ResponseURI](frlrfsystemnethttpwebresponseclassresponseuritopic) 属性将包含响应请求的实际Web资源。  如果设置 **AllowAutoRedirect** 到 **false**，应用程序必须能够处理重定向用作HTTP协议错误。  
  
 应用程序通过捕捉 <xref:System.Net.WebException> 接收HTTP协议错误和 <xref:System.Net.WebException.Status%2A> 设置为 [WebExceptionStatus.ProtocolError](frlrfsystemnetwebexceptionstatusclasstopic)。  <xref:System.Net.WebException.Response%2A> 属性包含服务器发送的 **WebResponse** 并指示遇到的实际HTTP错误。  
  
## 请参阅  
 [通过代理访问 Internet](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)   
 [使用应用程序协议](../../../docs/framework/network-programming/using-application-protocols.md)   
 [如何：访问 HTTP 特定的属性](../../../docs/framework/network-programming/how-to-access-http-specific-properties.md)