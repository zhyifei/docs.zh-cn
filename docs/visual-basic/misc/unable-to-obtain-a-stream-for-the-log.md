---
title: "无法获取日志的流"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrApplicationLog_ExhaustedPossibleStreamNames
ms.assetid: 33994f52-8efb-4790-a459-033e5c1db632
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: dba511ecd2a5c050fc2c037ac437e38715609e95
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="unable-to-obtain-a-stream-for-the-log"></a><span data-ttu-id="94ccb-102">无法获取日志的流</span><span class="sxs-lookup"><span data-stu-id="94ccb-102">Unable to obtain a stream for the log</span></span>
<span data-ttu-id="94ccb-103">无法获取日志的流。</span><span class="sxs-lookup"><span data-stu-id="94ccb-103">Unable to obtain a stream for the log.</span></span> <span data-ttu-id="94ccb-104">基于的潜在文件名\<名称 > 已被占用。</span><span class="sxs-lookup"><span data-stu-id="94ccb-104">Potential file names based on \<name> are already in use.</span></span>  
  
 <span data-ttu-id="94ccb-105"><xref:Microsoft.VisualBasic.Logging.FileLogTraceListener>类不能创建新的日志文件，因为所有潜在的日志文件名称基于\<名称 > 已被占用。</span><span class="sxs-lookup"><span data-stu-id="94ccb-105">The <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> class could not create a new log file because all potential log file names based on \<name> are already in use.</span></span>  
  
 <span data-ttu-id="94ccb-106">具有过多的日志文件可能表明应用程序存在结构问题。</span><span class="sxs-lookup"><span data-stu-id="94ccb-106">Having too many log files may indicate an architectural problem with the application.</span></span> <span data-ttu-id="94ccb-107">有关详细信息，请参阅 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> 类的文档。</span><span class="sxs-lookup"><span data-stu-id="94ccb-107">See the documentation for the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> class for more information.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="94ccb-108">更正此错误</span><span class="sxs-lookup"><span data-stu-id="94ccb-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="94ccb-109">将 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.LogFileCreationSchedule%2A> 属性设置为 <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Daily> 或 <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Weekly> ，以便在日志文件名中包含日期戳。</span><span class="sxs-lookup"><span data-stu-id="94ccb-109">Set the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.LogFileCreationSchedule%2A> property to <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Daily> or <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Weekly> to include a date-stamp in the log file name.</span></span>  
  
2.  <span data-ttu-id="94ccb-110">将现有日志存档后将其从计算机中删除，以允许 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> 对象创建新日志。</span><span class="sxs-lookup"><span data-stu-id="94ccb-110">Archive the existing logs and remove them from the computer to allow the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> object to create new logs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94ccb-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="94ccb-111">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener>  
 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.LogFileCreationSchedule%2A>  
 [<span data-ttu-id="94ccb-112">My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="94ccb-112">My.Application.Log</span></span>](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)  
 [<span data-ttu-id="94ccb-113">My.Application.Info.DirectoryPath</span><span class="sxs-lookup"><span data-stu-id="94ccb-113">My.Application.Info.DirectoryPath</span></span>](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
