---
title: 如何：重写全局代理选择
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0da481a9-b414-4230-beb0-e3ceba882fe5
ms.openlocfilehash: 44845fb67aac4ff9ab9dda8cf4934153c8c4f23c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2020
ms.locfileid: "71048263"
---
# <a name="how-to-override-a-global-proxy-selection"></a><span data-ttu-id="34007-102">如何：重写全局代理选择</span><span class="sxs-lookup"><span data-stu-id="34007-102">How to: Override a Global Proxy Selection</span></span>
<span data-ttu-id="34007-103">此示例将 WebRequest 发送到 **，其在端口 80 上使用名为**  的代理服务器替代全局代理选择`www.contoso.com``alternateproxy`。</span><span class="sxs-lookup"><span data-stu-id="34007-103">This example sends a **WebRequest** to `www.contoso.com` that overrides the global proxy selection with a proxy server named `alternateproxy` on port 80.</span></span>  
  
## <a name="example"></a><span data-ttu-id="34007-104">示例</span><span class="sxs-lookup"><span data-stu-id="34007-104">Example</span></span>  
  
```csharp  
WebRequest req = WebRequest.Create("http://www.contoso.com/");  
req.Proxy = new WebProxy("http://alternateproxy:80/");  
```  
  
```vb  
Dim req As WebRequest = WebRequest.Create("http://www.contoso.com/")  
req.Proxy = New WebProxy("http://alternateproxy:80/")  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="34007-105">编译代码</span><span class="sxs-lookup"><span data-stu-id="34007-105">Compiling the Code</span></span>  
 <span data-ttu-id="34007-106">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="34007-106">This example requires:</span></span>  
  
- <span data-ttu-id="34007-107">System.Net 命名空间的 [`using` 指令](../../csharp/language-reference/keywords/using-directive.md)  。</span><span class="sxs-lookup"><span data-stu-id="34007-107">A [`using` directive](../../csharp/language-reference/keywords/using-directive.md) for the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34007-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="34007-108">See also</span></span>

- [<span data-ttu-id="34007-109">使用应用程序协议</span><span class="sxs-lookup"><span data-stu-id="34007-109">Using Application Protocols</span></span>](using-application-protocols.md)
- [<span data-ttu-id="34007-110">通过代理访问 Internet</span><span class="sxs-lookup"><span data-stu-id="34007-110">Accessing the Internet Through a Proxy</span></span>](accessing-the-internet-through-a-proxy.md)
