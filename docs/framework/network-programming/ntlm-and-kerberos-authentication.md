---
title: "NTLM 和 Kerberos 身份验证 | Microsoft Docs"
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
  - "身份验证 [.NET Framework]，NTLM"
  - "身份验证 [.NET Framework]，Kerberos"
  - "用户身份验证，Kerberos"
  - "用户身份验证，NTLM"
  - "Kerberos 身份验证"
  - "接收数据，身份验证"
  - "NTLM 身份验证"
  - "Internet，身份验证"
  - "客户端身份验证，Kerberos"
  - "发送数据，身份验证"
  - "网络资源，身份验证"
  - "类 [.NET Framework]，身份验证"
  - "客户端身份验证，NTLM"
ms.assetid: 9ef65560-f596-4469-bcce-f4d5407b55cd
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# NTLM 和 Kerberos 身份验证
默认NTLM身份验证，而Kerberos Microsoft Windows NT用户凭据与调用应用程序尝试与服务器的身份验证的身份验证。  如下面的示例所示，当使用非默认的NTLM身份验证时，应用程序设置身份验证类型为NTLM并使用 <xref:System.Net.NetworkCredential> 对象将用户名、密码和字段添加到宿主，。  
  
```vb  
Dim MyURI As String = "http://www.contoso.com/"  
Dim WReq As WebRequest = WebRequest.Create(MyURI)  
WReq.Credentials = _  
    New NetworkCredential(UserName, SecurelyStoredPassword, Domain)  
```  
  
```csharp  
String MyURI = "http://www.contoso.com/";  
WebRequest WReq = WebRequest.Create (MyURI);  
WReq.Credentials =   
    new NetworkCredential(UserName, SecurelyStoredPassword, Domain);  
```  
  
 需要连接到Internet服务使用应用程序用户的凭据，如下面的示例所示的应用程序可能会执行与用户的默认凭据，。  
  
```vb  
Dim MyURI As String = "http://www.contoso.com/"  
Dim WReq As WebRequest = WebRequest.Create(MyURI)  
WReq.Credentials = CredentialCache.DefaultCredentials  
```  
  
```csharp  
String MyURI = "http://www.contoso.com/";  
WebRequest WReq = WebRequest.Create (MyURI);  
WReq.Credentials = CredentialCache.DefaultCredentials;  
```  
  
 协调身份验证模块确定远程服务器是否使用NTLM或Kerberos身份验证，并将相应的响应。  
  
> [!NOTE]
>  NTLM身份验证不会通过代理服务器工作。  
  
## 请参阅  
 [基本和摘要式身份验证](../../../docs/framework/network-programming/basic-and-digest-authentication.md)   
 [Internet 身份验证](../../../docs/framework/network-programming/internet-authentication.md)