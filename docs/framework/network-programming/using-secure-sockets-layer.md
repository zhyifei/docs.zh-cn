---
title: "使用安全套接字层 | Microsoft Docs"
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
  - "SSL"
  - "安全套接字层"
  - "从 Internet 请求数据，安全套接字层"
  - "发送数据，安全套接字层"
  - "网络资源"
  - "数据请求，安全套接字层"
  - "接收数据，安全套接字层"
  - "Internet，安全套接字层"
ms.assetid: 6e4289e6-d1b7-4e82-ab0d-e83e3b6063ed
caps.latest.revision: 14
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 14
---
# 使用安全套接字层
<xref:System.Net> 选件类使用安全套接字层\(SSL\)加密几种网络协议的连接。  
  
 对HTTP连接， <xref:System.Net.WebRequest> 和 <xref:System.Net.WebResponse> 选件类使用SSL与支持SSL的WEB宿主通信。  使用SSL的决策由赋予它的 <xref:System.Net.WebRequest> 选件类进行，具体取决于URI。  如果URI从“https开头为: ”，使用SSL;如果URI从“HTTP开始: ”，使用未加密的连接。  
  
 若要使用文件传输协议\(FTP\)的SSL，请设置 <xref:System.Net.FtpWebRequest.EnableSsl> 属性在调用 <xref:System.Net.FtpWebRequest.GetResponse>之前为true。  同样，应用于具有简单邮件传输协议\(SMTP\)的使用SSL，请设置 <xref:System.Net.Mail.SmtpClient.EnableSsl> 属性在将电子邮件发送到之前为true。  
  
 <xref:System.Net.Security.SslStream> 选件类为SSL提供基于流的抽象，并且提供了许多方式配置SSL握手。  
  
## 示例  
  
### 代码  
  
```vb  
Dim MyURI As String = "https://www.contoso.com/"  
Dim Wreq As WebRequest = WebRequest.Create(MyURI)  
  
Dim serverUri As String = "ftp://ftp.contoso.com/file.txt"  
Dim request As FtpWebRequest = CType(WebRequest.Create(serverUri), FtpWebRequest)  
request.Method = WebRequestMethods.Ftp.DeleteFile  
request.EnableSsl = True  
Dim response As FtpWebResponse = CType(request.GetResponse(), FtpWebResponse)  
```  
  
```csharp  
String MyURI = "https://www.contoso.com/";  
WebRequest WReq = WebRequest.Create(MyURI);  
  
String serverUri = "ftp://ftp.contoso.com/file.txt"  
FtpWebRequest request = (FtpWebRequest)WebRequest.Create(serverUri);  
request.EnableSsl = true;  
request.Method = WebRequestMethods.Ftp.DeleteFile;  
FtpWebResponse response = (FtpWebResponse)request.GetResponse();  
```  
  
## 编译代码  
 此示例需要：  
  
-   对 **System.Net** 命名空间。  
  
## 请参阅  
 [网络编程中的安全性](../../../docs/framework/network-programming/security-in-network-programming.md)   
 [.NET Framework 中的网络编程](../../../docs/framework/network-programming/index.md)   
 [证书选择和验证](../../../docs/framework/network-programming/certificate-selection-and-validation.md)