---
title: "从 WebRequest 派生 | Microsoft Docs"
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
  - "WebRequest 类，可插入协议"
  - "特定于协议的请求处理程序"
  - "发送数据，可插入协议"
  - "可插入协议，类条件"
  - "Internet，可插入协议"
  - "接收数据，可插入协议"
  - "协议，可插入"
ms.assetid: 9810c177-973e-43d7-823c-14960bd625ea
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 7
---
# 从 WebRequest 派生
<xref:System.Net.WebRequest> 选件类是创建一个协议特殊化请求处理程序提供基本的方法和属性是.NET Framework可插入协议模型的抽象基类。  使用 **WebRequest** 选件类的应用程序可以请求数据使用任何支持的协议，而无需指定要使用的协议。  
  
 必须满足两个条件为可插入协议中使用的协议特殊化选件类:选件类必须实现接口， <xref:System.Net.IWebRequestCreate> ，它必须具有 <xref:System.Net.WebRequest.RegisterPrefix%2A?displayProperty=fullName> 方法进行注册。  选件类必须重写 **WebRequest** 所有抽象方法和属性提供可插入的接口。  
  
 **WebRequest** 实例供一次性使用;如果要使另一个请求，则创建一个新的 **WebRequest**。  **WebRequest** 支持 <xref:System.Runtime.Serialization.ISerializable> 接口允许开发人员序列化模板 **WebRequest** 然后重新生成附加请求的模板。  
  
## IWebRequest创建方法  
 <xref:System.Net.IWebRequestCreate.Create%2A> 方法以初始化协议特殊化选件类的新实例负责。  在新 **WebRequest** 创建时， <xref:System.Net.WebRequest.Create%2A?displayProperty=fullName> 方法对请求的URI以URI前缀将向 **RegisterPrefix** 方法中注册。  相应的协议特殊化后代的 **创建** 方法必须返回该后代的初始化的实例的执行协议的一个标准请求\/响应事务不需要修改的任何协议特殊化字段。  
  
## ConnectionGroupName属性  
 <xref:System.Net.WebRequest.ConnectionGroupName%2A> 属性用于命名连接的一组的资源，以便多个请求可以在单个连接。  若要实现连接共享，因此您必须使用合并和分配连接一个协议特殊化方法。  例如，提供的 <xref:System.Net.ServicePointManager> 选件类实现共享功能 <xref:System.Net.HttpWebRequest> 选件类的连接。  为每个连接组提供与特定的服务器的连接的 **ServicePointManager** 选件类创建 <xref:System.Net.ServicePoint> 。  
  
## ContentLength属性  
 <xref:System.Net.WebRequest.ContentLength%2A> 属性指定字节数将发送到服务器时，上载数据中的数据。  
  
 通常必须设置 <xref:System.Net.WebRequest.Method%2A> 属性指示上载时，会发生 **ContentLength** 属性相对于零时设置为值大于。  
  
## ContentType属性  
 <xref:System.Net.WebRequest.ContentType%2A> 属性提供任何特定的信息。协议要求您发送到服务器识别正在发送内容的类型。  这通常是上载的所有数据的MIME内容类型。  
  
## 凭据属性  
 <xref:System.Net.WebRequest.Credentials%2A> 属性包含必需的信息验证与服务器的请求。  您必须实现的详细信息为您的协议身份验证过程。  <xref:System.Net.AuthenticationManager> 选件类为验证请求和提供身份验证令牌负责。  提供自己的协议使用的凭据的选件类必须实现 <xref:System.Net.ICredentials> 接口。  
  
## 标头属性  
 <xref:System.Net.WebRequest.Headers%2A> 属性包含名称\/值的任意集合对元数据与该请求。  可以表示为名称\/值的协议要求的所有元数据在 **标头** 属性对可以包含。  通常必须在调用 <xref:System.Net.WebRequest.GetRequestStream%2A> 或 <xref:System.Net.WebRequest.GetResponse%2A> 方法之前设置此信息;一次该请求，元数据被视为只读。  
  
 您无需使用 **标头** 属性使用标头元数据。  协议特殊化元数据都显示为属性;例如， <xref:System.Net.HttpWebRequest.UserAgent%2A?displayProperty=fullName> 属性公开 **User\-Agent** HTTP标头。  当显示标头元数据作为属性时，使用 **标头** 属性，则不应允许同一属性设置。  
  
## 方案属性  
 <xref:System.Net.WebRequest.Method%2A> 属性包含该谓词或操作请求需要服务器执行。  **方法** 属性的默认值必须启用标准请求\/响应事件不需要任何协议特殊化属性设置为。  例如， [HttpWebResponse](frlrfSystemNetHttpWebResponseClassMethodTopic) 方法默认访问，从Web服务器请求的资源并返回响应。  
  
 通常比零必须设置 **ContentLength** 属性设置为值，当 **方法** 属性设置为以指示的谓词或操作时上载发生。  
  
## PreAuthenticate属性  
 应用程序设置 <xref:System.Net.WebRequest.PreAuthenticate%2A> 属性指示应该将身份验证信息与初始请求而不是等待身份验证难题。  ，如果协议支持身份验证凭据发送的初始请求， **预先进行身份验证** 属性仅是有意义的。  
  
## 代理属性  
 <xref:System.Net.WebRequest.Proxy%2A> 属性包含用于访问所请求资源的一 <xref:System.Net.IWebProxy> 接口。  ，仅当您的协议支持proxied请求， **代理** 属性是有意义的。  ，如果您的协议，需要一个必须设置默认代理。  
  
 在某些环境下，例如在公司firewall后，可能需要您的协议使用代理。  在这种情况下，必须实现接口 **IWebProxy** 创建专为协议将运行的代理选件类。  
  
## RequestUri属性  
 传递给 **WebRequest.Create** 方法的 <xref:System.Net.WebRequest.RequestUri%2A> 属性包含URI。  ，在 **WebRequest** 创建的，它是只读的，不能更改。  如果您的协议支持重定向，响应可能来自其他URI标识的资源。  如果需要提供对响应的URI，必须提供包含该URI的附加属性。  
  
## 超时属性  
 <xref:System.Net.WebRequest.Timeout%2A> 属性以毫秒为单位包含时间长度，，在发出请求之前等待时间并引发异常。  **超时** 仅适用于使用 <xref:System.Net.WebRequest.GetResponse%2A> 方法所做的同步请求;异步请求必须使用 <xref:System.Net.WebRequest.Abort%2A> 方法取消挂起的请求。  
  
 ，仅当协议特殊化选件类实现超时进程，设置 **超时** 属性是有意义的。  
  
## 中止方法  
 <xref:System.Net.WebRequest.Abort%2A> 方法取消挂起的异步请求到服务器。  在请求取消后，调用 **GetResponse**， **BeginGetResponse**、 **EndGetResponse**、 **GetRequestStream**、 **BeginGetRequestStream**或 **EndGetRequestStream** 将引发以及 <xref:System.Net.WebException.Status%2A> 属性的 <xref:System.Net.WebException> 设置为 [RequestCanceled](frlrfSystemNetWebExceptionStatusClassTopic)。  
  
## BeginGetRequestStream和EndGetRequestStream方法  
 <xref:System.Net.WebRequest.BeginGetRequestStream%2A> 方法启动异步请求使用对服务器、数据的流。  <xref:System.Net.WebRequest.EndGetRequestStream%2A> 方法完成该异步请求并返回请求的流。  使用标准.NET Framework异步模式，这些方法执行 **GetRequestStream** 方法。  
  
## BeginGetResponse和EndGetResponse方法  
 <xref:System.Net.WebRequest.BeginGetResponse%2A> 方法启动异步请求到服务器。  <xref:System.Net.WebRequest.EndGetResponse%2A> 方法完成该异步请求并返回请求的响应。  使用标准.NET Framework异步模式，这些方法执行 **GetResponse** 方法。  
  
## GetRequestStream方法  
 <xref:System.Net.WebRequest.GetRequestStream%2A> 方法返回使用到所请求的服务器上写入数据的流。  返回的流应不希望的只读流;旨在用作到服务器编写的单向数据流。  流返回错误 <xref:System.IO.Stream.CanRead%2A> 和 <xref:System.IO.Stream.CanSeek%2A> 属性并为 <xref:System.IO.Stream.CanWrite%2A> 属性设置为true。  
  
 **GetRequestStream** 方法在返回流之前通常会打开与服务器的连接，因此，发送，指示的标题信息数据发送到服务器。  由于 **GetRequestStream** 启动该请求，将任何 **标头** 属性或 **ContentLength** 属性不在调用 **GetRequestStream**后通常允许。  
  
## GetResponse方法  
 <xref:System.Net.WebRequest.GetResponse%2A> 方法返回表示来自服务器的响应 <xref:System.Net.WebResponse> 选件类的一个协议特殊化子代。  除非 **GetRequestStream** 方法已启动了请求， **GetResponse** 方法创建与 **RequestUri**标识的资源的连接，发送指示请求的类型标头信息进行，然后接收来自资源的答案。  
  
 在 **GetResponse** 方法调用，应考虑所有属性是只读的。  **WebRequest** 实例供一次性使用;如果要使另一个请求，则应创建新的 **WebRequest**。  
  
 **GetResponse** 方法将创建一个适当的 **WebResponse** 子代负责包含传入响应。  
  
## 请参阅  
 <xref:System.Net.WebRequest>   
 <xref:System.Net.HttpWebRequest>   
 <xref:System.Net.FileWebRequest>   
 [对可插入协议进行编程](../../../docs/framework/network-programming/programming-pluggable-protocols.md)   
 [从 WebResponse 派生](../../../docs/framework/network-programming/deriving-from-webresponse.md)