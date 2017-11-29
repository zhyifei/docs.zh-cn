---
title: "终结点：Calls Failed Per Second（每秒失败的调用次数）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bcbe9da4-c8dd-4e27-b630-11611adc7580
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5da436c5e8159ff922c36172490a28e854bbee8b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="endpoint-calls-failed-per-second"></a>终结点：Calls Failed Per Second（每秒失败的调用次数）
计数器名称：Calls Failed Per Second（每秒失败的调用次数）。  
  
## <a name="description"></a>描述  
 一秒钟内通过此终结点收到且具有未处理的异常的调用次数。  
  
 此计数器为性能计数器类型[PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649)，使用以下公式计算其值。  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)  
  
 每当此终结点处有未处理的异常时，此计数器就会增加。  
  
## <a name="see-also"></a>另请参阅  
 [在协定和服务中指定并处理错误](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
