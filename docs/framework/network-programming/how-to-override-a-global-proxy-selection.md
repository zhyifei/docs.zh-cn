---
title: "如何：重写全局代理选择"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 0da481a9-b414-4230-beb0-e3ceba882fe5
caps.latest.revision: "8"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: dc9f8f4e958d1988cecd769431e99d70ff2a4cfd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-override-a-global-proxy-selection"></a>如何：重写全局代理选择
此示例将 WebRequest 发送到 www.contoso.com，其在端口 80 上使用名为 `alternateproxy` 的代理服务器替代全局代理选择。  
  
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
  
-   引用 System.Net 命名空间。  
  
## <a name="see-also"></a>另请参阅  
 [使用应用程序协议](../../../docs/framework/network-programming/using-application-protocols.md)  
 [通过代理访问 Internet](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)
