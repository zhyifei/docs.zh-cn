---
title: StatusBar 控件（Windows 窗体）
ms.date: 03/30/2017
helpviewer_keywords:
- StatusBar control [Windows Forms]
- status bars [Windows Forms], creating
ms.assetid: 6f543e27-cf78-4b7f-b4d0-6a8030155d48
ms.openlocfilehash: 9ef6bc125a641538e7fd2da4c17c5f25dfc62709
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57718462"
---
# <a name="statusbar-control-windows-forms"></a><span data-ttu-id="197b1-102">StatusBar 控件（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="197b1-102">StatusBar Control (Windows Forms)</span></span>
> [!NOTE]
>  <span data-ttu-id="197b1-103">
  <xref:System.Windows.Forms.ToolStripStatusLabel> 控件取代了 <xref:System.Windows.Forms.StatusBar> 控件并添加了功能；但是，可以选择保留 <xref:System.Windows.Forms.StatusBar> 控件以实现向后兼容并供将来使用。</span><span class="sxs-lookup"><span data-stu-id="197b1-103">The <xref:System.Windows.Forms.ToolStripStatusLabel> control replaces and adds functionality to the <xref:System.Windows.Forms.StatusBar> control; however, the <xref:System.Windows.Forms.StatusBar> control is retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="197b1-104">Windows 窗体 <xref:System.Windows.Forms.StatusBar> 控件在窗体中用作区域，通常显示在窗口底部，应用程序可在此显示各种状态信息。</span><span class="sxs-lookup"><span data-stu-id="197b1-104">The Windows Forms <xref:System.Windows.Forms.StatusBar> control is used on forms as an area, usually displayed at the bottom of a window, in which an application can display various kinds of status information.</span></span> <span data-ttu-id="197b1-105"><xref:System.Windows.Forms.StatusBar> 控件可以具有状态栏面板上显示的图标来指示状态或一系列的动画中的图标指示进程正在运行;例如，Microsoft Word，该值指示是要保存文档。</span><span class="sxs-lookup"><span data-stu-id="197b1-105"><xref:System.Windows.Forms.StatusBar> controls can have status-bar panels on them that display icons to indicate state, or a series of icons in an animation that indicate a process is working; for example, Microsoft Word indicating that the document is being saved.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="197b1-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="197b1-106">In This Section</span></span>  
 [<span data-ttu-id="197b1-107">StatusBar 控件概述</span><span class="sxs-lookup"><span data-stu-id="197b1-107">StatusBar Control Overview</span></span>](statusbar-control-overview-windows-forms.md)  
 <span data-ttu-id="197b1-108">引入了的一般概念<xref:System.Windows.Forms.StatusBar>控件，让用户可查看具有焦点的控件的相关信息。</span><span class="sxs-lookup"><span data-stu-id="197b1-108">Introduces the general concepts of the <xref:System.Windows.Forms.StatusBar> control, which enables users to see relevant information for the control that has focus.</span></span>  
  
 [<span data-ttu-id="197b1-109">如何：向 StatusBar 控件添加面板</span><span class="sxs-lookup"><span data-stu-id="197b1-109">How to: Add Panels to a StatusBar Control</span></span>](how-to-add-panels-to-a-statusbar-control.md)  
 <span data-ttu-id="197b1-110">介绍如何添加到可编程面板<xref:System.Windows.Forms.StatusBar>控件。</span><span class="sxs-lookup"><span data-stu-id="197b1-110">Explains how to add programmable panels to the <xref:System.Windows.Forms.StatusBar> control.</span></span>  
  
 [<span data-ttu-id="197b1-111">如何：确定已单击 Windows 窗体 StatusBar 控件中的面板</span><span class="sxs-lookup"><span data-stu-id="197b1-111">How to: Determine Which Panel in the Windows Forms StatusBar Control Was Clicked</span></span>](determine-which-panel-wf-statusbar-control-was-clicked.md)  
 <span data-ttu-id="197b1-112">说明如何处理<xref:System.Windows.Forms.Control.Click>事件引发从<xref:System.Windows.Forms.StatusBar>控件。</span><span class="sxs-lookup"><span data-stu-id="197b1-112">Explains how to handle <xref:System.Windows.Forms.Control.Click> events raised from the <xref:System.Windows.Forms.StatusBar> control.</span></span>  
  
 [<span data-ttu-id="197b1-113">如何：设置状态栏面板的大小</span><span class="sxs-lookup"><span data-stu-id="197b1-113">How to: Set the Size of Status-Bar Panels</span></span>](how-to-set-the-size-of-status-bar-panels.md)  
 <span data-ttu-id="197b1-114">提供的属性的控件的宽度和在运行时重设大小行为的状态栏面板的详细信息。</span><span class="sxs-lookup"><span data-stu-id="197b1-114">Gives details on the properties that control the width and resize behavior of status-bar panels at run time.</span></span>  
  
 [<span data-ttu-id="197b1-115">演练：在运行时的更新状态栏信息</span><span class="sxs-lookup"><span data-stu-id="197b1-115">Walkthrough: Updating Status Bar Information at Run Time</span></span>](walkthrough-updating-status-bar-information-at-run-time.md)  
 <span data-ttu-id="197b1-116">说明如何以编程方式控制状态栏面板中的数据。</span><span class="sxs-lookup"><span data-stu-id="197b1-116">Explains how to programmatically control the data within status-bar panels.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="197b1-117">参考</span><span class="sxs-lookup"><span data-stu-id="197b1-117">Reference</span></span>  
 <xref:System.Windows.Forms.StatusBar>  
 <span data-ttu-id="197b1-118">提供类及其成员的相关引用信息。</span><span class="sxs-lookup"><span data-stu-id="197b1-118">Provides reference information on the class and its members.</span></span>  
  
 <xref:System.Windows.Forms.ToolStripStatusLabel>  
 <span data-ttu-id="197b1-119">替换并添加了功能<xref:System.Windows.Forms.StatusBar>控件。</span><span class="sxs-lookup"><span data-stu-id="197b1-119">Replaces and adds functionality to the <xref:System.Windows.Forms.StatusBar> control.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="197b1-120">相关章节</span><span class="sxs-lookup"><span data-stu-id="197b1-120">Related Sections</span></span>  
 [<span data-ttu-id="197b1-121">在 Windows 窗体上使用的控件</span><span class="sxs-lookup"><span data-stu-id="197b1-121">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="197b1-122">提供 Windows 窗体控件的完整列表，附带其使用情况相关信息的链接。</span><span class="sxs-lookup"><span data-stu-id="197b1-122">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>
