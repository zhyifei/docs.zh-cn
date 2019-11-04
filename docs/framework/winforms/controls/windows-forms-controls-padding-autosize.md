---
title: 演练：使用 Padding、Margins 和 AutoSize 属性对 Windows 窗体控件进行布局
ms.date: 03/30/2017
f1_keywords:
- Margin.Bottom
- Margin.Left
- Margin.Top
- Margin.All
- Margin.Right
helpviewer_keywords:
- Margin property [Windows Forms], walkthroughs
- walkthroughs [Windows Forms], layout
- AutoSize property [Windows Forms], walkthroughs
- Padding property [Windows Forms], walkthroughs
- layout [Windows Forms], margins and padding
- Windows Forms, layout
ms.assetid: f8ae2a6b-db13-4630-8e25-d104091205c7
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 76c880c208355b01d0fbaf46cf58091ad147846b
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460610"
---
# <a name="walkthrough-lay-out-controls-with-padding-margins-and-the-autosize-property"></a><span data-ttu-id="bcc2f-102">演练：按填充、边距和 AutoSize 属性对控件进行布局</span><span class="sxs-lookup"><span data-stu-id="bcc2f-102">Walkthrough: Lay out controls with padding, margins, and the AutoSize property</span></span>

<span data-ttu-id="bcc2f-103">在窗体上精确地放置控件对于许多应用程序而言是高优先级。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-103">Precise placement of controls on your form is a high priority for many applications.</span></span> <span data-ttu-id="bcc2f-104">Visual Studio 中的**Windows 窗体设计器**提供了许多布局工具来实现此目的。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-104">The **Windows Forms Designer** in Visual Studio gives you many layout tools to accomplish this.</span></span> <span data-ttu-id="bcc2f-105">其中三个最重要的是 <xref:System.Windows.Forms.Control.Margin%2A>、<xref:System.Windows.Forms.Control.Padding%2A>和 <xref:System.Windows.Forms.Control.AutoSize%2A> 属性，这些属性在所有 Windows 窗体控件上都存在。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-105">Three of the most important are the <xref:System.Windows.Forms.Control.Margin%2A>, <xref:System.Windows.Forms.Control.Padding%2A>, and <xref:System.Windows.Forms.Control.AutoSize%2A> properties, which are present on all Windows Forms controls.</span></span>

<span data-ttu-id="bcc2f-106"><xref:System.Windows.Forms.Control.Margin%2A> 属性定义控件周围的空间，该空间使其他控件与该控件的边框保持指定的距离。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-106">The <xref:System.Windows.Forms.Control.Margin%2A> property defines the space around the control that keeps other controls a specified distance from the control's borders.</span></span>

<span data-ttu-id="bcc2f-107"><xref:System.Windows.Forms.Control.Padding%2A> 属性定义控件内部的空间，该空间使控件的内容（例如，其 <xref:System.Windows.Forms.Control.Text%2A> 属性的值）与该控件的边框保持指定的距离。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-107">The <xref:System.Windows.Forms.Control.Padding%2A> property defines the space in the interior of a control that keeps the control's content (for example, the value of its <xref:System.Windows.Forms.Control.Text%2A> property) a specified distance from the control's borders.</span></span>

<span data-ttu-id="bcc2f-108">下图显示控件上的 <xref:System.Windows.Forms.Control.Padding%2A> 和 <xref:System.Windows.Forms.Control.Margin%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-108">The following illustration shows the <xref:System.Windows.Forms.Control.Padding%2A> and <xref:System.Windows.Forms.Control.Margin%2A> properties on a control.</span></span>

![Windows 窗体控件的填充和边距](./media/vs-winformpadmargin.gif)

<span data-ttu-id="bcc2f-110"><xref:System.Windows.Forms.Control.AutoSize%2A> 属性通知控件自动调整其内容的大小。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-110">The <xref:System.Windows.Forms.Control.AutoSize%2A> property tells a control to automatically size itself to its contents.</span></span> <span data-ttu-id="bcc2f-111">它不会将其大小调整为小于其原始 <xref:System.Windows.Forms.Control.Size%2A> 属性的值，并且将考虑其 <xref:System.Windows.Forms.Control.Padding%2A> 属性的值。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-111">It will not resize itself to be smaller than the value of its original <xref:System.Windows.Forms.Control.Size%2A> property, and it will account for the value of its <xref:System.Windows.Forms.Control.Padding%2A> property.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bcc2f-112">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="bcc2f-112">Prerequisites</span></span>

<span data-ttu-id="bcc2f-113">需要 Visual Studio 才能完成此演练。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-113">You'll need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="bcc2f-114">创建项目</span><span class="sxs-lookup"><span data-stu-id="bcc2f-114">Create the project</span></span>

1. <span data-ttu-id="bcc2f-115">在 Visual Studio 中，创建一个名为 `LayoutExample`的**Windows 应用程序**项目。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-115">In Visual Studio, create a **Windows Application** project called `LayoutExample`.</span></span>

2. <span data-ttu-id="bcc2f-116">在**Windows 窗体设计器**中选择窗体。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-116">Select the form in the **Windows Forms Designer**.</span></span>

## <a name="set-margins-for-controls"></a><span data-ttu-id="bcc2f-117">设置控件的边距</span><span class="sxs-lookup"><span data-stu-id="bcc2f-117">Set margins for controls</span></span>

<span data-ttu-id="bcc2f-118">您可以使用 <xref:System.Windows.Forms.Control.Margin%2A> 属性设置控件之间的默认距离。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-118">You can set the default distance between your controls using the <xref:System.Windows.Forms.Control.Margin%2A> property.</span></span> <span data-ttu-id="bcc2f-119">当您将控件向右移动到另一个控件时，将看到显示两个控件的边距的对齐线。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-119">When you move a control close enough to another control, you will see a snapline that shows the margins for the two controls.</span></span> <span data-ttu-id="bcc2f-120">您要移动的控件也将与边距定义的距离对齐。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-120">The control you are moving will also snap to the distance defined by the margins.</span></span>

### <a name="arrange-controls-on-your-form-using-the-margin-property"></a><span data-ttu-id="bcc2f-121">使用 Margin 属性排列窗体上的控件</span><span class="sxs-lookup"><span data-stu-id="bcc2f-121">Arrange controls on your form using the Margin property</span></span>

1. <span data-ttu-id="bcc2f-122">将两个 <xref:System.Windows.Forms.Button> 控件从**工具箱**拖到窗体上。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-122">Drag two <xref:System.Windows.Forms.Button> controls from the **Toolbox** onto your form.</span></span>

2. <span data-ttu-id="bcc2f-123">选择某个 <xref:System.Windows.Forms.Button> 控件，并将其移动到另一个控件，直到它们接近。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-123">Select one of the <xref:System.Windows.Forms.Button> controls and move it close to the other, until they are almost touching.</span></span>

   <span data-ttu-id="bcc2f-124">观察它们之间出现的对齐线。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-124">Observe the snapline that appears between them.</span></span> <span data-ttu-id="bcc2f-125">此距离是两个控件的 <xref:System.Windows.Forms.Control.Margin%2A> 值之和。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-125">This distance is the sum of the two controls' <xref:System.Windows.Forms.Control.Margin%2A> values.</span></span> <span data-ttu-id="bcc2f-126">正在移动的控件将对齐到此距离。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-126">The control you are moving snaps to this distance.</span></span> <span data-ttu-id="bcc2f-127">有关详细信息，请参阅[演练：使用对齐线排列 Windows 窗体上的控件](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-127">For details, see [Walkthrough: Arranging Controls on Windows Forms Using Snaplines](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span></span>

3. <span data-ttu-id="bcc2f-128">通过在 "**属性**" 窗口中展开 "<xref:System.Windows.Forms.Control.Margin%2A>" 条目并将 "<xref:System.Windows.Forms.Padding.All%2A>" 属性设置为 " **20**"，更改其中一个控件的 <xref:System.Windows.Forms.Control.Margin%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-128">Change the <xref:System.Windows.Forms.Control.Margin%2A> property of one of the controls by expanding the <xref:System.Windows.Forms.Control.Margin%2A> entry in the **Properties** window and setting the <xref:System.Windows.Forms.Padding.All%2A> property to **20**.</span></span>

4. <span data-ttu-id="bcc2f-129">选择某个 <xref:System.Windows.Forms.Button> 控件，并将其移到另一个控件附近。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-129">Select one of the <xref:System.Windows.Forms.Button> controls and move it close to the other.</span></span>

   <span data-ttu-id="bcc2f-130">定义边距值的和的对齐线会更长，并使控件与其他控件对齐。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-130">The snapline defining the sum of the margin values is longer and that the control snaps to a greater distance from the other control.</span></span>

5. <span data-ttu-id="bcc2f-131">通过在 "**属性**" 窗口中展开 "<xref:System.Windows.Forms.Control.Margin%2A>" 条目并将 "<xref:System.Windows.Forms.Padding.Top%2A>" 属性设置为 " **5**"，更改所选控件的 <xref:System.Windows.Forms.Control.Margin%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-131">Change the <xref:System.Windows.Forms.Control.Margin%2A> property of the selected control by expanding the <xref:System.Windows.Forms.Control.Margin%2A> entry in the **Properties** window and setting the <xref:System.Windows.Forms.Padding.Top%2A> property to **5**.</span></span>

6. <span data-ttu-id="bcc2f-132">将所选控件移动到另一个控件的下方，并观察对齐线是否更短。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-132">Move the selected control below the other control and observe that the snapline is shorter.</span></span> <span data-ttu-id="bcc2f-133">将所选控件移动到另一个控件的左侧，并观察对齐线是否保留步骤4中观测到的值。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-133">Move the selected control to the left of the other control and observe that the snapline retains the value observed in step 4.</span></span>

7. <span data-ttu-id="bcc2f-134">您可以将 <xref:System.Windows.Forms.Control.Margin%2A> 属性的每个方面（<xref:System.Windows.Forms.Padding.Left%2A>、<xref:System.Windows.Forms.Padding.Top%2A>、<xref:System.Windows.Forms.Padding.Right%2A>、<xref:System.Windows.Forms.Padding.Bottom%2A>）设置为不同的值，也可以将它们全部设置为与 <xref:System.Windows.Forms.Padding.All%2A> 属性相同的值。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-134">You can set each of the aspects of the <xref:System.Windows.Forms.Control.Margin%2A> property, <xref:System.Windows.Forms.Padding.Left%2A>, <xref:System.Windows.Forms.Padding.Top%2A>, <xref:System.Windows.Forms.Padding.Right%2A>, <xref:System.Windows.Forms.Padding.Bottom%2A>, to different values, or you can set them all to the same value with the <xref:System.Windows.Forms.Padding.All%2A> property.</span></span>

## <a name="set-padding-for-controls"></a><span data-ttu-id="bcc2f-135">为控件设置填充</span><span class="sxs-lookup"><span data-stu-id="bcc2f-135">Set padding for controls</span></span>

<span data-ttu-id="bcc2f-136">若要实现应用程序所需的精确布局，控件通常会包含子控件。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-136">To achieve the precise layout required for your application, your controls will often contain child controls.</span></span> <span data-ttu-id="bcc2f-137">若要指定子控件边框到父控件边框的邻近性，请结合使用父控件的 <xref:System.Windows.Forms.Control.Padding%2A> 属性和子控件的 <xref:System.Windows.Forms.Control.Margin%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-137">When you want to specify the proximity of the child control's border to the parent control's border, use the parent control's <xref:System.Windows.Forms.Control.Padding%2A> property in conjunction with the child control's <xref:System.Windows.Forms.Control.Margin%2A> property.</span></span> <span data-ttu-id="bcc2f-138"><xref:System.Windows.Forms.Control.Padding%2A> 属性还可用于控制控件内容（例如，<xref:System.Windows.Forms.Button> 控件的 <xref:System.Windows.Forms.Control.Text%2A> 属性）与边框的邻近性。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-138">The <xref:System.Windows.Forms.Control.Padding%2A> property is also used to control the proximity of a control's content (for example, a <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Text%2A> property) to its borders.</span></span>

### <a name="arrange-controls-on-your-form-using-padding"></a><span data-ttu-id="bcc2f-139">使用填充排列窗体上的控件</span><span class="sxs-lookup"><span data-stu-id="bcc2f-139">Arrange controls on your form using padding</span></span>

1. <span data-ttu-id="bcc2f-140">从 <xref:System.Windows.Forms.Button> “工具箱” **将** 控件拖到你的窗体上。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-140">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto your form.</span></span>

2. <span data-ttu-id="bcc2f-141">将 <xref:System.Windows.Forms.Button> 控件的 <xref:System.Windows.Forms.Control.AutoSize%2A> 属性的值更改为**true**。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-141">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.AutoSize%2A> property to **true**.</span></span>

3. <span data-ttu-id="bcc2f-142">在 "**属性**" 窗口中展开 "<xref:System.Windows.Forms.Control.Padding%2A>" 条目，并将 "<xref:System.Windows.Forms.Padding.All%2A>" 属性设置为 " **5**"，更改 "<xref:System.Windows.Forms.Control.Padding%2A>" 属性。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-142">Change the <xref:System.Windows.Forms.Control.Padding%2A> property by expanding the <xref:System.Windows.Forms.Control.Padding%2A> entry in the **Properties** window and setting the <xref:System.Windows.Forms.Padding.All%2A> property to **5**.</span></span>

   <span data-ttu-id="bcc2f-143">控件将展开以为新的填充提供空间。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-143">The control expands to provide room for the new padding.</span></span>

4. <span data-ttu-id="bcc2f-144">从 <xref:System.Windows.Forms.GroupBox> “工具箱” **将** 控件拖到你的窗体上。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-144">Drag a <xref:System.Windows.Forms.GroupBox> control from the **Toolbox** onto your form.</span></span> <span data-ttu-id="bcc2f-145">将 <xref:System.Windows.Forms.Button> 控件从**工具箱**拖动到 <xref:System.Windows.Forms.GroupBox> 控件中。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-145">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** into the <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="bcc2f-146">将 <xref:System.Windows.Forms.Button> 控件定位，使其与 <xref:System.Windows.Forms.GroupBox> 控件的右下角对齐。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-146">Position the <xref:System.Windows.Forms.Button> control so it is flush with the lower-right corner of the <xref:System.Windows.Forms.GroupBox> control.</span></span>

   <span data-ttu-id="bcc2f-147">观察显示的对齐线，<xref:System.Windows.Forms.Button> 控件接近 <xref:System.Windows.Forms.GroupBox> 控件的下边框和右边框。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-147">Observe the snaplines that appear as the <xref:System.Windows.Forms.Button> control approaches the bottom and right borders of the <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="bcc2f-148">这些对齐线对应于 <xref:System.Windows.Forms.Button>的 <xref:System.Windows.Forms.Control.Margin%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-148">These snaplines correspond to the <xref:System.Windows.Forms.Control.Margin%2A> property of the <xref:System.Windows.Forms.Button>.</span></span>

5. <span data-ttu-id="bcc2f-149">通过在 "**属性**" 窗口中展开 <xref:System.Windows.Forms.Control.Padding%2A> 项并将 <xref:System.Windows.Forms.Padding.All%2A> 属性设置为**20**，更改 <xref:System.Windows.Forms.GroupBox> 控件的 <xref:System.Windows.Forms.Control.Padding%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-149">Change the <xref:System.Windows.Forms.GroupBox> control's <xref:System.Windows.Forms.Control.Padding%2A> property by expanding the <xref:System.Windows.Forms.Control.Padding%2A> entry in the **Properties** window and setting the <xref:System.Windows.Forms.Padding.All%2A> property to **20**.</span></span>

6. <span data-ttu-id="bcc2f-150">选择 <xref:System.Windows.Forms.GroupBox> 控件中的 "<xref:System.Windows.Forms.Button>" 控件，并将其移到 <xref:System.Windows.Forms.GroupBox>中心。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-150">Select the <xref:System.Windows.Forms.Button> control within the <xref:System.Windows.Forms.GroupBox> control and move it toward the center of the <xref:System.Windows.Forms.GroupBox>.</span></span>

   <span data-ttu-id="bcc2f-151">对齐线与 <xref:System.Windows.Forms.GroupBox> 控件边框的显示距离更远。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-151">The snaplines appear at a greater distance from the borders of the <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="bcc2f-152">此距离是 <xref:System.Windows.Forms.Button> 控件的 <xref:System.Windows.Forms.Control.Margin%2A> 属性与 <xref:System.Windows.Forms.GroupBox> 控件的 <xref:System.Windows.Forms.Control.Padding%2A> 属性之和。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-152">This distance is the sum of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Margin%2A> property and the <xref:System.Windows.Forms.GroupBox> control's <xref:System.Windows.Forms.Control.Padding%2A> property.</span></span>

## <a name="size-controls-automatically"></a><span data-ttu-id="bcc2f-153">自动调整控件大小</span><span class="sxs-lookup"><span data-stu-id="bcc2f-153">Size controls automatically</span></span>

<span data-ttu-id="bcc2f-154">在某些应用程序中，控件的大小在运行时与设计时的大小不相同。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-154">In some applications, the size of a control will not be the same at run time as it was at design time.</span></span> <span data-ttu-id="bcc2f-155">例如，可以从数据库中获取 <xref:System.Windows.Forms.Button> 控件的文本，并且它的长度事先未知。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-155">The text of a <xref:System.Windows.Forms.Button> control, for example, may be taken from a database, and its length are not known in advance.</span></span>

<span data-ttu-id="bcc2f-156">当 <xref:System.Windows.Forms.Control.AutoSize%2A> 属性设置为 `true`时，控件的大小会自行调整为其内容。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-156">When the <xref:System.Windows.Forms.Control.AutoSize%2A> property is set to `true`, the control will size itself to its content.</span></span> <span data-ttu-id="bcc2f-157">有关详细信息，请参阅[AutoSize 属性概述](autosize-property-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-157">For more information, see [AutoSize Property Overview](autosize-property-overview.md).</span></span>

### <a name="arrange-controls-on-your-form-using-the-autosize-property"></a><span data-ttu-id="bcc2f-158">使用 AutoSize 属性排列窗体上的控件</span><span class="sxs-lookup"><span data-stu-id="bcc2f-158">Arrange controls on your form using the AutoSize property</span></span>

1. <span data-ttu-id="bcc2f-159">从 <xref:System.Windows.Forms.Button> “工具箱” **将** 控件拖到你的窗体上。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-159">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto your form.</span></span>

2. <span data-ttu-id="bcc2f-160">将 <xref:System.Windows.Forms.Button> 控件的 <xref:System.Windows.Forms.Control.AutoSize%2A> 属性的值更改为**true**。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-160">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.AutoSize%2A> property to **true**.</span></span>

3. <span data-ttu-id="bcc2f-161">将 <xref:System.Windows.Forms.Button> 控件的 <xref:System.Windows.Forms.Control.Text%2A> 属性更改为**此按钮的 Text 属性的长字符串**。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-161">Change the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Text%2A> property to **This button has a long string for its Text property**.</span></span>

   <span data-ttu-id="bcc2f-162">提交更改时，<xref:System.Windows.Forms.Button> 控件会调整其自身大小以适应新文本。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-162">When you commit the change, the <xref:System.Windows.Forms.Button> control resizes itself to fit the new text.</span></span>

4. <span data-ttu-id="bcc2f-163">将另一个 <xref:System.Windows.Forms.Button> 控件从**工具箱**拖到窗体上。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-163">Drag another <xref:System.Windows.Forms.Button> control from the **Toolbox** onto your form.</span></span>

5. <span data-ttu-id="bcc2f-164">将 <xref:System.Windows.Forms.Button> 控件的 <xref:System.Windows.Forms.Control.Text%2A> 属性更改为 "**此按钮的 Text 属性的长字符串。** "</span><span class="sxs-lookup"><span data-stu-id="bcc2f-164">Change the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Text%2A> property to "**This button has a long string for its Text property.**"</span></span>

   <span data-ttu-id="bcc2f-165">提交更改时，<xref:System.Windows.Forms.Button> 控件不会调整其自身的大小，而是由控件的右边缘剪切文本。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-165">When you commit the change, the <xref:System.Windows.Forms.Button> control does not resize itself, and the text is clipped by the right edge of the control.</span></span>

6. <span data-ttu-id="bcc2f-166">在 "**属性**" 窗口中展开 "<xref:System.Windows.Forms.Control.Padding%2A>" 条目，并将 "<xref:System.Windows.Forms.Padding.All%2A>" 属性设置为 " **5**"，更改 "<xref:System.Windows.Forms.Control.Padding%2A>" 属性。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-166">Change the <xref:System.Windows.Forms.Control.Padding%2A> property by expanding the <xref:System.Windows.Forms.Control.Padding%2A> entry in the **Properties** window and setting the <xref:System.Windows.Forms.Padding.All%2A> property to **5**.</span></span>

   <span data-ttu-id="bcc2f-167">控件内部的文本在所有四个边都被剪切。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-167">The text in the control's interior is clipped on all four sides.</span></span>

7. <span data-ttu-id="bcc2f-168">将 <xref:System.Windows.Forms.Button> 控件的 <xref:System.Windows.Forms.Control.AutoSize%2A> 属性更改为**true**。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-168">Change the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.AutoSize%2A> property to **true**.</span></span>

   <span data-ttu-id="bcc2f-169"><xref:System.Windows.Forms.Button> 控件调整自身大小以包含整个字符串。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-169">The <xref:System.Windows.Forms.Button> control resizes itself to encompass the entire string.</span></span> <span data-ttu-id="bcc2f-170">此外，文本周围还添加了填充，导致 <xref:System.Windows.Forms.Button> 控件在四个方向上都展开。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-170">Also, padding has been added around the text, causing the <xref:System.Windows.Forms.Button> control to expand in all four directions.</span></span>

8. <span data-ttu-id="bcc2f-171">从 <xref:System.Windows.Forms.Button> “工具箱” **将** 控件拖到你的窗体上。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-171">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto your form.</span></span> <span data-ttu-id="bcc2f-172">将其放置在窗体右下角附近。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-172">Position it near the lower-right corner of the form.</span></span>

9. <span data-ttu-id="bcc2f-173">将 <xref:System.Windows.Forms.Button> 控件的 <xref:System.Windows.Forms.Control.AutoSize%2A> 属性的值更改为**true**。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-173">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.AutoSize%2A> property to **true**.</span></span>

10. <span data-ttu-id="bcc2f-174">将 <xref:System.Windows.Forms.Button> 控件的 <xref:System.Windows.Forms.Control.Anchor%2A> 属性设置为 <xref:System.Windows.Forms.AnchorStyles.Right>，<xref:System.Windows.Forms.AnchorStyles.Bottom>。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-174">Set the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to <xref:System.Windows.Forms.AnchorStyles.Right>, <xref:System.Windows.Forms.AnchorStyles.Bottom>.</span></span>

11. <span data-ttu-id="bcc2f-175">将 <xref:System.Windows.Forms.Button> 控件的 <xref:System.Windows.Forms.Control.Text%2A> 属性更改为 "**此按钮的 Text 属性的长字符串。** "</span><span class="sxs-lookup"><span data-stu-id="bcc2f-175">Change the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Text%2A> property to "**This button has a long string for its Text property.**"</span></span>

   <span data-ttu-id="bcc2f-176">提交更改时，<xref:System.Windows.Forms.Button> 控件向左调整其自身大小。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-176">When you commit the change, the <xref:System.Windows.Forms.Button> control resizes itself toward the left.</span></span> <span data-ttu-id="bcc2f-177">通常，自动调整大小会将控件的大小增加 <xref:System.Windows.Forms.Control.Anchor%2A> 属性设置的方向。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-177">In general, automatic sizing will increase the size of a control in the direction opposite its <xref:System.Windows.Forms.Control.Anchor%2A> property setting.</span></span>

## <a name="autosize-and-autosizemode-properties"></a><span data-ttu-id="bcc2f-178">AutoSize 和 AutoSizeMode 属性</span><span class="sxs-lookup"><span data-stu-id="bcc2f-178">AutoSize and AutoSizeMode properties</span></span>

 <span data-ttu-id="bcc2f-179">某些控件支持 `AutoSizeMode` 属性，这使你可以更精细地控制控件的自动调整大小行为。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-179">Some controls support the `AutoSizeMode` property, which gives you more fine-grained control over the automatic sizing behavior of a control.</span></span>

### <a name="use-the-autosizemode-property"></a><span data-ttu-id="bcc2f-180">使用 AutoSizeMode 属性</span><span class="sxs-lookup"><span data-stu-id="bcc2f-180">Use the AutoSizeMode property</span></span>

1. <span data-ttu-id="bcc2f-181">从 <xref:System.Windows.Forms.Panel> “工具箱” **将** 控件拖到你的窗体上。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-181">Drag a <xref:System.Windows.Forms.Panel> control from the **Toolbox** onto your form.</span></span>

2. <span data-ttu-id="bcc2f-182">将 <xref:System.Windows.Forms.Panel> 控件的 <xref:System.Windows.Forms.Control.AutoSize%2A> 属性的值设置为**true**。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-182">Set the value of the <xref:System.Windows.Forms.Panel> control's <xref:System.Windows.Forms.Control.AutoSize%2A> property to **true**.</span></span>

3. <span data-ttu-id="bcc2f-183">将 <xref:System.Windows.Forms.Button> 控件从**工具箱**拖动到 <xref:System.Windows.Forms.Panel> 控件中。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-183">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** into the <xref:System.Windows.Forms.Panel> control.</span></span>

4. <span data-ttu-id="bcc2f-184">将 <xref:System.Windows.Forms.Button> 控件放在 <xref:System.Windows.Forms.Panel> 控件右下角附近。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-184">Place the <xref:System.Windows.Forms.Button> control near the lower-right corner of the <xref:System.Windows.Forms.Panel> control.</span></span>

5. <span data-ttu-id="bcc2f-185">选择 "<xref:System.Windows.Forms.Panel>" 控件并抓住右下的大小调整控点。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-185">Select the <xref:System.Windows.Forms.Panel> control and grab the lower-right sizing handle.</span></span> <span data-ttu-id="bcc2f-186">将 <xref:System.Windows.Forms.Panel> 控件的大小调整为更大、更小。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-186">Resize the <xref:System.Windows.Forms.Panel> control to be larger and smaller.</span></span>

   > [!NOTE]
   > <span data-ttu-id="bcc2f-187">可以自由调整 <xref:System.Windows.Forms.Panel> 控件的大小，但不能将其大小调整为小于 <xref:System.Windows.Forms.Button> 控件右下角的位置。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-187">You can freely resize the <xref:System.Windows.Forms.Panel> control, but you cannot size it smaller than the position of the <xref:System.Windows.Forms.Button> control's lower-right corner.</span></span> <span data-ttu-id="bcc2f-188">此行为由 <xref:System.Windows.Forms.AutoSizeMode.GrowOnly>`AutoSizeMode` 属性的默认值指定。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-188">This behavior is specified by the default value of the `AutoSizeMode` property, which is <xref:System.Windows.Forms.AutoSizeMode.GrowOnly>.</span></span>

6. <span data-ttu-id="bcc2f-189">将 <xref:System.Windows.Forms.Panel> 控件的 `AutoSizeMode` 属性的值设置为 "<xref:System.Windows.Forms.AutoSizeMode.GrowAndShrink>"。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-189">Set the value of the <xref:System.Windows.Forms.Panel> control's `AutoSizeMode` property to <xref:System.Windows.Forms.AutoSizeMode.GrowAndShrink>.</span></span>

   <span data-ttu-id="bcc2f-190"><xref:System.Windows.Forms.Panel> 控件调整自身大小以包围 <xref:System.Windows.Forms.Button> 控件。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-190">The <xref:System.Windows.Forms.Panel> control sizes itself to surround the <xref:System.Windows.Forms.Button> control.</span></span> <span data-ttu-id="bcc2f-191">无法调整 <xref:System.Windows.Forms.Panel> 控件的大小。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-191">You cannot resize the <xref:System.Windows.Forms.Panel> control.</span></span>

7. <span data-ttu-id="bcc2f-192">将 <xref:System.Windows.Forms.Button> 控件拖向 <xref:System.Windows.Forms.Panel> 控件的左上角。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-192">Drag the <xref:System.Windows.Forms.Button> control toward the upper-left corner of the <xref:System.Windows.Forms.Panel> control.</span></span>

   <span data-ttu-id="bcc2f-193"><xref:System.Windows.Forms.Panel> 控件调整到 <xref:System.Windows.Forms.Button> 控件的新位置。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-193">The <xref:System.Windows.Forms.Panel> control resizes to the <xref:System.Windows.Forms.Button> control's new position.</span></span>

## <a name="next-steps"></a><span data-ttu-id="bcc2f-194">后续步骤</span><span class="sxs-lookup"><span data-stu-id="bcc2f-194">Next steps</span></span>

<span data-ttu-id="bcc2f-195">在 Windows 窗体应用程序中排列控件还有很多其他布局功能。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-195">There are many other layout features for arranging controls in your Windows Forms applications.</span></span> <span data-ttu-id="bcc2f-196">下面是可以尝试的一些组合：</span><span class="sxs-lookup"><span data-stu-id="bcc2f-196">Here are some combinations you might try:</span></span>

- <span data-ttu-id="bcc2f-197">使用 <xref:System.Windows.Forms.TableLayoutPanel> 控件生成窗体。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-197">Build a form using a <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span> <span data-ttu-id="bcc2f-198">有关详细信息，请参阅[演练：使用 TableLayoutPanel 排列 Windows 窗体上的控件](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-198">For details, see [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).</span></span> <span data-ttu-id="bcc2f-199">尝试更改 <xref:System.Windows.Forms.TableLayoutPanel> 控件的 <xref:System.Windows.Forms.Control.Padding%2A> 属性的值以及其子控件上的 <xref:System.Windows.Forms.Control.Margin%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-199">Try changing the values of the <xref:System.Windows.Forms.TableLayoutPanel> control's <xref:System.Windows.Forms.Control.Padding%2A> property, as well as the <xref:System.Windows.Forms.Control.Margin%2A> property on its child controls.</span></span>

- <span data-ttu-id="bcc2f-200">使用 <xref:System.Windows.Forms.FlowLayoutPanel> 控件尝试相同的试验。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-200">Try the same experiment using a <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span> <span data-ttu-id="bcc2f-201">有关详细信息，请参阅[演练：使用 FlowLayoutPanel 排列 Windows 窗体上的控件](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-201">For details, see [Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md).</span></span>

- <span data-ttu-id="bcc2f-202">尝试在 <xref:System.Windows.Forms.Panel> 控件中停靠子控件。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-202">Experiment with docking child controls in a <xref:System.Windows.Forms.Panel> control.</span></span> <span data-ttu-id="bcc2f-203"><xref:System.Windows.Forms.Control.Padding%2A> 属性是对 <xref:System.Windows.Forms.ScrollableControl.DockPadding%2A> 属性的更通用的实现，你可以通过将子控件置于 <xref:System.Windows.Forms.Panel> 控件中并将子控件的 <xref:System.Windows.Forms.Control.Dock%2A> 属性设置为 <xref:System.Windows.Forms.DockStyle.Fill>来满足这种情况。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-203">The <xref:System.Windows.Forms.Control.Padding%2A> property is a more general realization of the <xref:System.Windows.Forms.ScrollableControl.DockPadding%2A> property, and you can satisfy yourself that this is the case by putting a child control in a <xref:System.Windows.Forms.Panel> control and setting the child control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span> <span data-ttu-id="bcc2f-204">将 <xref:System.Windows.Forms.Panel> 控件的 <xref:System.Windows.Forms.Control.Padding%2A> 属性设置为不同的值，并记下该效果。</span><span class="sxs-lookup"><span data-stu-id="bcc2f-204">Set the <xref:System.Windows.Forms.Panel> control's <xref:System.Windows.Forms.Control.Padding%2A> property to various values and note the effect.</span></span>

## <a name="see-also"></a><span data-ttu-id="bcc2f-205">请参阅</span><span class="sxs-lookup"><span data-stu-id="bcc2f-205">See also</span></span>

- <xref:System.Windows.Forms.Control.AutoSize%2A>
- <xref:System.Windows.Forms.ScrollableControl.DockPadding%2A>
- <xref:System.Windows.Forms.Control.Margin%2A>
- <xref:System.Windows.Forms.Control.Padding%2A>
- [<span data-ttu-id="bcc2f-206">AutoSize 属性概述</span><span class="sxs-lookup"><span data-stu-id="bcc2f-206">AutoSize Property Overview</span></span>](autosize-property-overview.md)
- [<span data-ttu-id="bcc2f-207">演练：使用 TableLayoutPanel 在 Windows 窗体上排列控件</span><span class="sxs-lookup"><span data-stu-id="bcc2f-207">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [<span data-ttu-id="bcc2f-208">演练：使用 FlowLayoutPanel 在 Windows 窗体上排列控件</span><span class="sxs-lookup"><span data-stu-id="bcc2f-208">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [<span data-ttu-id="bcc2f-209">演练：使用对齐线在 Windows 窗体上排列控件</span><span class="sxs-lookup"><span data-stu-id="bcc2f-209">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
