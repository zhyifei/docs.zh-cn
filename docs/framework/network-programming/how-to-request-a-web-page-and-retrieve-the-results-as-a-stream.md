---
title: 如何：请求网页并以数据流的形式检索结果
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d32b7f35-29d8-4fb7-ad71-d219edc5e359
ms.openlocfilehash: 23c094f0a3f528750c9589dbc99a0ada86236967
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59097195"
---
# <a name="how-to-request-a-web-page-and-retrieve-the-results-as-a-stream"></a><span data-ttu-id="e2423-102">如何：请求网页并以数据流的形式检索结果</span><span class="sxs-lookup"><span data-stu-id="e2423-102">How to: Request a Web Page and Retrieve the Results as a Stream</span></span>
<span data-ttu-id="e2423-103">此示例演示如何请求 Web 页并在流中检索结果。</span><span class="sxs-lookup"><span data-stu-id="e2423-103">This example shows how to request a Web page and retrieve the results in a stream.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e2423-104">示例</span><span class="sxs-lookup"><span data-stu-id="e2423-104">Example</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="e2423-105">编译代码</span><span class="sxs-lookup"><span data-stu-id="e2423-105">Compiling the Code</span></span>  
 <span data-ttu-id="e2423-106">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="e2423-106">This example requires:</span></span>  
  
-   <span data-ttu-id="e2423-107">对 <xref:System.IO> 和 <xref:System.Net> 命名空间的引用。</span><span class="sxs-lookup"><span data-stu-id="e2423-107">References to the <xref:System.IO> and <xref:System.Net> namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2423-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="e2423-108">See also</span></span>

- [<span data-ttu-id="e2423-109">正在请求数据...</span><span class="sxs-lookup"><span data-stu-id="e2423-109">Requesting Data</span></span>](../../../docs/framework/network-programming/requesting-data.md)
