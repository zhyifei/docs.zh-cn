---
title: 如何：在 Windows 窗体上停靠控件
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], docking
- Explorer-style applications [Windows Forms], creating
- Windows Forms controls, filling client area
ms.assetid: bc11f2e4-e90a-4830-b0e2-f43b6e2b8bec
ms.openlocfilehash: d015dce7307bec092f6da1dc5ee31691a6baf1f0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61941488"
---
# <a name="how-to-dock-controls-on-windows-forms"></a><span data-ttu-id="65da9-102">如何：在 Windows 窗体上停靠控件</span><span class="sxs-lookup"><span data-stu-id="65da9-102">How to: Dock Controls on Windows Forms</span></span>
<span data-ttu-id="65da9-103">可以将控件停靠到窗体的边缘，或使它们填充控件的容器 （窗体或容器控件）。</span><span class="sxs-lookup"><span data-stu-id="65da9-103">You can dock controls to the edges of your form or have them fill the control's container (either a form or a container control).</span></span> <span data-ttu-id="65da9-104">例如，Windows 资源管理器将停靠及其<xref:System.Windows.Forms.TreeView>窗口的左侧和右侧的控件并将其<xref:System.Windows.Forms.ListView>控件窗口的右侧。</span><span class="sxs-lookup"><span data-stu-id="65da9-104">For example, Windows Explorer docks its <xref:System.Windows.Forms.TreeView> control to the left side of the window and its <xref:System.Windows.Forms.ListView> control to the right side of the window.</span></span> <span data-ttu-id="65da9-105">使用<xref:System.Windows.Forms.Control.Dock%2A>所有可见的 Windows 窗体控件来定义停靠模式的属性。</span><span class="sxs-lookup"><span data-stu-id="65da9-105">Use the <xref:System.Windows.Forms.Control.Dock%2A> property for all visible Windows Forms controls to define the docking mode.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="65da9-106">控件停靠在 z 顺序中反向。</span><span class="sxs-lookup"><span data-stu-id="65da9-106">Controls are docked in reverse z-order.</span></span>  
  
 <span data-ttu-id="65da9-107"><xref:System.Windows.Forms.Control.Dock%2A>与属性交互<xref:System.Windows.Forms.Control.AutoSize%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="65da9-107">The <xref:System.Windows.Forms.Control.Dock%2A> property interacts with the <xref:System.Windows.Forms.Control.AutoSize%2A> property.</span></span> <span data-ttu-id="65da9-108">有关详细信息，请参阅[AutoSize 属性概述](autosize-property-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="65da9-108">For more information, see [AutoSize Property Overview](autosize-property-overview.md).</span></span>  
  
### <a name="to-dock-a-control"></a><span data-ttu-id="65da9-109">若要停靠控件</span><span class="sxs-lookup"><span data-stu-id="65da9-109">To dock a control</span></span>  
  
1. <span data-ttu-id="65da9-110">选择你想要停靠的控件。</span><span class="sxs-lookup"><span data-stu-id="65da9-110">Select the control that you want to dock.</span></span>  
  
2. <span data-ttu-id="65da9-111">在属性窗口中，单击右侧的箭头<xref:System.Windows.Forms.Control.Dock%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="65da9-111">In the Properties window, click the arrow to the right of the <xref:System.Windows.Forms.Control.Dock%2A> property.</span></span>  
  
     <span data-ttu-id="65da9-112">显示一个编辑器，其中显示一系列的框表示边缘和窗体的中心。</span><span class="sxs-lookup"><span data-stu-id="65da9-112">An editor is displayed that shows a series of boxes representing the edges and the center of the form.</span></span>  
  
3. <span data-ttu-id="65da9-113">单击代表要停靠控件与窗体边缘的按钮。</span><span class="sxs-lookup"><span data-stu-id="65da9-113">Click the button that represents the edge of the form where you want to dock the control.</span></span> <span data-ttu-id="65da9-114">若要填充控件的窗体或容器控件的内容，请单击中心框。</span><span class="sxs-lookup"><span data-stu-id="65da9-114">To fill the contents of the control's form or container control, click the center box.</span></span> <span data-ttu-id="65da9-115">单击 **（无）** 禁用停靠。</span><span class="sxs-lookup"><span data-stu-id="65da9-115">Click **(none)** to disable docking.</span></span>  
  
     <span data-ttu-id="65da9-116">控件自动调整大小以适合的停靠边缘的边界。</span><span class="sxs-lookup"><span data-stu-id="65da9-116">The control is automatically resized to fit the boundaries of the docked edge.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="65da9-117">继承的控件必须是`Protected`能够停靠。</span><span class="sxs-lookup"><span data-stu-id="65da9-117">Inherited controls must be `Protected` to be able to be docked.</span></span> <span data-ttu-id="65da9-118">若要更改控件的访问级别，设置其**修饰符**属性窗口中的属性。</span><span class="sxs-lookup"><span data-stu-id="65da9-118">To change the access level of a control, set its **Modifier** property in the Properties window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65da9-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="65da9-119">See also</span></span>

- [<span data-ttu-id="65da9-120">Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="65da9-120">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="65da9-121">在 Windows 窗体上排列控件</span><span class="sxs-lookup"><span data-stu-id="65da9-121">Arranging Controls on Windows Forms</span></span>](arranging-controls-on-windows-forms.md)
- [<span data-ttu-id="65da9-122">标记各个 Windows 窗体控件并创建它们的快捷键</span><span class="sxs-lookup"><span data-stu-id="65da9-122">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="65da9-123">在 Windows 窗体上使用的控件</span><span class="sxs-lookup"><span data-stu-id="65da9-123">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="65da9-124">按功能列出的 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="65da9-124">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
- [<span data-ttu-id="65da9-125">如何：锚定和停靠子控件在 FlowLayoutPanel 控件中</span><span class="sxs-lookup"><span data-stu-id="65da9-125">How to: Anchor and Dock Child Controls in a FlowLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)
- [<span data-ttu-id="65da9-126">如何：锚定和停靠在 TableLayoutPanel 控件中的子控件</span><span class="sxs-lookup"><span data-stu-id="65da9-126">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [<span data-ttu-id="65da9-127">AutoSize 属性概述</span><span class="sxs-lookup"><span data-stu-id="65da9-127">AutoSize Property Overview</span></span>](autosize-property-overview.md)
- [<span data-ttu-id="65da9-128">如何：在 Windows 窗体上定位控件</span><span class="sxs-lookup"><span data-stu-id="65da9-128">How to: Anchor Controls on Windows Forms</span></span>](how-to-anchor-controls-on-windows-forms.md)
