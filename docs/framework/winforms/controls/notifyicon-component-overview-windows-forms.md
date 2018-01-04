---
title: "NotifyIcon 组件概述（Windows 窗体）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: NotifyIcon
helpviewer_keywords:
- NotifyIcon component [Windows Forms], about NotifyIcon component
- system tray icons [Windows Forms], about system tray icons
- system tray icons [Windows Forms], using in Windows Forms
ms.assetid: 5b9189fa-d4ae-41a6-9b97-eb1f44bb1a69
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8c909537bd4c52a546faeb83c6e9291c4de76d76
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="notifyicon-component-overview-windows-forms"></a><span data-ttu-id="6705d-102">NotifyIcon 组件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="6705d-102">NotifyIcon Component Overview (Windows Forms)</span></span>
<span data-ttu-id="6705d-103">Windows 窗体 <xref:System.Windows.Forms.NotifyIcon> 组件通常用于显示在后台运行且大部分时间不显示用户界面的进程的图标。</span><span class="sxs-lookup"><span data-stu-id="6705d-103">The Windows Forms <xref:System.Windows.Forms.NotifyIcon> component is typically used to display icons for processes that run in the background and do not show a user interface much of the time.</span></span> <span data-ttu-id="6705d-104">例如，可通过单击任务栏的状态通知区域中的图标访问的病毒防护程序。</span><span class="sxs-lookup"><span data-stu-id="6705d-104">An example would be a virus protection program that can be accessed by clicking an icon in the status notification area of the taskbar.</span></span>  
  
## <a name="key-properties-of-notifyicons"></a><span data-ttu-id="6705d-105">NotifyIcons 的键属性</span><span class="sxs-lookup"><span data-stu-id="6705d-105">Key Properties of NotifyIcons</span></span>  
 <span data-ttu-id="6705d-106">每个 <xref:System.Windows.Forms.NotifyIcon> 组件均显示状态区域中的一个图标。</span><span class="sxs-lookup"><span data-stu-id="6705d-106">Each <xref:System.Windows.Forms.NotifyIcon> component displays a single icon in the status area.</span></span> <span data-ttu-id="6705d-107">如果你有三个后台进程，并希望为每个进程显示一个图标，则必须添加三个 <xref:System.Windows.Forms.NotifyIcon> 组件到窗体。</span><span class="sxs-lookup"><span data-stu-id="6705d-107">If you have three background processes and wish to display an icon for each, you must add three <xref:System.Windows.Forms.NotifyIcon> components to the form.</span></span> <span data-ttu-id="6705d-108"><xref:System.Windows.Forms.NotifyIcon> 组件的键属性为 <xref:System.Windows.Forms.NotifyIcon.Icon%2A> 和 <xref:System.Windows.Forms.NotifyIcon.Visible%2A>。</span><span class="sxs-lookup"><span data-stu-id="6705d-108">The key properties of the <xref:System.Windows.Forms.NotifyIcon> component are <xref:System.Windows.Forms.NotifyIcon.Icon%2A> and <xref:System.Windows.Forms.NotifyIcon.Visible%2A>.</span></span> <span data-ttu-id="6705d-109"><xref:System.Windows.Forms.NotifyIcon.Icon%2A> 属性设置状态区域中显示的图标。</span><span class="sxs-lookup"><span data-stu-id="6705d-109">The <xref:System.Windows.Forms.NotifyIcon.Icon%2A> property sets the icon that appears in the status area.</span></span> <span data-ttu-id="6705d-110">为了显示图标，必须将 <xref:System.Windows.Forms.NotifyIcon.Visible%2A> 属性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="6705d-110">In order for the icon to appear, the <xref:System.Windows.Forms.NotifyIcon.Visible%2A> property must be set to `true`.</span></span>  
  
 <span data-ttu-id="6705d-111">如果使用的是 [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)]，你可以访问能够与 <xref:System.Windows.Forms.NotifyIcon> 控件一起使用的大型标准图像库。</span><span class="sxs-lookup"><span data-stu-id="6705d-111">If you are using [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)], you have access to a large library of standard images that you can use with the <xref:System.Windows.Forms.NotifyIcon> control.</span></span>  
  
## <a name="notifyicons-options"></a><span data-ttu-id="6705d-112">NotifyIcons 选项</span><span class="sxs-lookup"><span data-stu-id="6705d-112">NotifyIcons Options</span></span>  
 <span data-ttu-id="6705d-113">你可以将气球提示、快捷菜单和工具提示与 <xref:System.Windows.Forms.NotifyIcon> 进行关联，以辅助用户。</span><span class="sxs-lookup"><span data-stu-id="6705d-113">You can associate balloon tips, shortcut menus, and ToolTips with a <xref:System.Windows.Forms.NotifyIcon> to assist the user.</span></span>  
  
 <span data-ttu-id="6705d-114">你可以通过调用 <xref:System.Windows.Forms.NotifyIcon.ShowBalloonTip%2A> 方法来指定需要气球提示显示的时间跨度，从而显示 <xref:System.Windows.Forms.NotifyIcon> 的气球提示。</span><span class="sxs-lookup"><span data-stu-id="6705d-114">You can display balloon tips for a <xref:System.Windows.Forms.NotifyIcon> by calling the <xref:System.Windows.Forms.NotifyIcon.ShowBalloonTip%2A> method specifying the time span you wish the balloon tip to display.</span></span> <span data-ttu-id="6705d-115">还可以为气球提示的文本、图标和标题分别指定 <xref:System.Windows.Forms.NotifyIcon.BalloonTipText%2A>、<xref:System.Windows.Forms.NotifyIcon.BalloonTipIcon%2A> 和 <xref:System.Windows.Forms.NotifyIcon.BalloonTipTitle%2A>。</span><span class="sxs-lookup"><span data-stu-id="6705d-115">You can also specify the text, icon and title of the balloon tip with the <xref:System.Windows.Forms.NotifyIcon.BalloonTipText%2A>, <xref:System.Windows.Forms.NotifyIcon.BalloonTipIcon%2A> and <xref:System.Windows.Forms.NotifyIcon.BalloonTipTitle%2A>, respectively.</span></span> <span data-ttu-id="6705d-116"><xref:System.Windows.Forms.NotifyIcon> 组件还可以具有相关联的工具提示和快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="6705d-116"><xref:System.Windows.Forms.NotifyIcon> components can also have associated ToolTips and shortcut menus.</span></span> <span data-ttu-id="6705d-117">有关详细信息，请参阅[工具提示组件概述](../../../../docs/framework/winforms/controls/tooltip-component-overview-windows-forms.md)和[ContextMenu 组件概述](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="6705d-117">For more information, see [ToolTip Component Overview](../../../../docs/framework/winforms/controls/tooltip-component-overview-windows-forms.md) and [ContextMenu Component Overview](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6705d-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="6705d-118">See Also</span></span>  
 <xref:System.Windows.Forms.NotifyIcon>  
 [<span data-ttu-id="6705d-119">NotifyIcon 组件</span><span class="sxs-lookup"><span data-stu-id="6705d-119">NotifyIcon Component</span></span>](../../../../docs/framework/winforms/controls/notifyicon-component-windows-forms.md)
