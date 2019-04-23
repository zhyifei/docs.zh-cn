---
title: 如何：转换 WebRequest 以访问协议特定属性
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d9a8eae2-7454-46f9-b43b-c98477c5bcde
ms.openlocfilehash: a9488e484aad7ba3df23c33b2cb5b79f234b758e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59088361"
---
# <a name="how-to-typecast-a-webrequest-to-access-protocol-specific-properties"></a><span data-ttu-id="c85d5-102">如何：转换 WebRequest 以访问协议特定属性</span><span class="sxs-lookup"><span data-stu-id="c85d5-102">How to: Typecast a WebRequest to Access Protocol Specific Properties</span></span>
<span data-ttu-id="c85d5-103">此示例演示如何类型转换 WebRequest 以访问特定于协议的属性。</span><span class="sxs-lookup"><span data-stu-id="c85d5-103">This example shows how to typecast a WebRequest so that you can access protocol specific properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c85d5-104">示例</span><span class="sxs-lookup"><span data-stu-id="c85d5-104">Example</span></span>  
  
```csharp  
HttpWebRequest httpreq =   
   (HttpWebRequest) WebRequest.Create("http://www.contoso.com/");  
```  
  
```vb  
Dim httpreq As HttpWebRequest = _  
   CType(WebRequest.Create("http://www.contoso.com/"), HttpWebRequest)  
```  
  
## <a name="see-also"></a><span data-ttu-id="c85d5-105">请参阅</span><span class="sxs-lookup"><span data-stu-id="c85d5-105">See also</span></span>

- [<span data-ttu-id="c85d5-106">对可插入协议进行编程</span><span class="sxs-lookup"><span data-stu-id="c85d5-106">Programming Pluggable Protocols</span></span>](../../../docs/framework/network-programming/programming-pluggable-protocols.md)
