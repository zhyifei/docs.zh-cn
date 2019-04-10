---
title: Windows 窗体中的电源管理
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- battery states
- power states
ms.assetid: ad04a801-5682-4d88-92c5-26eb9cdb209a
ms.openlocfilehash: 6bb9b4f30a88ece93b17ff2510087b220d538738
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59154669"
---
# <a name="power-management-in-windows-forms"></a><span data-ttu-id="49f6f-102">Windows 窗体中的电源管理</span><span class="sxs-lookup"><span data-stu-id="49f6f-102">Power Management in Windows Forms</span></span>
<span data-ttu-id="49f6f-103">在 Windows 操作系统中，Windows 窗体应用程序可以充分利用电源管理功能。</span><span class="sxs-lookup"><span data-stu-id="49f6f-103">Your Windows Forms applications can take advantage of the power management features in the Windows operating system.</span></span> <span data-ttu-id="49f6f-104">你的应用程序可以监视计算机的电源状态和状态更改发生时执行操作。</span><span class="sxs-lookup"><span data-stu-id="49f6f-104">Your applications can monitor the power status of a computer and take action when a status change occurs.</span></span> <span data-ttu-id="49f6f-105">例如，如果你的应用程序运行在便携式计算机上，您可能想要计算机的电池电量低于某个级别时禁用你的应用程序中的某些功能。</span><span class="sxs-lookup"><span data-stu-id="49f6f-105">For example, if your application is running on a portable computer, you might want to disable certain features in your application when the computer's battery charge falls under a certain level.</span></span>  
  
 <span data-ttu-id="49f6f-106">[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]提供了<xref:Microsoft.Win32.SystemEvents.PowerModeChanged>的电源状态，例如，当用户挂起或恢复操作系统，或 AC 电源状态或电池状态发生更改时变化时，会发生的事件。</span><span class="sxs-lookup"><span data-stu-id="49f6f-106">The [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] provides a <xref:Microsoft.Win32.SystemEvents.PowerModeChanged> event that occurs whenever there is a change in power status, such as when a user suspends or resumes the operating system, or when the AC power status or battery status changes.</span></span> <span data-ttu-id="49f6f-107"><xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>属性的<xref:System.Windows.Forms.SystemInformation>类可以用来查询有关当前状态，如下面的代码示例中所示。</span><span class="sxs-lookup"><span data-stu-id="49f6f-107">The <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> property of the <xref:System.Windows.Forms.SystemInformation> class can be used to query for the current status, as shown in the following code example.</span></span>  
  
 [!code-csharp[PowerMode#1](~/samples/snippets/csharp/VS_Snippets_Winforms/powermode/cs/form1.cs#1)]
 [!code-vb[PowerMode#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/powermode/vb/form1.vb#1)]  
  
 <span data-ttu-id="49f6f-108">除了<xref:System.Windows.Forms.BatteryChargeStatus>枚举<xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>属性还包含用于确定电池容量枚举 (<xref:System.Windows.Forms.PowerStatus.BatteryFullLifetime%2A>) 和电池电量百分比 (<xref:System.Windows.Forms.PowerStatus.BatteryLifePercent%2A>， <xref:System.Windows.Forms.PowerStatus.BatteryLifeRemaining%2A>)。</span><span class="sxs-lookup"><span data-stu-id="49f6f-108">Besides the <xref:System.Windows.Forms.BatteryChargeStatus> enumerations, the <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> property also contains enumerations for determining battery capacity (<xref:System.Windows.Forms.PowerStatus.BatteryFullLifetime%2A>) and battery charge percentage (<xref:System.Windows.Forms.PowerStatus.BatteryLifePercent%2A>, <xref:System.Windows.Forms.PowerStatus.BatteryLifeRemaining%2A>).</span></span>  
  
 <span data-ttu-id="49f6f-109">可以使用<xref:System.Windows.Forms.Application.SetSuspendState%2A>方法的<xref:System.Windows.Forms.Application>使计算机进入休眠状态或暂停模式。</span><span class="sxs-lookup"><span data-stu-id="49f6f-109">You can use the <xref:System.Windows.Forms.Application.SetSuspendState%2A> method of the <xref:System.Windows.Forms.Application> to put a computer into hibernation or suspend mode.</span></span> <span data-ttu-id="49f6f-110">如果`force`参数设置为`false`，操作系统将广播请求挂起的权限的所有应用程序的事件。</span><span class="sxs-lookup"><span data-stu-id="49f6f-110">If the `force` argument is set to `false`, the operating system will broadcast an event to all applications requesting permission to suspend.</span></span> <span data-ttu-id="49f6f-111">如果`disableWakeEvent`参数设置为`true`，操作系统将禁用唤醒的所有事件。</span><span class="sxs-lookup"><span data-stu-id="49f6f-111">If the `disableWakeEvent` argument is set to `true`, the operating system disables all wake events.</span></span>  
  
 <span data-ttu-id="49f6f-112">下面的代码示例演示如何使计算机进入休眠状态。</span><span class="sxs-lookup"><span data-stu-id="49f6f-112">The following code example demonstrates how to put a computer into hibernation.</span></span>  
  
 [!code-csharp[PowerMode#2](~/samples/snippets/csharp/VS_Snippets_Winforms/powermode/cs/form1.cs#2)]
 [!code-vb[PowerMode#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/powermode/vb/form1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="49f6f-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="49f6f-113">See also</span></span>

- <xref:Microsoft.Win32.SystemEvents.PowerModeChanged>
- <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>
- <xref:System.Windows.Forms.Application.SetSuspendState%2A>
- <xref:Microsoft.Win32.SystemEvents.SessionSwitch>
