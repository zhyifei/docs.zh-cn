---
title: 终结点性能计数器
ms.date: 03/30/2017
ms.assetid: 7d44d576-bd4e-453b-8b76-a818ce90b806
ms.openlocfilehash: 8354cff600f8c16a5ab9b4f6efd3c0b93a46276c
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2018
ms.locfileid: "33803132"
---
# <a name="endpoint-performance-counters"></a>终结点性能计数器
终结点性能计数器可以捕获能够揭示终结点如何接受消息的数据。 如果使用性能监视器查看，可以在 `ServiceModelEndpoint 4.0.0.0` 性能对象下找到它们。 性能计数器实例使用以下模式命名：  
  
```  
(ServiceName).(ContractName)@(endpoint listener address)  
```  
  
 它们所捕获的数据与针对单个操作收集的数据类似，不同之处仅在于在整个终结点中进行了聚合。  
  
> [!CAUTION]
>  性能计数器实例的名称长度存在限制。 Windows Communication Foundation (WCF) 计数器实例名称超出最大长度，WCF 会将哈希值替换实例名称的一部分。  
  
## <a name="see-also"></a>请参阅  
 [性能计数器](../../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)
