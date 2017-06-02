---
title: "从 WebResponse 派生 | Microsoft Docs"
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
  - "从 WebResponse 派生"
ms.assetid: f11d4866-a199-4087-9306-a5a4c18b13db
caps.latest.revision: 7
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 7
---
# 从 WebResponse 派生
<xref:System.Net.WebResponse> 选件类是创建一个协议特殊化响应提供基本的方法和属性是.NET Framework可插入协议模型的抽象基类。  使用 <xref:System.Net.WebRequest> 选件类请求资源的数据的应用程序接收到 **WebResponse**的答案。  协议特殊化 **WebResponse** 子代必须实现 **WebResponse** 选件类的抽象成员。  
  
 关联的 **WebRequest** 选件类必须创建 **WebResponse** 子代。  例如，由于调用 <xref:System.Net.HttpWebRequest.GetResponse%2A?displayProperty=fullName> 或 <xref:System.Net.HttpWebRequest.EndGetResponse%2A?displayProperty=fullName>， <xref:System.Net.HttpWebResponse> 实例仅创建。  每 **WebResponse** 包含请求的结果对资源和不应由重用。  
  
## ContentLength属性  
 <xref:System.Net.WebResponse.ContentLength%2A> 属性指示字节数从 <xref:System.Net.WebResponse.GetResponseStream%2A> 方法返回的流中可用的数据。  **ContentLength** 属性不指示字节数服务器或元数据信息返回的标头;它仅指示字节数在请求的资源的数据。  
  
## ContentType属性  
 <xref:System.Net.WebResponse.ContentType%2A> 属性提供任何特定的信息。协议要求您向客户端发送标识服务器发送的内容的类型。  这通常是返回的所有数据的MIME内容类型。  
  
## 标头属性  
 <xref:System.Net.WebResponse.Headers%2A> 属性包含名称\/值的任意集合对元数据与响应。  可以表示为名称\/值的协议要求的所有元数据在 **标头** 属性对可以包含。  
  
 您无需使用 **标头** 属性使用标头元数据。  协议特殊化元数据都显示为属性;例如， <xref:System.Net.HttpWebResponse.LastModified%2A?displayProperty=fullName> 属性公开 **Last\-Modified** HTTP标头。  当显示标头元数据作为属性时，使用 **标头** 属性，则不应允许同一属性设置。  
  
## ResponseUri属性  
 <xref:System.Net.WebResponse.ResponseUri%2A> 属性包含实际提供响应资源的URI。  对于不支持重定向的协议， **ResponseUri** 与该创建响应 **WebRequest** 的 <xref:System.Net.WebRequest.RequestUri%2A> 属性。  如果协议支持将请求重定向， **ResponseUri** 将包含响应的URI。  
  
## close方法  
 <xref:System.Net.WebResponse.Close%2A> 方法关闭请求和响应生成的所有连接并清理响应使用的资源。  **关闭** 方法结束响应使用的所有流实例，但是，它不会引发异常，如果响应流通过对 <xref:System.IO.Stream.Close%2A?displayProperty=fullName> 方法的调用之前关闭。  
  
## GetResponseStream方法  
 <xref:System.Net.WebResponse.GetResponseStream%2A> 方法返回包含从请求资源的流响应。  响应流包含该资源返回的是数据;应从响应中去除并显示在响应或元数据中包含的所有标头在应用程序通过协议特殊化属性或 **标头** 属性。  
  
 **GetResponseStream** 方法返回的流实例由应用程序拥有，并且可以关闭，并且无需关闭 **WebResponse**。  按照约定，调用 **WebResponse.Close** 方法也关闭 **GetResponse**返回的流。  
  
## 请参阅  
 <xref:System.Net.WebResponse>   
 <xref:System.Net.HttpWebResponse>   
 <xref:System.Net.FileWebResponse>   
 [对可插入协议进行编程](../../../docs/framework/network-programming/programming-pluggable-protocols.md)   
 [从 WebRequest 派生](../../../docs/framework/network-programming/deriving-from-webrequest.md)