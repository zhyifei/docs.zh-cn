---
title: 跟踪类型摘要
ms.date: 03/30/2017
ms.assetid: e639410b-d1d1-479c-b78e-a4701d4e4085
ms.openlocfilehash: 8f54f71ef63338708a29fac5557c7c7e8f257f58
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70856014"
---
# <a name="trace-type-summary"></a>跟踪类型摘要
[源级别](https://go.microsoft.com/fwlink/?LinkID=94943)定义了不同的跟踪级别：严重、错误、警告、信息和详细信息，并提供`ActivityTracing`标志的说明，该标志用于切换跟踪边界和活动传输事件的输出。  
  
 对于可以从<xref:System.Diagnostics>发出的跟踪类型，还可以查看[TraceEventType](https://go.microsoft.com/fwlink/?LinkId=95169) 。  
  
 下表列出了最重要的跟踪类型。  
  
|跟踪类型|描述|  
|----------------|-----------------|  
|关键|致命错误或应用程序崩溃。|  
|Error|可恢复的错误。|  
|警告|信息性消息。|  
|Information|非严重问题。|  
|详细|调试跟踪。|  
|Start|开始处理逻辑单元。|  
|挂起|挂起逻辑单元处理。|  
|Resume|继续逻辑单元处理。|  
|停止|停止处理逻辑单元。|  
|传输|更改相关标识。|  
  
 活动定义为上述跟踪类型的组合。  
  
 下面的正则表达式用于定义本地（跟踪源）范围内的理想活动，  
  
 `R = Start (Critical | Error | Warning | Information | Verbose | Transfer | (Transfer Suspend Transfer Resume) )* Stop`  
  
 这意味着活动必须满足以下条件。  
  
- 它必须分别由开始跟踪和停止跟踪来启动和停止  
  
- 它必须刚好在挂起跟踪或恢复跟踪之前具有传输跟踪  
  
- 如果有挂起和恢复跟踪，则在挂起跟踪和恢复跟踪之间不能有任何跟踪  
  
- 只要符合上述条件，就可以有任意多个严重/错误/警告/信息/详细/传输跟踪  
  
 下面的正则表达式用于定义全局范围内的理想活动，  
  
`R+`  
  
 R 是本地范围内活动的正则表达式。 这将转换为，  
  
`[R+ = Start ( Critical | Error | Warning | Information | Verbose | Transfer | (Transfer Suspend Transfer Resume) )* Stop]+`
