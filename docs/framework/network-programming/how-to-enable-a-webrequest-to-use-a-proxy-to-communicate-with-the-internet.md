---
title: "如何：使 WebRequest 能够使用代理以与 Internet 通信"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
ms.assetid: 63c0ef2c-44b5-4c54-9804-ba0b9b001ac7
caps.latest.revision: 9
author: mcleblanc
ms.author: markl
manager: markl
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a42b9f947f4c3d59c3e17a892e4db405e2bc8b64
ms.contentlocale: zh-cn
ms.lasthandoff: 08/21/2017

---
# <a name="how-to-enable-a-webrequest-to-use-a-proxy-to-communicate-with-the-internet"></a><span data-ttu-id="31cb7-102">如何：使 WebRequest 能够使用代理以与 Internet 通信</span><span class="sxs-lookup"><span data-stu-id="31cb7-102">How to: Enable a WebRequest to Use a Proxy to Communicate With the Internet</span></span>
<span data-ttu-id="31cb7-103">此示例将创建一个全局代理实例，该实例将启用任何 <xref:System.Net.WebRequest> 以使用代理与 Internet 进行通信。</span><span class="sxs-lookup"><span data-stu-id="31cb7-103">This example creates a global proxy instance that will enable any <xref:System.Net.WebRequest> to use a proxy to communicate with the Internet.</span></span> <span data-ttu-id="31cb7-104">该示例假定代理服务器名为 `webproxy`，且在端口 80（标准 HTTP 端口）上进行通信。</span><span class="sxs-lookup"><span data-stu-id="31cb7-104">The example assumes that the proxy server is named `webproxy` and that it communicates on port 80, the standard HTTP port.</span></span>  
  
## <a name="example"></a><span data-ttu-id="31cb7-105">示例</span><span class="sxs-lookup"><span data-stu-id="31cb7-105">Example</span></span>  
  
```csharp  
WebProxy proxyObject = new WebProxy("http://webproxy:80/");  
GlobalProxySelection.Select = proxyObject;  
```  
  
```vb  
Dim proxyObject As WebProxy = New WebProxy("http://webproxy:80/")  
GlobalProxySelection.Select = proxyObject  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="31cb7-106">编译代码</span><span class="sxs-lookup"><span data-stu-id="31cb7-106">Compiling the Code</span></span>  
 <span data-ttu-id="31cb7-107">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="31cb7-107">This example requires:</span></span>  
  
-   <span data-ttu-id="31cb7-108">引用 System.Net 命名空间。</span><span class="sxs-lookup"><span data-stu-id="31cb7-108">References to the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31cb7-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="31cb7-109">See Also</span></span>  
 <span data-ttu-id="31cb7-110">[使用应用程序协议](../../../docs/framework/network-programming/using-application-protocols.md) </span><span class="sxs-lookup"><span data-stu-id="31cb7-110">[Using Application Protocols](../../../docs/framework/network-programming/using-application-protocols.md) </span></span>  
 [<span data-ttu-id="31cb7-111">通过代理访问 Internet</span><span class="sxs-lookup"><span data-stu-id="31cb7-111">Accessing the Internet Through a Proxy</span></span>](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)

