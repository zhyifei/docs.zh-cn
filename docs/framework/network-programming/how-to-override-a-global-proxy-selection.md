---
title: "如何：重写全局代理选择"
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
ms.assetid: 0da481a9-b414-4230-beb0-e3ceba882fe5
caps.latest.revision: 8
author: mcleblanc
ms.author: markl
manager: markl
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: cecb98628231e6a8b2847043e3f3c2206c164ae3
ms.contentlocale: zh-cn
ms.lasthandoff: 08/21/2017

---
# <a name="how-to-override-a-global-proxy-selection"></a><span data-ttu-id="c9bea-102">如何：重写全局代理选择</span><span class="sxs-lookup"><span data-stu-id="c9bea-102">How to: Override a Global Proxy Selection</span></span>
<span data-ttu-id="c9bea-103">此示例将 WebRequest 发送到 www.contoso.com，其在端口 80 上使用名为 `alternateproxy` 的代理服务器替代全局代理选择。</span><span class="sxs-lookup"><span data-stu-id="c9bea-103">This example sends a **WebRequest** to www.contoso.com that overrides the global proxy selection with a proxy server named `alternateproxy` on port 80.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c9bea-104">示例</span><span class="sxs-lookup"><span data-stu-id="c9bea-104">Example</span></span>  
  
```csharp  
WebRequest req = WebRequest.Create("http://www.contoso.com/");  
req.Proxy = new WebProxy("http://alternateproxy:80/");  
```  
  
```vb  
Dim req As WebRequest = WebRequest.Create("http://www.contoso.com/")  
req.Proxy = New WebProxy("http://alternateproxy:80/")  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c9bea-105">编译代码</span><span class="sxs-lookup"><span data-stu-id="c9bea-105">Compiling the Code</span></span>  
 <span data-ttu-id="c9bea-106">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="c9bea-106">This example requires:</span></span>  
  
-   <span data-ttu-id="c9bea-107">引用 System.Net 命名空间。</span><span class="sxs-lookup"><span data-stu-id="c9bea-107">References to the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9bea-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c9bea-108">See Also</span></span>  
 <span data-ttu-id="c9bea-109">[使用应用程序协议](../../../docs/framework/network-programming/using-application-protocols.md) </span><span class="sxs-lookup"><span data-stu-id="c9bea-109">[Using Application Protocols](../../../docs/framework/network-programming/using-application-protocols.md) </span></span>  
 [<span data-ttu-id="c9bea-110">通过代理访问 Internet</span><span class="sxs-lookup"><span data-stu-id="c9bea-110">Accessing the Internet Through a Proxy</span></span>](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)

