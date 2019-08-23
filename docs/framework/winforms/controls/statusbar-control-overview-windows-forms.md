---
title: StatusBar 控件概述（Windows 窗体）
ms.date: 03/30/2017
f1_keywords:
- StatusBar
helpviewer_keywords:
- StatusBar control [Windows Forms], about StatusBar control
- status bars
ms.assetid: b7b9852c-633d-4416-bb2e-94852b989c6c
ms.openlocfilehash: bd58d4c70e3a3c88e57fe242957f669d1944fd71
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964434"
---
# <a name="statusbar-control-overview-windows-forms"></a><span data-ttu-id="8e5a9-102">StatusBar 控件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="8e5a9-102">StatusBar Control Overview (Windows Forms)</span></span>
> [!IMPORTANT]
> <span data-ttu-id="8e5a9-103"><xref:System.Windows.Forms.StatusBarPanel> <xref:System.Windows.Forms.StatusBar> <xref:System.Windows.Forms.StatusBar>和控件替换和添加了和控件的功能; 但是, 和<xref:System.Windows.Forms.StatusBarPanel>控件将保留以实现向后兼容性和将来使用, 前提是你<xref:System.Windows.Forms.ToolStripStatusLabel> <xref:System.Windows.Forms.StatusStrip>.</span><span class="sxs-lookup"><span data-stu-id="8e5a9-103">The <xref:System.Windows.Forms.StatusStrip> and <xref:System.Windows.Forms.ToolStripStatusLabel> controls replace and add functionality to the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls; however, the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls are retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="8e5a9-104">Windows 窗体[状态栏控件](statusbar-control-windows-forms.md)在窗体上用作区域, 通常显示在窗口底部, 应用程序可在窗口中显示各种类型的状态信息。</span><span class="sxs-lookup"><span data-stu-id="8e5a9-104">The Windows Forms [StatusBar Control](statusbar-control-windows-forms.md) is used on forms as an area, usually displayed at the bottom of a window, in which an application can display various kinds of status information.</span></span> <span data-ttu-id="8e5a9-105"><xref:System.Windows.Forms.StatusBar>控件可在其上具有状态栏面板, 这些面板显示用于指示状态的文本或图标, 或动画中指示进程工作的一系列图标。例如, Microsoft Word 表明文档正在保存。</span><span class="sxs-lookup"><span data-stu-id="8e5a9-105"><xref:System.Windows.Forms.StatusBar> controls can have status bar panels on them that display text or icons to indicate state, or a series of icons in an animation that indicate a process is working; for example, Microsoft Word indicating that the document is being saved.</span></span>  
  
## <a name="using-the-statusbar-control"></a><span data-ttu-id="8e5a9-106">使用 "状态栏" 控件</span><span class="sxs-lookup"><span data-stu-id="8e5a9-106">Using the StatusBar Control</span></span>  
 <span data-ttu-id="8e5a9-107">当鼠标滚动到超链接上时, Internet Explorer 将使用状态栏来指示页面的 URL;Microsoft Word 提供了有关页面位置、分区位置和编辑模式 (如改写和修订跟踪) 的信息;Visual Studio 使用状态栏为上下文相关的信息, 如告诉您如何操作停靠或浮动的窗口。</span><span class="sxs-lookup"><span data-stu-id="8e5a9-107">Internet Explorer uses a status bar to indicate the URL of a page when the mouse rolls over the hyperlink; Microsoft Word gives you information on page location, section location, and editing modes such as overtype and revision tracking; and Visual Studio uses the status bar to give context-sensitive information, such as telling you how to manipulate dockable windows as either docked or floating.</span></span>  
  
 <span data-ttu-id="8e5a9-108">您可以通过将<xref:System.Windows.Forms.StatusBar.ShowPanels%2A>属性设置为`false` ( <xref:System.Windows.Forms.StatusBar.Text%2A>默认值), 然后将状态栏的属性设置为要在状态栏中显示的文本, 在状态栏上显示一条消息。</span><span class="sxs-lookup"><span data-stu-id="8e5a9-108">You can display a single message on the status bar by setting the <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> property to `false` (the default) and setting the <xref:System.Windows.Forms.StatusBar.Text%2A> property of the status bar to the text you want to appear in the status bar.</span></span> <span data-ttu-id="8e5a9-109"><xref:System.Windows.Forms.StatusBar.ShowPanels%2A>您可以通过将属性设置为`true` <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>并使用<xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection.Add%2A>的方法, 将状态栏划分为多个面板以显示多种类型的信息。</span><span class="sxs-lookup"><span data-stu-id="8e5a9-109">You can divide the status bar into panels to display more than one type of information by setting the <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> property to `true` and using the <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection.Add%2A> method of <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e5a9-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="8e5a9-110">See also</span></span>

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [<span data-ttu-id="8e5a9-111">如何：确定单击 Windows 窗体状态栏控件中的哪个面板</span><span class="sxs-lookup"><span data-stu-id="8e5a9-111">How to: Determine Which Panel in the Windows Forms StatusBar Control Was Clicked</span></span>](determine-which-panel-wf-statusbar-control-was-clicked.md)
