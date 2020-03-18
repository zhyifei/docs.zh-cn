---
title: 如何：重写全局代理选择
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0da481a9-b414-4230-beb0-e3ceba882fe5
ms.openlocfilehash: 44845fb67aac4ff9ab9dda8cf4934153c8c4f23c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2020
ms.locfileid: "71048263"
---
# <a name="how-to-override-a-global-proxy-selection"></a>如何：重写全局代理选择
此示例将 WebRequest 发送到 **，其在端口 80 上使用名为**  的代理服务器替代全局代理选择`www.contoso.com``alternateproxy`。  
  
## <a name="example"></a>示例  
  
```csharp  
WebRequest req = WebRequest.Create("http://www.contoso.com/");  
req.Proxy = new WebProxy("http://alternateproxy:80/");  
```  
  
```vb  
Dim req As WebRequest = WebRequest.Create("http://www.contoso.com/")  
req.Proxy = New WebProxy("http://alternateproxy:80/")  
```  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
- System.Net 命名空间的 [`using` 指令](../../csharp/language-reference/keywords/using-directive.md)  。  
  
## <a name="see-also"></a>另请参阅

- [使用应用程序协议](using-application-protocols.md)
- [通过代理访问 Internet](accessing-the-internet-through-a-proxy.md)
