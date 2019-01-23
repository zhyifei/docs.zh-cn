---
title: StatusBar 控件概述（Windows 窗体）
ms.date: 03/30/2017
f1_keywords:
- StatusBar
helpviewer_keywords:
- StatusBar control [Windows Forms], about StatusBar control
- status bars
ms.assetid: b7b9852c-633d-4416-bb2e-94852b989c6c
ms.openlocfilehash: c3e52a91a31eb898d0176bc35a97cda7de9a8368
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54491345"
---
# <a name="statusbar-control-overview-windows-forms"></a><span data-ttu-id="89a32-102">StatusBar 控件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="89a32-102">StatusBar Control Overview (Windows Forms)</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="89a32-103"><xref:System.Windows.Forms.StatusStrip>并<xref:System.Windows.Forms.ToolStripStatusLabel>控件替换，并将功能添加到<xref:System.Windows.Forms.StatusBar>并<xref:System.Windows.Forms.StatusBarPanel>控制; 但是，<xref:System.Windows.Forms.StatusBar>和<xref:System.Windows.Forms.StatusBarPanel>控件将保留用于向后兼容性并供将来使用，如果你选择。</span><span class="sxs-lookup"><span data-stu-id="89a32-103">The <xref:System.Windows.Forms.StatusStrip> and <xref:System.Windows.Forms.ToolStripStatusLabel> controls replace and add functionality to the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls; however, the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls are retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="89a32-104">Windows 窗体[StatusBar 控件](../../../../docs/framework/winforms/controls/statusbar-control-windows-forms.md)窗体上用作区域，通常显示在底部窗口中，应用程序可以在其中显示各种类型的状态信息。</span><span class="sxs-lookup"><span data-stu-id="89a32-104">The Windows Forms [StatusBar Control](../../../../docs/framework/winforms/controls/statusbar-control-windows-forms.md) is used on forms as an area, usually displayed at the bottom of a window, in which an application can display various kinds of status information.</span></span> <span data-ttu-id="89a32-105"><xref:System.Windows.Forms.StatusBar> 控件可以具有状态栏面板上显示的文本或图标，用于指示状态或一系列的动画中的图标指示进程正在运行;例如， [!INCLUDE[ofprword](../../../../includes/ofprword-md.md)] ，该值指示保存该文档。</span><span class="sxs-lookup"><span data-stu-id="89a32-105"><xref:System.Windows.Forms.StatusBar> controls can have status bar panels on them that display text or icons to indicate state, or a series of icons in an animation that indicate a process is working; for example, [!INCLUDE[ofprword](../../../../includes/ofprword-md.md)] indicating that the document is being saved.</span></span>  
  
## <a name="using-the-statusbar-control"></a><span data-ttu-id="89a32-106">使用 StatusBar 控件</span><span class="sxs-lookup"><span data-stu-id="89a32-106">Using the StatusBar Control</span></span>  
 <span data-ttu-id="89a32-107">Internet Explorer 使用状态栏来指示当鼠标滚动超链接; 时的页的 URL[!INCLUDE[ofprword](../../../../includes/ofprword-md.md)]为您提供信息页的位置、 部分位置和编辑模式，例如改写和修订跟踪; 以及 Visual Studio 使用状态栏提供上下文相关的信息，例如告诉您如何操作可停靠窗口为停靠或浮动。</span><span class="sxs-lookup"><span data-stu-id="89a32-107">Internet Explorer uses a status bar to indicate the URL of a page when the mouse rolls over the hyperlink; [!INCLUDE[ofprword](../../../../includes/ofprword-md.md)] gives you information on page location, section location, and editing modes such as overtype and revision tracking; and Visual Studio uses the status bar to give context-sensitive information, such as telling you how to manipulate dockable windows as either docked or floating.</span></span>  
  
 <span data-ttu-id="89a32-108">可以在状态栏上显示一条消息，通过设置<xref:System.Windows.Forms.StatusBar.ShowPanels%2A>属性设置为`false`（默认值） 和设置<xref:System.Windows.Forms.StatusBar.Text%2A>到你想要在状态栏中显示的文本的状态栏的属性。</span><span class="sxs-lookup"><span data-stu-id="89a32-108">You can display a single message on the status bar by setting the <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> property to `false` (the default) and setting the <xref:System.Windows.Forms.StatusBar.Text%2A> property of the status bar to the text you want to appear in the status bar.</span></span> <span data-ttu-id="89a32-109">可以将状态栏划分为多个面板，以通过设置显示的信息的多个类型<xref:System.Windows.Forms.StatusBar.ShowPanels%2A>属性设置为`true`并使用<xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection.Add%2A>方法的<xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>。</span><span class="sxs-lookup"><span data-stu-id="89a32-109">You can divide the status bar into panels to display more than one type of information by setting the <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> property to `true` and using the <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection.Add%2A> method of <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89a32-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="89a32-110">See also</span></span>
- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [<span data-ttu-id="89a32-111">如何：确定已单击 Windows 窗体 StatusBar 控件中的面板</span><span class="sxs-lookup"><span data-stu-id="89a32-111">How to: Determine Which Panel in the Windows Forms StatusBar Control Was Clicked</span></span>](../../../../docs/framework/winforms/controls/determine-which-panel-wf-statusbar-control-was-clicked.md)
