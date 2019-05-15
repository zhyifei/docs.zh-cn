---
title: 如何：访问 HTTP 特定的属性
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f8848c7e-f5c5-4d42-b86d-9951ff8f4146
ms.openlocfilehash: 044a48aaffbd2d4ef490405a65236b17ecca1fbf
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64645809"
---
# <a name="how-to-access-http-specific-properties"></a>如何：访问 HTTP 特定的属性
此示例演示如何关闭 HTTP 保持的连接行为并从 Web 服务器获取协议版本号。  
  
## <a name="example"></a>示例  
  
```vb  
Dim HttpWReq As HttpWebRequest= _  
    CType(WebRequest.Create("http://www.contoso.com"), HttpWebRequest)  
' Turn off connection keep-alives.  
HttpWReq.KeepAlive = False  
  
Dim HttpWResp As HttpWebResponse = _  
    CType(HttpWReq.GetResponse(), HttpWebResponse)  
  
' Get the HTTP protocol version number returned by the server.  
Dim ver As String = HttpWResp.ProtocolVersion.ToString()  
HttpWResp.Close()  
```  
  
```csharp  
HttpWebRequest HttpWReq =   
    (HttpWebRequest)WebRequest.Create("http://www.contoso.com");  
// Turn off connection keep-alives.  
HttpWReq.KeepAlive = false;  
  
HttpWebResponse HttpWResp = (HttpWebResponse)HttpWReq.GetResponse();  
  
// Get the HTTP protocol version number returned by the server.  
String ver = HttpWResp.ProtocolVersion.ToString();  
HttpWResp.Close();  
```  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
- 引用 System.Net 命名空间。  
  
## <a name="see-also"></a>请参阅

- [通过代理访问 Internet](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)
- [使用应用程序协议](../../../docs/framework/network-programming/using-application-protocols.md)
- [HTTP](../../../docs/framework/network-programming/http.md)
