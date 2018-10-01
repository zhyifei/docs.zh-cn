---
title: 如何：使 WebRequest 能够使用代理以与 Internet 通信
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 63c0ef2c-44b5-4c54-9804-ba0b9b001ac7
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 86bf21580db9bc6d9890f0935e283b653ba2e0b5
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/27/2018
ms.locfileid: "47397785"
---
# <a name="how-to-enable-a-webrequest-to-use-a-proxy-to-communicate-with-the-internet"></a>如何：使 WebRequest 能够使用代理以与 Internet 通信
此示例将创建一个全局代理实例，该实例将启用任何 <xref:System.Net.WebRequest> 以使用代理与 Internet 进行通信。 该示例假定代理服务器名为 `webproxy`，且在端口 80（标准 HTTP 端口）上进行通信。  
  
## <a name="example"></a>示例  
  
```csharp  
WebProxy proxyObject = new WebProxy("http://webproxy:80/");  
GlobalProxySelection.Select = proxyObject;  
```  
  
```vb  
Dim proxyObject As WebProxy = New WebProxy("http://webproxy:80/")  
GlobalProxySelection.Select = proxyObject  
```  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
-   引用 System.Net 命名空间。  
  
## <a name="see-also"></a>请参阅  
 [使用应用程序协议](../../../docs/framework/network-programming/using-application-protocols.md)  
 [通过代理访问 Internet](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)
