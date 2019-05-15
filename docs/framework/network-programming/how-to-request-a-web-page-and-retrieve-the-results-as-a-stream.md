---
title: 如何：请求网页并以数据流的形式检索结果
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d32b7f35-29d8-4fb7-ad71-d219edc5e359
ms.openlocfilehash: 74cb739d381c0b1422d9277be8c3c338a46f8fba
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64647423"
---
# <a name="how-to-request-a-web-page-and-retrieve-the-results-as-a-stream"></a><span data-ttu-id="8aec4-102">如何：请求网页并以数据流的形式检索结果</span><span class="sxs-lookup"><span data-stu-id="8aec4-102">How to: Request a Web Page and Retrieve the Results as a Stream</span></span>
<span data-ttu-id="8aec4-103">此示例演示如何请求 Web 页并在流中检索结果。</span><span class="sxs-lookup"><span data-stu-id="8aec4-103">This example shows how to request a Web page and retrieve the results in a stream.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8aec4-104">示例</span><span class="sxs-lookup"><span data-stu-id="8aec4-104">Example</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="8aec4-105">编译代码</span><span class="sxs-lookup"><span data-stu-id="8aec4-105">Compiling the Code</span></span>  
 <span data-ttu-id="8aec4-106">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="8aec4-106">This example requires:</span></span>  
  
- <span data-ttu-id="8aec4-107">对 <xref:System.IO> 和 <xref:System.Net> 命名空间的引用。</span><span class="sxs-lookup"><span data-stu-id="8aec4-107">References to the <xref:System.IO> and <xref:System.Net> namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8aec4-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="8aec4-108">See also</span></span>

- [<span data-ttu-id="8aec4-109">请求数据</span><span class="sxs-lookup"><span data-stu-id="8aec4-109">Requesting Data</span></span>](../../../docs/framework/network-programming/requesting-data.md)
