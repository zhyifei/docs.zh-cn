---
title: "另一个事件日志已使用该名称注册了一个源"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
ms.assetid: e6f5cd95-bb3f-4845-84fb-ae623a9bd44e
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8beea344d233794ddc36d7fc53db1c01be84399f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="another-event-log-has-already-registered-a-source-with-this-name"></a><span data-ttu-id="dcfce-102">另一个事件日志已使用该名称注册了一个源</span><span class="sxs-lookup"><span data-stu-id="dcfce-102">Another event log has already registered a source with this name</span></span>
<span data-ttu-id="dcfce-103">已尝试向事件日志写入条目，其中指定的源使用其他事件日志进行注册。</span><span class="sxs-lookup"><span data-stu-id="dcfce-103">An attempt was made to write an entry to an event log where the specified source is registered with another event log.</span></span>  
  
 <span data-ttu-id="dcfce-104">在组件将条目写入日志前，必须设置 <xref:System.Diagnostics.EventLog.Source%2A> 组件实例的 <xref:System.Diagnostics.EventLog> 属性。</span><span class="sxs-lookup"><span data-stu-id="dcfce-104">You must set the <xref:System.Diagnostics.EventLog.Source%2A> property of your <xref:System.Diagnostics.EventLog> component instance before your component writes an entry to a log.</span></span> <span data-ttu-id="dcfce-105">发生此情况时，系统将检查所指定的源是否使用写入该组件的事件日志进行注册，并在需要时调用 <xref:System.Diagnostics.EventLog.CreateEventSource%2A> 。</span><span class="sxs-lookup"><span data-stu-id="dcfce-105">When this happens, the system checks that the source you specified is registered with the event log to which the component is writing, and calls <xref:System.Diagnostics.EventLog.CreateEventSource%2A> if needed.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="dcfce-106">更正此错误</span><span class="sxs-lookup"><span data-stu-id="dcfce-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="dcfce-107">使用 <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> 或 <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> 方法删除源与第一个日志之间的关联。</span><span class="sxs-lookup"><span data-stu-id="dcfce-107">Remove the association of the source with the first log using the <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> or the <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> method.</span></span>  
  
2.  <span data-ttu-id="dcfce-108">使用新的日志注册源。</span><span class="sxs-lookup"><span data-stu-id="dcfce-108">Register the source with the new log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcfce-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dcfce-109">See Also</span></span>  
 [<span data-ttu-id="dcfce-110">My.Application.Log 对象</span><span class="sxs-lookup"><span data-stu-id="dcfce-110">My.Application.Log Object</span></span>](../../visual-basic/language-reference/objects/my-application-log-object.md)  
 [<span data-ttu-id="dcfce-111">如何： 删除的事件源</span><span class="sxs-lookup"><span data-stu-id="dcfce-111">How to: Remove an Event Source</span></span>](http://msdn.microsoft.com/en-us/bc66c900-4b8a-426a-b8e2-17031a20167e)  
 [<span data-ttu-id="dcfce-112">如何： 将你的应用程序添加为事件日志条目的源</span><span class="sxs-lookup"><span data-stu-id="dcfce-112">How to: Add Your Application as a Source of Event Log Entries</span></span>](http://msdn.microsoft.com/en-us/948ff920-a739-4e66-a191-ee951512d42c)
