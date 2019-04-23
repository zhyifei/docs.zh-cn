---
title: 无法写入日志文件，原因是写入将导致日志文件超过 MaximumSize 值。
ms.date: 07/20/2015
f1_keywords:
- vbrApplicationLog_FileExceedsMaximumSize
ms.assetid: 61747a9c-e460-424b-a365-73cdba9dd428
ms.openlocfilehash: 587b35282c7e78da1fdf4ccf9d08214e5665119c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59298599"
---
# <a name="unable-to-write-to-log-file-because-writing-to-it-would-cause-it-to-exceed-maximumsize-value"></a><span data-ttu-id="8ed6e-102">无法写入日志文件，原因是写入将导致日志文件超过 MaximumSize 值。</span><span class="sxs-lookup"><span data-stu-id="8ed6e-102">Unable to write to log file because writing to it would cause it to exceed MaximumSize value</span></span>
<span data-ttu-id="8ed6e-103"><xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> 类无法写入日志文件，原因如下：</span><span class="sxs-lookup"><span data-stu-id="8ed6e-103">The <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> class could not write to the log file because:</span></span>  
  
-   <span data-ttu-id="8ed6e-104">日志文件的大小（以字节为单位）大于 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.MaxFileSize%2A> 属性的值</span><span class="sxs-lookup"><span data-stu-id="8ed6e-104">The log file size (in bytes) is greater than the value of the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.MaxFileSize%2A> property</span></span>  
  
     <span data-ttu-id="8ed6e-105">—和—</span><span class="sxs-lookup"><span data-stu-id="8ed6e-105">—and—</span></span>  
  
-   <span data-ttu-id="8ed6e-106"><xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> 属性的值为 <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.ThrowException>。</span><span class="sxs-lookup"><span data-stu-id="8ed6e-106">The value of the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> property was <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.ThrowException>.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="8ed6e-107">更正此错误</span><span class="sxs-lookup"><span data-stu-id="8ed6e-107">To correct this error</span></span>  
  
1. <span data-ttu-id="8ed6e-108">将现有日志存档后将其从计算机中删除，以允许 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> 对象创建新日志。</span><span class="sxs-lookup"><span data-stu-id="8ed6e-108">Archive the existing logs and remove them from the computer to allow the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> object to create new logs.</span></span>  
  
2. <span data-ttu-id="8ed6e-109">更改 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.MaxFileSize%2A> 属性的值，以允许写入更大的日志。</span><span class="sxs-lookup"><span data-stu-id="8ed6e-109">Change the value of the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.MaxFileSize%2A> property to allow for larger logs.</span></span>  
  
3. <span data-ttu-id="8ed6e-110">如果日志过大，则将 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> 属性设置为 <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.DiscardMessages> 以放弃消息而不发出警告。</span><span class="sxs-lookup"><span data-stu-id="8ed6e-110">Set the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> property to <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.DiscardMessages> to discard messages without warning if the log is too large.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ed6e-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="8ed6e-111">See also</span></span>

- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.MaxFileSize%2A>
- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A>
- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener>
- [<span data-ttu-id="8ed6e-112">My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="8ed6e-112">My.Application.Log</span></span>](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
- [<span data-ttu-id="8ed6e-113">My.Application.Info.DirectoryPath</span><span class="sxs-lookup"><span data-stu-id="8ed6e-113">My.Application.Info.DirectoryPath</span></span>](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
