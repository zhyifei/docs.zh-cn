---
title: 如何：请求 Web 页并以流的形式检索结果
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d32b7f35-29d8-4fb7-ad71-d219edc5e359
ms.openlocfilehash: 65bda268cd77959dbcd786c365d0a30c324b89ce
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2020
ms.locfileid: "71393106"
---
# <a name="how-to-request-a-web-page-and-retrieve-the-results-as-a-stream"></a><span data-ttu-id="2f3db-102">如何：请求 Web 页并以流的形式检索结果</span><span class="sxs-lookup"><span data-stu-id="2f3db-102">How to: Request a Web Page and Retrieve the Results as a Stream</span></span>

<span data-ttu-id="2f3db-103">此示例演示如何请求 Web 页并在流中检索结果。</span><span class="sxs-lookup"><span data-stu-id="2f3db-103">This example shows how to request a Web page and retrieve the results in a stream.</span></span>
  
## <a name="example"></a><span data-ttu-id="2f3db-104">示例</span><span class="sxs-lookup"><span data-stu-id="2f3db-104">Example</span></span>

```csharp
var myClient = new WebClient();
Stream response = myClient.OpenRead("https://docs.microsoft.com/dotnet/");
// The stream data is used here.
response.Close();
```

```vb
Dim myClient As New WebClient()
Dim response As Stream = myClient.OpenRead("https://docs.microsoft.com/dotnet/")
' The stream data is used here.
response.Close()
```

## <a name="compiling-the-code"></a><span data-ttu-id="2f3db-105">编译代码</span><span class="sxs-lookup"><span data-stu-id="2f3db-105">Compiling the Code</span></span>

 <span data-ttu-id="2f3db-106">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="2f3db-106">This example requires:</span></span>

- <span data-ttu-id="2f3db-107">对 <xref:System.IO> 和 <xref:System.Net> 命名空间的引用。</span><span class="sxs-lookup"><span data-stu-id="2f3db-107">References to the <xref:System.IO> and <xref:System.Net> namespaces.</span></span>

## <a name="see-also"></a><span data-ttu-id="2f3db-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2f3db-108">See also</span></span>

- [<span data-ttu-id="2f3db-109">请求数据</span><span class="sxs-lookup"><span data-stu-id="2f3db-109">Requesting Data</span></span>](requesting-data.md)
