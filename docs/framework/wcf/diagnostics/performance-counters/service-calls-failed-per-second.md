---
title: 服务：Calls Failed Per Second（每秒失败的调用次数）
ms.date: 03/30/2017
ms.assetid: 5a2c7939-107d-4f0c-b43c-e02e079e8a9d
ms.openlocfilehash: e165348a71101b21fa66bd4907c43335b1e476e4
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163977"
---
# <a name="service-calls-failed-per-second"></a>服务：Calls Failed Per Second（每秒失败的调用次数）
计数器名称：Calls Failed Per Second（每秒失败的调用次数）。  
  
## <a name="description"></a>描述  
 一秒钟内由此服务收到且具有未处理异常的调用次数。  
  
 此计数器的性能计数器类型[PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))，其值使用以下公式进行计算。  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)  
  
 在托管代码中，出现错误条件时引发异常。  
  
 在托管代码中，出现错误条件时引发异常。  
  
 此服务中每出现一个未处理异常，此计数器就会递增。  
  
## <a name="see-also"></a>另请参阅

- [在协定和服务中指定并处理错误](../../specifying-and-handling-faults-in-contracts-and-services.md)
