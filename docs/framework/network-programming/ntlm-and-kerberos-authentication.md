---
title: NTLM 和 Kerberos 身份验证
ms.date: 03/30/2017
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
ms.openlocfilehash: 254ffea79612c10f147984dda37d0117edbf9e3e
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/28/2018
ms.locfileid: "50190289"
---
# <a name="ntlm-and-kerberos-authentication"></a><span data-ttu-id="4f922-102">NTLM 和 Kerberos 身份验证</span><span class="sxs-lookup"><span data-stu-id="4f922-102">NTLM and Kerberos Authentication</span></span>
<span data-ttu-id="4f922-103">默认 NTLM 身份验证和 Kerberos 身份验证使用与调用应用程序关联的 Microsoft Windows NT 用户凭据来尝试通过服务器进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="4f922-103">Default NTLM authentication and Kerberos authentication use the Microsoft Windows NT user credentials associated with the calling application to attempt authentication with the server.</span></span> <span data-ttu-id="4f922-104">使用非默认 NTLM 身份验证时，应用程序会将认证类型设置为 NTLM，并使用 <xref:System.Net.NetworkCredential> 对象将用户名、密码和域传递给主机，如下例所示。</span><span class="sxs-lookup"><span data-stu-id="4f922-104">When using non-default NTLM authentication, the application sets the authentication type to NTLM and uses a <xref:System.Net.NetworkCredential> object to pass the user name, password, and domain to the host, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="4f922-105">需要使用应用程序用户凭据连接到 Internet 服务的应用程序可以使用用户默认凭据进行此操作，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="4f922-105">Applications that need to connect to Internet services using the credentials of the application user can do so with the user's default credentials, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="4f922-106">协商身份验证模块确定远程服务器使用 NTLM 身份验证还是 Kerberos 身份验证，并发送相应响应。</span><span class="sxs-lookup"><span data-stu-id="4f922-106">The negotiate authentication module determines whether the remote server is using NTLM or Kerberos authentication, and sends the appropriate response.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4f922-107">无法通过代理服务器进行 NTLM 身份验证。</span><span class="sxs-lookup"><span data-stu-id="4f922-107">NTLM authentication does not work through a proxy server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f922-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="4f922-108">See Also</span></span>  
 [<span data-ttu-id="4f922-109">基本和摘要式身份验证</span><span class="sxs-lookup"><span data-stu-id="4f922-109">Basic and Digest Authentication</span></span>](../../../docs/framework/network-programming/basic-and-digest-authentication.md)  
 [<span data-ttu-id="4f922-110">Internet 身份验证</span><span class="sxs-lookup"><span data-stu-id="4f922-110">Internet Authentication</span></span>](../../../docs/framework/network-programming/internet-authentication.md)
