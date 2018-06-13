---
title: 如何：请求 Web 页并以流的形式检索结果
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d32b7f35-29d8-4fb7-ad71-d219edc5e359
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 31856e7fc7136b3bdb8fab9fdf8185de32a3007a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33395208"
---
# <a name="how-to-request-a-web-page-and-retrieve-the-results-as-a-stream"></a><span data-ttu-id="bfeeb-102">如何：请求 Web 页并以流的形式检索结果</span><span class="sxs-lookup"><span data-stu-id="bfeeb-102">How to: Request a Web Page and Retrieve the Results as a Stream</span></span>
<span data-ttu-id="bfeeb-103">此示例演示如何请求 Web 页并在流中检索结果。</span><span class="sxs-lookup"><span data-stu-id="bfeeb-103">This example shows how to request a Web page and retrieve the results in a stream.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bfeeb-104">示例</span><span class="sxs-lookup"><span data-stu-id="bfeeb-104">Example</span></span>  
  
```csharp  
WebClient myClient = new WebClient();  
Stream response = myClient.OpenRead("http://www.contoso.com/index.htm");  
// The stream data is used here.  
response.Close();  
```  
  
```vb  
Dim myClient As WebClient = New WebClient()  
Dim response As Stream = myClient.OpenRead("http://www.contoso.com/index.htm")  
' The stream data is used here.  
response.Close()  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="bfeeb-105">编译代码</span><span class="sxs-lookup"><span data-stu-id="bfeeb-105">Compiling the Code</span></span>  
 <span data-ttu-id="bfeeb-106">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="bfeeb-106">This example requires:</span></span>  
  
-   <span data-ttu-id="bfeeb-107">对 <xref:System.IO> 和 <xref:System.Net> 命名空间的引用。</span><span class="sxs-lookup"><span data-stu-id="bfeeb-107">References to the <xref:System.IO> and <xref:System.Net> namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfeeb-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="bfeeb-108">See Also</span></span>  
 [<span data-ttu-id="bfeeb-109">请求数据</span><span class="sxs-lookup"><span data-stu-id="bfeeb-109">Requesting Data</span></span>](../../../docs/framework/network-programming/requesting-data.md)
