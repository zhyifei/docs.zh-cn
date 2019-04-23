---
title: 如何：使用 WebRequest 注册自定义协议
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 98ddbdb9-66b1-4080-92ad-51f5c447fcf8
ms.openlocfilehash: 5c9a81fc61a2272056ba34fa387fdafee6203824
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59079495"
---
# <a name="how-to-register-a-custom-protocol-using-webrequest"></a><span data-ttu-id="dbe3a-102">如何：使用 WebRequest 注册自定义协议</span><span class="sxs-lookup"><span data-stu-id="dbe3a-102">How to: Register a Custom Protocol Using WebRequest</span></span>
<span data-ttu-id="dbe3a-103">此示例演示如何注册在其他位置定义的特定于协议的类。</span><span class="sxs-lookup"><span data-stu-id="dbe3a-103">This example shows how to register a protocol specific class that is defined elsewhere.</span></span> <span data-ttu-id="dbe3a-104">在此示例中，`CustomWebRequestCreator` 是用户实现对象，它实现返回 `CustomWebRequest` 对象的“Create”方法。</span><span class="sxs-lookup"><span data-stu-id="dbe3a-104">In this example, `CustomWebRequestCreator` is the user-implemented object that implements the **Create** method that returns the `CustomWebRequest` object.</span></span> <span data-ttu-id="dbe3a-105">此代码示例假定已编写了实现自定义协议的 `CustomWebRequest` 代码。</span><span class="sxs-lookup"><span data-stu-id="dbe3a-105">The code example assumes that you have written the `CustomWebRequest` code that implements the custom protocol.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dbe3a-106">示例</span><span class="sxs-lookup"><span data-stu-id="dbe3a-106">Example</span></span>  
  
```csharp  
WebRequest.RegisterPrefix("custom", new CustomWebRequestCreator());  
WebRequest req = WebRequest.Create("custom://customHost.contoso.com/");  
```  
  
```vb  
WebRequest.RegisterPrefix("custom", New CustomWebRequestCreator())  
Dim req As WebRequest = WebRequest.Create("custom://customHost.contoso.com/")  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="dbe3a-107">编译代码</span><span class="sxs-lookup"><span data-stu-id="dbe3a-107">Compiling the Code</span></span>  
 <span data-ttu-id="dbe3a-108">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="dbe3a-108">This example requires:</span></span>  
  
 <span data-ttu-id="dbe3a-109">对 <xref:System.Net> 命名空间的引用。</span><span class="sxs-lookup"><span data-stu-id="dbe3a-109">References to the <xref:System.Net> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbe3a-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="dbe3a-110">See also</span></span>

- [<span data-ttu-id="dbe3a-111">对可插入协议进行编程</span><span class="sxs-lookup"><span data-stu-id="dbe3a-111">Programming Pluggable Protocols</span></span>](../../../docs/framework/network-programming/programming-pluggable-protocols.md)
