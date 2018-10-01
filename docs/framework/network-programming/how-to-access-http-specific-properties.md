---
title: 如何：访问 HTTP 特定的属性
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f8848c7e-f5c5-4d42-b86d-9951ff8f4146
author: mcleblanc
ms.author: markl
ms.openlocfilehash: f008cf82b80e29f8fe741034a0e820b5eae5b0ba
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2018
ms.locfileid: "47193721"
---
# <a name="how-to-access-http-specific-properties"></a><span data-ttu-id="dbd47-102">如何：访问 HTTP 特定的属性</span><span class="sxs-lookup"><span data-stu-id="dbd47-102">How to: Access HTTP-Specific Properties</span></span>
<span data-ttu-id="dbd47-103">此示例演示如何关闭 HTTP 保持的连接行为并从 Web 服务器获取协议版本号。</span><span class="sxs-lookup"><span data-stu-id="dbd47-103">This sample shows how to turn off the HTTP **Keep-alive** behavior and get the protocol version number from the Web server.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dbd47-104">示例</span><span class="sxs-lookup"><span data-stu-id="dbd47-104">Example</span></span>  
  
```vb  
Dim HttpWReq As HttpWebRequest= _  
    CType(WebRequest.Create("http://www.contoso.com"), HttpWebRequest)  
' Turn off connection keep-alives.  
HttpWReq.KeepAlive = False  
  
Dim HttpWResp As HttpWebResponse = _  
    CType(HttpWReq.GetResponse(), HttpWebResponse)  
  
' Get the HTTP protocol version number returned by the server.  
Dim ver As String = HttpWResp.ProtocolVersion.ToString()  
HttpWResp.Close()  
```  
  
```csharp  
HttpWebRequest HttpWReq =   
    (HttpWebRequest)WebRequest.Create("http://www.contoso.com");  
// Turn off connection keep-alives.  
HttpWReq.KeepAlive = false;  
  
HttpWebResponse HttpWResp = (HttpWebResponse)HttpWReq.GetResponse();  
  
// Get the HTTP protocol version number returned by the server.  
String ver = HttpWResp.ProtocolVersion.ToString();  
HttpWResp.Close();  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="dbd47-105">编译代码</span><span class="sxs-lookup"><span data-stu-id="dbd47-105">Compiling the Code</span></span>  
 <span data-ttu-id="dbd47-106">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="dbd47-106">This example requires:</span></span>  
  
-   <span data-ttu-id="dbd47-107">引用 System.Net 命名空间。</span><span class="sxs-lookup"><span data-stu-id="dbd47-107">References to the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbd47-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="dbd47-108">See Also</span></span>  
 [<span data-ttu-id="dbd47-109">通过代理访问 Internet</span><span class="sxs-lookup"><span data-stu-id="dbd47-109">Accessing the Internet Through a Proxy</span></span>](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)  
 [<span data-ttu-id="dbd47-110">使用应用程序协议</span><span class="sxs-lookup"><span data-stu-id="dbd47-110">Using Application Protocols</span></span>](../../../docs/framework/network-programming/using-application-protocols.md)  
 [<span data-ttu-id="dbd47-111">HTTP</span><span class="sxs-lookup"><span data-stu-id="dbd47-111">HTTP</span></span>](../../../docs/framework/network-programming/http.md)
