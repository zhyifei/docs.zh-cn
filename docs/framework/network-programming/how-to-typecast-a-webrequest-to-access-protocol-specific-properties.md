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
# <a name="how-to-typecast-a-webrequest-to-access-protocol-specific-properties"></a>如何：转换 WebRequest 以访问协议特定属性
此示例演示如何类型转换 WebRequest 以访问特定于协议的属性。  
  
## <a name="example"></a>示例  
  
```csharp  
HttpWebRequest httpreq =   
   (HttpWebRequest) WebRequest.Create("http://www.contoso.com/");  
```  
  
```vb  
Dim httpreq As HttpWebRequest = _  
   CType(WebRequest.Create("http://www.contoso.com/"), HttpWebRequest)  
```  
  
## <a name="see-also"></a>请参阅

- [对可插入协议进行编程](../../../docs/framework/network-programming/programming-pluggable-protocols.md)
