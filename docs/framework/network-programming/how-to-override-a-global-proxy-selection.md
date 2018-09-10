---
title: 如何：重写全局代理选择
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0da481a9-b414-4230-beb0-e3ceba882fe5
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 244315b5df4200524685bc5b9fb75a0d7fd9b39e
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/09/2018
ms.locfileid: "44185030"
---
# <a name="how-to-override-a-global-proxy-selection"></a><span data-ttu-id="f3545-102">如何：重写全局代理选择</span><span class="sxs-lookup"><span data-stu-id="f3545-102">How to: Override a Global Proxy Selection</span></span>
<span data-ttu-id="f3545-103">此示例将 WebRequest 发送到 `www.contoso.com`，其在端口 80 上使用名为 `alternateproxy` 的代理服务器替代全局代理选择。</span><span class="sxs-lookup"><span data-stu-id="f3545-103">This example sends a **WebRequest** to `www.contoso.com` that overrides the global proxy selection with a proxy server named `alternateproxy` on port 80.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f3545-104">示例</span><span class="sxs-lookup"><span data-stu-id="f3545-104">Example</span></span>  
  
```csharp  
WebRequest req = WebRequest.Create("http://www.contoso.com/");  
req.Proxy = new WebProxy("http://alternateproxy:80/");  
```  
  
```vb  
Dim req As WebRequest = WebRequest.Create("http://www.contoso.com/")  
req.Proxy = New WebProxy("http://alternateproxy:80/")  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f3545-105">编译代码</span><span class="sxs-lookup"><span data-stu-id="f3545-105">Compiling the Code</span></span>  
 <span data-ttu-id="f3545-106">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="f3545-106">This example requires:</span></span>  
  
-   <span data-ttu-id="f3545-107">System.Net 命名空间的 [`using` 指令](~/docs/csharp/language-reference/keywords/using-directive.md)。</span><span class="sxs-lookup"><span data-stu-id="f3545-107">A [`using` directive](~/docs/csharp/language-reference/keywords/using-directive.md) for the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3545-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="f3545-108">See Also</span></span>  
 [<span data-ttu-id="f3545-109">使用应用程序协议</span><span class="sxs-lookup"><span data-stu-id="f3545-109">Using Application Protocols</span></span>](../../../docs/framework/network-programming/using-application-protocols.md)  
 [<span data-ttu-id="f3545-110">通过代理访问 Internet</span><span class="sxs-lookup"><span data-stu-id="f3545-110">Accessing the Internet Through a Proxy</span></span>](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)
