---
title: 如何：检索与 WebRequest 匹配的特定于协议的 WebResponse
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d8c90785-f16b-42a5-8439-ed2f731b2ba8
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 2a72e57156903c9d436a49aaf6da596868af4003
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2018
ms.locfileid: "47454864"
---
# <a name="how-to-retrieve-a-protocol-specific-webresponse-that-matches-a-webrequest"></a><span data-ttu-id="bc13d-102">如何：检索与 WebRequest 匹配的特定于协议的 WebResponse</span><span class="sxs-lookup"><span data-stu-id="bc13d-102">How to: Retrieve a Protocol-Specific WebResponse that Matches a WebRequest</span></span>
<span data-ttu-id="bc13d-103">此示例演示如何检索与 WebRequest 匹配的特定于协议的 WebResponse。</span><span class="sxs-lookup"><span data-stu-id="bc13d-103">This example shows how to retrieve a protocol-specific WebResponse that matches a WebRequest.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bc13d-104">示例</span><span class="sxs-lookup"><span data-stu-id="bc13d-104">Example</span></span>  
  
```csharp  
WebRequest req = WebRequest.Create("http://www.contoso.com/");  
WebResponse resp = req.GetResponse();  
```  
  
```vb  
Dim req As WebRequest = WebRequest.Create("http://www.contoso.com")  
Dim resp As WebResponse = req.GetResponse()  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="bc13d-105">编译代码</span><span class="sxs-lookup"><span data-stu-id="bc13d-105">Compiling the Code</span></span>  
 <span data-ttu-id="bc13d-106">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="bc13d-106">This example requires:</span></span>  
  
-   <span data-ttu-id="bc13d-107">引用 System.Net 命名空间。</span><span class="sxs-lookup"><span data-stu-id="bc13d-107">References to the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc13d-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="bc13d-108">See Also</span></span>  
 [<span data-ttu-id="bc13d-109">请求数据</span><span class="sxs-lookup"><span data-stu-id="bc13d-109">Requesting Data</span></span>](../../../docs/framework/network-programming/requesting-data.md)
