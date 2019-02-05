---
title: 不能删除系统事件日志
ms.date: 07/20/2015
ms.assetid: 26ca8819-4ce5-49c6-98f3-27fe9e2e8e3d
ms.openlocfilehash: 7c2d03b0e9c27c0cc935963251006cfe83f11aba
ms.sourcegitcommit: facefcacd7ae2e5645e463bc841df213c505ffd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2019
ms.locfileid: "55739119"
---
# <a name="system-event-log-cannot-be-deleted"></a><span data-ttu-id="d9a2b-102">不能删除系统事件日志</span><span class="sxs-lookup"><span data-stu-id="d9a2b-102">System event log cannot be deleted</span></span>
<span data-ttu-id="d9a2b-103">试图删除系统事件日志（该日志是不能被删除的）。</span><span class="sxs-lookup"><span data-stu-id="d9a2b-103">An attempt has been made to delete the system event log, which cannot be deleted.</span></span> <span data-ttu-id="d9a2b-104">系统日志跟踪系统事件（如系统启动和硬件故障）。</span><span class="sxs-lookup"><span data-stu-id="d9a2b-104">The system log tracks system events such as system startup and hardware failures.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d9a2b-105">更正此错误</span><span class="sxs-lookup"><span data-stu-id="d9a2b-105">To correct this error</span></span>  
  
-   <span data-ttu-id="d9a2b-106">请考虑让应用程序写入应用程序或自定义日志，而不是系统事件日志。</span><span class="sxs-lookup"><span data-stu-id="d9a2b-106">Consider having your application write to an application or custom log, rather than the system event log.</span></span>  
  
-   <span data-ttu-id="d9a2b-107">请勿试图删除系统事件日志。</span><span class="sxs-lookup"><span data-stu-id="d9a2b-107">Do not attempt to delete the system event log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9a2b-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="d9a2b-108">See also</span></span>
- <span data-ttu-id="d9a2b-109">[管理事件日志](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/4f69axw4(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="d9a2b-109">[Administering Event Logs](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/4f69axw4(v=vs.90))</span></span>
- <span data-ttu-id="d9a2b-110">[如何：创建和删除自定义事件日志](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/49dwckkz(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="d9a2b-110">[How to: Create and Remove Custom Event Logs](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/49dwckkz(v=vs.90))</span></span>
