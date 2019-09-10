---
title: 终结点性能计数器
ms.date: 03/30/2017
ms.assetid: 7d44d576-bd4e-453b-8b76-a818ce90b806
ms.openlocfilehash: 72512a15d5b378b1ccb65995441f8f67e251febb
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70856093"
---
# <a name="endpoint-performance-counters"></a>终结点性能计数器
终结点性能计数器可以捕获能够揭示终结点如何接受消息的数据。 如果使用性能监视器查看，可以在 `ServiceModelEndpoint 4.0.0.0` 性能对象下找到它们。 性能计数器实例使用以下模式命名：  
  
`(ServiceName).(ContractName)@(endpoint listener address)`  
  
 它们所捕获的数据与针对单个操作收集的数据类似，不同之处仅在于在整个终结点中进行了聚合。  
  
> [!CAUTION]
> 性能计数器实例的名称长度存在限制。 当 Windows Communication Foundation （WCF）计数器实例名称超出最大长度时，WCF 会将部分实例名称替换为哈希值。  
  
## <a name="see-also"></a>请参阅

- [性能计数器](../../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)
