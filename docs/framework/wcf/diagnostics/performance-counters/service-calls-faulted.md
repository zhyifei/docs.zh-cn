---
title: 服务：Calls Faulted（出错的调用次数）
ms.date: 03/30/2017
ms.assetid: 6da7f100-3f61-4b3c-9409-fe1360829b8a
ms.openlocfilehash: d02139bcd6540fb973e0f1040c8877c04addc2f4
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2019
ms.locfileid: "72321435"
---
# <a name="service-calls-faulted"></a>服务：Calls Faulted（出错的调用次数）
计数器名称：Calls Faulted（出错的调用次数）。  
  
## <a name="description"></a>描述  
 此服务的返回错误的调用次数。 在 Windows Communication Foundation （WCF）应用程序中，服务方法使用 SOAP 错误消息来传递处理错误信息。 SOAP 错误是包括在服务操作元数据中的消息类型，因此会创建一个错误协定，客户端可使用该协定来使执行更加可靠或更具交互性。 由于 SOAP 错误在客户端以 XML 格式表示，因此具有高度的互操作性。  
  
## <a name="see-also"></a>请参阅

- [在协定和服务中指定并处理错误](../../specifying-and-handling-faults-in-contracts-and-services.md)
