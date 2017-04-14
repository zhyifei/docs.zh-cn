---
title: "Internet 身份验证 | Microsoft Docs"
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
  - "IAuthenticationModule 接口"
  - "ICredentialLookup 接口"
  - "CredentialCache 类，关于 CredentialCache 类"
  - "接收数据，身份验证"
  - "AuthenticationManager 类，关于 AuthenticationManager 类"
  - "Internet，身份验证"
  - "发送数据，身份验证"
  - "网络资源，身份验证"
  - "用户身份验证，用于身份验证的类"
  - "NetworkCredential 类，关于 NetworkCredential 类"
  - "客户端身份验证，用于身份验证的类"
ms.assetid: d342e87c-f672-4660-a513-41a2f2b80c4a
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# Internet 身份验证
<xref:System.Net> 选件类支持各种客户端身份验证机制，包括基本标准Internet的身份验证方法，抽象类，协商， NTLM和Kerberos身份验证，以及可创建的自定义方法。  
  
 身份验证凭据 <xref:System.Net.NetworkCredential> 和 <xref:System.Net.CredentialCache> 选件类存储， <xref:System.Net.ICredentials> 实现接口。  当这些选件类之一为凭据中查询，则返回 **NetworkCredential** 选件类的实例。  身份验证过程由 <xref:System.Net.AuthenticationManager> 选件类管理，并且，实际身份验证过程由实现 <xref:System.Net.IAuthenticationModule> 接口的身份验证模块选件类执行。  ，才能使用，必须注册了 **AuthenticationManager** 的自定义身份验证模块它;基本的模块，抽象类，协商， NTLM，默认情况下，和Kerberos身份验证方法中注册。  
  
 **NetworkCredential** 存储设置凭据与URI标识的一个Internet资源并将其返回响应任何调用。 <xref:System.Net.NetworkCredential.GetCredential%2A> 方法。  访问Internet资源有限的或供应用程序使用同一在任何情况下都设置凭据的应用程序通常使用 **NetworkCredential** 选件类。  
  
 **CredentialCache** 选件类存储凭据的集合各种Web资源。  当 <xref:System.Net.CredentialCache.GetCredential%2A> 调用方法时， **CredentialCache** 返回相应设置凭据，由Web资源和请求的身份验证方案的URI。  使用不同的身份验证方案的各种Internet资源受益于使用 **CredentialCache** 选件类的应用程序，，因为它存储所有凭据并提供自己按请求。  
  
 当Internet资源请求身份验证时， <xref:System.Net.WebRequest.GetResponse%2A?displayProperty=fullName> 方法会 <xref:System.Net.WebRequest> 到 **AuthenticationManager** 使用需要的凭据。  请求根据以下然后验证过程:  
  
1.  **AuthenticationManager** 对每一个的 <xref:System.Net.IAuthenticationModule.Authenticate%2A> 方法注册的身份验证模块按注册的序列。  **AuthenticationManager** 使用不返回 **null** 执行身份验证过程的第一个模块。  过程的详细信息随所涉及的身份验证模块的类型。  
  
2.  当身份验证过程完成后，包含信息必需的访问Internet资源的身份验证模块返回 <xref:System.Net.Authorization> 到 **WebRequest** 。  
  
 某些身份验证方案可以验证用户，而无需先创建一个需要资源。  应用程序可以通过preauthenticating具有该资源的用户可以节省时间，从而消除至少一往返至服务器。  或者，还可以后执行身份验证在程序启动时才对用户的响应能力更强。  可以使用preauthentication的身份验证方案设置 [CanPreAuthenticate](frlrfsystemnetiauthenticationmoduleclasspreauthenticatetopic) 属性设置为 **true**。  
  
## 请参阅  
 [基本和摘要式身份验证](../../../docs/framework/network-programming/basic-and-digest-authentication.md)   
 [NTLM 和 Kerberos 身份验证](../../../docs/framework/network-programming/ntlm-and-kerberos-authentication.md)   
 [网络编程中的安全性](../../../docs/framework/network-programming/security-in-network-programming.md)