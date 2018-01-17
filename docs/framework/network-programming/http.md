---
title: HTTP
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- protocols, HTTP
- sending data, HTTP
- HttpWebResponse class, sending and receiving data
- HTTP
- receiving data, HTTP
- application protocols, HTTP
- Internet, HTTP
- network resources, HTTP
- HTTP, about HTTP
- HttpWebRequest class, sending and receiving data
ms.assetid: 985fe5d8-eb71-4024-b361-41fbdc1618d8
caps.latest.revision: "10"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: f72a77e19d04c0dd55887628033f7c975ac3ff25
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="http"></a>HTTP
.NET Framework 提供全面的支持对 HTTP 协议，可使所有 Internet 流量，大多数与<xref:System.Net.HttpWebRequest>和<xref:System.Net.HttpWebResponse>类。 这些类派生自 <xref:System.Net.WebRequest> 和 <xref:System.Net.WebResponse>，默认情况下将被返回，无论静态方法 <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> 遇到以“http”还是“https”开头的 URI。 大多数情况下，WebRequest 和 WebResponse 类提供发出请求的所有必需项，但如果需要访问作为属性公开的特定于 HTTP 的功能，可以将这些类转换为 HttpWebRequest 或 HttpWebResponse 类型。  
  
 HttpWebRequest 和 HttpWebResponse 封装标准 HTTP 请求和响应事务，并提供对通用 HTTP 标头的访问。 这些类还支持大多数 HTTP 1.1 功能，包括管道、在区块中发送和接收数据、身份验证、预身份验证、加密、代理支持、服务器证书验证和连接管理。 自定义标头和未通过属性提供的标头可以存储在 Headers 属性并通过该属性进行访问。  
  
 HttpWebRequest 是 WebRequest 使用的默认类，并且无需注册即可将 URI 传递到 WebRequest.Create 方法。  
  
 可以通过将 <xref:System.Net.HttpWebRequest.AllowAutoRedirect%2A> 属性设置为 true（默认值）来使应用程序自动遵循 HTTP 重定向。 应用程序将重定向请求，并且 HttpWebResponse 的 <xref:System.Net.HttpWebResponse.ResponseUri%2A> 属性将包含响应请求的实际 Web 资源。 如果将 AllowAutoRedirect 设置为 false，则需要应用程序能将重定向处理为 HTTP 协议错误。  
  
 应用程序通过捕获 <xref:System.Net.WebException>（其中 <xref:System.Net.WebException.Status%2A> 设置为 <xref:System.Net.WebExceptionStatus>）来接收 HTTP 协议错误。 <xref:System.Net.WebException.Response%2A> 属性包含由服务器发送的 WebResponse，并指示遇到的实际 HTTP 错误。  
  
## <a name="see-also"></a>请参阅  
 [通过代理访问 Internet](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)  
 [使用应用程序协议](../../../docs/framework/network-programming/using-application-protocols.md)  
 [如何：访问 HTTP 特定的属性](../../../docs/framework/network-programming/how-to-access-http-specific-properties.md)
