---
title: "NTLM 和 Kerberos 身份验证"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- authentication [.NET Framework], NTLM
- authentication [.NET Framework], Kerberos
- user authentication, Kerberos
- user authentication, NTLM
- Kerberos authentication
- receiving data, authentication
- NTLM authentication
- Internet, authentication
- client authentication, Kerberos
- sending data, authentication
- network resources, authentication
- classes [.NET Framework], authentication
- client authentication, NTLM
ms.assetid: 9ef65560-f596-4469-bcce-f4d5407b55cd
caps.latest.revision: "9"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 36e88b163ab857180a02278828dba7dcec457736
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ntlm-and-kerberos-authentication"></a><span data-ttu-id="8f064-102">NTLM 和 Kerberos 身份验证</span><span class="sxs-lookup"><span data-stu-id="8f064-102">NTLM and Kerberos Authentication</span></span>
<span data-ttu-id="8f064-103">默认 NTLM 身份验证和 Kerberos 身份验证使用与调用应用程序关联的 Microsoft Windows NT 用户凭据来尝试通过服务器进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="8f064-103">Default NTLM authentication and Kerberos authentication use the Microsoft Windows NT user credentials associated with the calling application to attempt authentication with the server.</span></span> <span data-ttu-id="8f064-104">使用非默认 NTLM 身份验证时，应用程序会将认证类型设置为 NTLM，并使用 <xref:System.Net.NetworkCredential> 对象将用户名、密码和域传递给主机，如下例所示。</span><span class="sxs-lookup"><span data-stu-id="8f064-104">When using non-default NTLM authentication, the application sets the authentication type to NTLM and uses a <xref:System.Net.NetworkCredential> object to pass the user name, password, and domain to the host, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="8f064-105">需要使用应用程序用户凭据连接到 Internet 服务的应用程序可以使用用户默认凭据进行此操作，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="8f064-105">Applications that need to connect to Internet services using the credentials of the application user can do so with the user's default credentials, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="8f064-106">协商身份验证模块确定远程服务器使用 NTLM 身份验证还是 Kerberos 身份验证，并发送相应响应。</span><span class="sxs-lookup"><span data-stu-id="8f064-106">The negotiate authentication module determines whether the remote server is using NTLM or Kerberos authentication, and sends the appropriate response.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8f064-107">无法通过代理服务器进行 NTLM 身份验证。</span><span class="sxs-lookup"><span data-stu-id="8f064-107">NTLM authentication does not work through a proxy server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f064-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8f064-108">See Also</span></span>  
 [<span data-ttu-id="8f064-109">基本和摘要式身份验证</span><span class="sxs-lookup"><span data-stu-id="8f064-109">Basic and Digest Authentication</span></span>](../../../docs/framework/network-programming/basic-and-digest-authentication.md)  
 [<span data-ttu-id="8f064-110">Internet 身份验证</span><span class="sxs-lookup"><span data-stu-id="8f064-110">Internet Authentication</span></span>](../../../docs/framework/network-programming/internet-authentication.md)
