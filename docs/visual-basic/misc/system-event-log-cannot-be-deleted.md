---
title: 不能删除系统事件日志
ms.date: 07/20/2015
ms.assetid: 26ca8819-4ce5-49c6-98f3-27fe9e2e8e3d
ms.openlocfilehash: 72f648751107db90449a085e1a49892927fcd29b
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64620482"
---
# <a name="system-event-log-cannot-be-deleted"></a><span data-ttu-id="5c18e-102">不能删除系统事件日志</span><span class="sxs-lookup"><span data-stu-id="5c18e-102">System event log cannot be deleted</span></span>
<span data-ttu-id="5c18e-103">试图删除系统事件日志（该日志是不能被删除的）。</span><span class="sxs-lookup"><span data-stu-id="5c18e-103">An attempt has been made to delete the system event log, which cannot be deleted.</span></span> <span data-ttu-id="5c18e-104">系统日志跟踪系统事件（如系统启动和硬件故障）。</span><span class="sxs-lookup"><span data-stu-id="5c18e-104">The system log tracks system events such as system startup and hardware failures.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5c18e-105">更正此错误</span><span class="sxs-lookup"><span data-stu-id="5c18e-105">To correct this error</span></span>  
  
- <span data-ttu-id="5c18e-106">请考虑让应用程序写入应用程序或自定义日志，而不是系统事件日志。</span><span class="sxs-lookup"><span data-stu-id="5c18e-106">Consider having your application write to an application or custom log, rather than the system event log.</span></span>  
  
- <span data-ttu-id="5c18e-107">请勿试图删除系统事件日志。</span><span class="sxs-lookup"><span data-stu-id="5c18e-107">Do not attempt to delete the system event log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c18e-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="5c18e-108">See also</span></span>

- <span data-ttu-id="5c18e-109">[管理事件日志](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/4f69axw4(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="5c18e-109">[Administering Event Logs](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/4f69axw4(v=vs.90))</span></span>
- <span data-ttu-id="5c18e-110">[如何：创建和删除自定义事件日志](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/49dwckkz(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="5c18e-110">[How to: Create and Remove Custom Event Logs](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/49dwckkz(v=vs.90))</span></span>
