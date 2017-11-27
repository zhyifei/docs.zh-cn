---
title: "基本和摘要式身份验证"
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
- authentication [.NET Framework], classes
- Basic authentication
- authentication [.NET Framework], basic
- client authentication, basic
- user authentication, basic
- authentication [.NET Framework], digest
- receiving data, authentication
- client authentication, digest
- Internet, authentication
- digest authentication
- sending data, authentication
- network resources, authentication
- user authentication, digest
ms.assetid: 8cce2742-8d52-4643-9dd2-64ddf38aa878
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: a72635cb77f23e2b87abb54f3f6a4438a3019f22
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="basic-and-digest-authentication"></a><span data-ttu-id="a5898-102">基本和摘要式身份验证</span><span class="sxs-lookup"><span data-stu-id="a5898-102">Basic and Digest Authentication</span></span>
<span data-ttu-id="a5898-103">基本身份验证和摘要式身份验证的 <xref:System.Net> 实现符合 RFC2617 – HTTP 身份验证：基本身份验证和摘要式身份验证（适用于万维网联合会 Web 网站 (www.w3.org)）。</span><span class="sxs-lookup"><span data-stu-id="a5898-103">The <xref:System.Net> implementation of basic and digest authentication complies with RFC2617 – HTTP Authentication: Basic and Digest Authentication (available on the World Wide Web Consortium's Web site at www.w3.org).</span></span>  
  
 <span data-ttu-id="a5898-104">若要使用基本身份验证和摘要式身份验证，应用程序必须在 <xref:System.Net.WebRequest> 对象的 <xref:System.Net.WebRequest.Credentials%2A> 属性中提供用户名和密码，该对象用于从 Internet 中请求数据，如下例所示。</span><span class="sxs-lookup"><span data-stu-id="a5898-104">To use basic and digest authentication, an application must provide a user name and password in the <xref:System.Net.WebRequest.Credentials%2A> property of the <xref:System.Net.WebRequest> object that it uses to request data from the Internet, as shown in the following example.</span></span>  
  
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
>  <span data-ttu-id="a5898-105">使用基本和摘要式身份验证发送的数据不会加密，因此攻击者会看到数据。</span><span class="sxs-lookup"><span data-stu-id="a5898-105">Data sent with Basic and Digest Authentication is not encrypted, so the data can be seen by an adversary.</span></span> <span data-ttu-id="a5898-106">此外，基本身份验证凭据（用户名和密码）是以明文形式发送的，会被截取。</span><span class="sxs-lookup"><span data-stu-id="a5898-106">Additionally, Basic Authentication credentials (user name and password) are sent in the clear and can be intercepted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5898-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a5898-107">See Also</span></span>  
 [<span data-ttu-id="a5898-108">NTLM 和 Kerberos 身份验证</span><span class="sxs-lookup"><span data-stu-id="a5898-108">NTLM and Kerberos Authentication</span></span>](../../../docs/framework/network-programming/ntlm-and-kerberos-authentication.md)  
 [<span data-ttu-id="a5898-109">Internet 身份验证</span><span class="sxs-lookup"><span data-stu-id="a5898-109">Internet Authentication</span></span>](../../../docs/framework/network-programming/internet-authentication.md)
