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
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2018
ms.locfileid: "42930823"
---
# <a name="how-to-override-a-global-proxy-selection"></a><span data-ttu-id="65394-102">如何：重写全局代理选择</span><span class="sxs-lookup"><span data-stu-id="65394-102">How to: Override a Global Proxy Selection</span></span>
<span data-ttu-id="65394-103">此示例将 WebRequest 发送到 `www.contoso.com`，其在端口 80 上使用名为 `alternateproxy` 的代理服务器替代全局代理选择。</span><span class="sxs-lookup"><span data-stu-id="65394-103">This example sends a **WebRequest** to `www.contoso.com` that overrides the global proxy selection with a proxy server named `alternateproxy` on port 80.</span></span>  
  
## <a name="example"></a><span data-ttu-id="65394-104">示例</span><span class="sxs-lookup"><span data-stu-id="65394-104">Example</span></span>  
  
```csharp  
WebRequest req = WebRequest.Create("http://www.contoso.com/");  
req.Proxy = new WebProxy("http://alternateproxy:80/");  
```  
  
```vb  
Dim req As WebRequest = WebRequest.Create("http://www.contoso.com/")  
req.Proxy = New WebProxy("http://alternateproxy:80/")  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="65394-105">编译代码</span><span class="sxs-lookup"><span data-stu-id="65394-105">Compiling the Code</span></span>  
 <span data-ttu-id="65394-106">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="65394-106">This example requires:</span></span>  
  
-   <span data-ttu-id="65394-107">System.Net 命名空间的 [`using` 指令](~/docs/csharp/language-reference/keywords/using-directive.md)。</span><span class="sxs-lookup"><span data-stu-id="65394-107">A [`using` directive](~/docs/csharp/language-reference/keywords/using-directive.md) for the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65394-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="65394-108">See Also</span></span>  
 [<span data-ttu-id="65394-109">使用应用程序协议</span><span class="sxs-lookup"><span data-stu-id="65394-109">Using Application Protocols</span></span>](../../../docs/framework/network-programming/using-application-protocols.md)  
 [<span data-ttu-id="65394-110">通过代理访问 Internet</span><span class="sxs-lookup"><span data-stu-id="65394-110">Accessing the Internet Through a Proxy</span></span>](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)
