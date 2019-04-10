---
title: 无法获取日志的流
ms.date: 07/20/2015
f1_keywords:
- vbrApplicationLog_ExhaustedPossibleStreamNames
ms.assetid: 33994f52-8efb-4790-a459-033e5c1db632
ms.openlocfilehash: 540ff3fbba72d33b2efaa58ad7a8019628f5e83f
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59344749"
---
# <a name="unable-to-obtain-a-stream-for-the-log"></a><span data-ttu-id="e098f-102">无法获取日志的流</span><span class="sxs-lookup"><span data-stu-id="e098f-102">Unable to obtain a stream for the log</span></span>
<span data-ttu-id="e098f-103">无法获取日志的流。</span><span class="sxs-lookup"><span data-stu-id="e098f-103">Unable to obtain a stream for the log.</span></span> <span data-ttu-id="e098f-104">基于潜在文件名\<名称 > 已在使用。</span><span class="sxs-lookup"><span data-stu-id="e098f-104">Potential file names based on \<name> are already in use.</span></span>  
  
 <span data-ttu-id="e098f-105"><xref:Microsoft.VisualBasic.Logging.FileLogTraceListener>类不能创建新的日志文件，因为所有潜在的日志文件名称基于\<名称 > 已在使用。</span><span class="sxs-lookup"><span data-stu-id="e098f-105">The <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> class could not create a new log file because all potential log file names based on \<name> are already in use.</span></span>  
  
 <span data-ttu-id="e098f-106">具有过多的日志文件可能表明应用程序存在结构问题。</span><span class="sxs-lookup"><span data-stu-id="e098f-106">Having too many log files may indicate an architectural problem with the application.</span></span> <span data-ttu-id="e098f-107">有关详细信息，请参阅 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> 类的文档。</span><span class="sxs-lookup"><span data-stu-id="e098f-107">See the documentation for the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> class for more information.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e098f-108">更正此错误</span><span class="sxs-lookup"><span data-stu-id="e098f-108">To correct this error</span></span>  
  
1. <span data-ttu-id="e098f-109">将 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.LogFileCreationSchedule%2A> 属性设置为 <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Daily> 或 <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Weekly> ，以便在日志文件名中包含日期戳。</span><span class="sxs-lookup"><span data-stu-id="e098f-109">Set the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.LogFileCreationSchedule%2A> property to <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Daily> or <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Weekly> to include a date-stamp in the log file name.</span></span>  
  
2. <span data-ttu-id="e098f-110">将现有日志存档后将其从计算机中删除，以允许 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> 对象创建新日志。</span><span class="sxs-lookup"><span data-stu-id="e098f-110">Archive the existing logs and remove them from the computer to allow the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> object to create new logs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e098f-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="e098f-111">See also</span></span>

- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener>
- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.LogFileCreationSchedule%2A>
- [<span data-ttu-id="e098f-112">My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="e098f-112">My.Application.Log</span></span>](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
- [<span data-ttu-id="e098f-113">My.Application.Info.DirectoryPath</span><span class="sxs-lookup"><span data-stu-id="e098f-113">My.Application.Info.DirectoryPath</span></span>](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
