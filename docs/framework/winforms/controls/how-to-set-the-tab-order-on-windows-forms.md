---
title: "如何：设置 Windows 窗体上的 Tab 键顺序"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- TabStop
- TabIndex
helpviewer_keywords:
- tab order [Windows Forms], controls on Windows forms
- Windows Forms controls, setting tab order
- controls [Windows Forms], setting tab order
- Windows Forms, setting tab order
ms.assetid: 71fa8e76-0472-414b-ad3c-0f90166e0ad7
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a7acca633a5a2b98d7c4b6dd64355996e763d6df
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-the-tab-order-on-windows-forms"></a><span data-ttu-id="665fa-102">如何：设置 Windows 窗体上的 Tab 键顺序</span><span class="sxs-lookup"><span data-stu-id="665fa-102">How to: Set the Tab Order on Windows Forms</span></span>
<span data-ttu-id="665fa-103">Tab 键顺序是在其中用户焦点从一个控件移到另一个通过按 TAB 键顺序。</span><span class="sxs-lookup"><span data-stu-id="665fa-103">The tab order is the order in which a user moves focus from one control to another by pressing the TAB key.</span></span> <span data-ttu-id="665fa-104">每个窗体具有其自己的 tab 键顺序。</span><span class="sxs-lookup"><span data-stu-id="665fa-104">Each form has its own tab order.</span></span> <span data-ttu-id="665fa-105">默认情况下，tab 键顺序是创建控件的顺序相同。</span><span class="sxs-lookup"><span data-stu-id="665fa-105">By default, the tab order is the same as the order in which you created the controls.</span></span> <span data-ttu-id="665fa-106">Tab 键顺序编号从 0 开始。</span><span class="sxs-lookup"><span data-stu-id="665fa-106">Tab-order numbering begins with zero.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="665fa-107">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="665fa-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="665fa-108">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="665fa-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="665fa-109">有关详细信息，请参阅[在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。</span><span class="sxs-lookup"><span data-stu-id="665fa-109">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-set-the-tab-order-of-a-control"></a><span data-ttu-id="665fa-110">若要设置控件的 tab 键次序</span><span class="sxs-lookup"><span data-stu-id="665fa-110">To set the tab order of a control</span></span>  
  
1.  <span data-ttu-id="665fa-111">上**视图**菜单上，单击**tab 键顺序**。</span><span class="sxs-lookup"><span data-stu-id="665fa-111">On the **View** menu, click **Tab Order**.</span></span>  
  
     <span data-ttu-id="665fa-112">这将激活窗体上的 tab 键顺序选择模式。</span><span class="sxs-lookup"><span data-stu-id="665fa-112">This activates the tab-order selection mode on the form.</span></span> <span data-ttu-id="665fa-113">一个数字 (表示<xref:System.Windows.Forms.Control.TabIndex%2A>属性) 显示在每个控件的左上角。</span><span class="sxs-lookup"><span data-stu-id="665fa-113">A number (representing the <xref:System.Windows.Forms.Control.TabIndex%2A> property) appears in the upper-left corner of each control.</span></span>  
  
2.  <span data-ttu-id="665fa-114">单击的控件按顺序建立所需的选项卡顺序。</span><span class="sxs-lookup"><span data-stu-id="665fa-114">Click the controls sequentially to establish the tab order you want.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="665fa-115">大于或等于 0，在选项卡顺序内的控件的位置可以设置为任何值。</span><span class="sxs-lookup"><span data-stu-id="665fa-115">A control's place within the tab order can be set to any value greater than or equal to 0.</span></span> <span data-ttu-id="665fa-116">当出现重复时，计算的两个控件的 z 顺序，并位于上面的控件为第一个选项卡式。</span><span class="sxs-lookup"><span data-stu-id="665fa-116">When duplicates occur, the z-order of the two controls is evaluated and the control on top is tabbed to first.</span></span> <span data-ttu-id="665fa-117">（z 顺序是沿窗体的 z 轴 [深度] 窗体上控件的可视化分层。</span><span class="sxs-lookup"><span data-stu-id="665fa-117">(The z-order is the visual layering of controls on a form along the form's z-axis [depth].</span></span> <span data-ttu-id="665fa-118">Z 顺序确定哪些控件位于其他控件的前面。）Z 顺序的详细信息，请参阅[Windows 窗体上的分层对象](../../../../docs/framework/winforms/controls/how-to-layer-objects-on-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="665fa-118">The z-order determines which controls are in front of other controls.) For more information on z-order, see [Layering Objects on Windows Forms](../../../../docs/framework/winforms/controls/how-to-layer-objects-on-windows-forms.md).</span></span>  
  
3.  <span data-ttu-id="665fa-119">完成后，单击**tab 键顺序**上**视图**菜单再次离开 tab 键顺序模式。</span><span class="sxs-lookup"><span data-stu-id="665fa-119">When you have finished, click **Tab Order** on the **View** menu again to leave tab order mode.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="665fa-120">无法获得焦点的控件，以及禁用，并且不可见控件没有<xref:System.Windows.Forms.Control.TabIndex%2A>属性，也不包括的 tab 键顺序。</span><span class="sxs-lookup"><span data-stu-id="665fa-120">Controls that cannot get the focus, as well as disabled and invisible controls, do not have a <xref:System.Windows.Forms.Control.TabIndex%2A> property and are not included in the tab order.</span></span> <span data-ttu-id="665fa-121">当用户按 TAB 键，则跳过这些控件。</span><span class="sxs-lookup"><span data-stu-id="665fa-121">As a user presses the TAB key, these controls are skipped.</span></span>  
  
 <span data-ttu-id="665fa-122">或者，可以在属性窗口中使用设置 tab 键顺序<xref:System.Windows.Forms.Control.TabIndex%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="665fa-122">Alternatively, tab order can be set in the Properties window using the <xref:System.Windows.Forms.Control.TabIndex%2A> property.</span></span> <span data-ttu-id="665fa-123"><xref:System.Windows.Forms.Control.TabIndex%2A>控件的属性确定的 tab 键顺序的放置位置。</span><span class="sxs-lookup"><span data-stu-id="665fa-123">The <xref:System.Windows.Forms.Control.TabIndex%2A> property of a control determines where it is positioned in the tab order.</span></span> <span data-ttu-id="665fa-124">默认情况下，第一个控件绘制具有<xref:System.Windows.Forms.Control.TabIndex%2A>值为 0，第二个具有<xref:System.Windows.Forms.Control.TabIndex%2A>为 1，依次类推。</span><span class="sxs-lookup"><span data-stu-id="665fa-124">By default, the first control drawn has a <xref:System.Windows.Forms.Control.TabIndex%2A> value of 0, the second has a <xref:System.Windows.Forms.Control.TabIndex%2A> of 1, and so on.</span></span>  
  
 <span data-ttu-id="665fa-125">此外，默认情况下，<xref:System.Windows.Forms.GroupBox>控件具有其自己<xref:System.Windows.Forms.Control.TabIndex%2A>值，该值是一个整数。</span><span class="sxs-lookup"><span data-stu-id="665fa-125">Additionally, by default, a <xref:System.Windows.Forms.GroupBox> control has its own <xref:System.Windows.Forms.Control.TabIndex%2A> value, which is a whole number.</span></span> <span data-ttu-id="665fa-126">A<xref:System.Windows.Forms.GroupBox>控件本身不能在运行时具有焦点。</span><span class="sxs-lookup"><span data-stu-id="665fa-126">A <xref:System.Windows.Forms.GroupBox> control itself cannot have focus at run time.</span></span> <span data-ttu-id="665fa-127">因此，在每个控件<xref:System.Windows.Forms.GroupBox>具有其自己的十进制<xref:System.Windows.Forms.Control.TabIndex%2A>值，开头.0。</span><span class="sxs-lookup"><span data-stu-id="665fa-127">Thus, each control within a <xref:System.Windows.Forms.GroupBox> has its own decimal <xref:System.Windows.Forms.Control.TabIndex%2A> value, beginning with .0.</span></span> <span data-ttu-id="665fa-128">当然，作为<xref:System.Windows.Forms.Control.TabIndex%2A>的<xref:System.Windows.Forms.GroupBox>控件即会递增，其中的控件将相应递增。</span><span class="sxs-lookup"><span data-stu-id="665fa-128">Naturally, as the <xref:System.Windows.Forms.Control.TabIndex%2A> of a <xref:System.Windows.Forms.GroupBox> control is incremented, the controls within it will be incremented accordingly.</span></span> <span data-ttu-id="665fa-129">如果你更改<xref:System.Windows.Forms.Control.TabIndex%2A>介于 5 和 6，值<xref:System.Windows.Forms.Control.TabIndex%2A>在其组的第一个控件的值自动更改为 6.0 中，依次类推。</span><span class="sxs-lookup"><span data-stu-id="665fa-129">If you changed a <xref:System.Windows.Forms.Control.TabIndex%2A> value from 5 to 6, the <xref:System.Windows.Forms.Control.TabIndex%2A> value of the first control in its group automatically changes to 6.0, and so on.</span></span>  
  
 <span data-ttu-id="665fa-130">最后，任何控件的窗体上多可以跳过的 tab 键顺序。</span><span class="sxs-lookup"><span data-stu-id="665fa-130">Finally, any control of the many on your form can be skipped in the tab order.</span></span> <span data-ttu-id="665fa-131">通常情况下，连续按 tab 键在运行的时选择每个控件的 tab 键顺序。</span><span class="sxs-lookup"><span data-stu-id="665fa-131">Usually, pressing TAB successively at run time selects each control in the tab order.</span></span> <span data-ttu-id="665fa-132">通过关闭<xref:System.Windows.Forms.Control.TabStop%2A>属性，可以使控件通过传递窗体的 tab 键顺序。</span><span class="sxs-lookup"><span data-stu-id="665fa-132">By turning off the <xref:System.Windows.Forms.Control.TabStop%2A> property, you can make a control be passed over in the tab order of the form.</span></span>  
  
#### <a name="to-remove-a-control-from-the-tab-order"></a><span data-ttu-id="665fa-133">若要从 tab 键顺序中移除控件</span><span class="sxs-lookup"><span data-stu-id="665fa-133">To remove a control from the tab order</span></span>  
  
1.  <span data-ttu-id="665fa-134">设置控件的<xref:System.Windows.Forms.Control.TabStop%2A>属性`false`属性窗口中。</span><span class="sxs-lookup"><span data-stu-id="665fa-134">Set the control's <xref:System.Windows.Forms.Control.TabStop%2A> property to `false` in the Properties window.</span></span>  
  
     <span data-ttu-id="665fa-135">一个控件<xref:System.Windows.Forms.Control.TabStop%2A>属性已设置为`false`仍保持 tab 键顺序中，其位置，即使控件循环使用 TAB 键时，控件将跳过。</span><span class="sxs-lookup"><span data-stu-id="665fa-135">A control whose <xref:System.Windows.Forms.Control.TabStop%2A> property has been set to `false` still maintains its position in the tab order, even though the control is skipped when you cycle through the controls with the TAB key.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="665fa-136">单选按钮组具有一个制表位运行时。</span><span class="sxs-lookup"><span data-stu-id="665fa-136">A radio button group has a single tab stop at run time.</span></span> <span data-ttu-id="665fa-137">所选的按钮 (即，具有的按钮其<xref:System.Windows.Forms.RadioButton.Checked%2A>属性设置为`true`) 具有其<xref:System.Windows.Forms.Control.TabStop%2A>属性自动设置为`true`，而其他按钮拥有其<xref:System.Windows.Forms.Control.TabStop%2A>属性设置为`false`。</span><span class="sxs-lookup"><span data-stu-id="665fa-137">The selected button (that is, the button with its <xref:System.Windows.Forms.RadioButton.Checked%2A> property set to `true`) has its <xref:System.Windows.Forms.Control.TabStop%2A> property automatically set to `true`, while the other buttons have their <xref:System.Windows.Forms.Control.TabStop%2A> property set to `false`.</span></span> <span data-ttu-id="665fa-138">有关更多信息分组<xref:System.Windows.Forms.RadioButton>控件，请参阅[分组用作一组 Windows 窗体 RadioButton 控件](../../../../docs/framework/winforms/controls/how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set.md)。</span><span class="sxs-lookup"><span data-stu-id="665fa-138">For more information about grouping <xref:System.Windows.Forms.RadioButton> controls, see [Grouping Windows Forms RadioButton Controls to Function as a Set](../../../../docs/framework/winforms/controls/how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="665fa-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="665fa-139">See Also</span></span>  
 [<span data-ttu-id="665fa-140">Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="665fa-140">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)  
 [<span data-ttu-id="665fa-141">在 Windows 窗体上排列控件</span><span class="sxs-lookup"><span data-stu-id="665fa-141">Arranging Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [<span data-ttu-id="665fa-142">在 Windows 窗体上使用的控件</span><span class="sxs-lookup"><span data-stu-id="665fa-142">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [<span data-ttu-id="665fa-143">按功能列出的 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="665fa-143">Windows Forms Controls by Function</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)
