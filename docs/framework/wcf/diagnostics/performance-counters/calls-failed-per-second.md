---
title: Calls Failed Per Second（每秒失败的调用次数）
ms.date: 03/30/2017
ms.assetid: e4ef3773-f650-4876-99cf-4d0c02aa03d4
ms.openlocfilehash: aa8cd4c2d9f642b525b2b9ccb931c4f2101a5129
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/28/2019
ms.locfileid: "67421791"
---
# <a name="calls-failed-per-second"></a>Calls Failed Per Second（每秒失败的调用次数）
计数器名称：Calls Failed Per Second（每秒失败的调用次数）  
  
## <a name="description"></a>描述  
 该操作中每秒钟出现未处理异常的调用数目。  
  
 此计数器为性能计数器类型[PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649)，使用以下公式计算其值。  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)  
  
 此计数器在每次在此操作中出现未处理异常时递增。  
  
## <a name="see-also"></a>请参阅

- [在协定和服务中指定并处理错误](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
