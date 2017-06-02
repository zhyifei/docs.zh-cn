---
title: "创建 Internet 请求 | Microsoft Docs"
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
  - "WebRequest 类，发送和接收数据"
  - "网络"
  - "HttpWebResponse 类，发送和接收数据"
  - "从 Internet 请求数据，创建请求"
  - "网络资源"
  - "Internet，请求数据"
  - "数据请求，创建请求"
ms.assetid: faab683e-3f1e-4eee-b5e9-59f7245033d5
caps.latest.revision: 8
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 8
---
# 创建 Internet 请求
应用程序通过 <xref:System.Net.WebRequest.Create%2A?displayProperty=fullName> 方法创建 <xref:System.Net.WebRequest> 实例。  这是创建从 **WebRequest** 派生的类选件基于URI方案传递给它的静态方法。  
  
## Web、文件和FTP请求  
 .NET Framework提供 <xref:System.Net.HttpWebRequest> 选件类，从 **WebRequest**派生，处理HTTP和HTTPS请求。  在大多数情况下， **WebRequest** 选件类提供您所请求的所有属性;但是，如果需要，您可以将 **WebRequest.Create** 方法创建的 **WebRequest** 对象。 **HttpWebRequest** 类型访问该请求的HTTP特定特性。  同样， **HttpWebResponse** 对象处理从HTTP和HTTPS请求的响应。  访问 **HttpWebResponse** 对象，您的HTTP特定属性需要转换为 **HttpWebResponse** 类型的 **WebResponse** 对象。  
  
 .NET Framework还提供 <xref:System.Net.FileWebRequest> ，并处理的 <xref:System.Net.FileWebResponse> 选件类请求使用“文件的资源: ” URI方案。  同样， <xref:System.Net.FtpWebRequest> 和 <xref:System.Net.FtpWebResponse> 选件类提供处理请求时使用“FTP的资源: ”模式。  如果您的请求针对使用这些模式中的任何一个的资源，可以使用 **WebRequest.Create** 方法获取对请求对象。  
  
 处理请求的其他应用程序级协议，您需要实现从 **WebRequest** 和 **WebResponse**派生的协议特殊化选件类。  有关更多信息，请参见 [编程的可插入协议](../../../docs/framework/network-programming/programming-pluggable-protocols.md)。  
  
## 请参阅  
 [如何使用 WebRequest 类请求数据](../../../docs/framework/network-programming/how-to-request-data-using-the-webrequest-class.md)   
 [正在请求数据...](../../../docs/framework/network-programming/requesting-data.md)