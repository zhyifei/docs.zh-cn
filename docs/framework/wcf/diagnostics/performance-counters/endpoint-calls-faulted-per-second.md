---
title: 终结点：Calls Faulted Per Second（每秒出错的调用次数）
ms.date: 03/30/2017
ms.assetid: 9840fc0a-0e4d-4638-96fd-40e3ab9e4667
ms.openlocfilehash: ead4b074748307f30d16557c3359f730880595da
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163535"
---
# <a name="endpoint-calls-faulted-per-second"></a>终结点：Calls Faulted Per Second（每秒出错的调用次数）
计数器名称：Calls Faulted Per Second（每秒出错的调用次数）。  
  
## <a name="description"></a>描述  
 一秒内向此终结点返回了错误的调用的数目。  
  
 此计数器的性能计数器类型[PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))，其值使用以下公式进行计算。  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)  
  
 在 Windows Communication Foundation （WCF）应用程序中，服务方法使用 SOAP 错误消息来传递处理错误信息。 SOAP 错误是包括在服务操作元数据中的消息类型，因此会创建一个错误协定，客户端可使用该协定来使执行更加可靠或更具交互性。 由于 SOAP 错误在客户端以 XML 格式表示，因此具有高度的互操作性。  
  
## <a name="see-also"></a>另请参阅

- [在协定和服务中指定并处理错误](../../specifying-and-handling-faults-in-contracts-and-services.md)
