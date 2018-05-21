---
title: 如何：检索与 WebRequest 匹配的特定于协议的 WebResponse
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d8c90785-f16b-42a5-8439-ed2f731b2ba8
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: d15b63482cb37fa986dd065beefcf6baee4c8312
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-retrieve-a-protocol-specific-webresponse-that-matches-a-webrequest"></a><span data-ttu-id="c5ab8-102">如何：检索与 WebRequest 匹配的特定于协议的 WebResponse</span><span class="sxs-lookup"><span data-stu-id="c5ab8-102">How to: Retrieve a Protocol-Specific WebResponse that Matches a WebRequest</span></span>
<span data-ttu-id="c5ab8-103">此示例演示如何检索与 WebRequest 匹配的特定于协议的 WebResponse。</span><span class="sxs-lookup"><span data-stu-id="c5ab8-103">This example shows how to retrieve a protocol-specific WebResponse that matches a WebRequest.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c5ab8-104">示例</span><span class="sxs-lookup"><span data-stu-id="c5ab8-104">Example</span></span>  
  
```csharp  
WebRequest req = WebRequest.Create("http://www.contoso.com/");  
WebResponse resp = req.GetResponse();  
```  
  
```vb  
Dim req As WebRequest = WebRequest.Create("http://www.contoso.com")  
Dim resp As WebResponse = req.GetResponse()  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c5ab8-105">编译代码</span><span class="sxs-lookup"><span data-stu-id="c5ab8-105">Compiling the Code</span></span>  
 <span data-ttu-id="c5ab8-106">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="c5ab8-106">This example requires:</span></span>  
  
-   <span data-ttu-id="c5ab8-107">引用 System.Net 命名空间。</span><span class="sxs-lookup"><span data-stu-id="c5ab8-107">References to the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5ab8-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="c5ab8-108">See Also</span></span>  
 [<span data-ttu-id="c5ab8-109">请求数据</span><span class="sxs-lookup"><span data-stu-id="c5ab8-109">Requesting Data</span></span>](../../../docs/framework/network-programming/requesting-data.md)
