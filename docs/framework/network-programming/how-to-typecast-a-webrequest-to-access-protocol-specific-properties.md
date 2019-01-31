---
title: 如何：转换 WebRequest 以访问协议特定属性
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d9a8eae2-7454-46f9-b43b-c98477c5bcde
ms.openlocfilehash: 6202b0b02d334c076dbe41a785195344dd2d7efe
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54564508"
---
# <a name="how-to-typecast-a-webrequest-to-access-protocol-specific-properties"></a><span data-ttu-id="1e3b0-102">如何：转换 WebRequest 以访问协议特定属性</span><span class="sxs-lookup"><span data-stu-id="1e3b0-102">How to: Typecast a WebRequest to Access Protocol Specific Properties</span></span>
<span data-ttu-id="1e3b0-103">此示例演示如何类型转换 WebRequest 以访问特定于协议的属性。</span><span class="sxs-lookup"><span data-stu-id="1e3b0-103">This example shows how to typecast a WebRequest so that you can access protocol specific properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1e3b0-104">示例</span><span class="sxs-lookup"><span data-stu-id="1e3b0-104">Example</span></span>  
  
```csharp  
HttpWebRequest httpreq =   
   (HttpWebRequest) WebRequest.Create("http://www.contoso.com/");  
```  
  
```vb  
Dim httpreq As HttpWebRequest = _  
   CType(WebRequest.Create("http://www.contoso.com/"), HttpWebRequest)  
```  
  
## <a name="see-also"></a><span data-ttu-id="1e3b0-105">请参阅</span><span class="sxs-lookup"><span data-stu-id="1e3b0-105">See also</span></span>
- [<span data-ttu-id="1e3b0-106">对可插入协议进行编程</span><span class="sxs-lookup"><span data-stu-id="1e3b0-106">Programming Pluggable Protocols</span></span>](../../../docs/framework/network-programming/programming-pluggable-protocols.md)
