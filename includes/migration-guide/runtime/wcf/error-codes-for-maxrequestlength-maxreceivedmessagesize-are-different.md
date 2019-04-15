---
ms.openlocfilehash: c9d6111edcfeec6852f23cc0768833de32e61022
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235153"
---
### <a name="error-codes-for-maxrequestlength-or-maxreceivedmessagesize-are-different"></a>maxRequestLength 或 maxReceivedMessageSize 的错误代码是不同的

|   |   |
|---|---|
|详细信息|Internet Information Services (IIS) 或 ASP.NET 开发服务器承载的 WCF Web 服务中的消息如果超过 maxRequestLength（在 ASP.NET 中）或 maxReceivedMessageSize（在 WCF 中），则有不同的错误代码。HTTP 状态代码已从 400（错误请求）更改为 413（请求实体太大），并且超过 maxRequestLength 或 maxReceivedMessageSize 设置的消息引发了 <xref:System.ServiceModel.ProtocolException?displayProperty=name> 异常。 这包括转换模式为“流式处理”的情况。|
|建议|在消息长度超过 ASP.NET 或 WCF 所允许的限制的情况下，此更改有利于调试。必须基于 HTTP 400 状态代码修改执行处理的任何代码。|
|范围|边缘|
|版本|4.5|
|类型|运行时|
