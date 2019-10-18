---
title: Calls Failed Per Second（每秒失败的调用次数）
ms.date: 03/30/2017
ms.assetid: e4ef3773-f650-4876-99cf-4d0c02aa03d4
ms.openlocfilehash: e7c0b53f4c2b1a7e87a5791b44e452ec9146c459
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2019
ms.locfileid: "72321120"
---
# <a name="calls-failed-per-second"></a>Calls Failed Per Second（每秒失败的调用次数）
计数器名称：Calls Failed Per Second（每秒失败的调用次数）  
  
## <a name="description"></a>描述  
 该操作中每秒钟出现未处理异常的调用数目。  
  
 此计数器的性能计数器类型为[PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649)，其值使用以下公式进行计算。  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)  
  
 此操作中每次出现未处理的异常时，此计数器都会递增。  
  
## <a name="see-also"></a>请参阅

- [在协定和服务中指定并处理错误](../../specifying-and-handling-faults-in-contracts-and-services.md)
