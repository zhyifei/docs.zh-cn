---
title: 不能删除系统事件日志
ms.date: 07/20/2015
ms.assetid: 26ca8819-4ce5-49c6-98f3-27fe9e2e8e3d
ms.openlocfilehash: de8b4918af90510aa9a600272dcff1182b961153
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43501552"
---
# <a name="system-event-log-cannot-be-deleted"></a><span data-ttu-id="95429-102">不能删除系统事件日志</span><span class="sxs-lookup"><span data-stu-id="95429-102">System event log cannot be deleted</span></span>
<span data-ttu-id="95429-103">试图删除系统事件日志（该日志是不能被删除的）。</span><span class="sxs-lookup"><span data-stu-id="95429-103">An attempt has been made to delete the system event log, which cannot be deleted.</span></span> <span data-ttu-id="95429-104">系统日志跟踪系统事件（如系统启动和硬件故障）。</span><span class="sxs-lookup"><span data-stu-id="95429-104">The system log tracks system events such as system startup and hardware failures.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="95429-105">更正此错误</span><span class="sxs-lookup"><span data-stu-id="95429-105">To correct this error</span></span>  
  
-   <span data-ttu-id="95429-106">请考虑让应用程序写入应用程序或自定义日志，而不是系统事件日志。</span><span class="sxs-lookup"><span data-stu-id="95429-106">Consider having your application write to an application or custom log, rather than the system event log.</span></span>  
  
-   <span data-ttu-id="95429-107">请勿试图删除系统事件日志。</span><span class="sxs-lookup"><span data-stu-id="95429-107">Do not attempt to delete the system event log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95429-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="95429-108">See Also</span></span>  
 [<span data-ttu-id="95429-109">管理事件日志</span><span class="sxs-lookup"><span data-stu-id="95429-109">Administering Event Logs</span></span>](https://msdn.microsoft.com/library/35f53238-bdd2-417b-acd8-2fd9f7397f18)  
 [<span data-ttu-id="95429-110">如何： 创建和删除自定义事件日志</span><span class="sxs-lookup"><span data-stu-id="95429-110">How to: Create and Remove Custom Event Logs</span></span>](https://msdn.microsoft.com/library/af9b7da0-80c7-46ac-b7f7-897063ddd503)
