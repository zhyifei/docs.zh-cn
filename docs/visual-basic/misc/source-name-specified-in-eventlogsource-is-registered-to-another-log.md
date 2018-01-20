---
title: "EventLogSource 中指定的源名称已注册到不同于 EventLogName 中所指定的日志的另一个日志"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
ms.assetid: 7317e100-098b-408d-86e5-7c74cf8558c7
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e0a100789486dda403f483489e73accbf219374c
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="source-name-specified-in-eventlogsource-is-registered-to-a-log-other-than-that-specified-in-eventlogname"></a>EventLogSource 中指定的源名称已注册到不同于 EventLogName 中所指定的日志的另一个日志
`EventLog` 正在尝试引用注册到其他日志的源。 如果要向事件日志写入条目，则必须指定 <xref:System.Diagnostics.EventLog.Source%2A> 属性。 <xref:System.Diagnostics.EventLog.Source%2A> 属性将具有事件日志的组件注册为条目的有效源。 单个源一次仅可关联（从而仅能将条目写入）一个事件日志。  
  
 默认情况下，如果在未事先将组件注册为有效源的情况下尝试写入条目，系统将自动使用 <xref:System.Diagnostics.EventLog.Source%2A> 属性的值作为源字符串将该源注册到事件日志。  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   确保已将源注册到正确的日志。 要执行此操作，请使用 <xref:System.Diagnostics.EventLog.CreateEventSource%2A> 方法或其重载之一来指定向事件日志唯一标识你的组件的字符串。  
  
## <a name="see-also"></a>请参阅  
 [管理事件日志](http://msdn.microsoft.com/library/35f53238-bdd2-417b-acd8-2fd9f7397f18)  
 [事件日志引用](http://msdn.microsoft.com/library/4af0661c-6c96-49f4-961d-b26ed9bc3e87)  
 [如何： 将你的应用程序添加为事件日志条目的源](http://msdn.microsoft.com/library/948ff920-a739-4e66-a191-ee951512d42c)  
 [如何： 删除的事件源](http://msdn.microsoft.com/library/bc66c900-4b8a-426a-b8e2-17031a20167e)
