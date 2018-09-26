---
title: EventLogSource 中指定的源名称已注册到不同于 EventLogName 中所指定的日志的另一个日志
ms.date: 07/20/2015
ms.assetid: 7317e100-098b-408d-86e5-7c74cf8558c7
ms.openlocfilehash: 03fcc41b0fbb84233aa037d7af17d168050a98b6
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2018
ms.locfileid: "47208415"
---
# <a name="source-name-specified-in-eventlogsource-is-registered-to-a-log-other-than-that-specified-in-eventlogname"></a><span data-ttu-id="4f4c7-102">EventLogSource 中指定的源名称已注册到不同于 EventLogName 中所指定的日志的另一个日志</span><span class="sxs-lookup"><span data-stu-id="4f4c7-102">Source name specified in EventLogSource is registered to a log other than that specified in EventLogName</span></span>
<span data-ttu-id="4f4c7-103">`EventLog` 正在尝试引用注册到其他日志的源。</span><span class="sxs-lookup"><span data-stu-id="4f4c7-103">The `EventLog` is attempting to refer to a source that is registered to a different log.</span></span> <span data-ttu-id="4f4c7-104">如果要向事件日志写入条目，则必须指定 <xref:System.Diagnostics.EventLog.Source%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="4f4c7-104">If you are writing entries to an event log, you must specify the <xref:System.Diagnostics.EventLog.Source%2A> property.</span></span> <span data-ttu-id="4f4c7-105"><xref:System.Diagnostics.EventLog.Source%2A> 属性将具有事件日志的组件注册为条目的有效源。</span><span class="sxs-lookup"><span data-stu-id="4f4c7-105">The <xref:System.Diagnostics.EventLog.Source%2A> property registers your component with the event log as a valid source of entries.</span></span> <span data-ttu-id="4f4c7-106">单个源一次仅可关联（从而仅能将条目写入）一个事件日志。</span><span class="sxs-lookup"><span data-stu-id="4f4c7-106">A single source can be associated with (and therefore write entries to) only one event log at a time.</span></span>  
  
 <span data-ttu-id="4f4c7-107">默认情况下，如果在未事先将组件注册为有效源的情况下尝试写入条目，系统将自动使用 <xref:System.Diagnostics.EventLog.Source%2A> 属性的值作为源字符串将该源注册到事件日志。</span><span class="sxs-lookup"><span data-stu-id="4f4c7-107">By default, if you try to write an entry without first having registered your component as a valid source, the system automatically registers the source with the event log, using the value of the <xref:System.Diagnostics.EventLog.Source%2A> property as the source string.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4f4c7-108">更正此错误</span><span class="sxs-lookup"><span data-stu-id="4f4c7-108">To correct this error</span></span>  
  
-   <span data-ttu-id="4f4c7-109">确保已将源注册到正确的日志。</span><span class="sxs-lookup"><span data-stu-id="4f4c7-109">Make sure the source is registered to the correct log.</span></span> <span data-ttu-id="4f4c7-110">要执行此操作，请使用 <xref:System.Diagnostics.EventLog.CreateEventSource%2A> 方法或其重载之一来指定向事件日志唯一标识你的组件的字符串。</span><span class="sxs-lookup"><span data-stu-id="4f4c7-110">To do this, use the <xref:System.Diagnostics.EventLog.CreateEventSource%2A> method or one of its overloads to specify a string that uniquely identifies your component to the event log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f4c7-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="4f4c7-111">See Also</span></span>  
 [<span data-ttu-id="4f4c7-112">管理事件日志</span><span class="sxs-lookup"><span data-stu-id="4f4c7-112">Administering Event Logs</span></span>](https://msdn.microsoft.com/library/35f53238-bdd2-417b-acd8-2fd9f7397f18)  
 [<span data-ttu-id="4f4c7-113">事件日志引用</span><span class="sxs-lookup"><span data-stu-id="4f4c7-113">Event Log References</span></span>](https://msdn.microsoft.com/library/4af0661c-6c96-49f4-961d-b26ed9bc3e87)  
 [<span data-ttu-id="4f4c7-114">如何： 将你的应用程序添加为事件日志项的源</span><span class="sxs-lookup"><span data-stu-id="4f4c7-114">How to: Add Your Application as a Source of Event Log Entries</span></span>](https://msdn.microsoft.com/library/948ff920-a739-4e66-a191-ee951512d42c)  
 [<span data-ttu-id="4f4c7-115">如何： 删除事件源</span><span class="sxs-lookup"><span data-stu-id="4f4c7-115">How to: Remove an Event Source</span></span>](https://msdn.microsoft.com/library/bc66c900-4b8a-426a-b8e2-17031a20167e)
