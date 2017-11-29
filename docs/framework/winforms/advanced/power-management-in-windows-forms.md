---
title: "Windows 窗体中的电源管理"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- battery states
- power states
ms.assetid: ad04a801-5682-4d88-92c5-26eb9cdb209a
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e12f39a63a4f81e6deec4512a4e18ad2bda7e5e0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="power-management-in-windows-forms"></a>Windows 窗体中的电源管理
在 Windows 操作系统中，Windows 窗体应用程序可以充分利用电源管理功能。 你的应用程序可以监视计算机的电源状态，并发生状态更改时执行操作。 例如，如果便携式计算机上运行你的应用程序，你可能想要在计算机的电池电量低于特定级别时禁用你的应用程序中的某些功能。  
  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]提供<xref:Microsoft.Win32.SystemEvents.PowerModeChanged>只要出现电源状态，例如当用户将挂起或恢复操作系统，或 AC 电源状态或电池状态更改时中的更改，都会引发的事件。 <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>属性<xref:System.Windows.Forms.SystemInformation>类可以是用来查询有关当前状态，如下面的代码示例中所示。  
  
 [!code-csharp[PowerMode#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/powermode/cs/form1.cs#1)]
 [!code-vb[PowerMode#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/powermode/vb/form1.vb#1)]  
  
 除了<xref:System.Windows.Forms.BatteryChargeStatus>枚举，<xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>属性还包含用于确定电池容量枚举 (<xref:System.Windows.Forms.PowerStatus.BatteryFullLifetime%2A>) 和电池电量百分比 (<xref:System.Windows.Forms.PowerStatus.BatteryLifePercent%2A>， <xref:System.Windows.Forms.PowerStatus.BatteryLifeRemaining%2A>)。  
  
 你可以使用<xref:System.Windows.Forms.Application.SetSuspendState%2A>方法<xref:System.Windows.Forms.Application>以使计算机进入休眠状态或挂起模式。 如果`force`参数设置为`false`，操作系统将广播对请求挂起的权限的所有应用程序事件。 如果`disableWakeEvent`参数设置为`true`，操作系统禁用唤醒的所有事件。  
  
 下面的代码示例演示如何使计算机进入休眠状态。  
  
 [!code-csharp[PowerMode#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/powermode/cs/form1.cs#2)]
 [!code-vb[PowerMode#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/powermode/vb/form1.vb#2)]  
  
## <a name="see-also"></a>另请参阅  
 <xref:Microsoft.Win32.SystemEvents.PowerModeChanged>  
 <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>  
 <xref:System.Windows.Forms.Application.SetSuspendState%2A>  
 <xref:Microsoft.Win32.SystemEvents.SessionSwitch>
