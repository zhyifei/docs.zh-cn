---
title: 服务性能计数器
ms.date: 03/30/2017
ms.assetid: 4210f549-31f2-4ea7-99bd-69eaffb98ddf
ms.openlocfilehash: bdc68fd2b629c538c097dab4e1cf3f89b7f3a091
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2018
ms.locfileid: "33810182"
---
# <a name="service-performance-counters"></a>服务性能计数器
服务性能计数器将服务行为作为整体来进行衡量，可用于诊断服务整体性能。 如果使用性能监视器 (Perfmon.exe) 查看，可以在 `ServiceModelService 4.0.0.0` 性能对象下找到服务性能计数器。 使用以下模式命名计数器实例：  
  
```  
ServiceName@ServiceBaseAddress  
```  
  
> [!CAUTION]
>  性能计数器实例的名称长度存在限制。 Windows Communication Foundation (WCF) 计数器实例名称超出最大长度，WCF 会将哈希值替换实例名称的一部分。  
  
## <a name="see-also"></a>请参阅  
 [性能计数器](../../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)
