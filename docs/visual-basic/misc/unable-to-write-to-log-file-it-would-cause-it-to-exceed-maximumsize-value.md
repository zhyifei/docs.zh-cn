---
title: 无法写入日志文件，原因是写入将导致日志文件超过 MaximumSize 值。
ms.date: 07/20/2015
f1_keywords:
- vbrApplicationLog_FileExceedsMaximumSize
ms.assetid: 61747a9c-e460-424b-a365-73cdba9dd428
ms.openlocfilehash: 6b8a7682e2764910551cfd9730e82293d1b2ca1a
ms.sourcegitcommit: 5c1abeec15fbddcc7dbaa729fabc1f1f29f12045
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2019
ms.locfileid: "58026673"
---
# <a name="unable-to-write-to-log-file-because-writing-to-it-would-cause-it-to-exceed-maximumsize-value"></a><span data-ttu-id="6bcc9-102">无法写入日志文件，原因是写入将导致日志文件超过 MaximumSize 值。</span><span class="sxs-lookup"><span data-stu-id="6bcc9-102">Unable to write to log file because writing to it would cause it to exceed MaximumSize value</span></span>
<span data-ttu-id="6bcc9-103"><xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> 类无法写入日志文件，原因如下：</span><span class="sxs-lookup"><span data-stu-id="6bcc9-103">The <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> class could not write to the log file because:</span></span>  
  
-   <span data-ttu-id="6bcc9-104">日志文件的大小（以字节为单位）大于 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.MaxFileSize%2A> 属性的值</span><span class="sxs-lookup"><span data-stu-id="6bcc9-104">The log file size (in bytes) is greater than the value of the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.MaxFileSize%2A> property</span></span>  
  
     <span data-ttu-id="6bcc9-105">—和—</span><span class="sxs-lookup"><span data-stu-id="6bcc9-105">—and—</span></span>  
  
-   <span data-ttu-id="6bcc9-106"><xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> 属性的值为 <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.ThrowException>。</span><span class="sxs-lookup"><span data-stu-id="6bcc9-106">The value of the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> property was <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.ThrowException>.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="6bcc9-107">更正此错误</span><span class="sxs-lookup"><span data-stu-id="6bcc9-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="6bcc9-108">将现有日志存档后将其从计算机中删除，以允许 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> 对象创建新日志。</span><span class="sxs-lookup"><span data-stu-id="6bcc9-108">Archive the existing logs and remove them from the computer to allow the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> object to create new logs.</span></span>  
  
2.  <span data-ttu-id="6bcc9-109">更改 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.MaxFileSize%2A> 属性的值，以允许写入更大的日志。</span><span class="sxs-lookup"><span data-stu-id="6bcc9-109">Change the value of the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.MaxFileSize%2A> property to allow for larger logs.</span></span>  
  
3.  <span data-ttu-id="6bcc9-110">如果日志过大，则将 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> 属性设置为 <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.DiscardMessages> 以放弃消息而不发出警告。</span><span class="sxs-lookup"><span data-stu-id="6bcc9-110">Set the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> property to <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.DiscardMessages> to discard messages without warning if the log is too large.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bcc9-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="6bcc9-111">See also</span></span>

- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.MaxFileSize%2A>
- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A>
- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener>
- [<span data-ttu-id="6bcc9-112">My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="6bcc9-112">My.Application.Log</span></span>](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
- [<span data-ttu-id="6bcc9-113">My.Application.Info.DirectoryPath</span><span class="sxs-lookup"><span data-stu-id="6bcc9-113">My.Application.Info.DirectoryPath</span></span>](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
