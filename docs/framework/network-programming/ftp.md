---
title: "FTP | Microsoft Docs"
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
  - "FTP"
ms.assetid: 9b43f8b4-89d7-46a7-89fc-71aca916dd32
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# FTP
.NET Framework提供全面用于 <xref:System.Net.FtpWebRequest> 和 <xref:System.Net.FtpWebResponse> 选件类的FTP协议支持。  这些选件类从 <xref:System.Net.WebRequest> 和 <xref:System.Net.WebResponse>派生。  在大多数情况下， <xref:System.Net.WebRequest> 和 <xref:System.Net.WebResponse> 选件类提供所有需要发出请求，，但是，如果需要对作为属性公开的FTP特定功能的访问，可以强制转换这些选件类。 <xref:System.Net.FtpWebRequest> 或 <xref:System.Net.FtpWebResponse>。  
  
## 示例  
 有关更多信息，请参见以下主题: [如何：使用 FTP 下载文件](../../../docs/framework/network-programming/how-to-download-files-with-ftp.md)、 [如何：使用 FTP 上载文件](../../../docs/framework/network-programming/how-to-upload-files-with-ftp.md)和 [如何：使用 FTP 列出目录内容](../../../docs/framework/network-programming/how-to-list-directory-contents-with-ftp.md)。  
  
## FTP和代理  
 如果代理\(指定由 <xref:System.Net.FtpWebRequest.Proxy%2A> 属性\)是HTTP协议，则 <xref:System.Net.WebRequestMethods.Ftp.DownloadFile>、 <xref:System.Net.WebRequestMethods.Ftp.ListDirectory>并仅 <xref:System.Net.WebRequestMethods.Ftp.ListDirectoryDetails> 命令支持。  
  
## 请参阅  
 [通过代理访问 Internet](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)   
 [网络编程示例](../../../docs/framework/network-programming/network-programming-samples.md)   
 [FTP客户端技术示例](http://go.microsoft.com/fwlink/?LinkID=179557)   
 [FTP资源管理器技术示例](http://go.microsoft.com/fwlink/?LinkID=179569)   
 [使用应用程序协议](../../../docs/framework/network-programming/using-application-protocols.md)