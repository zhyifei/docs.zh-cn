---
title: 服务性能计数器
ms.date: 03/30/2017
ms.assetid: 4210f549-31f2-4ea7-99bd-69eaffb98ddf
ms.openlocfilehash: 18a9e6336b70341f5da9c7b73cbd3f9bd3f958c7
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2019
ms.locfileid: "70044277"
---
# <a name="service-performance-counters"></a>服务性能计数器
服务性能计数器将服务行为作为整体来进行衡量，可用于诊断服务整体性能。 如果使用性能监视器 (Perfmon.exe) 查看，可以在 `ServiceModelService 4.0.0.0` 性能对象下找到服务性能计数器。 使用以下模式命名计数器实例：  
  
```  
ServiceName@ServiceBaseAddress  
```  
  
> [!CAUTION]
> 性能计数器实例的名称长度存在限制。 当 Windows Communication Foundation (WCF) 计数器实例名称超出最大长度时, WCF 会将部分实例名称替换为哈希值。  
  
## <a name="see-also"></a>请参阅

- [性能计数器](../../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)
