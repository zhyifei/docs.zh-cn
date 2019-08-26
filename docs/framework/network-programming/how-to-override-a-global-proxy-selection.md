---
title: 如何：重写全局代理选择
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0da481a9-b414-4230-beb0-e3ceba882fe5
ms.openlocfilehash: e5f4dc22ad75dc4d4f7dc30f44e6ae304403ef16
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69914534"
---
# <a name="how-to-override-a-global-proxy-selection"></a><span data-ttu-id="89ba2-102">如何：重写全局代理选择</span><span class="sxs-lookup"><span data-stu-id="89ba2-102">How to: Override a Global Proxy Selection</span></span>
<span data-ttu-id="89ba2-103">此示例将 WebRequest 发送到 `www.contoso.com`，其在端口 80 上使用名为 `alternateproxy` 的代理服务器替代全局代理选择  。</span><span class="sxs-lookup"><span data-stu-id="89ba2-103">This example sends a **WebRequest** to `www.contoso.com` that overrides the global proxy selection with a proxy server named `alternateproxy` on port 80.</span></span>  
  
## <a name="example"></a><span data-ttu-id="89ba2-104">示例</span><span class="sxs-lookup"><span data-stu-id="89ba2-104">Example</span></span>  
  
```csharp  
WebRequest req = WebRequest.Create("http://www.contoso.com/");  
req.Proxy = new WebProxy("http://alternateproxy:80/");  
```  
  
```vb  
Dim req As WebRequest = WebRequest.Create("http://www.contoso.com/")  
req.Proxy = New WebProxy("http://alternateproxy:80/")  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="89ba2-105">编译代码</span><span class="sxs-lookup"><span data-stu-id="89ba2-105">Compiling the Code</span></span>  
 <span data-ttu-id="89ba2-106">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="89ba2-106">This example requires:</span></span>  
  
- <span data-ttu-id="89ba2-107">System.Net 命名空间的 [`using` 指令](../../csharp/language-reference/keywords/using-directive.md)  。</span><span class="sxs-lookup"><span data-stu-id="89ba2-107">A [`using` directive](../../csharp/language-reference/keywords/using-directive.md) for the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89ba2-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="89ba2-108">See also</span></span>

- [<span data-ttu-id="89ba2-109">使用应用程序协议</span><span class="sxs-lookup"><span data-stu-id="89ba2-109">Using Application Protocols</span></span>](../../../docs/framework/network-programming/using-application-protocols.md)
- [<span data-ttu-id="89ba2-110">通过代理访问 Internet</span><span class="sxs-lookup"><span data-stu-id="89ba2-110">Accessing the Internet Through a Proxy</span></span>](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)
