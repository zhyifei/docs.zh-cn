---
title: "证书选择和验证 | Microsoft Docs"
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
ms.assetid: c933aca2-4cd0-4ff1-9df9-267143f25a6f
caps.latest.revision: 15
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 15
---
# 证书选择和验证
<xref:System.Net> 选件类支持多种方式使用安全套接字层\(SSL\)连接选择和验证 <xref:System.Security.Cryptography.X509Certificates> 。  客户端可以选择一个或多个证书验证到服务器。  服务器可能需要客户端证书包含身份验证的一个或多个特定特性。  
  
## 定义  
 证书是包含一个公钥、属性的ASCII字节流\(例如版本号、号码和截止日期\)以及证书颁发机构的数字签名。  证书用于生成加密的连接或验证客户端到服务器。  
  
## 客户端证书选择和验证  
 客户端可以为给定的SSL连接选择一个或多个证书。  客户端证书可以与与web服务器或SMTP邮件服务器的SSL连接。  客户端添加证书。 <xref:System.Security.Cryptography.X509Certificates.X509Certificate> 或 <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> 选件类对象的集合。  使用电子邮件例如，证书集合是 <xref:System.Security.Cryptography.X509Certificates.X509CertificateCollection>的实例\)与 <xref:System.Net.Mail.SmtpClient> 选件类的 <xref:System.Net.Mail.SmtpClient.ClientCertificates%2A> 属性。  <xref:System.Net.HttpWebRequest> 选件类有一个类似的 <xref:System.Net.HttpWebRequest.ClientCertificates%2A> 属性。  
  
 <xref:System.Security.Cryptography.X509Certificates.X509Certificate> 和 <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> 选件类之间的主要区别在于私钥必须位于 <xref:System.Security.Cryptography.X509Certificates.X509Certificate> 选件类的证书存储区。  
  
 即使证书添加到集合并与特定SSL连接，证书不会被发送到服务器，除非服务器请求它们。  如果多个客户端证书在连接设置，将使用最佳一个基于考虑在证书颁发者列表服务器提供的和客户端证书颁发者名称之间的匹配算法。  
  
 <xref:System.Net.Security.SslStream> 选件类提供对SSL的更握手控件。  客户端可以指定要使用的客户端证书的委托选择。  
  
 远程服务器可以验证客户端证书有效，当前和签名由相应证书颁发机构。  可以将委托添加到 <xref:System.Net.ServicePointManager.ServerCertificateValidationCallback%2A> 强制证书验证。  
  
## 客户端证书选择  
 .NET Framework选择客户端证书按以下方式提供给服务器:  
  
1.  如果客户端证书以前存在到服务器时，缓存证书，当首次呈现和对于后续的客户端证书请求重复使用。  
  
2.  如果委托存在，请始终使用从委托的结果用作客户端证书选择。  尝试使用已缓存的证书，如果可能，但是，不要使用缓存的匿名凭据，如果委托返回null，并且证书集合不为null。  
  
3.  如果这是客户端证书的第一个挑战，结构枚举 <xref:System.Security.Cryptography.X509Certificates.X509Certificate> 的证书或 <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> 选件类对象与连接，查找在证书颁发者列表服务器提供的和客户端证书颁发者名称之间的匹配。  匹配的第一个证书发送到服务器。  如果证书不匹配或证书集合为空，则匿名凭据发送到服务器。  
  
## 用于证书配置的工具  
 许多工具进行客户端和服务器证书配置可用。  
  
 *Winhttpcertcfg.exe* 工具可用于配置客户端证书。  *Winhttpcertcfg.exe* 附带的工具为某个工具Windows Server 2003 Resource Kit。  此工具也可用作下载作为Windows Server 2003 Resource Kit工具的一部分在www.microsoft.com。  
  
 *HttpCfg.exe* 工具可用于配置 <xref:System.Net.HttpListener> 选件类的服务器证书。  *HttpCfg.exe* 工具提供作为参数之一为Windows Server 2003和Windows XP Service Pack 2.的支持工具。  默认情况下*HttpCfg.exe* 和其他在Windows Server 2003或Windows XP支持工具未安装。  在Windows Server 2003。  支持工具在Windows Server 2003 CD\-ROM单独安装将以下文件夹和文件:  
  
 \\支持\\ tools \\ Suptools.msi  
  
 用于Windows XP Service Pack 2的使用， Windows XP支持工具可用作从www.microsoft.com中下载。  
  
 为 *HttpCfg.exe* 工具版本的源代码还提供作为示例Windows server SDK。  为以下文件夹下，的Windows SDK的一部分。 *HttpCfg.exe* 示例的默认情况下源代码安装与网络连接示例:  
  
 *C:\\Program Files\\Microsoft SDKs \\ Windows \\ v1.0 \\ samples \\ NetDS \\ HTTP \\ serviceconfig*  
  
 除了这些工具外， <xref:System.Security.Cryptography.X509Certificates.X509Certificate> 和 <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> 选件类用于加载证书提供方法从文件系统。  
  
## 请参阅  
 [网络编程中的安全性](../../../docs/framework/network-programming/security-in-network-programming.md)   
 [.NET Framework 中的网络编程](../../../docs/framework/network-programming/index.md)