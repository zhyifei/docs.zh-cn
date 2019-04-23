---
title: 如何：在 Windows 窗体上锚定控件
ms.date: 03/30/2017
helpviewer_keywords:
- Anchor property [Windows Forms], enabling resizable forms
- Windows Forms controls, screen resolutions
- resizing forms [Windows Forms]
- Windows Forms controls, size
- screen resolution and control display
- controls [Windows Forms], anchoring
- forms [Windows Forms], resizing
- Windows Forms, resizing
- controls [Windows Forms], positioning
ms.assetid: 59ea914f-fbd3-427a-80fe-decd02f7ae6d
ms.openlocfilehash: b5550aef220ece09d5486421275b19a37bfe9011
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59329773"
---
# <a name="how-to-anchor-controls-on-windows-forms"></a><span data-ttu-id="81670-102">如何：在 Windows 窗体上锚定控件</span><span class="sxs-lookup"><span data-stu-id="81670-102">How to: Anchor Controls on Windows Forms</span></span>
<span data-ttu-id="81670-103">设计用户可以在运行时调整大小的窗体时，如果你的窗体上的控件应调整大小并正确地重新定位。</span><span class="sxs-lookup"><span data-stu-id="81670-103">If you are designing a form that the user can resize at run time, the controls on your form should resize and reposition properly.</span></span> <span data-ttu-id="81670-104">若要调整动态处理该窗体控件的大小，可以使用<xref:System.Windows.Forms.Control.Anchor%2A>Windows 窗体控件的属性。</span><span class="sxs-lookup"><span data-stu-id="81670-104">To resize controls dynamically with the form, you can use the <xref:System.Windows.Forms.Control.Anchor%2A> property of Windows Forms controls.</span></span> <span data-ttu-id="81670-105"><xref:System.Windows.Forms.Control.Anchor%2A>属性定义控件的定位点位置。</span><span class="sxs-lookup"><span data-stu-id="81670-105">The <xref:System.Windows.Forms.Control.Anchor%2A> property defines an anchor position for the control.</span></span> <span data-ttu-id="81670-106">当控件锚定到窗体和窗体调整时，控件将保持该控件的定位点位置之间的距离。</span><span class="sxs-lookup"><span data-stu-id="81670-106">When a control is anchored to a form and the form is resized, the control maintains the distance between the control and the anchor positions.</span></span> <span data-ttu-id="81670-107">例如，如果你有<xref:System.Windows.Forms.TextBox>控件的窗体调整大小时，定位到左侧、 右侧和底部边缘与窗体，<xref:System.Windows.Forms.TextBox>水平控件调整大小时，以便保持与窗体的右侧和左侧边的距离相同。</span><span class="sxs-lookup"><span data-stu-id="81670-107">For example, if you have a <xref:System.Windows.Forms.TextBox> control that is anchored to the left, right, and bottom edges of the form, as the form is resized, the <xref:System.Windows.Forms.TextBox> control resizes horizontally so that it maintains the same distance from the right and left sides of the form.</span></span> <span data-ttu-id="81670-108">此外，该控件垂直定位其自身，以便其位置始终是与窗体的下边缘的距离相同。</span><span class="sxs-lookup"><span data-stu-id="81670-108">In addition, the control positions itself vertically so that its location is always the same distance from the bottom edge of the form.</span></span> <span data-ttu-id="81670-109">如果控件未锚定和调整窗体，则更改控件相对于窗体的边缘的位置。</span><span class="sxs-lookup"><span data-stu-id="81670-109">If a control is not anchored and the form is resized, the position of the control relative to the edges of the form is changed.</span></span>  
  
 <span data-ttu-id="81670-110"><xref:System.Windows.Forms.Control.Anchor%2A>与属性交互<xref:System.Windows.Forms.Control.AutoSize%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="81670-110">The <xref:System.Windows.Forms.Control.Anchor%2A> property interacts with the <xref:System.Windows.Forms.Control.AutoSize%2A> property.</span></span> <span data-ttu-id="81670-111">有关详细信息，请参阅[AutoSize 属性概述](autosize-property-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="81670-111">For more information, see [AutoSize Property Overview](autosize-property-overview.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="81670-112">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="81670-112">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="81670-113">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="81670-113">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="81670-114">有关详细信息，请参阅[个性化设置 Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)。</span><span class="sxs-lookup"><span data-stu-id="81670-114">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-anchor-a-control-on-a-form"></a><span data-ttu-id="81670-115">若要定位到窗体上控件</span><span class="sxs-lookup"><span data-stu-id="81670-115">To anchor a control on a form</span></span>  
  
1. <span data-ttu-id="81670-116">选择你想要定位的控件。</span><span class="sxs-lookup"><span data-stu-id="81670-116">Select the control you want to anchor.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="81670-117">您可以通过按住 CTRL 键，单击每个控件以选择它，然后按照此过程的其余部分同时定位多个控件。</span><span class="sxs-lookup"><span data-stu-id="81670-117">You can anchor multiple controls simultaneously by pressing the CTRL key, clicking each control to select it, and then following the rest of this procedure.</span></span>  
  
2. <span data-ttu-id="81670-118">在中**属性**窗口中，单击右侧的箭头<xref:System.Windows.Forms.Control.Anchor%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="81670-118">In the **Properties** window, click the arrow to the right of the <xref:System.Windows.Forms.Control.Anchor%2A> property.</span></span>  
  
     <span data-ttu-id="81670-119">显示一个编辑器，显示十字形。</span><span class="sxs-lookup"><span data-stu-id="81670-119">An editor is displayed that shows a cross.</span></span>  
  
3. <span data-ttu-id="81670-120">若要设置定位点，请单击上、 左、 右或十字线的下半部分。</span><span class="sxs-lookup"><span data-stu-id="81670-120">To set an anchor, click the top, left, right, or bottom section of the cross.</span></span>  
  
     <span data-ttu-id="81670-121">控件锚定到顶部，并且默认情况下保留。</span><span class="sxs-lookup"><span data-stu-id="81670-121">Controls are anchored to the top and left by default.</span></span>  
  
4. <span data-ttu-id="81670-122">若要清除已定位的控件的一侧，单击跨该 arm。</span><span class="sxs-lookup"><span data-stu-id="81670-122">To clear a side of the control that has been anchored, click that arm of the cross.</span></span>  
  
5. <span data-ttu-id="81670-123">若要关闭<xref:System.Windows.Forms.Control.Anchor%2A>属性编辑器中，单击<xref:System.Windows.Forms.Control.Anchor%2A>再次属性名称。</span><span class="sxs-lookup"><span data-stu-id="81670-123">To close the <xref:System.Windows.Forms.Control.Anchor%2A> property editor, click the <xref:System.Windows.Forms.Control.Anchor%2A> property name again.</span></span>  
  
 <span data-ttu-id="81670-124">当在运行时显示窗体时，该控件调整大小，以保持与窗体的边缘的距离相同不变。</span><span class="sxs-lookup"><span data-stu-id="81670-124">When your form is displayed at run time, the control resizes to remain positioned at the same distance from the edge of the form.</span></span> <span data-ttu-id="81670-125">定位边缘的距离始终保持不变所定义的距离时将控件置于 Windows 窗体设计器。</span><span class="sxs-lookup"><span data-stu-id="81670-125">The distance from the anchored edge always remains the same as the distance defined when the control is positioned in the Windows Forms Designer.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="81670-126">某些控件，如<xref:System.Windows.Forms.ComboBox>控件，为其高度的限制。</span><span class="sxs-lookup"><span data-stu-id="81670-126">Certain controls, such as the <xref:System.Windows.Forms.ComboBox> control, have a limit to their height.</span></span> <span data-ttu-id="81670-127">锚定到其窗体或容器的底部的控件不能强制超过其高度限制的控件。</span><span class="sxs-lookup"><span data-stu-id="81670-127">Anchoring the control to the bottom of its form or container cannot force the control to exceed its height limit.</span></span>  
  
 <span data-ttu-id="81670-128">继承的控件必须是`Protected`能够定位。</span><span class="sxs-lookup"><span data-stu-id="81670-128">Inherited controls must be `Protected` to be able to be anchored.</span></span> <span data-ttu-id="81670-129">若要更改控件的访问级别，设置其`Modifiers`中的属性**属性**窗口。</span><span class="sxs-lookup"><span data-stu-id="81670-129">To change the access level of a control, set its `Modifiers` property in the **Properties** window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81670-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="81670-130">See also</span></span>

- [<span data-ttu-id="81670-131">Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="81670-131">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="81670-132">在 Windows 窗体上排列控件</span><span class="sxs-lookup"><span data-stu-id="81670-132">Arranging Controls on Windows Forms</span></span>](arranging-controls-on-windows-forms.md)
- [<span data-ttu-id="81670-133">AutoSize 属性概述</span><span class="sxs-lookup"><span data-stu-id="81670-133">AutoSize Property Overview</span></span>](autosize-property-overview.md)
- [<span data-ttu-id="81670-134">如何：在 Windows 窗体上停靠控件</span><span class="sxs-lookup"><span data-stu-id="81670-134">How to: Dock Controls on Windows Forms</span></span>](how-to-dock-controls-on-windows-forms.md)
- [<span data-ttu-id="81670-135">演练：使用 FlowLayoutPanel 的 Windows 窗体上排列控件</span><span class="sxs-lookup"><span data-stu-id="81670-135">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [<span data-ttu-id="81670-136">演练：使用 TableLayoutPanel 的 Windows 窗体上排列控件</span><span class="sxs-lookup"><span data-stu-id="81670-136">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [<span data-ttu-id="81670-137">演练：布局 Windows 窗体控件与 Padding、 Margins 和 AutoSize 属性</span><span class="sxs-lookup"><span data-stu-id="81670-137">Walkthrough: Laying Out Windows Forms Controls with Padding, Margins, and the AutoSize Property</span></span>](windows-forms-controls-padding-autosize.md)
