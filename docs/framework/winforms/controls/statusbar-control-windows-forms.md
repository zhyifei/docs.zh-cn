---
title: "StatusBar 控件（Windows 窗体）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- StatusBar control [Windows Forms]
- status bars [Windows Forms], creating
ms.assetid: 6f543e27-cf78-4b7f-b4d0-6a8030155d48
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 775d1a350075811dc02ae33efd1a6ae05328c4ff
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="statusbar-control-windows-forms"></a><span data-ttu-id="d8a7e-102">StatusBar 控件（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="d8a7e-102">StatusBar Control (Windows Forms)</span></span>
> [!NOTE]
>  <span data-ttu-id="d8a7e-103"><xref:System.Windows.Forms.ToolStripStatusLabel> 控件取代了 <xref:System.Windows.Forms.StatusBar> 控件并添加了功能；但是，可以选择保留 <xref:System.Windows.Forms.StatusBar> 控件以实现向后兼容并供将来使用。</span><span class="sxs-lookup"><span data-stu-id="d8a7e-103">The <xref:System.Windows.Forms.ToolStripStatusLabel> control replaces and adds functionality to the <xref:System.Windows.Forms.StatusBar> control; however, the <xref:System.Windows.Forms.StatusBar> control is retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="d8a7e-104">Windows 窗体 <xref:System.Windows.Forms.StatusBar> 控件在窗体中用作区域，通常显示在窗口底部，应用程序可在此显示各种状态信息。</span><span class="sxs-lookup"><span data-stu-id="d8a7e-104">The Windows Forms <xref:System.Windows.Forms.StatusBar> control is used on forms as an area, usually displayed at the bottom of a window, in which an application can display various kinds of status information.</span></span> <span data-ttu-id="d8a7e-105"><xref:System.Windows.Forms.StatusBar>控件可以具有在其上显示的图标来指示状态或一系列表示正在进程; 在动画中的图标的状态栏面板例如，Microsoft Word，该值指示文档正在保存。</span><span class="sxs-lookup"><span data-stu-id="d8a7e-105"><xref:System.Windows.Forms.StatusBar> controls can have status-bar panels on them that display icons to indicate state, or a series of icons in an animation that indicate a process is working; for example, Microsoft Word indicating that the document is being saved.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d8a7e-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="d8a7e-106">In This Section</span></span>  
 [<span data-ttu-id="d8a7e-107">StatusBar 控件概述</span><span class="sxs-lookup"><span data-stu-id="d8a7e-107">StatusBar Control Overview</span></span>](../../../../docs/framework/winforms/controls/statusbar-control-overview-windows-forms.md)  
 <span data-ttu-id="d8a7e-108">引入了的一般概念<xref:System.Windows.Forms.StatusBar>控件，这使得用户能够查看具有焦点的控件的相关信息。</span><span class="sxs-lookup"><span data-stu-id="d8a7e-108">Introduces the general concepts of the <xref:System.Windows.Forms.StatusBar> control, which enables users to see relevant information for the control that has focus.</span></span>  
  
 [<span data-ttu-id="d8a7e-109">如何：向 StatusBar 控件添加面板</span><span class="sxs-lookup"><span data-stu-id="d8a7e-109">How to: Add Panels to a StatusBar Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-panels-to-a-statusbar-control.md)  
 <span data-ttu-id="d8a7e-110">介绍如何将添加到的可编程面板<xref:System.Windows.Forms.StatusBar>控件。</span><span class="sxs-lookup"><span data-stu-id="d8a7e-110">Explains how to add programmable panels to the <xref:System.Windows.Forms.StatusBar> control.</span></span>  
  
 [<span data-ttu-id="d8a7e-111">如何：确定 Windows 窗体 StatusBar 控件中的哪个面板获得了单击</span><span class="sxs-lookup"><span data-stu-id="d8a7e-111">How to: Determine Which Panel in the Windows Forms StatusBar Control Was Clicked</span></span>](../../../../docs/framework/winforms/controls/determine-which-panel-wf-statusbar-control-was-clicked.md)  
 <span data-ttu-id="d8a7e-112">说明如何处理<xref:System.Windows.Forms.Control.Click>事件引发从<xref:System.Windows.Forms.StatusBar>控件。</span><span class="sxs-lookup"><span data-stu-id="d8a7e-112">Explains how to handle <xref:System.Windows.Forms.Control.Click> events raised from the <xref:System.Windows.Forms.StatusBar> control.</span></span>  
  
 [<span data-ttu-id="d8a7e-113">如何：设置状态栏面板的大小</span><span class="sxs-lookup"><span data-stu-id="d8a7e-113">How to: Set the Size of Status-Bar Panels</span></span>](../../../../docs/framework/winforms/controls/how-to-set-the-size-of-status-bar-panels.md)  
 <span data-ttu-id="d8a7e-114">提供有关的属性，控制宽度在运行时调整大小行为的状态栏面板的详细信息。</span><span class="sxs-lookup"><span data-stu-id="d8a7e-114">Gives details on the properties that control the width and resize behavior of status-bar panels at run time.</span></span>  
  
 [<span data-ttu-id="d8a7e-115">演练：在运行时更新状态栏信息</span><span class="sxs-lookup"><span data-stu-id="d8a7e-115">Walkthrough: Updating Status Bar Information at Run Time</span></span>](../../../../docs/framework/winforms/controls/walkthrough-updating-status-bar-information-at-run-time.md)  
 <span data-ttu-id="d8a7e-116">说明如何以编程方式控制状态栏面板内的数据。</span><span class="sxs-lookup"><span data-stu-id="d8a7e-116">Explains how to programmatically control the data within status-bar panels.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="d8a7e-117">参考</span><span class="sxs-lookup"><span data-stu-id="d8a7e-117">Reference</span></span>  
 <xref:System.Windows.Forms.StatusBar>  
 <span data-ttu-id="d8a7e-118">提供类及其成员的相关引用信息。</span><span class="sxs-lookup"><span data-stu-id="d8a7e-118">Provides reference information on the class and its members.</span></span>  
  
 <xref:System.Windows.Forms.ToolStripStatusLabel>  
 <span data-ttu-id="d8a7e-119">替换并添加了功能<xref:System.Windows.Forms.StatusBar>控件。</span><span class="sxs-lookup"><span data-stu-id="d8a7e-119">Replaces and adds functionality to the <xref:System.Windows.Forms.StatusBar> control.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d8a7e-120">相关章节</span><span class="sxs-lookup"><span data-stu-id="d8a7e-120">Related Sections</span></span>  
 [<span data-ttu-id="d8a7e-121">在 Windows 窗体上使用的控件</span><span class="sxs-lookup"><span data-stu-id="d8a7e-121">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="d8a7e-122">提供 Windows 窗体控件的完整列表，附带其使用情况相关信息的链接。</span><span class="sxs-lookup"><span data-stu-id="d8a7e-122">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>
