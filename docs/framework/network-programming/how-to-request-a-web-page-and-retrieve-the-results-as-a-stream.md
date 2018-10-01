---
title: 如何：请求 Web 页并以流的形式检索结果
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d32b7f35-29d8-4fb7-ad71-d219edc5e359
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 2ceaa7cbaf2035276a0ba0105f3969f0249c6132
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2018
ms.locfileid: "47402599"
---
# <a name="how-to-request-a-web-page-and-retrieve-the-results-as-a-stream"></a><span data-ttu-id="b0159-102">如何：请求 Web 页并以流的形式检索结果</span><span class="sxs-lookup"><span data-stu-id="b0159-102">How to: Request a Web Page and Retrieve the Results as a Stream</span></span>
<span data-ttu-id="b0159-103">此示例演示如何请求 Web 页并在流中检索结果。</span><span class="sxs-lookup"><span data-stu-id="b0159-103">This example shows how to request a Web page and retrieve the results in a stream.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b0159-104">示例</span><span class="sxs-lookup"><span data-stu-id="b0159-104">Example</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="b0159-105">编译代码</span><span class="sxs-lookup"><span data-stu-id="b0159-105">Compiling the Code</span></span>  
 <span data-ttu-id="b0159-106">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="b0159-106">This example requires:</span></span>  
  
-   <span data-ttu-id="b0159-107">对 <xref:System.IO> 和 <xref:System.Net> 命名空间的引用。</span><span class="sxs-lookup"><span data-stu-id="b0159-107">References to the <xref:System.IO> and <xref:System.Net> namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0159-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="b0159-108">See Also</span></span>  
 [<span data-ttu-id="b0159-109">请求数据</span><span class="sxs-lookup"><span data-stu-id="b0159-109">Requesting Data</span></span>](../../../docs/framework/network-programming/requesting-data.md)
