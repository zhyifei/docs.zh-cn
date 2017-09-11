---
title: "如何：请求 Web 页并以流的形式检索结果"
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
ms.assetid: d32b7f35-29d8-4fb7-ad71-d219edc5e359
caps.latest.revision: 12
author: mcleblanc
ms.author: markl
manager: markl
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ec19e46289131ec137081c610c1a8194ad22611f
ms.contentlocale: zh-cn
ms.lasthandoff: 08/21/2017

---
# <a name="how-to-request-a-web-page-and-retrieve-the-results-as-a-stream"></a><span data-ttu-id="8d2b7-102">如何：请求 Web 页并以流的形式检索结果</span><span class="sxs-lookup"><span data-stu-id="8d2b7-102">How to: Request a Web Page and Retrieve the Results as a Stream</span></span>
<span data-ttu-id="8d2b7-103">此示例演示如何请求 Web 页并在流中检索结果。</span><span class="sxs-lookup"><span data-stu-id="8d2b7-103">This example shows how to request a Web page and retrieve the results in a stream.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8d2b7-104">示例</span><span class="sxs-lookup"><span data-stu-id="8d2b7-104">Example</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="8d2b7-105">编译代码</span><span class="sxs-lookup"><span data-stu-id="8d2b7-105">Compiling the Code</span></span>  
 <span data-ttu-id="8d2b7-106">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="8d2b7-106">This example requires:</span></span>  
  
-   <span data-ttu-id="8d2b7-107">对 <xref:System.IO> 和 <xref:System.Net> 命名空间的引用。</span><span class="sxs-lookup"><span data-stu-id="8d2b7-107">References to the <xref:System.IO> and <xref:System.Net> namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d2b7-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8d2b7-108">See Also</span></span>  
 [<span data-ttu-id="8d2b7-109">请求数据</span><span class="sxs-lookup"><span data-stu-id="8d2b7-109">Requesting Data</span></span>](../../../docs/framework/network-programming/requesting-data.md)

