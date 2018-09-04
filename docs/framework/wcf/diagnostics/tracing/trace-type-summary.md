---
title: 跟踪类型摘要
ms.date: 03/30/2017
ms.assetid: e639410b-d1d1-479c-b78e-a4701d4e4085
ms.openlocfilehash: 73777df2b58b14947c416ce409bcb42d439499ec
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43512533"
---
# <a name="trace-type-summary"></a>跟踪类型摘要
[源级别](https://go.microsoft.com/fwlink/?LinkID=94943)定义各种跟踪级别： 严重、 错误、 警告、 信息和详细、 并提供的说明`ActivityTracing`标志切换的输出以跟踪边界和活动传输事件。  
  
 此外可以查看[TraceEventType](https://go.microsoft.com/fwlink/?LinkId=95169)可以从发出的跟踪类型<xref:System.Diagnostics>。  
  
 下表列出了最重要的跟踪类型。  
  
|跟踪类型|描述|  
|----------------|-----------------|  
|严重|致命错误或应用程序崩溃。|  
|错误|可恢复的错误。|  
|警告|信息性消息。|  
|信息|非严重问题。|  
|详细|调试跟踪。|  
|Start|开始处理逻辑单元。|  
|挂起|挂起逻辑单元处理。|  
|继续|继续逻辑单元处理。|  
|停止|停止处理逻辑单元。|  
|传输|更改相关标识。|  
  
 活动定义为上述跟踪类型的组合。  
  
 下面的正则表达式用于定义本地（跟踪源）范围内的理想活动，  
  
 `R = Start (Critical | Error | Warning | Information | Verbose | Transfer | (Transfer Suspend Transfer Resume) )* Stop`  
  
 这意味着活动必须满足以下条件。  
  
-   它必须分别由开始跟踪和停止跟踪来启动和停止  
  
-   它必须刚好在挂起跟踪或恢复跟踪之前具有传输跟踪  
  
-   如果有挂起和恢复跟踪，则在挂起跟踪和恢复跟踪之间不能有任何跟踪  
  
-   只要符合上述条件，就可以有任意多个严重/错误/警告/信息/详细/传输跟踪  
  
 下面的正则表达式用于定义全局范围内的理想活动，  
  
```  
R+   
```  
  
 R 是本地范围内活动的正则表达式。 这将转换为，  
  
```  
[R+ = Start ( Critical | Error | Warning | Information | Verbose | Transfer | (Transfer Suspend Transfer Resume) )* Stop]+  
```
