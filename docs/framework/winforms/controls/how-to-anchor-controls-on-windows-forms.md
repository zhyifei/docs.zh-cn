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
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 94fa6fe90e5583a3bfecf376af59d53f6d8528af
ms.sourcegitcommit: 37616676fde89153f563a485fc6159fc57326fc2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2019
ms.locfileid: "69987493"
---
# <a name="how-to-anchor-controls-on-windows-forms"></a><span data-ttu-id="46bcf-102">如何：Windows 窗体上的定位控件</span><span class="sxs-lookup"><span data-stu-id="46bcf-102">How to: Anchor controls on Windows Forms</span></span>

<span data-ttu-id="46bcf-103">如果要设计一个窗体, 用户可以在运行时调整其大小, 则窗体上的控件应正确调整大小和重新定位。</span><span class="sxs-lookup"><span data-stu-id="46bcf-103">If you're designing a form that the user can resize at run time, the controls on your form should resize and reposition properly.</span></span> <span data-ttu-id="46bcf-104">若要使用窗体动态调整控件大小, 可以使用<xref:System.Windows.Forms.Control.Anchor%2A> Windows 窗体控件的属性。</span><span class="sxs-lookup"><span data-stu-id="46bcf-104">To resize controls dynamically with the form, you can use the <xref:System.Windows.Forms.Control.Anchor%2A> property of Windows Forms controls.</span></span> <span data-ttu-id="46bcf-105"><xref:System.Windows.Forms.Control.Anchor%2A>属性定义控件的定位点位置。</span><span class="sxs-lookup"><span data-stu-id="46bcf-105">The <xref:System.Windows.Forms.Control.Anchor%2A> property defines an anchor position for the control.</span></span> <span data-ttu-id="46bcf-106">当控件锚定到窗体并且调整了窗体的大小时, 控件将保持控件和定位点之间的距离。</span><span class="sxs-lookup"><span data-stu-id="46bcf-106">When a control is anchored to a form and the form is resized, the control maintains the distance between the control and the anchor positions.</span></span> <span data-ttu-id="46bcf-107">例如, 如果您有一个<xref:System.Windows.Forms.TextBox>控件, 该控件锚定到窗体的左边缘、右边缘和下边缘, 则当调整窗体大小时<xref:System.Windows.Forms.TextBox> , 控件会水平调整大小, 以便与窗体的右侧和左侧保持相同的距离。</span><span class="sxs-lookup"><span data-stu-id="46bcf-107">For example, if you have a <xref:System.Windows.Forms.TextBox> control that is anchored to the left, right, and bottom edges of the form, as the form is resized, the <xref:System.Windows.Forms.TextBox> control resizes horizontally so that it maintains the same distance from the right and left sides of the form.</span></span> <span data-ttu-id="46bcf-108">此外, 控件将对其自身定位, 使其位置与窗体下边缘的距离始终相同。</span><span class="sxs-lookup"><span data-stu-id="46bcf-108">In addition, the control positions itself vertically so that its location is always the same distance from the bottom edge of the form.</span></span> <span data-ttu-id="46bcf-109">如果控件未定位并且调整了窗体的大小, 则相对于窗体边缘的控件位置会发生更改。</span><span class="sxs-lookup"><span data-stu-id="46bcf-109">If a control is not anchored and the form is resized, the position of the control relative to the edges of the form is changed.</span></span>

<span data-ttu-id="46bcf-110"><xref:System.Windows.Forms.Control.Anchor%2A> 属性<xref:System.Windows.Forms.Control.AutoSize%2A>与属性交互。</span><span class="sxs-lookup"><span data-stu-id="46bcf-110">The <xref:System.Windows.Forms.Control.Anchor%2A> property interacts with the <xref:System.Windows.Forms.Control.AutoSize%2A> property.</span></span> <span data-ttu-id="46bcf-111">有关详细信息, 请参阅[AutoSize 属性概述](autosize-property-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="46bcf-111">For more information, see [AutoSize Property Overview](autosize-property-overview.md).</span></span>

## <a name="anchor-a-control-on-a-form"></a><span data-ttu-id="46bcf-112">在窗体上定位控件</span><span class="sxs-lookup"><span data-stu-id="46bcf-112">Anchor a control on a form</span></span>

1. <span data-ttu-id="46bcf-113">在 Visual Studio 中, 选择要定位的控件。</span><span class="sxs-lookup"><span data-stu-id="46bcf-113">In Visual Studio, select the control you want to anchor.</span></span>

    > [!NOTE]
    > <span data-ttu-id="46bcf-114">您可以通过按 CTRL 键, 单击每个控件以选择它, 然后按照此过程的其余部分, 来同时定位多个控件。</span><span class="sxs-lookup"><span data-stu-id="46bcf-114">You can anchor multiple controls simultaneously by pressing the CTRL key, clicking each control to select it, and then following the rest of this procedure.</span></span>

2. <span data-ttu-id="46bcf-115">在 "**属性**" 窗口中, 单击<xref:System.Windows.Forms.Control.Anchor%2A>属性右侧的箭头。</span><span class="sxs-lookup"><span data-stu-id="46bcf-115">In the **Properties** window, click the arrow to the right of the <xref:System.Windows.Forms.Control.Anchor%2A> property.</span></span>

     <span data-ttu-id="46bcf-116">将显示一个编辑器, 其中显示交叉。</span><span class="sxs-lookup"><span data-stu-id="46bcf-116">An editor is displayed that shows a cross.</span></span>

3. <span data-ttu-id="46bcf-117">若要设置定位点, 请单击交叉的上、左、右或下部分。</span><span class="sxs-lookup"><span data-stu-id="46bcf-117">To set an anchor, click the top, left, right, or bottom section of the cross.</span></span>

     <span data-ttu-id="46bcf-118">控件默认锚定到顶部和左侧。</span><span class="sxs-lookup"><span data-stu-id="46bcf-118">Controls are anchored to the top and left by default.</span></span>

4. <span data-ttu-id="46bcf-119">若要清除已锚定的控件侧, 请单击交叉的该侧。</span><span class="sxs-lookup"><span data-stu-id="46bcf-119">To clear a side of the control that has been anchored, click that arm of the cross.</span></span>

5. <span data-ttu-id="46bcf-120">若要关闭<xref:System.Windows.Forms.Control.Anchor%2A> "属性编辑器", <xref:System.Windows.Forms.Control.Anchor%2A>请再次单击属性名称。</span><span class="sxs-lookup"><span data-stu-id="46bcf-120">To close the <xref:System.Windows.Forms.Control.Anchor%2A> property editor, click the <xref:System.Windows.Forms.Control.Anchor%2A> property name again.</span></span>

<span data-ttu-id="46bcf-121">当在运行时显示窗体时, 控件调整大小以保持与窗体边缘的距离相同。</span><span class="sxs-lookup"><span data-stu-id="46bcf-121">When your form is displayed at run time, the control resizes to remain positioned at the same distance from the edge of the form.</span></span> <span data-ttu-id="46bcf-122">与定位边缘的距离始终与控件定位在 Windows 窗体设计器时所定义的距离相同。</span><span class="sxs-lookup"><span data-stu-id="46bcf-122">The distance from the anchored edge always remains the same as the distance defined when the control is positioned in the Windows Forms Designer.</span></span>

> [!NOTE]
> <span data-ttu-id="46bcf-123">某些控件<xref:System.Windows.Forms.ComboBox> (如控件) 的高度限制为。</span><span class="sxs-lookup"><span data-stu-id="46bcf-123">Certain controls, such as the <xref:System.Windows.Forms.ComboBox> control, have a limit to their height.</span></span> <span data-ttu-id="46bcf-124">将控件定位到窗体或容器的底部不能强制控件超出其高度限制。</span><span class="sxs-lookup"><span data-stu-id="46bcf-124">Anchoring the control to the bottom of its form or container cannot force the control to exceed its height limit.</span></span>

<span data-ttu-id="46bcf-125">继承的控件必须`Protected`是能够锚定的。</span><span class="sxs-lookup"><span data-stu-id="46bcf-125">Inherited controls must be `Protected` to be able to be anchored.</span></span> <span data-ttu-id="46bcf-126">若要更改控件的访问级别, 请在 " `Modifiers` **属性**" 窗口中设置其属性。</span><span class="sxs-lookup"><span data-stu-id="46bcf-126">To change the access level of a control, set its `Modifiers` property in the **Properties** window.</span></span>

## <a name="see-also"></a><span data-ttu-id="46bcf-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="46bcf-127">See also</span></span>

- [<span data-ttu-id="46bcf-128">Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="46bcf-128">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="46bcf-129">AutoSize 属性概述</span><span class="sxs-lookup"><span data-stu-id="46bcf-129">AutoSize Property Overview</span></span>](autosize-property-overview.md)
- [<span data-ttu-id="46bcf-130">如何：在 Windows 窗体上停靠控件</span><span class="sxs-lookup"><span data-stu-id="46bcf-130">How to: Dock Controls on Windows Forms</span></span>](how-to-dock-controls-on-windows-forms.md)
- [<span data-ttu-id="46bcf-131">演练：使用 FlowLayoutPanel 排列 Windows 窗体上的控件</span><span class="sxs-lookup"><span data-stu-id="46bcf-131">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [<span data-ttu-id="46bcf-132">演练：使用 TableLayoutPanel 排列 Windows 窗体上的控件</span><span class="sxs-lookup"><span data-stu-id="46bcf-132">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [<span data-ttu-id="46bcf-133">演练：通过填充、边距和 AutoSize 属性排放 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="46bcf-133">Walkthrough: Laying Out Windows Forms Controls with Padding, Margins, and the AutoSize Property</span></span>](windows-forms-controls-padding-autosize.md)
