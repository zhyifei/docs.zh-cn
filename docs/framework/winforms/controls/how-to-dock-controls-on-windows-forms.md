---
title: "如何：在 Windows 窗体上停靠控件"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [Windows Forms], docking
- Explorer-style applications [Windows Forms], creating
- Windows Forms controls, filling client area
ms.assetid: bc11f2e4-e90a-4830-b0e2-f43b6e2b8bec
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4897a195dcafb8264bbab619f1a46118a829f44e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-dock-controls-on-windows-forms"></a><span data-ttu-id="327ca-102">如何：在 Windows 窗体上停靠控件</span><span class="sxs-lookup"><span data-stu-id="327ca-102">How to: Dock Controls on Windows Forms</span></span>
<span data-ttu-id="327ca-103">你可以将控件停靠到窗体的边缘，或使它们填充控件的容器 （窗体或容器控件）。</span><span class="sxs-lookup"><span data-stu-id="327ca-103">You can dock controls to the edges of your form or have them fill the control's container (either a form or a container control).</span></span> <span data-ttu-id="327ca-104">例如，Windows 资源管理器停靠其<xref:System.Windows.Forms.TreeView>窗口左侧的控件并将其<xref:System.Windows.Forms.ListView>窗口的右侧的控件。</span><span class="sxs-lookup"><span data-stu-id="327ca-104">For example, Windows Explorer docks its <xref:System.Windows.Forms.TreeView> control to the left side of the window and its <xref:System.Windows.Forms.ListView> control to the right side of the window.</span></span> <span data-ttu-id="327ca-105">使用<xref:System.Windows.Forms.Control.Dock%2A>所有可见的 Windows 窗体控件来定义停靠模式的属性。</span><span class="sxs-lookup"><span data-stu-id="327ca-105">Use the <xref:System.Windows.Forms.Control.Dock%2A> property for all visible Windows Forms controls to define the docking mode.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="327ca-106">控件停靠在相反的 z 顺序。</span><span class="sxs-lookup"><span data-stu-id="327ca-106">Controls are docked in reverse z-order.</span></span>  
  
 <span data-ttu-id="327ca-107"><xref:System.Windows.Forms.Control.Dock%2A>属性与交互<xref:System.Windows.Forms.Control.AutoSize%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="327ca-107">The <xref:System.Windows.Forms.Control.Dock%2A> property interacts with the <xref:System.Windows.Forms.Control.AutoSize%2A> property.</span></span> <span data-ttu-id="327ca-108">有关详细信息，请参阅[AutoSize 属性概述](../../../../docs/framework/winforms/controls/autosize-property-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="327ca-108">For more information, see [AutoSize Property Overview](../../../../docs/framework/winforms/controls/autosize-property-overview.md).</span></span>  
  
### <a name="to-dock-a-control"></a><span data-ttu-id="327ca-109">若要将控件停靠</span><span class="sxs-lookup"><span data-stu-id="327ca-109">To dock a control</span></span>  
  
1.  <span data-ttu-id="327ca-110">选择你想要停靠的控件。</span><span class="sxs-lookup"><span data-stu-id="327ca-110">Select the control that you want to dock.</span></span>  
  
2.  <span data-ttu-id="327ca-111">在属性窗口中，单击右侧的箭头<xref:System.Windows.Forms.Control.Dock%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="327ca-111">In the Properties window, click the arrow to the right of the <xref:System.Windows.Forms.Control.Dock%2A> property.</span></span>  
  
     <span data-ttu-id="327ca-112">显示一个编辑器，其中显示框的边缘和窗体的中心表示一系列。</span><span class="sxs-lookup"><span data-stu-id="327ca-112">An editor is displayed that shows a series of boxes representing the edges and the center of the form.</span></span>  
  
3.  <span data-ttu-id="327ca-113">单击表示你要将控件停靠的窗体的边缘的按钮。</span><span class="sxs-lookup"><span data-stu-id="327ca-113">Click the button that represents the edge of the form where you want to dock the control.</span></span> <span data-ttu-id="327ca-114">若要填充的控件的窗体或容器控件的内容，单击中心框。</span><span class="sxs-lookup"><span data-stu-id="327ca-114">To fill the contents of the control's form or container control, click the center box.</span></span> <span data-ttu-id="327ca-115">单击**（无）**禁用停靠。</span><span class="sxs-lookup"><span data-stu-id="327ca-115">Click **(none)** to disable docking.</span></span>  
  
     <span data-ttu-id="327ca-116">控件自动调整大小以适合的停靠边缘的边界。</span><span class="sxs-lookup"><span data-stu-id="327ca-116">The control is automatically resized to fit the boundaries of the docked edge.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="327ca-117">继承的控件必须`Protected`能够停靠。</span><span class="sxs-lookup"><span data-stu-id="327ca-117">Inherited controls must be `Protected` to be able to be docked.</span></span> <span data-ttu-id="327ca-118">若要更改控件的访问级别，设置其**修饰符**属性窗口中的属性。</span><span class="sxs-lookup"><span data-stu-id="327ca-118">To change the access level of a control, set its **Modifier** property in the Properties window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="327ca-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="327ca-119">See Also</span></span>  
 [<span data-ttu-id="327ca-120">Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="327ca-120">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)  
 [<span data-ttu-id="327ca-121">在 Windows 窗体上排列控件</span><span class="sxs-lookup"><span data-stu-id="327ca-121">Arranging Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [<span data-ttu-id="327ca-122">标记各个 Windows 窗体控件并创建它们的快捷键</span><span class="sxs-lookup"><span data-stu-id="327ca-122">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [<span data-ttu-id="327ca-123">在 Windows 窗体上使用的控件</span><span class="sxs-lookup"><span data-stu-id="327ca-123">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [<span data-ttu-id="327ca-124">按功能列出的 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="327ca-124">Windows Forms Controls by Function</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)  
 [<span data-ttu-id="327ca-125">如何：在 FlowLayoutPanel 控件中锚定和停靠子控件</span><span class="sxs-lookup"><span data-stu-id="327ca-125">How to: Anchor and Dock Child Controls in a FlowLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)  
 [<span data-ttu-id="327ca-126">如何：在 TableLayoutPanel 控件中锚定和停靠子控件</span><span class="sxs-lookup"><span data-stu-id="327ca-126">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)  
 [<span data-ttu-id="327ca-127">AutoSize 属性概述</span><span class="sxs-lookup"><span data-stu-id="327ca-127">AutoSize Property Overview</span></span>](../../../../docs/framework/winforms/controls/autosize-property-overview.md)  
 [<span data-ttu-id="327ca-128">如何：在 Windows 窗体上锚定控件</span><span class="sxs-lookup"><span data-stu-id="327ca-128">How to: Anchor Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-anchor-controls-on-windows-forms.md)
