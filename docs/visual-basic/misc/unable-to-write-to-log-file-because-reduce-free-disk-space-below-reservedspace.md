---
title: 无法写入日志文件，因为写入日志文件会使可用磁盘空间低于 ReservedSpace 值
ms.date: 07/20/2015
f1_keywords:
- vbrApplicationLog_ReservedSpaceEncroached
ms.assetid: 95832e70-4ecc-47aa-90c1-f35c4d468151
ms.openlocfilehash: dc7e97bfc5aa3963e1edcd204f5b81d21edab579
ms.sourcegitcommit: e08b319358a8025cc6aa38737854f7bdb87183d6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/29/2019
ms.locfileid: "64913236"
---
# <a name="unable-to-write-to-log-file-because-writing-to-it-would-reduce-free-disk-space-below-reservedspace-value"></a><span data-ttu-id="3296e-102">无法写入日志文件，因为写入日志文件会使可用磁盘空间低于 ReservedSpace 值</span><span class="sxs-lookup"><span data-stu-id="3296e-102">Unable to write to log file because writing to it would reduce free disk space below ReservedSpace value</span></span>
<span data-ttu-id="3296e-103"><xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> 类无法写入日志文件，原因如下：</span><span class="sxs-lookup"><span data-stu-id="3296e-103">The <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> class could not write to the log file because:</span></span>  
  
- <span data-ttu-id="3296e-104">可用磁盘空间量（以字节为单位）小于 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.ReserveDiskSpace%2A> 属性的值</span><span class="sxs-lookup"><span data-stu-id="3296e-104">The amount of free disk space (in bytes) is less than the value of the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.ReserveDiskSpace%2A> property</span></span>  
  
     <span data-ttu-id="3296e-105">—和—</span><span class="sxs-lookup"><span data-stu-id="3296e-105">—and—</span></span>  
  
- <span data-ttu-id="3296e-106"><xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> 属性的值为 <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.ThrowException>。</span><span class="sxs-lookup"><span data-stu-id="3296e-106">The value of the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> property was <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.ThrowException>.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="3296e-107">更正此错误</span><span class="sxs-lookup"><span data-stu-id="3296e-107">To correct this error</span></span>  
  
1. <span data-ttu-id="3296e-108">将现有日志存档后将其从计算机中删除，以允许 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> 对象创建新日志。</span><span class="sxs-lookup"><span data-stu-id="3296e-108">Archive the existing logs and remove them from the computer to allow the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> object to create new logs.</span></span>  
  
2. <span data-ttu-id="3296e-109">将 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.ReserveDiskSpace%2A> 属性的值更改为一个较小的数字，以保留更少的磁盘空间。</span><span class="sxs-lookup"><span data-stu-id="3296e-109">Change the value of the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.ReserveDiskSpace%2A> property to a smaller number to reserve less disk space.</span></span>  
  
3. <span data-ttu-id="3296e-110">如果没有足够的可用磁盘空间，则将 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> 属性设置为 <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.DiscardMessages> 以放弃消息而不发出警告消息。</span><span class="sxs-lookup"><span data-stu-id="3296e-110">Set the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> property to <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.DiscardMessages> to discard messages without warning if there is not enough free disk space.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3296e-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="3296e-111">See also</span></span>

- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.ReserveDiskSpace%2A>
- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A>
- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener>
- [<span data-ttu-id="3296e-112">My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="3296e-112">My.Application.Log</span></span>](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
- [<span data-ttu-id="3296e-113">My.Application.Info.DirectoryPath</span><span class="sxs-lookup"><span data-stu-id="3296e-113">My.Application.Info.DirectoryPath</span></span>](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
