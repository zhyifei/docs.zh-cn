---
title: 不能删除系统事件日志
ms.date: 07/20/2015
ms.assetid: 26ca8819-4ce5-49c6-98f3-27fe9e2e8e3d
ms.openlocfilehash: 30be01d03a25c246eda2be69a6fbc05e5ff25672
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61593888"
---
# <a name="system-event-log-cannot-be-deleted"></a><span data-ttu-id="1c3c7-102">不能删除系统事件日志</span><span class="sxs-lookup"><span data-stu-id="1c3c7-102">System event log cannot be deleted</span></span>
<span data-ttu-id="1c3c7-103">试图删除系统事件日志（该日志是不能被删除的）。</span><span class="sxs-lookup"><span data-stu-id="1c3c7-103">An attempt has been made to delete the system event log, which cannot be deleted.</span></span> <span data-ttu-id="1c3c7-104">系统日志跟踪系统事件（如系统启动和硬件故障）。</span><span class="sxs-lookup"><span data-stu-id="1c3c7-104">The system log tracks system events such as system startup and hardware failures.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1c3c7-105">更正此错误</span><span class="sxs-lookup"><span data-stu-id="1c3c7-105">To correct this error</span></span>  
  
- <span data-ttu-id="1c3c7-106">请考虑让应用程序写入应用程序或自定义日志，而不是系统事件日志。</span><span class="sxs-lookup"><span data-stu-id="1c3c7-106">Consider having your application write to an application or custom log, rather than the system event log.</span></span>  
  
- <span data-ttu-id="1c3c7-107">请勿试图删除系统事件日志。</span><span class="sxs-lookup"><span data-stu-id="1c3c7-107">Do not attempt to delete the system event log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c3c7-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="1c3c7-108">See also</span></span>

- <span data-ttu-id="1c3c7-109">[管理事件日志](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/4f69axw4(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="1c3c7-109">[Administering Event Logs](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/4f69axw4(v=vs.90))</span></span>
- <span data-ttu-id="1c3c7-110">[如何：创建和删除自定义事件日志](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/49dwckkz(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="1c3c7-110">[How to: Create and Remove Custom Event Logs](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/49dwckkz(v=vs.90))</span></span>
