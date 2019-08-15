---
title: 演练：使用对齐线在 Windows 窗体上排列控件
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], arranging with snaplines
- snaplines [Windows Forms], arranging Windows Forms controls
- SnapLine class [Windows Forms], walkthroughs
- Windows Forms controls, arranging
ms.assetid: d5c9edc7-cf30-4a97-8ebe-201d569340f8
ms.openlocfilehash: 3ce6c250fadbb56b341d5e8dec3a9cb9d28940fe
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040260"
---
# <a name="walkthrough-arranging-controls-on-windows-forms-using-snaplines"></a><span data-ttu-id="96c92-102">演练：使用对齐线在 Windows 窗体上排列控件</span><span class="sxs-lookup"><span data-stu-id="96c92-102">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>
<span data-ttu-id="96c92-103">在窗体上精确地放置控件对于许多应用程序而言是高优先级。</span><span class="sxs-lookup"><span data-stu-id="96c92-103">Precise placement of controls on your form is a high priority for many applications.</span></span> <span data-ttu-id="96c92-104">Windows 窗体设计器提供了许多布局工具来实现此目的。</span><span class="sxs-lookup"><span data-stu-id="96c92-104">The Windows Forms Designer gives you many layout tools to accomplish this.</span></span> <span data-ttu-id="96c92-105">最重要的一项是<xref:System.Windows.Forms.Design.Behavior.SnapLine>功能。</span><span class="sxs-lookup"><span data-stu-id="96c92-105">One of the most important is the <xref:System.Windows.Forms.Design.Behavior.SnapLine> feature.</span></span>

 <span data-ttu-id="96c92-106">对齐线可精确显示控件与其他控件的对齐位置。</span><span class="sxs-lookup"><span data-stu-id="96c92-106">Snaplines show you precisely where to line up controls with other controls.</span></span> <span data-ttu-id="96c92-107">它们还显示了建议的距离, 如 Windows 用户界面准则所指定。</span><span class="sxs-lookup"><span data-stu-id="96c92-107">They also show you the recommended distances for margins between controls, as specified by the Windows User Interface Guidelines.</span></span> <span data-ttu-id="96c92-108">有关详细信息, 请参阅[用户界面设计和开发](https://go.microsoft.com/FWLink/?LinkId=83878)。</span><span class="sxs-lookup"><span data-stu-id="96c92-108">For details, see [User Interface Design and Development](https://go.microsoft.com/FWLink/?LinkId=83878).</span></span>

 <span data-ttu-id="96c92-109">利用对齐线, 可以轻松地对齐控件, 实现简洁、专业的外观和行为 (外观)。</span><span class="sxs-lookup"><span data-stu-id="96c92-109">Snaplines make it easy to align your controls, for crisp, professional appearance and behavior (look and feel).</span></span>

 <span data-ttu-id="96c92-110">本演练涉及以下任务：</span><span class="sxs-lookup"><span data-stu-id="96c92-110">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="96c92-111">创建 Windows 窗体项目</span><span class="sxs-lookup"><span data-stu-id="96c92-111">Creating a Windows Forms project</span></span>

- <span data-ttu-id="96c92-112">使用对齐线的间距和对齐控件</span><span class="sxs-lookup"><span data-stu-id="96c92-112">Spacing and Aligning Controls Using Snaplines</span></span>

- <span data-ttu-id="96c92-113">对齐窗体和容器边距</span><span class="sxs-lookup"><span data-stu-id="96c92-113">Aligning to Form and Container Margins</span></span>

- <span data-ttu-id="96c92-114">对齐分组控件</span><span class="sxs-lookup"><span data-stu-id="96c92-114">Aligning to Grouped Controls</span></span>

- <span data-ttu-id="96c92-115">使用对齐线通过大纲显示控件</span><span class="sxs-lookup"><span data-stu-id="96c92-115">Using Snaplines to Place a Control by Outlining Its Size</span></span>

- <span data-ttu-id="96c92-116">从工具箱拖动控件时使用对齐线</span><span class="sxs-lookup"><span data-stu-id="96c92-116">Using Snaplines When Dragging a Control from the Toolbox</span></span>

- <span data-ttu-id="96c92-117">使用对齐线调整控件大小</span><span class="sxs-lookup"><span data-stu-id="96c92-117">Resizing Controls Using Snaplines</span></span>

- <span data-ttu-id="96c92-118">将标签与控件的文本对齐</span><span class="sxs-lookup"><span data-stu-id="96c92-118">Aligning a Label to a Control's Text</span></span>

- <span data-ttu-id="96c92-119">通过键盘导航使用对齐线</span><span class="sxs-lookup"><span data-stu-id="96c92-119">Using Snaplines with Keyboard Navigation</span></span>

- <span data-ttu-id="96c92-120">对齐线和布局面板</span><span class="sxs-lookup"><span data-stu-id="96c92-120">Snaplines and Layout Panels</span></span>

- <span data-ttu-id="96c92-121">禁用对齐线</span><span class="sxs-lookup"><span data-stu-id="96c92-121">Disabling Snaplines</span></span>

 <span data-ttu-id="96c92-122">完成后, 你将了解对齐线功能所扮演的布局角色。</span><span class="sxs-lookup"><span data-stu-id="96c92-122">When you are finished, you will have an understanding of the layout role played by the snaplines feature.</span></span>

## <a name="creating-the-project"></a><span data-ttu-id="96c92-123">创建项目</span><span class="sxs-lookup"><span data-stu-id="96c92-123">Creating the Project</span></span>
 <span data-ttu-id="96c92-124">第一步是创建项目并设置窗体。</span><span class="sxs-lookup"><span data-stu-id="96c92-124">The first step is to create the project and set up the form.</span></span>

### <a name="to-create-the-project"></a><span data-ttu-id="96c92-125">要创建项目</span><span class="sxs-lookup"><span data-stu-id="96c92-125">To create the project</span></span>

1. <span data-ttu-id="96c92-126">创建名为 "SnaplineExample" 的基于 Windows 的应用程序项目 (**文件** > **新** > **项目** > **视觉对象C#** 或经典**Visual Basic** > 桌面 > **Windows 窗体应用程序**)。</span><span class="sxs-lookup"><span data-stu-id="96c92-126">Create a Windows-based application project called "SnaplineExample" (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

2. <span data-ttu-id="96c92-127">在窗体设计器中选择窗体。</span><span class="sxs-lookup"><span data-stu-id="96c92-127">Select the form in the Forms Designer.</span></span>

## <a name="spacing-and-aligning-controls-using-snaplines"></a><span data-ttu-id="96c92-128">使用对齐线的间距和对齐控件</span><span class="sxs-lookup"><span data-stu-id="96c92-128">Spacing and Aligning Controls Using Snaplines</span></span>
 <span data-ttu-id="96c92-129">"对齐线" 为您显示窗体上控件的对齐方式。</span><span class="sxs-lookup"><span data-stu-id="96c92-129">Snaplines give you an accurate and intuitive way to align controls on your form.</span></span> <span data-ttu-id="96c92-130">当您将选定控件或控件移动到与另一个控件或控件集对齐的位置时, 它们将显示。</span><span class="sxs-lookup"><span data-stu-id="96c92-130">They appear when you are moving a selected control or controls near a position that would align with another control or set of controls.</span></span> <span data-ttu-id="96c92-131">在将其移到其他控件之后, 你的选择将 "对齐" 到建议的位置。</span><span class="sxs-lookup"><span data-stu-id="96c92-131">Your selection will "snap" to the suggested position as you move it past the other controls.</span></span>

### <a name="to-arrange-controls-using-snaplines"></a><span data-ttu-id="96c92-132">使用对齐线排列控件</span><span class="sxs-lookup"><span data-stu-id="96c92-132">To arrange controls using snaplines</span></span>

1. <span data-ttu-id="96c92-133">从 <xref:System.Windows.Forms.Button> “工具箱” **将** 控件拖到你的窗体上。</span><span class="sxs-lookup"><span data-stu-id="96c92-133">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto your form.</span></span>

2. <span data-ttu-id="96c92-134"><xref:System.Windows.Forms.Button>将控件移动到窗体的右下角。</span><span class="sxs-lookup"><span data-stu-id="96c92-134">Move the <xref:System.Windows.Forms.Button> control to the lower-right corner of the form.</span></span> <span data-ttu-id="96c92-135">请注意, 当<xref:System.Windows.Forms.Button>控件接近窗体的下边框和右边框时显示的对齐线。</span><span class="sxs-lookup"><span data-stu-id="96c92-135">Note the snaplines that appear as the <xref:System.Windows.Forms.Button> control approaches the bottom and right borders of the form.</span></span> <span data-ttu-id="96c92-136">这些对齐线显示控件边框与窗体边框之间的建议距离。</span><span class="sxs-lookup"><span data-stu-id="96c92-136">These snaplines display the recommended distance between the borders of the control and the form.</span></span>

3. <span data-ttu-id="96c92-137">围绕窗体的边框移动控件,并注意对齐线出现的位置。<xref:System.Windows.Forms.Button></span><span class="sxs-lookup"><span data-stu-id="96c92-137">Move the <xref:System.Windows.Forms.Button> control around the borders of the form and note where the snaplines appear.</span></span> <span data-ttu-id="96c92-138">完成后, 将<xref:System.Windows.Forms.Button>控件移动到窗体中心附近。</span><span class="sxs-lookup"><span data-stu-id="96c92-138">When you are finished, move the <xref:System.Windows.Forms.Button> control near the center of the form.</span></span>

4. <span data-ttu-id="96c92-139">将另<xref:System.Windows.Forms.Button>一个控件从**工具箱**拖到窗体上。</span><span class="sxs-lookup"><span data-stu-id="96c92-139">Drag another <xref:System.Windows.Forms.Button> control from the **Toolbox** onto your form.</span></span>

5. <span data-ttu-id="96c92-140">移动第二<xref:System.Windows.Forms.Button>个控件, 直到它接近第一个控件。</span><span class="sxs-lookup"><span data-stu-id="96c92-140">Move the second <xref:System.Windows.Forms.Button> control until it is nearly level with the first.</span></span> <span data-ttu-id="96c92-141">请注意, 在这两个按钮的文本基线上出现的对齐线, 并注意您正在移动的控件将对齐到与其他控件完全相同的位置。</span><span class="sxs-lookup"><span data-stu-id="96c92-141">Note the snapline that appears at the text baseline of both buttons, and note that the control you are moving snaps to a position that is exactly level with the other control.</span></span>

6. <span data-ttu-id="96c92-142">移动第二<xref:System.Windows.Forms.Button>个控件, 直到它直接位于第一个控件的上方。</span><span class="sxs-lookup"><span data-stu-id="96c92-142">Move the second <xref:System.Windows.Forms.Button> control until it is positioned directly above the first.</span></span> <span data-ttu-id="96c92-143">请注意在这两个按钮的左右边缘上出现的对齐线, 并注意您正在移动的控件将对齐到与其他控件完全对齐的位置。</span><span class="sxs-lookup"><span data-stu-id="96c92-143">Note the snaplines that appear along the left and right edges of both buttons, and note that the control you are moving snaps to a position that is exactly aligned with the other control.</span></span>

7. <span data-ttu-id="96c92-144">选择其中一个<xref:System.Windows.Forms.Button>控件, 并将其移动到另一个控件, 直到它们接近。</span><span class="sxs-lookup"><span data-stu-id="96c92-144">Select one of the <xref:System.Windows.Forms.Button> controls and move it close to the other, until they are almost touching.</span></span> <span data-ttu-id="96c92-145">请注意它们之间出现的对齐线。</span><span class="sxs-lookup"><span data-stu-id="96c92-145">Note the snapline that appears between them.</span></span> <span data-ttu-id="96c92-146">此距离是控件边框之间建议的距离。</span><span class="sxs-lookup"><span data-stu-id="96c92-146">This distance is the recommended distance between the borders of the controls.</span></span> <span data-ttu-id="96c92-147">另请注意, 正在移动的控件将对齐到此位置。</span><span class="sxs-lookup"><span data-stu-id="96c92-147">Also note that the control you are moving snaps to this position.</span></span>

8. <span data-ttu-id="96c92-148">将两<xref:System.Windows.Forms.Panel>个控件从**工具箱**拖到窗体上。</span><span class="sxs-lookup"><span data-stu-id="96c92-148">Drag two <xref:System.Windows.Forms.Panel> controls from the **Toolbox** onto your form.</span></span>

9. <span data-ttu-id="96c92-149">移动其中一个<xref:System.Windows.Forms.Panel>控件, 直到它接近于第一个控件。</span><span class="sxs-lookup"><span data-stu-id="96c92-149">Move one of the <xref:System.Windows.Forms.Panel> controls until it is nearly level with the first.</span></span> <span data-ttu-id="96c92-150">请注意沿两个控件的上边缘和下边缘显示的对齐线, 并注意您正在移动的控件对齐到与其他控件完全相同的位置。</span><span class="sxs-lookup"><span data-stu-id="96c92-150">Note the snaplines that appear along the top and bottom edges of both controls, and note that the control you are moving snaps to a position that is exactly level with the other control.</span></span>

## <a name="aligning-to-form-and-container-margins"></a><span data-ttu-id="96c92-151">对齐窗体和容器边距</span><span class="sxs-lookup"><span data-stu-id="96c92-151">Aligning to Form and Container Margins</span></span>
 <span data-ttu-id="96c92-152">对齐线有助于以一致的方式将控件与窗体和容器边距对齐。</span><span class="sxs-lookup"><span data-stu-id="96c92-152">Snaplines help you to align your controls to form and container margins in a consistent manner.</span></span>

### <a name="to-align-controls-to-form-and-container-margins"></a><span data-ttu-id="96c92-153">将控件与窗体和容器边距对齐</span><span class="sxs-lookup"><span data-stu-id="96c92-153">To align controls to form and container margins</span></span>

1. <span data-ttu-id="96c92-154">选择其中一个<xref:System.Windows.Forms.Button>控件, 并将其移动到窗体的右边框, 直到出现对齐线。</span><span class="sxs-lookup"><span data-stu-id="96c92-154">Select one of the <xref:System.Windows.Forms.Button> controls and move it close to the right border of the form until a snapline appears.</span></span> <span data-ttu-id="96c92-155">对齐线与右边框的距离是控件的<xref:System.Windows.Forms.Control.Margin%2A>属性和窗体的<xref:System.Windows.Forms.Control.Padding%2A>属性值之和。</span><span class="sxs-lookup"><span data-stu-id="96c92-155">The snapline's distance from the right border is the sum of the control's <xref:System.Windows.Forms.Control.Margin%2A> property and the form's <xref:System.Windows.Forms.Control.Padding%2A> property values.</span></span>

> [!NOTE]
>  <span data-ttu-id="96c92-156">如果窗体的<xref:System.Windows.Forms.Control.Padding%2A>属性设置为 0, 0, 0, 0, 则 Windows 窗体设计器为窗体提供一个阴影<xref:System.Windows.Forms.Control.Padding%2A>值9、9、9、9。</span><span class="sxs-lookup"><span data-stu-id="96c92-156">If the form's <xref:System.Windows.Forms.Control.Padding%2A> property is set to 0,0,0,0, the Windows Forms Designer gives the form a shadowed <xref:System.Windows.Forms.Control.Padding%2A> value of 9,9,9,9.</span></span> <span data-ttu-id="96c92-157">若要重写此行为, 请指定0、0、0、0以外的值。</span><span class="sxs-lookup"><span data-stu-id="96c92-157">To override this behavior, assign a value other than 0,0,0,0.</span></span>

1. <span data-ttu-id="96c92-158">通过在 "**属性**" <xref:System.Windows.Forms.Button>窗口中<xref:System.Windows.Forms.Control.Margin%2A>展开<xref:System.Windows.Forms.Control.Margin%2A> <xref:System.Windows.Forms.Padding.All%2A>条目并将属性设置为 0, 可更改控件的属性的值。</span><span class="sxs-lookup"><span data-stu-id="96c92-158">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Margin%2A> property by expanding the <xref:System.Windows.Forms.Control.Margin%2A> entry in the **Properties** window and setting the <xref:System.Windows.Forms.Padding.All%2A> property to 0.</span></span> <span data-ttu-id="96c92-159">有关详细信息, [请参阅演练:通过填充、边距和 AutoSize 属性](windows-forms-controls-padding-autosize.md)对 Windows 窗体控件进行布局。</span><span class="sxs-lookup"><span data-stu-id="96c92-159">For details, see [Walkthrough: Laying Out Windows Forms Controls with Padding, Margins, and the AutoSize Property](windows-forms-controls-padding-autosize.md).</span></span>

2. <span data-ttu-id="96c92-160"><xref:System.Windows.Forms.Button>将控件移动到窗体的右边框附近, 直到出现对齐线。</span><span class="sxs-lookup"><span data-stu-id="96c92-160">Move the <xref:System.Windows.Forms.Button> control close to the right border of the form until a snapline appears.</span></span> <span data-ttu-id="96c92-161">此距离现在由窗体的<xref:System.Windows.Forms.Control.Padding%2A>属性的值提供。</span><span class="sxs-lookup"><span data-stu-id="96c92-161">This distance is now given by the value of the form's <xref:System.Windows.Forms.Control.Padding%2A> property.</span></span>

3. <span data-ttu-id="96c92-162">从 <xref:System.Windows.Forms.GroupBox> “工具箱” **将** 控件拖到你的窗体上。</span><span class="sxs-lookup"><span data-stu-id="96c92-162">Drag a <xref:System.Windows.Forms.GroupBox> control from the **Toolbox** onto your form.</span></span>

4. <span data-ttu-id="96c92-163">通过在 "**属性**" <xref:System.Windows.Forms.GroupBox>窗口中<xref:System.Windows.Forms.Control.Padding%2A>展开<xref:System.Windows.Forms.Control.Padding%2A> <xref:System.Windows.Forms.Padding.All%2A>条目并将属性设置为 10, 来更改控件的属性的值。</span><span class="sxs-lookup"><span data-stu-id="96c92-163">Change the value of the <xref:System.Windows.Forms.GroupBox> control's <xref:System.Windows.Forms.Control.Padding%2A> property by expanding the <xref:System.Windows.Forms.Control.Padding%2A> entry in the **Properties** window and setting the <xref:System.Windows.Forms.Padding.All%2A> property to 10.</span></span>

5. <span data-ttu-id="96c92-164">将控件从 " <xref:System.Windows.Forms.GroupBox>工具箱" 拖放到控件中。 <xref:System.Windows.Forms.Button></span><span class="sxs-lookup"><span data-stu-id="96c92-164">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** into the <xref:System.Windows.Forms.GroupBox> control.</span></span>

6. <span data-ttu-id="96c92-165">将控件移动到<xref:System.Windows.Forms.GroupBox>控件的右边框附近, 直到出现对齐线。 <xref:System.Windows.Forms.Button></span><span class="sxs-lookup"><span data-stu-id="96c92-165">Move the <xref:System.Windows.Forms.Button> control close to the right border of the <xref:System.Windows.Forms.GroupBox> control until a snapline appears.</span></span> <span data-ttu-id="96c92-166">移动控件<xref:System.Windows.Forms.GroupBox>内的控件,并注意对齐线<xref:System.Windows.Forms.Button>出现的位置。</span><span class="sxs-lookup"><span data-stu-id="96c92-166">Move the <xref:System.Windows.Forms.Button> control within the <xref:System.Windows.Forms.GroupBox> control and note where the snaplines appear.</span></span>

## <a name="aligning-to-grouped-controls"></a><span data-ttu-id="96c92-167">对齐分组控件</span><span class="sxs-lookup"><span data-stu-id="96c92-167">Aligning to Grouped Controls</span></span>
 <span data-ttu-id="96c92-168">您可以使用对齐线对齐<xref:System.Windows.Forms.GroupBox>控件中的分组控件和控件。</span><span class="sxs-lookup"><span data-stu-id="96c92-168">You can use snaplines to align grouped controls as well as controls within a <xref:System.Windows.Forms.GroupBox> control.</span></span>

### <a name="to-align-to-grouped-controls"></a><span data-ttu-id="96c92-169">对齐分组控件</span><span class="sxs-lookup"><span data-stu-id="96c92-169">To align to grouped controls</span></span>

1. <span data-ttu-id="96c92-170">选择窗体上的两个控件。</span><span class="sxs-lookup"><span data-stu-id="96c92-170">Select two of the controls on your form.</span></span> <span data-ttu-id="96c92-171">移动所选内容, 并记下所选内容与其他控件之间出现的对齐线。</span><span class="sxs-lookup"><span data-stu-id="96c92-171">Move the selection around and note the snaplines that appear between your selection and the other controls.</span></span>

2. <span data-ttu-id="96c92-172">从 <xref:System.Windows.Forms.GroupBox> “工具箱” **将** 控件拖到你的窗体上。</span><span class="sxs-lookup"><span data-stu-id="96c92-172">Drag a <xref:System.Windows.Forms.GroupBox> control from the **Toolbox** onto your form.</span></span>

3. <span data-ttu-id="96c92-173">将控件从 " <xref:System.Windows.Forms.GroupBox>工具箱" 拖放到控件中。 <xref:System.Windows.Forms.Button></span><span class="sxs-lookup"><span data-stu-id="96c92-173">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** into the <xref:System.Windows.Forms.GroupBox> control.</span></span>

4. <span data-ttu-id="96c92-174">选择其中一个<xref:System.Windows.Forms.Button>控件, 并在<xref:System.Windows.Forms.GroupBox>控件上移动它。</span><span class="sxs-lookup"><span data-stu-id="96c92-174">Select one of the <xref:System.Windows.Forms.Button> controls and move it around the <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="96c92-175">请注意<xref:System.Windows.Forms.GroupBox>控件边缘上出现的对齐线。</span><span class="sxs-lookup"><span data-stu-id="96c92-175">Note the snaplines that appear at the edges of the <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="96c92-176">另请注意控件所包含<xref:System.Windows.Forms.Button> <xref:System.Windows.Forms.GroupBox>控件边缘上出现的对齐线。</span><span class="sxs-lookup"><span data-stu-id="96c92-176">Also note the snaplines that appear at the edges of the <xref:System.Windows.Forms.Button> control that is contained by the <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="96c92-177">容器控件的子级控件也支持对齐线。</span><span class="sxs-lookup"><span data-stu-id="96c92-177">Controls that are children of a container control also support snaplines.</span></span>

## <a name="using-snaplines-to-place-a-control-by-outlining-its-size"></a><span data-ttu-id="96c92-178">使用对齐线通过大纲显示控件</span><span class="sxs-lookup"><span data-stu-id="96c92-178">Using Snaplines to Place a Control by Outlining Its Size</span></span>
 <span data-ttu-id="96c92-179">当你首次将控件放置在窗体上时, 对齐线可帮助你对齐控件。</span><span class="sxs-lookup"><span data-stu-id="96c92-179">Snaplines help you align controls when you first place them on a form.</span></span>

### <a name="to-use-snaplines-to-place-a-control-by-outlining-its-size"></a><span data-ttu-id="96c92-180">通过勾画控件大小来使用对齐线放置控件</span><span class="sxs-lookup"><span data-stu-id="96c92-180">To use snaplines to place a control by outlining its size</span></span>

1. <span data-ttu-id="96c92-181">在“工具箱”中，单击 <xref:System.Windows.Forms.Button> 控件图标。</span><span class="sxs-lookup"><span data-stu-id="96c92-181">In the **Toolbox**, click the <xref:System.Windows.Forms.Button> control icon.</span></span> <span data-ttu-id="96c92-182">请勿将其拖到窗体上。</span><span class="sxs-lookup"><span data-stu-id="96c92-182">Do not drag it onto the form.</span></span>

2. <span data-ttu-id="96c92-183">将鼠标指针移动到窗体的设计图面上。</span><span class="sxs-lookup"><span data-stu-id="96c92-183">Move the mouse pointer over the form's design surface.</span></span> <span data-ttu-id="96c92-184">请注意，指针会更改为十字形，同时会附上 <xref:System.Windows.Forms.Button> 控件图标。</span><span class="sxs-lookup"><span data-stu-id="96c92-184">Note that the pointer changes to a crosshair with the <xref:System.Windows.Forms.Button> control icon attached.</span></span> <span data-ttu-id="96c92-185">另请注意为<xref:System.Windows.Forms.Button>控件建议对齐位置的对齐线。</span><span class="sxs-lookup"><span data-stu-id="96c92-185">Also note the snaplines that appear to suggest aligned positions for the <xref:System.Windows.Forms.Button> control.</span></span>

3. <span data-ttu-id="96c92-186">单击并按住鼠标按钮。</span><span class="sxs-lookup"><span data-stu-id="96c92-186">Click and hold the mouse button.</span></span>

4. <span data-ttu-id="96c92-187">在窗体上拖动鼠标指针。</span><span class="sxs-lookup"><span data-stu-id="96c92-187">Drag the mouse pointer around the form.</span></span> <span data-ttu-id="96c92-188">请注意, 会绘制一个轮廓, 指示控件的位置和大小。</span><span class="sxs-lookup"><span data-stu-id="96c92-188">Note that an outline is drawn, indicating the position and the size of the control.</span></span>

5. <span data-ttu-id="96c92-189">拖动指针, 直到它与窗体上的另一个控件对齐。</span><span class="sxs-lookup"><span data-stu-id="96c92-189">Drag the pointer until it aligns with another control on the form.</span></span> <span data-ttu-id="96c92-190">请注意, 将显示一条对齐线以指示对齐方式。</span><span class="sxs-lookup"><span data-stu-id="96c92-190">Note that a snapline appears to indicate alignment.</span></span>

6. <span data-ttu-id="96c92-191">释放鼠标按钮。</span><span class="sxs-lookup"><span data-stu-id="96c92-191">Release the mouse button.</span></span> <span data-ttu-id="96c92-192">控件在由轮廓指示的位置和大小创建。</span><span class="sxs-lookup"><span data-stu-id="96c92-192">The control is created at the position and size indicated by the outline.</span></span>

## <a name="using-snaplines-when-dragging-a-control-from-the-toolbox"></a><span data-ttu-id="96c92-193">从工具箱拖动控件时使用对齐线</span><span class="sxs-lookup"><span data-stu-id="96c92-193">Using Snaplines When Dragging a Control from the Toolbox</span></span>
 <span data-ttu-id="96c92-194">当你将控件从 "**工具箱**" 拖到窗体上时, 对齐线可帮助你对齐控件。</span><span class="sxs-lookup"><span data-stu-id="96c92-194">Snaplines help you align controls when you drag them from the **Toolbox** onto your form.</span></span>

### <a name="to-use-snaplines-when-dragging-a-control-from-the-toolbox"></a><span data-ttu-id="96c92-195">从工具箱拖动控件时使用对齐线</span><span class="sxs-lookup"><span data-stu-id="96c92-195">To use snaplines when dragging a control from the Toolbox</span></span>

1. <span data-ttu-id="96c92-196">将控件从 "工具箱" 拖到窗体上, 但不释放鼠标按钮。 <xref:System.Windows.Forms.Button></span><span class="sxs-lookup"><span data-stu-id="96c92-196">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto your form, but do not release the mouse button.</span></span>

2. <span data-ttu-id="96c92-197">将鼠标指针移动到窗体的设计图面上。</span><span class="sxs-lookup"><span data-stu-id="96c92-197">Move the mouse pointer over the form's design surface.</span></span> <span data-ttu-id="96c92-198">请注意, 指针会更改以指示将创建新<xref:System.Windows.Forms.Button>控件的位置。</span><span class="sxs-lookup"><span data-stu-id="96c92-198">Note that the pointer changes to indicate the position at which the new <xref:System.Windows.Forms.Button> control will be created.</span></span>

3. <span data-ttu-id="96c92-199">在窗体上拖动鼠标指针。</span><span class="sxs-lookup"><span data-stu-id="96c92-199">Drag the mouse pointer around the form.</span></span> <span data-ttu-id="96c92-200">请注意显示的对齐线, 用于建议<xref:System.Windows.Forms.Button>控件的对齐位置。</span><span class="sxs-lookup"><span data-stu-id="96c92-200">Note the snaplines that appear to suggest aligned positions for the <xref:System.Windows.Forms.Button> control.</span></span> <span data-ttu-id="96c92-201">查找与其他控件对齐的位置。</span><span class="sxs-lookup"><span data-stu-id="96c92-201">Find a position that is aligned with other controls.</span></span>

4. <span data-ttu-id="96c92-202">释放鼠标按钮。</span><span class="sxs-lookup"><span data-stu-id="96c92-202">Release the mouse button.</span></span> <span data-ttu-id="96c92-203">控件将在对齐线指示的位置创建。</span><span class="sxs-lookup"><span data-stu-id="96c92-203">The control is created at the position indicated by the snaplines.</span></span>

## <a name="resizing-controls-using-snaplines"></a><span data-ttu-id="96c92-204">使用对齐线调整控件大小</span><span class="sxs-lookup"><span data-stu-id="96c92-204">Resizing Controls Using Snaplines</span></span>
 <span data-ttu-id="96c92-205">对齐线有助于调整控件的大小。</span><span class="sxs-lookup"><span data-stu-id="96c92-205">Snaplines help you align controls as you resize them.</span></span>

### <a name="to-resize-a-control-using-snaplines"></a><span data-ttu-id="96c92-206">使用对齐线调整控件大小</span><span class="sxs-lookup"><span data-stu-id="96c92-206">To resize a control using snaplines</span></span>

1. <span data-ttu-id="96c92-207">从 <xref:System.Windows.Forms.Button> “工具箱” **将** 控件拖到你的窗体上。</span><span class="sxs-lookup"><span data-stu-id="96c92-207">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto your form.</span></span>

2. <span data-ttu-id="96c92-208">通过获取一个角大小调整控点并拖动来调整控件的大小。<xref:System.Windows.Forms.Button></span><span class="sxs-lookup"><span data-stu-id="96c92-208">Resize the <xref:System.Windows.Forms.Button> control by grabbing one of the corner sizing handles and dragging.</span></span> <span data-ttu-id="96c92-209">有关详细信息，请参阅[如何：Windows 窗体](how-to-resize-controls-on-windows-forms.md)上的调整控件大小。</span><span class="sxs-lookup"><span data-stu-id="96c92-209">For details, see [How to: Resize Controls on Windows Forms](how-to-resize-controls-on-windows-forms.md).</span></span>

3. <span data-ttu-id="96c92-210">拖动调整大小控点, 直到其中<xref:System.Windows.Forms.Button>一个控件的边框与另一个控件对齐。</span><span class="sxs-lookup"><span data-stu-id="96c92-210">Drag the sizing handle until one of the <xref:System.Windows.Forms.Button> control's borders is aligned with another control.</span></span> <span data-ttu-id="96c92-211">请注意, 会显示对齐线。</span><span class="sxs-lookup"><span data-stu-id="96c92-211">Note that a snapline appears.</span></span> <span data-ttu-id="96c92-212">另请注意, 大小调整控点与对齐线指示的位置对齐。</span><span class="sxs-lookup"><span data-stu-id="96c92-212">Also note that the sizing handle snaps to the position indicated by the snapline.</span></span>

4. <span data-ttu-id="96c92-213">按不同方向调整控件大小,并将大小调整控点与不同控件对齐。<xref:System.Windows.Forms.Button></span><span class="sxs-lookup"><span data-stu-id="96c92-213">Resize the <xref:System.Windows.Forms.Button> control in different directions and align the sizing handle to different controls.</span></span> <span data-ttu-id="96c92-214">请注意对齐线如何出现在各种方向上以指示对齐方式。</span><span class="sxs-lookup"><span data-stu-id="96c92-214">Note how the snaplines appear in various orientations to indicate alignment.</span></span>

## <a name="aligning-a-label-to-a-controls-text"></a><span data-ttu-id="96c92-215">将标签与控件的文本对齐</span><span class="sxs-lookup"><span data-stu-id="96c92-215">Aligning a Label to a Control's Text</span></span>
 <span data-ttu-id="96c92-216">某些控件提供了用于将其他控件对齐到显示文本的对齐线。</span><span class="sxs-lookup"><span data-stu-id="96c92-216">Some controls offer a snapline for aligning other controls to displayed text.</span></span>

### <a name="to-align-a-label-to-a-controls-text"></a><span data-ttu-id="96c92-217">将标签与控件的文本对齐</span><span class="sxs-lookup"><span data-stu-id="96c92-217">To align a label to a control's text</span></span>

1. <span data-ttu-id="96c92-218">从 <xref:System.Windows.Forms.TextBox> “工具箱” **将** 控件拖到你的窗体上。</span><span class="sxs-lookup"><span data-stu-id="96c92-218">Drag a <xref:System.Windows.Forms.TextBox> control from the **Toolbox** onto your form.</span></span> <span data-ttu-id="96c92-219">将<xref:System.Windows.Forms.TextBox>控件放到窗体上时, 单击智能标记标志符号, 然后选择 "**将文本设置为 textBox1** " 选项。</span><span class="sxs-lookup"><span data-stu-id="96c92-219">When you drop the <xref:System.Windows.Forms.TextBox> control onto the form, click the smart-tag glyph and select the **Set text to textBox1** option.</span></span> <span data-ttu-id="96c92-220">有关详细信息, [请参阅演练:使用 Windows 窗体控件](performing-common-tasks-using-smart-tags-on-wf-controls.md)上的智能标记执行常见任务。</span><span class="sxs-lookup"><span data-stu-id="96c92-220">For details, see [Walkthrough: Performing Common Tasks Using Smart Tags on Windows Forms Controls](performing-common-tasks-using-smart-tags-on-wf-controls.md).</span></span>

2. <span data-ttu-id="96c92-221">从 <xref:System.Windows.Forms.Label> “工具箱” **将** 控件拖到你的窗体上。</span><span class="sxs-lookup"><span data-stu-id="96c92-221">Drag a <xref:System.Windows.Forms.Label> control from the **Toolbox** onto your form.</span></span>

3. <span data-ttu-id="96c92-222">将 <xref:System.Windows.Forms.Label> 控件的 <xref:System.Windows.Forms.Control.AutoSize%2A> 属性值更改为 `true`。</span><span class="sxs-lookup"><span data-stu-id="96c92-222">Change the value of the <xref:System.Windows.Forms.Label> control's <xref:System.Windows.Forms.Control.AutoSize%2A> property to `true`.</span></span> <span data-ttu-id="96c92-223">请注意, 控件的边框会调整以适应显示文本。</span><span class="sxs-lookup"><span data-stu-id="96c92-223">Note that the control's borders are adjusted to fit the display text.</span></span>

4. <span data-ttu-id="96c92-224">将控件移动到<xref:System.Windows.Forms.TextBox>控件的左侧, 使其与<xref:System.Windows.Forms.TextBox>控件的下边缘对齐。 <xref:System.Windows.Forms.Label></span><span class="sxs-lookup"><span data-stu-id="96c92-224">Move the <xref:System.Windows.Forms.Label> control to the left of the <xref:System.Windows.Forms.TextBox> control, so it is aligned with the bottom edge of the <xref:System.Windows.Forms.TextBox> control.</span></span> <span data-ttu-id="96c92-225">请注意在两个控件的下边缘显示的对齐线。</span><span class="sxs-lookup"><span data-stu-id="96c92-225">Note the snapline that appears along the bottom edges of the two controls.</span></span>

5. <span data-ttu-id="96c92-226">稍微向上移动<xref:System.Windows.Forms.Label> <xref:System.Windows.Forms.TextBox>控件, 直到文本和文本对齐。 <xref:System.Windows.Forms.Label></span><span class="sxs-lookup"><span data-stu-id="96c92-226">Move the <xref:System.Windows.Forms.Label> control slightly upward, until the <xref:System.Windows.Forms.Label> text and the <xref:System.Windows.Forms.TextBox> text are aligned.</span></span> <span data-ttu-id="96c92-227">请注意显示的样式不同的对齐线, 指示两个控件的文本字段对齐的时间。</span><span class="sxs-lookup"><span data-stu-id="96c92-227">Note the differently styled snapline that appears, indicating when the text fields of both controls are aligned.</span></span>

## <a name="using-snaplines-with-keyboard-navigation"></a><span data-ttu-id="96c92-228">通过键盘导航使用对齐线</span><span class="sxs-lookup"><span data-stu-id="96c92-228">Using Snaplines with Keyboard Navigation</span></span>
 <span data-ttu-id="96c92-229">当使用键盘的箭头键排列控件时, 对齐线可帮助您对齐控件。</span><span class="sxs-lookup"><span data-stu-id="96c92-229">Snaplines help you align controls when you are arranging them using the keyboard's arrow keys.</span></span>

### <a name="to-use-snaplines-with-keyboard-navigation"></a><span data-ttu-id="96c92-230">将对齐线用于键盘导航</span><span class="sxs-lookup"><span data-stu-id="96c92-230">To use snaplines with keyboard navigation</span></span>

1. <span data-ttu-id="96c92-231">从 <xref:System.Windows.Forms.Button> “工具箱” **将** 控件拖到你的窗体上。</span><span class="sxs-lookup"><span data-stu-id="96c92-231">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto your form.</span></span> <span data-ttu-id="96c92-232">将其放在窗体的左上角。</span><span class="sxs-lookup"><span data-stu-id="96c92-232">Place it in the upper-left corner of the form.</span></span>

2. <span data-ttu-id="96c92-233">按 CTRL + 向下键。</span><span class="sxs-lookup"><span data-stu-id="96c92-233">Press CTRL+DOWN ARROW.</span></span> <span data-ttu-id="96c92-234">请注意, 控件向下移动到第一个可用的水平对齐位置。</span><span class="sxs-lookup"><span data-stu-id="96c92-234">Note that the control moves down the form to the first available horizontal alignment position.</span></span>

3. <span data-ttu-id="96c92-235">按 CTRL + 向下键, 直到控件到达窗体的底部。</span><span class="sxs-lookup"><span data-stu-id="96c92-235">Press CTRL+DOWN ARROW until the control reaches the bottom of the form.</span></span> <span data-ttu-id="96c92-236">请注意, 它在窗体中向下移动时所占据的位置。</span><span class="sxs-lookup"><span data-stu-id="96c92-236">Note the positions it occupies as it moves down the form.</span></span>

4. <span data-ttu-id="96c92-237">按 CTRL + 向右键。</span><span class="sxs-lookup"><span data-stu-id="96c92-237">Press CTRL+RIGHT ARROW.</span></span> <span data-ttu-id="96c92-238">请注意, 控件在窗体上移动到第一个可用的垂直对齐位置。</span><span class="sxs-lookup"><span data-stu-id="96c92-238">Note that the control moves across the form to the first available vertical alignment position.</span></span>

5. <span data-ttu-id="96c92-239">按 CTRL + 向右键直到控件到达窗体的一侧。</span><span class="sxs-lookup"><span data-stu-id="96c92-239">Press CTRL+RIGHT ARROW until the control reaches the side of the form.</span></span> <span data-ttu-id="96c92-240">请注意, 它在窗体中移动时所占据的位置。</span><span class="sxs-lookup"><span data-stu-id="96c92-240">Note the positions it occupies as it moves across the form.</span></span>

6. <span data-ttu-id="96c92-241">使用箭头键的组合在窗体周围移动控件。</span><span class="sxs-lookup"><span data-stu-id="96c92-241">Move the control around the form with a combination of arrow keys.</span></span> <span data-ttu-id="96c92-242">请注意控件占据的位置以及伴随控件的对齐线。</span><span class="sxs-lookup"><span data-stu-id="96c92-242">Note the positions the control occupies and the snaplines that accompany them.</span></span>

7. <span data-ttu-id="96c92-243">按 SHIFT + 任意箭头键可按一个<xref:System.Windows.Forms.Button>像素的增量调整控件的大小。</span><span class="sxs-lookup"><span data-stu-id="96c92-243">Press SHIFT+any arrow key to resize the <xref:System.Windows.Forms.Button> control by increments of one pixel.</span></span>

8. <span data-ttu-id="96c92-244">按 CTRL + SHIFT + 任意箭头键可在对齐<xref:System.Windows.Forms.Button>线增量中调整控件的大小。</span><span class="sxs-lookup"><span data-stu-id="96c92-244">Press CTRL+SHIFT+any arrow key to resize the <xref:System.Windows.Forms.Button> control in snapline increments.</span></span>

## <a name="snaplines-and-layout-panels"></a><span data-ttu-id="96c92-245">对齐线和布局面板</span><span class="sxs-lookup"><span data-stu-id="96c92-245">Snaplines and Layout Panels</span></span>
 <span data-ttu-id="96c92-246">布局面板中已禁用对齐线。</span><span class="sxs-lookup"><span data-stu-id="96c92-246">Snaplines are disabled within layout panels.</span></span>

### <a name="to-selectively-disable-snaplines"></a><span data-ttu-id="96c92-247">有选择地禁用对齐线</span><span class="sxs-lookup"><span data-stu-id="96c92-247">To selectively disable snaplines</span></span>

1. <span data-ttu-id="96c92-248">从 <xref:System.Windows.Forms.TableLayoutPanel> “工具箱” **将** 控件拖到你的窗体上。</span><span class="sxs-lookup"><span data-stu-id="96c92-248">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>

2. <span data-ttu-id="96c92-249">在“工具箱” <xref:System.Windows.Forms.Button>**中，双击**控件图标。</span><span class="sxs-lookup"><span data-stu-id="96c92-249">Double-click the <xref:System.Windows.Forms.Button> control icon in the **Toolbox**.</span></span> <span data-ttu-id="96c92-250">请注意, 新的按钮控件出现在<xref:System.Windows.Forms.TableLayoutPanel>控件的第一个单元格中。</span><span class="sxs-lookup"><span data-stu-id="96c92-250">Note that a new button control appears in the <xref:System.Windows.Forms.TableLayoutPanel> control's first cell.</span></span>

3. <span data-ttu-id="96c92-251">再次双击**工具箱**中<xref:System.Windows.Forms.Button>的控件图标。</span><span class="sxs-lookup"><span data-stu-id="96c92-251">Double-click the <xref:System.Windows.Forms.Button> control icon in the **Toolbox** twice more.</span></span> <span data-ttu-id="96c92-252">这会在<xref:System.Windows.Forms.TableLayoutPanel>控件中保留一个空单元。</span><span class="sxs-lookup"><span data-stu-id="96c92-252">This leaves one empty cell in the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

4. <span data-ttu-id="96c92-253">将控件从 "**工具箱**" 拖到<xref:System.Windows.Forms.TableLayoutPanel>控件的空单元中。 <xref:System.Windows.Forms.Button></span><span class="sxs-lookup"><span data-stu-id="96c92-253">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** into the empty cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span> <span data-ttu-id="96c92-254">请注意, 不会显示对齐线。</span><span class="sxs-lookup"><span data-stu-id="96c92-254">Note that no snaplines appear.</span></span>

5. <span data-ttu-id="96c92-255">将控件拖出<xref:System.Windows.Forms.TableLayoutPanel>控件<xref:System.Windows.Forms.TableLayoutPanel> , 并将其移动到控件上。 <xref:System.Windows.Forms.Button></span><span class="sxs-lookup"><span data-stu-id="96c92-255">Drag the <xref:System.Windows.Forms.Button> control out of the <xref:System.Windows.Forms.TableLayoutPanel> control and move it around the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span> <span data-ttu-id="96c92-256">请注意, 对齐线将再次出现。</span><span class="sxs-lookup"><span data-stu-id="96c92-256">Note that snaplines appear again.</span></span>

## <a name="disabling-snaplines"></a><span data-ttu-id="96c92-257">禁用对齐线</span><span class="sxs-lookup"><span data-stu-id="96c92-257">Disabling Snaplines</span></span>
 <span data-ttu-id="96c92-258">默认情况下, 对齐线已打开。</span><span class="sxs-lookup"><span data-stu-id="96c92-258">Snaplines are turned on by default.</span></span> <span data-ttu-id="96c92-259">您可以有选择地禁用对齐线, 也可以在设计环境中禁用它。</span><span class="sxs-lookup"><span data-stu-id="96c92-259">You can disable snaplines selectively, or you can disable them in the design environment.</span></span>

### <a name="to-selectively-disable-snaplines"></a><span data-ttu-id="96c92-260">有选择地禁用对齐线</span><span class="sxs-lookup"><span data-stu-id="96c92-260">To selectively disable snaplines</span></span>

- <span data-ttu-id="96c92-261">按 ALT 键, 同时在窗体中移动控件。</span><span class="sxs-lookup"><span data-stu-id="96c92-261">Press the ALT key and while moving a control around the form.</span></span>

     <span data-ttu-id="96c92-262">请注意, 不会显示对齐线, 并且控件不会与任何可能的对齐位置对齐。</span><span class="sxs-lookup"><span data-stu-id="96c92-262">Note that no snaplines appear and the control does not snap to any potential alignment positions.</span></span>

### <a name="to-disable-snaplines-in-the-design-environment"></a><span data-ttu-id="96c92-263">禁用设计环境中的对齐线</span><span class="sxs-lookup"><span data-stu-id="96c92-263">To disable snaplines in the design environment</span></span>

1. <span data-ttu-id="96c92-264">从 "**工具**" 菜单中, 打开 "**选项**" 对话框。</span><span class="sxs-lookup"><span data-stu-id="96c92-264">From the **Tools** menu, open the **Options** dialog box.</span></span> <span data-ttu-id="96c92-265">打开 "Windows 窗体设计器" 对话框。</span><span class="sxs-lookup"><span data-stu-id="96c92-265">Open the Windows Forms Designer dialog box.</span></span> <span data-ttu-id="96c92-266">有关详细信息, 请参阅[常规、Windows 窗体设计器、"选项" 对话框](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/5aazxs78(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="96c92-266">For details, see [General, Windows Forms Designer, Options Dialog Box](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/5aazxs78(v=vs.100)).</span></span>

2. <span data-ttu-id="96c92-267">选择 "**常规**" 节点。</span><span class="sxs-lookup"><span data-stu-id="96c92-267">Select the **General** node.</span></span> <span data-ttu-id="96c92-268">在 "**布局模式**" 部分中, 将所选内容从**对齐线**更改为 "**对齐**"。</span><span class="sxs-lookup"><span data-stu-id="96c92-268">In the **Layout Mode** section, change the selection from **SnapLines** to **SnapToGrid**.</span></span>

3. <span data-ttu-id="96c92-269">单击 "确定" 以应用设置。</span><span class="sxs-lookup"><span data-stu-id="96c92-269">Click OK to apply the setting.</span></span>

4. <span data-ttu-id="96c92-270">选择窗体上的控件, 并将其移动到其他控件上。</span><span class="sxs-lookup"><span data-stu-id="96c92-270">Select a control on your form and move it around the other controls.</span></span> <span data-ttu-id="96c92-271">请注意, 不会显示对齐线。</span><span class="sxs-lookup"><span data-stu-id="96c92-271">Note that snaplines do not appear.</span></span>

## <a name="next-steps"></a><span data-ttu-id="96c92-272">后续步骤</span><span class="sxs-lookup"><span data-stu-id="96c92-272">Next Steps</span></span>
 <span data-ttu-id="96c92-273">对齐线提供了在窗体上对齐控件的直观方式。</span><span class="sxs-lookup"><span data-stu-id="96c92-273">Snaplines offer an intuitive means of aligning controls on your form.</span></span> <span data-ttu-id="96c92-274">有关进一步探索的建议包括：</span><span class="sxs-lookup"><span data-stu-id="96c92-274">Suggestions for more exploration include:</span></span>

- <span data-ttu-id="96c92-275">尝试将<xref:System.Windows.Forms.GroupBox>控件嵌套在另<xref:System.Windows.Forms.GroupBox>一个控件中。</span><span class="sxs-lookup"><span data-stu-id="96c92-275">Try nesting a <xref:System.Windows.Forms.GroupBox> control within another <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="96c92-276">将控件置于子<xref:System.Windows.Forms.GroupBox>控件内, 并将其放在父<xref:System.Windows.Forms.GroupBox>控件中。 <xref:System.Windows.Forms.Button></span><span class="sxs-lookup"><span data-stu-id="96c92-276">Place a <xref:System.Windows.Forms.Button> control within the child <xref:System.Windows.Forms.GroupBox> control, and another within the parent <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="96c92-277"><xref:System.Windows.Forms.Button>移动控件以查看对齐线跨容器边界的方式。</span><span class="sxs-lookup"><span data-stu-id="96c92-277">Move the <xref:System.Windows.Forms.Button> controls around to see how the snaplines cross container boundaries.</span></span>

- <span data-ttu-id="96c92-278">创建列<xref:System.Windows.Forms.TextBox>控件和相应的<xref:System.Windows.Forms.Label>控件列。</span><span class="sxs-lookup"><span data-stu-id="96c92-278">Create a column of <xref:System.Windows.Forms.TextBox> controls and a corresponding column of <xref:System.Windows.Forms.Label> controls.</span></span> <span data-ttu-id="96c92-279">将<xref:System.Windows.Forms.Label> `true`控件的属性值设置为。 <xref:System.Windows.Forms.Control.AutoSize%2A></span><span class="sxs-lookup"><span data-stu-id="96c92-279">Set the value of the <xref:System.Windows.Forms.Label> controls' <xref:System.Windows.Forms.Control.AutoSize%2A> property to `true`.</span></span> <span data-ttu-id="96c92-280">使用对齐线移动<xref:System.Windows.Forms.Label>控件, 使其显示的文本与<xref:System.Windows.Forms.TextBox>控件中的文本对齐。</span><span class="sxs-lookup"><span data-stu-id="96c92-280">Use snaplines to move the <xref:System.Windows.Forms.Label> controls so their displayed text is aligned with the text in the <xref:System.Windows.Forms.TextBox> controls.</span></span>

 <span data-ttu-id="96c92-281">有关 Windows 用户界面设计的信息, 请参阅*Microsoft Windows 用户体验, Microsoft Windows 用户体验, 用户界面开发人员和设计人员的官方准则*, 华盛顿州:微软出版社, 1999。</span><span class="sxs-lookup"><span data-stu-id="96c92-281">For information about Windows user interface design, see the book *Microsoft Windows User Experience, Official Guidelines for User Interface Developers and Designers* Redmond, WA: Microsoft Press, 1999.</span></span> <span data-ttu-id="96c92-282">(USBN:0-7356-0566-1)。</span><span class="sxs-lookup"><span data-stu-id="96c92-282">(USBN: 0-7356-0566-1).</span></span>

## <a name="see-also"></a><span data-ttu-id="96c92-283">请参阅</span><span class="sxs-lookup"><span data-stu-id="96c92-283">See also</span></span>

- <xref:System.Windows.Forms.Design.Behavior.SnapLine>
- [<span data-ttu-id="96c92-284">演练：使用 FlowLayoutPanel 排列 Windows 窗体上的控件</span><span class="sxs-lookup"><span data-stu-id="96c92-284">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [<span data-ttu-id="96c92-285">演练：使用 TableLayoutPanel 排列 Windows 窗体上的控件</span><span class="sxs-lookup"><span data-stu-id="96c92-285">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [<span data-ttu-id="96c92-286">演练：通过填充、边距和 AutoSize 属性排放 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="96c92-286">Walkthrough: Laying Out Windows Forms Controls with Padding, Margins, and the AutoSize Property</span></span>](windows-forms-controls-padding-autosize.md)
- [<span data-ttu-id="96c92-287">在 Windows 窗体上排列控件</span><span class="sxs-lookup"><span data-stu-id="96c92-287">Arranging Controls on Windows Forms</span></span>](arranging-controls-on-windows-forms.md)
