---
title: "基本和摘要式身份验证 | Microsoft Docs"
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
  - "身份验证 [.NET Framework]，类"
  - "基本身份验证"
  - "身份验证 [.NET Framework]，基本"
  - "客户端身份验证，基本"
  - "用户身份验证，基本"
  - "身份验证 [.NET Framework]，摘要式"
  - "接收数据，身份验证"
  - "客户端身份验证，摘要式"
  - "Internet，身份验证"
  - "摘要式身份验证"
  - "发送数据，身份验证"
  - "网络资源，身份验证"
  - "用户身份验证，摘要式"
ms.assetid: 8cce2742-8d52-4643-9dd2-64ddf38aa878
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# 基本和摘要式身份验证
基本身份验证和摘要式身份验证的 <xref:System.Net> 实现符合RFC2617 – HTTP身份验证:基本身份验证和摘要式身份验证\(可在web联合的网站位于www.w3.org\)。  
  
 如下面的示例所示，若要使用基本身份验证和摘要式身份验证，应用程序必须提供用户名和密码在使用请求数据从Internet <xref:System.Net.WebRequest> 对象的属性， <xref:System.Net.WebRequest.Credentials%2A> 。  
  
```vb  
Dim MyURI As String = "http://www.contoso.com/"  
Dim WReq As WebRequest = WebRequest.Create(MyURI)  
WReq.Credentials = New NetworkCredential(UserName, SecurelyStoredPassword)  
```  
  
```csharp  
String MyURI = "http://www.contoso.com/";  
WebRequest WReq = WebRequest.Create(MyURI);  
WReq.Credentials = new NetworkCredential(UserName, SecurelyStoredPassword);  
```  
  
> [!CAUTION]
>  数据发送的基本身份验证和摘要式身份验证没有加密，因此，数据可以通过对手参见。  此外， \(用户名和密码\)未危险发送基本身份验证凭据和可被截获。  
  
## 请参阅  
 [NTLM 和 Kerberos 身份验证](../../../docs/framework/network-programming/ntlm-and-kerberos-authentication.md)   
 [Internet 身份验证](../../../docs/framework/network-programming/internet-authentication.md)