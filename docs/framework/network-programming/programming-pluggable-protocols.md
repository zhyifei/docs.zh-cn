---
title: "对可插入协议进行编程 | Microsoft Docs"
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
  - "下载 Internet 资源，可插入协议"
  - "WebRequest 类，可插入协议"
  - "响应 Internet 请求，可插入协议"
  - "WebResponse 类，可插入协议"
  - "发送数据，可插入协议"
  - "网络资源，可插入协议"
  - "Internet，可插入协议"
  - "对可插入协议进行编程"
  - "可插入协议，编程"
  - "从 Internet 请求数据，可插入协议"
  - "接收数据，可插入协议"
  - "协议，可插入"
ms.assetid: 66ef8456-7576-4e97-8956-959b216373db
caps.latest.revision: 12
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 12
---
# 对可插入协议进行编程
抽象 <xref:System.Net.WebRequest> 和 <xref:System.Net.WebResponse> 选件类为可插入协议提供了基础。  通过派生协议特殊化选件类从 <xref:System.Net.WebRequest> 和 <xref:System.Net.WebResponse>，应用程序可以请求从Internet资源的数据和读取响应，而无需指定要使用的协议。  
  
 在可以创建协议特殊化 <xref:System.Net.WebRequest>之前，必须其注册创建方法。  使用 <xref:System.Net.WebRequest> 静态 <xref:System.Net.WebRequest.RegisterPrefix%28System.String%2CSystem.Net.IWebRequestCreate%29> 方法注册 <xref:System.Net.WebRequest> 子代处理设置请求绑定到特定的Internet模式，为模式和服务器，或访问模式、服务器和路径。  
  
 在大多数情况下，可以发送和接收数据使用 <xref:System.Net.WebRequest> 的方法和属性类中。  但是，因此，如果需要访问协议特殊化属性，可以转换 <xref:System.Net.WebRequest> 到特定派生类的实例。  
  
 若要利用可插入协议，您的 <xref:System.Net.WebRequest> 子代必须提供不需要协议特殊化属性设置的默认值请求和响应事务。  例如， <xref:System.Net.HttpWebRequest> 选件类，默认情况下实现HTTP的 <xref:System.Net.WebRequest> 选件类，提供包含从Web服务器返回的流中的 `GET` 请求并返回 <xref:System.Net.HttpWebResponse> 。  
  
## 请参阅  
 [从 WebRequest 派生](../../../docs/framework/network-programming/deriving-from-webrequest.md)   
 [从 WebResponse 派生](../../../docs/framework/network-programming/deriving-from-webresponse.md)   
 [.NET Framework 中的网络编程](../../../docs/framework/network-programming/index.md)   
 [如何：转换 WebRequest 以访问特定于协议的属性](../../../docs/framework/network-programming/how-to-typecast-a-webrequest-to-access-protocol-specific-properties.md)