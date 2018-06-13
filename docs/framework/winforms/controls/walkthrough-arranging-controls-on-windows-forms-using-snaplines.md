---
title: 演练：使用对齐线在 Windows 窗体上排列控件
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], arranging with snaplines
- snaplines [Windows Forms], arranging Windows Forms controls
- SnapLine class [Windows Forms], walkthroughs
- Windows Forms controls, arranging
ms.assetid: d5c9edc7-cf30-4a97-8ebe-201d569340f8
ms.openlocfilehash: f8e8122f82bc6a8c4fab17b8b73c07d08bab4d26
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33541585"
---
# <a name="walkthrough-arranging-controls-on-windows-forms-using-snaplines"></a><span data-ttu-id="ff2b3-102">演练：使用对齐线在 Windows 窗体上排列控件</span><span class="sxs-lookup"><span data-stu-id="ff2b3-102">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>
<span data-ttu-id="ff2b3-103">在窗体上精确地放置控件对于许多应用程序而言是高优先级。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-103">Precise placement of controls on your form is a high priority for many applications.</span></span> <span data-ttu-id="ff2b3-104">Windows 窗体设计器为你提供许多布局工具实现此目的。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-104">The Windows Forms Designer gives you many layout tools to accomplish this.</span></span> <span data-ttu-id="ff2b3-105">最重要之一是<xref:System.Windows.Forms.Design.Behavior.SnapLine>功能。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-105">One of the most important is the <xref:System.Windows.Forms.Design.Behavior.SnapLine> feature.</span></span>  
  
 <span data-ttu-id="ff2b3-106">对齐线显示确切位置与其他控件的控件对齐。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-106">Snaplines show you precisely where to line up controls with other controls.</span></span> <span data-ttu-id="ff2b3-107">它们还显示你的控件，为指定的 Windows 用户界面指南之间的边距的建议的距离。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-107">They also show you the recommended distances for margins between controls, as specified by the Windows User Interface Guidelines.</span></span> <span data-ttu-id="ff2b3-108">有关详细信息，请参阅[用户界面设计和开发](http://go.microsoft.com/FWLink/?LinkId=83878)。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-108">For details, see [User Interface Design and Development](http://go.microsoft.com/FWLink/?LinkId=83878).</span></span>  
  
 <span data-ttu-id="ff2b3-109">对齐线可以方便轻松地对齐您控件，获得简洁、 专业外观和行为 （外观和感觉）。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-109">Snaplines make it easy to align your controls, for crisp, professional appearance and behavior (look and feel).</span></span>  
  
 <span data-ttu-id="ff2b3-110">本演练涉及以下任务：</span><span class="sxs-lookup"><span data-stu-id="ff2b3-110">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="ff2b3-111">创建 Windows 窗体项目</span><span class="sxs-lookup"><span data-stu-id="ff2b3-111">Creating a Windows Forms project</span></span>  
  
-   <span data-ttu-id="ff2b3-112">间距和对齐控件使用对齐线</span><span class="sxs-lookup"><span data-stu-id="ff2b3-112">Spacing and Aligning Controls Using Snaplines</span></span>  
  
-   <span data-ttu-id="ff2b3-113">到窗体和容器的边缘对齐</span><span class="sxs-lookup"><span data-stu-id="ff2b3-113">Aligning to Form and Container Margins</span></span>  
  
-   <span data-ttu-id="ff2b3-114">对齐到分组后的控件</span><span class="sxs-lookup"><span data-stu-id="ff2b3-114">Aligning to Grouped Controls</span></span>  
  
-   <span data-ttu-id="ff2b3-115">使用对齐线通过勾画放置控件</span><span class="sxs-lookup"><span data-stu-id="ff2b3-115">Using Snaplines to Place a Control by Outlining Its Size</span></span>  
  
-   <span data-ttu-id="ff2b3-116">从工具箱中拖动控件时使用对齐线</span><span class="sxs-lookup"><span data-stu-id="ff2b3-116">Using Snaplines When Dragging a Control from the Toolbox</span></span>  
  
-   <span data-ttu-id="ff2b3-117">使用对齐线的大小调整控件</span><span class="sxs-lookup"><span data-stu-id="ff2b3-117">Resizing Controls Using Snaplines</span></span>  
  
-   <span data-ttu-id="ff2b3-118">对齐标签与控件的文本</span><span class="sxs-lookup"><span data-stu-id="ff2b3-118">Aligning a Label to a Control's Text</span></span>  
  
-   <span data-ttu-id="ff2b3-119">使用键盘导航线对齐</span><span class="sxs-lookup"><span data-stu-id="ff2b3-119">Using Snaplines with Keyboard Navigation</span></span>  
  
-   <span data-ttu-id="ff2b3-120">对齐线和布局面板</span><span class="sxs-lookup"><span data-stu-id="ff2b3-120">Snaplines and Layout Panels</span></span>  
  
-   <span data-ttu-id="ff2b3-121">禁用对齐线</span><span class="sxs-lookup"><span data-stu-id="ff2b3-121">Disabling Snaplines</span></span>  
  
 <span data-ttu-id="ff2b3-122">完成后，将会对齐线功能所发挥的布局作用的了解。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-122">When you are finished, you will have an understanding of the layout role played by the snaplines feature.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ff2b3-123">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-123">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="ff2b3-124">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-124">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="ff2b3-125">有关详细信息，请参阅[在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-125">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="ff2b3-126">创建项目</span><span class="sxs-lookup"><span data-stu-id="ff2b3-126">Creating the Project</span></span>  
 <span data-ttu-id="ff2b3-127">第一步是创建项目并设置窗体。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-127">The first step is to create the project and set up the form.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="ff2b3-128">要创建项目</span><span class="sxs-lookup"><span data-stu-id="ff2b3-128">To create the project</span></span>  
  
1.  <span data-ttu-id="ff2b3-129">创建一个名为"SnaplineExample"的基于 Windows 的应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-129">Create a Windows-based application project called "SnaplineExample".</span></span> <span data-ttu-id="ff2b3-130">有关详细信息，请参阅[如何：创建一个 Windows 应用程序项目](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-130">For details, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).</span></span>  
  
2.  <span data-ttu-id="ff2b3-131">在窗体设计器中选择窗体。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-131">Select the form in the Forms Designer.</span></span>  
  
## <a name="spacing-and-aligning-controls-using-snaplines"></a><span data-ttu-id="ff2b3-132">间距和对齐控件使用对齐线</span><span class="sxs-lookup"><span data-stu-id="ff2b3-132">Spacing and Aligning Controls Using Snaplines</span></span>  
 <span data-ttu-id="ff2b3-133">对齐线使您可以在你的窗体上对齐控件准确且直观的方式。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-133">Snaplines give you an accurate and intuitive way to align controls on your form.</span></span> <span data-ttu-id="ff2b3-134">它们显示在与另一个控件或组控件将保持一致的位置附近移动选定的控件时。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-134">They appear when you are moving a selected control or controls near a position that would align with another control or set of controls.</span></span> <span data-ttu-id="ff2b3-135">你的选择将"对齐"到建议的位置根据越过其他控件。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-135">Your selection will "snap" to the suggested position as you move it past the other controls.</span></span>  
  
#### <a name="to-arrange-controls-using-snaplines"></a><span data-ttu-id="ff2b3-136">使用对齐线排列控件</span><span class="sxs-lookup"><span data-stu-id="ff2b3-136">To arrange controls using snaplines</span></span>  
  
1.  <span data-ttu-id="ff2b3-137">拖动<xref:System.Windows.Forms.Button>控件从**工具箱**拖动到窗体。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-137">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto your form.</span></span>  
  
2.  <span data-ttu-id="ff2b3-138">移动<xref:System.Windows.Forms.Button>在窗体右下角的控件。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-138">Move the <xref:System.Windows.Forms.Button> control to the lower-right corner of the form.</span></span> <span data-ttu-id="ff2b3-139">请注意显示为对齐线<xref:System.Windows.Forms.Button>控件接近下边缘和右边框的窗体。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-139">Note the snaplines that appear as the <xref:System.Windows.Forms.Button> control approaches the bottom and right borders of the form.</span></span> <span data-ttu-id="ff2b3-140">这些对齐线显示控件的边框和窗体的建议的距离。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-140">These snaplines display the recommended distance between the borders of the control and the form.</span></span>  
  
3.  <span data-ttu-id="ff2b3-141">移动<xref:System.Windows.Forms.Button>控件周围的边框的窗体并注意对齐线的显示位置。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-141">Move the <xref:System.Windows.Forms.Button> control around the borders of the form and note where the snaplines appear.</span></span> <span data-ttu-id="ff2b3-142">完成后，移动<xref:System.Windows.Forms.Button>附近窗体的中心。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-142">When you are finished, move the <xref:System.Windows.Forms.Button> control near the center of the form.</span></span>  
  
4.  <span data-ttu-id="ff2b3-143">将另一个<xref:System.Windows.Forms.Button>控件从**工具箱**拖动到窗体。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-143">Drag another <xref:System.Windows.Forms.Button> control from the **Toolbox** onto your form.</span></span>  
  
5.  <span data-ttu-id="ff2b3-144">移动第二个<xref:System.Windows.Forms.Button>控件，直到它是几乎与第一个级别。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-144">Move the second <xref:System.Windows.Forms.Button> control until it is nearly level with the first.</span></span> <span data-ttu-id="ff2b3-145">请注意出现在两个按钮的文本基线对齐线，并记下你移动的控件对齐到的位置，则完全与另一个控件的级别。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-145">Note the snapline that appears at the text baseline of both buttons, and note that the control you are moving snaps to a position that is exactly level with the other control.</span></span>  
  
6.  <span data-ttu-id="ff2b3-146">移动第二个<xref:System.Windows.Forms.Button>控制直到它位于第一个的正上方。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-146">Move the second <xref:System.Windows.Forms.Button> control until it is positioned directly above the first.</span></span> <span data-ttu-id="ff2b3-147">请注意出现沿左边缘和右边缘的两个按钮，并记下该控件与准确对齐与另一个控件的位置的移动对齐的对齐线。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-147">Note the snaplines that appear along the left and right edges of both buttons, and note that the control you are moving snaps to a position that is exactly aligned with the other control.</span></span>  
  
7.  <span data-ttu-id="ff2b3-148">选择其中一个<xref:System.Windows.Forms.Button>控制并将其移近另一个，直到它们几乎接触。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-148">Select one of the <xref:System.Windows.Forms.Button> controls and move it close to the other, until they are almost touching.</span></span> <span data-ttu-id="ff2b3-149">请注意它们之间的对齐线。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-149">Note the snapline that appears between them.</span></span> <span data-ttu-id="ff2b3-150">此距离是控件的边框之间的建议的距离。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-150">This distance is the recommended distance between the borders of the controls.</span></span> <span data-ttu-id="ff2b3-151">另请注意你移动的控件对齐到此位置。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-151">Also note that the control you are moving snaps to this position.</span></span>  
  
8.  <span data-ttu-id="ff2b3-152">将两个<xref:System.Windows.Forms.Panel>控件从**工具箱**拖动到窗体。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-152">Drag two <xref:System.Windows.Forms.Panel> controls from the **Toolbox** onto your form.</span></span>  
  
9. <span data-ttu-id="ff2b3-153">将其中一个移动<xref:System.Windows.Forms.Panel>控件，直到它是几乎与第一个级别。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-153">Move one of the <xref:System.Windows.Forms.Panel> controls until it is nearly level with the first.</span></span> <span data-ttu-id="ff2b3-154">请注意显示两个控件的边缘和下边缘沿并记下你移动的控件对齐到的位置，则完全级别与另一个控件的对齐线。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-154">Note the snaplines that appear along the top and bottom edges of both controls, and note that the control you are moving snaps to a position that is exactly level with the other control.</span></span>  
  
## <a name="aligning-to-form-and-container-margins"></a><span data-ttu-id="ff2b3-155">到窗体和容器的边缘对齐</span><span class="sxs-lookup"><span data-stu-id="ff2b3-155">Aligning to Form and Container Margins</span></span>  
 <span data-ttu-id="ff2b3-156">对齐线有助于以一致的方式对齐将控件与窗体和容器的边距。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-156">Snaplines help you to align your controls to form and container margins in a consistent manner.</span></span>  
  
#### <a name="to-align-controls-to-form-and-container-margins"></a><span data-ttu-id="ff2b3-157">对齐控件添加到窗体和容器的边距</span><span class="sxs-lookup"><span data-stu-id="ff2b3-157">To align controls to form and container margins</span></span>  
  
1.  <span data-ttu-id="ff2b3-158">选择其中一个<xref:System.Windows.Forms.Button>控制并将其移接近右边框的窗体中，直到显示对齐线。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-158">Select one of the <xref:System.Windows.Forms.Button> controls and move it close to the right border of the form until a snapline appears.</span></span> <span data-ttu-id="ff2b3-159">从右边框对齐线的距离是控件的总和<xref:System.Windows.Forms.Control.Margin%2A>属性和窗体的<xref:System.Windows.Forms.Control.Padding%2A>属性值。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-159">The snapline's distance from the right border is the sum of the control's <xref:System.Windows.Forms.Control.Margin%2A> property and the form's <xref:System.Windows.Forms.Control.Padding%2A> property values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ff2b3-160">如果窗体的<xref:System.Windows.Forms.Control.Padding%2A>属性设置为 0,0,0,0、 Windows 窗体设计器使该窗体指定隐藏<xref:System.Windows.Forms.Control.Padding%2A>9,9,9,9 的值。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-160">If the form's <xref:System.Windows.Forms.Control.Padding%2A> property is set to 0,0,0,0, the Windows Forms Designer gives the form a shadowed <xref:System.Windows.Forms.Control.Padding%2A> value of 9,9,9,9.</span></span> <span data-ttu-id="ff2b3-161">若要重写此行为，分配 0,0,0,0 以外的值。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-161">To override this behavior, assign a value other than 0,0,0,0.</span></span>  
  
1.  <span data-ttu-id="ff2b3-162">更改的值<xref:System.Windows.Forms.Button>控件的<xref:System.Windows.Forms.Control.Margin%2A>属性通过展开<xref:System.Windows.Forms.Control.Margin%2A>中的条目**属性**窗口和设置<xref:System.Windows.Forms.Padding.All%2A>属性设为 0。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-162">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Margin%2A> property by expanding the <xref:System.Windows.Forms.Control.Margin%2A> entry in the **Properties** window and setting the <xref:System.Windows.Forms.Padding.All%2A> property to 0.</span></span> <span data-ttu-id="ff2b3-163">有关详细信息，请参阅[演练： 设计出 Windows 窗体控件与 Padding、 Margins 和 AutoSize 属性](../../../../docs/framework/winforms/controls/windows-forms-controls-padding-autosize.md)。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-163">For details, see [Walkthrough: Laying Out Windows Forms Controls with Padding, Margins, and the AutoSize Property](../../../../docs/framework/winforms/controls/windows-forms-controls-padding-autosize.md).</span></span>  
  
2.  <span data-ttu-id="ff2b3-164">移动<xref:System.Windows.Forms.Button>接近右边框直到显示对齐线在窗体控件。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-164">Move the <xref:System.Windows.Forms.Button> control close to the right border of the form until a snapline appears.</span></span> <span data-ttu-id="ff2b3-165">此距离现在由窗体的值指定<xref:System.Windows.Forms.Control.Padding%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-165">This distance is now given by the value of the form's <xref:System.Windows.Forms.Control.Padding%2A> property.</span></span>  
  
3.  <span data-ttu-id="ff2b3-166">拖动<xref:System.Windows.Forms.GroupBox>控件从**工具箱**拖动到窗体。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-166">Drag a <xref:System.Windows.Forms.GroupBox> control from the **Toolbox** onto your form.</span></span>  
  
4.  <span data-ttu-id="ff2b3-167">更改的值<xref:System.Windows.Forms.GroupBox>控件的<xref:System.Windows.Forms.Control.Padding%2A>属性通过展开<xref:System.Windows.Forms.Control.Padding%2A>中的条目**属性**窗口和设置<xref:System.Windows.Forms.Padding.All%2A>属性设置为 10。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-167">Change the value of the <xref:System.Windows.Forms.GroupBox> control's <xref:System.Windows.Forms.Control.Padding%2A> property by expanding the <xref:System.Windows.Forms.Control.Padding%2A> entry in the **Properties** window and setting the <xref:System.Windows.Forms.Padding.All%2A> property to 10.</span></span>  
  
5.  <span data-ttu-id="ff2b3-168">拖动<xref:System.Windows.Forms.Button>控件从**工具箱**到<xref:System.Windows.Forms.GroupBox>控件。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-168">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** into the <xref:System.Windows.Forms.GroupBox> control.</span></span>  
  
6.  <span data-ttu-id="ff2b3-169">移动<xref:System.Windows.Forms.Button>接近的右边框的控件<xref:System.Windows.Forms.GroupBox>控制直到显示对齐线。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-169">Move the <xref:System.Windows.Forms.Button> control close to the right border of the <xref:System.Windows.Forms.GroupBox> control until a snapline appears.</span></span> <span data-ttu-id="ff2b3-170">移动<xref:System.Windows.Forms.Button>控件中<xref:System.Windows.Forms.GroupBox>控制和注意对齐线的显示位置。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-170">Move the <xref:System.Windows.Forms.Button> control within the <xref:System.Windows.Forms.GroupBox> control and note where the snaplines appear.</span></span>  
  
## <a name="aligning-to-grouped-controls"></a><span data-ttu-id="ff2b3-171">对齐到分组后的控件</span><span class="sxs-lookup"><span data-stu-id="ff2b3-171">Aligning to Grouped Controls</span></span>  
 <span data-ttu-id="ff2b3-172">你可以使用对齐线对齐分组后的控件以及为控件中<xref:System.Windows.Forms.GroupBox>控件。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-172">You can use snaplines to align grouped controls as well as controls within a <xref:System.Windows.Forms.GroupBox> control.</span></span>  
  
#### <a name="to-align-to-grouped-controls"></a><span data-ttu-id="ff2b3-173">对齐到一组控件</span><span class="sxs-lookup"><span data-stu-id="ff2b3-173">To align to grouped controls</span></span>  
  
1.  <span data-ttu-id="ff2b3-174">选择两个窗体上的控件。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-174">Select two of the controls on your form.</span></span> <span data-ttu-id="ff2b3-175">移动所选内容，并记下你的选择和其他控件之间显示的对齐线。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-175">Move the selection around and note the snaplines that appear between your selection and the other controls.</span></span>  
  
2.  <span data-ttu-id="ff2b3-176">拖动<xref:System.Windows.Forms.GroupBox>控件从**工具箱**拖动到窗体。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-176">Drag a <xref:System.Windows.Forms.GroupBox> control from the **Toolbox** onto your form.</span></span>  
  
3.  <span data-ttu-id="ff2b3-177">拖动<xref:System.Windows.Forms.Button>控件从**工具箱**到<xref:System.Windows.Forms.GroupBox>控件。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-177">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** into the <xref:System.Windows.Forms.GroupBox> control.</span></span>  
  
4.  <span data-ttu-id="ff2b3-178">选择其中一个<xref:System.Windows.Forms.Button>控制并移动文件<xref:System.Windows.Forms.GroupBox>控件。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-178">Select one of the <xref:System.Windows.Forms.Button> controls and move it around the <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="ff2b3-179">请注意显示的两端的对齐线<xref:System.Windows.Forms.GroupBox>控件。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-179">Note the snaplines that appear at the edges of the <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="ff2b3-180">另请注意显示的两端的对齐线<xref:System.Windows.Forms.Button>所包含的控件<xref:System.Windows.Forms.GroupBox>控件。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-180">Also note the snaplines that appear at the edges of the <xref:System.Windows.Forms.Button> control that is contained by the <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="ff2b3-181">控件的子级的容器控件还支持对齐线。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-181">Controls that are children of a container control also support snaplines.</span></span>  
  
## <a name="using-snaplines-to-place-a-control-by-outlining-its-size"></a><span data-ttu-id="ff2b3-182">使用对齐线通过勾画放置控件</span><span class="sxs-lookup"><span data-stu-id="ff2b3-182">Using Snaplines to Place a Control by Outlining Its Size</span></span>  
 <span data-ttu-id="ff2b3-183">对齐线有助于控件对齐时你首先将其放在窗体上。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-183">Snaplines help you align controls when you first place them on a form.</span></span>  
  
#### <a name="to-use-snaplines-to-place-a-control-by-outlining-its-size"></a><span data-ttu-id="ff2b3-184">若要使用对齐线控件置于通过勾画</span><span class="sxs-lookup"><span data-stu-id="ff2b3-184">To use snaplines to place a control by outlining its size</span></span>  
  
1.  <span data-ttu-id="ff2b3-185">在“工具箱” 中，单击 <xref:System.Windows.Forms.Button> 控件图标。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-185">In the **Toolbox**, click the <xref:System.Windows.Forms.Button> control icon.</span></span> <span data-ttu-id="ff2b3-186">请勿将其拖到窗体上。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-186">Do not drag it onto the form.</span></span>  
  
2.  <span data-ttu-id="ff2b3-187">将鼠标指针移窗体的设计图面。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-187">Move the mouse pointer over the form's design surface.</span></span> <span data-ttu-id="ff2b3-188">请注意，指针会更改为十字形，同时会附上 <xref:System.Windows.Forms.Button> 控件图标。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-188">Note that the pointer changes to a crosshair with the <xref:System.Windows.Forms.Button> control icon attached.</span></span> <span data-ttu-id="ff2b3-189">另请注意显示来建议对齐的位置的对齐线<xref:System.Windows.Forms.Button>控件。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-189">Also note the snaplines that appear to suggest aligned positions for the <xref:System.Windows.Forms.Button> control.</span></span>  
  
3.  <span data-ttu-id="ff2b3-190">单击并按住鼠标按钮。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-190">Click and hold the mouse button.</span></span>  
  
4.  <span data-ttu-id="ff2b3-191">拖动鼠标指针在窗体。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-191">Drag the mouse pointer around the form.</span></span> <span data-ttu-id="ff2b3-192">请注意，绘制概述，指示的位置和控件的大小。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-192">Note that an outline is drawn, indicating the position and the size of the control.</span></span>  
  
5.  <span data-ttu-id="ff2b3-193">拖动指针，直到它与另一个控件在窗体上对齐。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-193">Drag the pointer until it aligns with another control on the form.</span></span> <span data-ttu-id="ff2b3-194">请注意，显示对齐线，以指示对齐方式。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-194">Note that a snapline appears to indicate alignment.</span></span>  
  
6.  <span data-ttu-id="ff2b3-195">释放鼠标按钮。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-195">Release the mouse button.</span></span> <span data-ttu-id="ff2b3-196">位置和大小轮廓线指示在创建滑块控件。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-196">The control is created at the position and size indicated by the outline.</span></span>  
  
## <a name="using-snaplines-when-dragging-a-control-from-the-toolbox"></a><span data-ttu-id="ff2b3-197">从工具箱中拖动控件时使用对齐线</span><span class="sxs-lookup"><span data-stu-id="ff2b3-197">Using Snaplines When Dragging a Control from the Toolbox</span></span>  
 <span data-ttu-id="ff2b3-198">对齐线有助于控件对齐将它们从**工具箱**拖动到窗体。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-198">Snaplines help you align controls when you drag them from the **Toolbox** onto your form.</span></span>  
  
#### <a name="to-use-snaplines-when-dragging-a-control-from-the-toolbox"></a><span data-ttu-id="ff2b3-199">若要从工具箱中拖动控件时使用对齐线</span><span class="sxs-lookup"><span data-stu-id="ff2b3-199">To use snaplines when dragging a control from the Toolbox</span></span>  
  
1.  <span data-ttu-id="ff2b3-200">拖动<xref:System.Windows.Forms.Button>控件从**工具箱**拖动到窗体，但不是释放鼠标按钮。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-200">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto your form, but do not release the mouse button.</span></span>  
  
2.  <span data-ttu-id="ff2b3-201">将鼠标指针移窗体的设计图面。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-201">Move the mouse pointer over the form's design surface.</span></span> <span data-ttu-id="ff2b3-202">请注意，指针更改以指示的位置新<xref:System.Windows.Forms.Button>，都会创建控件。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-202">Note that the pointer changes to indicate the position at which the new <xref:System.Windows.Forms.Button> control will be created.</span></span>  
  
3.  <span data-ttu-id="ff2b3-203">拖动鼠标指针在窗体。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-203">Drag the mouse pointer around the form.</span></span> <span data-ttu-id="ff2b3-204">请注意显示来建议对齐的位置的对齐线<xref:System.Windows.Forms.Button>控件。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-204">Note the snaplines that appear to suggest aligned positions for the <xref:System.Windows.Forms.Button> control.</span></span> <span data-ttu-id="ff2b3-205">查找与其他控件对齐的位置。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-205">Find a position that is aligned with other controls.</span></span>  
  
4.  <span data-ttu-id="ff2b3-206">释放鼠标按钮。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-206">Release the mouse button.</span></span> <span data-ttu-id="ff2b3-207">在指示对齐线的位置创建该控件。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-207">The control is created at the position indicated by the snaplines.</span></span>  
  
## <a name="resizing-controls-using-snaplines"></a><span data-ttu-id="ff2b3-208">使用对齐线的大小调整控件</span><span class="sxs-lookup"><span data-stu-id="ff2b3-208">Resizing Controls Using Snaplines</span></span>  
 <span data-ttu-id="ff2b3-209">对齐线有助于对齐控件，如调整其大小。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-209">Snaplines help you align controls as you resize them.</span></span>  
  
#### <a name="to-resize-a-control-using-snaplines"></a><span data-ttu-id="ff2b3-210">若要调整大小使用对齐线的控件</span><span class="sxs-lookup"><span data-stu-id="ff2b3-210">To resize a control using snaplines</span></span>  
  
1.  <span data-ttu-id="ff2b3-211">拖动<xref:System.Windows.Forms.Button>控件从**工具箱**拖动到窗体。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-211">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto your form.</span></span>  
  
2.  <span data-ttu-id="ff2b3-212">调整大小<xref:System.Windows.Forms.Button>抓住角大小调整控点和拖动某个控件。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-212">Resize the <xref:System.Windows.Forms.Button> control by grabbing one of the corner sizing handles and dragging.</span></span> <span data-ttu-id="ff2b3-213">有关详细信息，请参阅[如何： 调整 Windows 窗体上的控件](../../../../docs/framework/winforms/controls/how-to-resize-controls-on-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-213">For details, see [How to: Resize Controls on Windows Forms](../../../../docs/framework/winforms/controls/how-to-resize-controls-on-windows-forms.md).</span></span>  
  
3.  <span data-ttu-id="ff2b3-214">拖动直到其中一个尺寸控点<xref:System.Windows.Forms.Button>与另一个控件对齐控件的边框。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-214">Drag the sizing handle until one of the <xref:System.Windows.Forms.Button> control's borders is aligned with another control.</span></span> <span data-ttu-id="ff2b3-215">请注意，显示对齐线。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-215">Note that a snapline appears.</span></span> <span data-ttu-id="ff2b3-216">另请注意尺寸控点对齐到指示对齐线的位置。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-216">Also note that the sizing handle snaps to the position indicated by the snapline.</span></span>  
  
4.  <span data-ttu-id="ff2b3-217">调整大小<xref:System.Windows.Forms.Button>在不同的方向中控制和对齐不同的控件的大小调整句柄。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-217">Resize the <xref:System.Windows.Forms.Button> control in different directions and align the sizing handle to different controls.</span></span> <span data-ttu-id="ff2b3-218">请注意对齐线中不同的方向，以指示对齐方式的显示方式。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-218">Note how the snaplines appear in various orientations to indicate alignment.</span></span>  
  
## <a name="aligning-a-label-to-a-controls-text"></a><span data-ttu-id="ff2b3-219">对齐标签与控件的文本</span><span class="sxs-lookup"><span data-stu-id="ff2b3-219">Aligning a Label to a Control's Text</span></span>  
 <span data-ttu-id="ff2b3-220">某些控件提供对齐到显示的文本的其他控件对齐的线。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-220">Some controls offer a snapline for aligning other controls to displayed text.</span></span>  
  
#### <a name="to-align-a-label-to-a-controls-text"></a><span data-ttu-id="ff2b3-221">若要对齐标签与控件的文本</span><span class="sxs-lookup"><span data-stu-id="ff2b3-221">To align a label to a control's text</span></span>  
  
1.  <span data-ttu-id="ff2b3-222">拖动<xref:System.Windows.Forms.TextBox>控件从**工具箱**拖动到窗体。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-222">Drag a <xref:System.Windows.Forms.TextBox> control from the **Toolbox** onto your form.</span></span> <span data-ttu-id="ff2b3-223">当删除<xref:System.Windows.Forms.TextBox>拖到窗体控件，请单击智能标记标志符号，选择**将文本设置为 textBox1**选项。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-223">When you drop the <xref:System.Windows.Forms.TextBox> control onto the form, click the smart-tag glyph and select the **Set text to textBox1** option.</span></span> <span data-ttu-id="ff2b3-224">有关详细信息，请参阅[演练： 执行常见任务使用智能标记 Windows 窗体控件上](../../../../docs/framework/winforms/controls/performing-common-tasks-using-smart-tags-on-wf-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-224">For details, see [Walkthrough: Performing Common Tasks Using Smart Tags on Windows Forms Controls](../../../../docs/framework/winforms/controls/performing-common-tasks-using-smart-tags-on-wf-controls.md).</span></span>  
  
2.  <span data-ttu-id="ff2b3-225">拖动<xref:System.Windows.Forms.Label>控件从**工具箱**拖动到窗体。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-225">Drag a <xref:System.Windows.Forms.Label> control from the **Toolbox** onto your form.</span></span>  
  
3.  <span data-ttu-id="ff2b3-226">将 <xref:System.Windows.Forms.Label> 控件的 <xref:System.Windows.Forms.Control.AutoSize%2A> 属性值更改为 `true`。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-226">Change the value of the <xref:System.Windows.Forms.Label> control's <xref:System.Windows.Forms.Control.AutoSize%2A> property to `true`.</span></span> <span data-ttu-id="ff2b3-227">请注意，将该控件的边框调整以适合显示文本。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-227">Note that the control's borders are adjusted to fit the display text.</span></span>  
  
4.  <span data-ttu-id="ff2b3-228">移动<xref:System.Windows.Forms.Label>控件左侧<xref:System.Windows.Forms.TextBox>控件，以便它与下边缘对齐<xref:System.Windows.Forms.TextBox>控件。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-228">Move the <xref:System.Windows.Forms.Label> control to the left of the <xref:System.Windows.Forms.TextBox> control, so it is aligned with the bottom edge of the <xref:System.Windows.Forms.TextBox> control.</span></span> <span data-ttu-id="ff2b3-229">请注意将沿两个控件的下边缘显示对齐线。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-229">Note the snapline that appears along the bottom edges of the two controls.</span></span>  
  
5.  <span data-ttu-id="ff2b3-230">移动<xref:System.Windows.Forms.Label>控件略微向上，直到<xref:System.Windows.Forms.Label>文本和<xref:System.Windows.Forms.TextBox>对齐文本。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-230">Move the <xref:System.Windows.Forms.Label> control slightly upward, until the <xref:System.Windows.Forms.Label> text and the <xref:System.Windows.Forms.TextBox> text are aligned.</span></span> <span data-ttu-id="ff2b3-231">请注意样式有所不同对齐线显示，该值指示当对齐两个控件的文本字段。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-231">Note the differently styled snapline that appears, indicating when the text fields of both controls are aligned.</span></span>  
  
## <a name="using-snaplines-with-keyboard-navigation"></a><span data-ttu-id="ff2b3-232">使用键盘导航线对齐</span><span class="sxs-lookup"><span data-stu-id="ff2b3-232">Using Snaplines with Keyboard Navigation</span></span>  
 <span data-ttu-id="ff2b3-233">对齐线有助于控件对齐时排列它们使用键盘上的箭头键。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-233">Snaplines help you align controls when you are arranging them using the keyboard's arrow keys.</span></span>  
  
#### <a name="to-use-snaplines-with-keyboard-navigation"></a><span data-ttu-id="ff2b3-234">若要使用键盘导航线对齐</span><span class="sxs-lookup"><span data-stu-id="ff2b3-234">To use snaplines with keyboard navigation</span></span>  
  
1.  <span data-ttu-id="ff2b3-235">拖动<xref:System.Windows.Forms.Button>控件从**工具箱**拖动到窗体。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-235">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto your form.</span></span> <span data-ttu-id="ff2b3-236">将其放在窗体的左上角。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-236">Place it in the upper-left corner of the form.</span></span>  
  
2.  <span data-ttu-id="ff2b3-237">按 CTRL + 向下箭头。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-237">Press CTRL+DOWN ARROW.</span></span> <span data-ttu-id="ff2b3-238">请注意，控件向窗体下移动到第一个可用的水平对齐位置。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-238">Note that the control moves down the form to the first available horizontal alignment position.</span></span>  
  
3.  <span data-ttu-id="ff2b3-239">按 CTRL + 向下箭头，直到控件到达窗体的底部。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-239">Press CTRL+DOWN ARROW until the control reaches the bottom of the form.</span></span> <span data-ttu-id="ff2b3-240">注意，它占用下移窗体的位置。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-240">Note the positions it occupies as it moves down the form.</span></span>  
  
4.  <span data-ttu-id="ff2b3-241">按 CTRL + 向右键。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-241">Press CTRL+RIGHT ARROW.</span></span> <span data-ttu-id="ff2b3-242">请注意，该控件在窗体移动到第一个可用的垂直对齐位置。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-242">Note that the control moves across the form to the first available vertical alignment position.</span></span>  
  
5.  <span data-ttu-id="ff2b3-243">按 CTRL + 向右键，直到控件到达窗体的左侧。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-243">Press CTRL+RIGHT ARROW until the control reaches the side of the form.</span></span> <span data-ttu-id="ff2b3-244">注意，它占用当它移到窗体的位置。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-244">Note the positions it occupies as it moves across the form.</span></span>  
  
6.  <span data-ttu-id="ff2b3-245">将在窗体控件移动使用箭头键的组合。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-245">Move the control around the form with a combination of arrow keys.</span></span> <span data-ttu-id="ff2b3-246">请注意控件所占据的位置和伴随它们出现的对齐线。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-246">Note the positions the control occupies and the snaplines that accompany them.</span></span>  
  
7.  <span data-ttu-id="ff2b3-247">按下 SHIFT + 任意箭头键调整大小<xref:System.Windows.Forms.Button>按一个像素的增量的控件。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-247">Press SHIFT+any arrow key to resize the <xref:System.Windows.Forms.Button> control by increments of one pixel.</span></span>  
  
8.  <span data-ttu-id="ff2b3-248">按 CTRL + SHIFT + 任意箭头键调整大小<xref:System.Windows.Forms.Button>控件中对齐线的增量。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-248">Press CTRL+SHIFT+any arrow key to resize the <xref:System.Windows.Forms.Button> control in snapline increments.</span></span>  
  
## <a name="snaplines-and-layout-panels"></a><span data-ttu-id="ff2b3-249">对齐线和布局面板</span><span class="sxs-lookup"><span data-stu-id="ff2b3-249">Snaplines and Layout Panels</span></span>  
 <span data-ttu-id="ff2b3-250">对齐线被禁用在布局面板内。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-250">Snaplines are disabled within layout panels.</span></span>  
  
#### <a name="to-selectively-disable-snaplines"></a><span data-ttu-id="ff2b3-251">若要有选择性地禁用对齐线</span><span class="sxs-lookup"><span data-stu-id="ff2b3-251">To selectively disable snaplines</span></span>  
  
1.  <span data-ttu-id="ff2b3-252">拖动<xref:System.Windows.Forms.TableLayoutPanel>控件从**工具箱**拖动到窗体。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-252">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>  
  
2.  <span data-ttu-id="ff2b3-253">在“工具箱” <xref:System.Windows.Forms.Button>**中，双击**控件图标。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-253">Double-click the <xref:System.Windows.Forms.Button> control icon in the **Toolbox**.</span></span> <span data-ttu-id="ff2b3-254">请注意，在将出现一个新的按钮控件<xref:System.Windows.Forms.TableLayoutPanel>控件的第一个单元格。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-254">Note that a new button control appears in the <xref:System.Windows.Forms.TableLayoutPanel> control's first cell.</span></span>  
  
3.  <span data-ttu-id="ff2b3-255">双击<xref:System.Windows.Forms.Button>中的控件图标**工具箱**两次。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-255">Double-click the <xref:System.Windows.Forms.Button> control icon in the **Toolbox** twice more.</span></span> <span data-ttu-id="ff2b3-256">这将使在一个空单元格<xref:System.Windows.Forms.TableLayoutPanel>控件。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-256">This leaves one empty cell in the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
4.  <span data-ttu-id="ff2b3-257">拖动<xref:System.Windows.Forms.Button>控件从**工具箱**到的空单元格中<xref:System.Windows.Forms.TableLayoutPanel>控件。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-257">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** into the empty cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span> <span data-ttu-id="ff2b3-258">请注意，没有对齐线显示。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-258">Note that no snaplines appear.</span></span>  
  
5.  <span data-ttu-id="ff2b3-259">拖动<xref:System.Windows.Forms.Button>外控制<xref:System.Windows.Forms.TableLayoutPanel>控制并移动文件<xref:System.Windows.Forms.TableLayoutPanel>控件。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-259">Drag the <xref:System.Windows.Forms.Button> control out of the <xref:System.Windows.Forms.TableLayoutPanel> control and move it around the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span> <span data-ttu-id="ff2b3-260">请注意，对齐线会再次出现。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-260">Note that snaplines appear again.</span></span>  
  
## <a name="disabling-snaplines"></a><span data-ttu-id="ff2b3-261">禁用对齐线</span><span class="sxs-lookup"><span data-stu-id="ff2b3-261">Disabling Snaplines</span></span>  
 <span data-ttu-id="ff2b3-262">默认情况下，对齐线被开启。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-262">Snaplines are turned on by default.</span></span> <span data-ttu-id="ff2b3-263">您可以有选择地，禁用对齐线，或者你可以在设计环境中禁用它们。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-263">You can disable snaplines selectively, or you can disable them in the design environment.</span></span>  
  
#### <a name="to-selectively-disable-snaplines"></a><span data-ttu-id="ff2b3-264">若要有选择性地禁用对齐线</span><span class="sxs-lookup"><span data-stu-id="ff2b3-264">To selectively disable snaplines</span></span>  
  
-   <span data-ttu-id="ff2b3-265">按 ALT 键和而移动在窗体控件。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-265">Press the ALT key and while moving a control around the form.</span></span>  
  
     <span data-ttu-id="ff2b3-266">请注意，没有对齐线显示该控件不会按任何可能的对齐位置。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-266">Note that no snaplines appear and the control does not snap to any potential alignment positions.</span></span>  
  
#### <a name="to-disable-snaplines-in-the-design-environment"></a><span data-ttu-id="ff2b3-267">若要禁用设计环境中的对齐线</span><span class="sxs-lookup"><span data-stu-id="ff2b3-267">To disable snaplines in the design environment</span></span>  
  
1.  <span data-ttu-id="ff2b3-268">从**工具**菜单上，打开**选项**对话框。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-268">From the **Tools** menu, open the **Options** dialog box.</span></span> <span data-ttu-id="ff2b3-269">打开 Windows 窗体设计器对话框。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-269">Open the Windows Forms Designer dialog box.</span></span> <span data-ttu-id="ff2b3-270">有关详细信息，请参阅[常规、 Windows 窗体设计器、 选项对话框](http://msdn.microsoft.com/library/8dd170af-72f0-4212-b04b-034ceee92834)。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-270">For details, see [General, Windows Forms Designer, Options Dialog Box](http://msdn.microsoft.com/library/8dd170af-72f0-4212-b04b-034ceee92834).</span></span>  
  
2.  <span data-ttu-id="ff2b3-271">选择**常规**节点。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-271">Select the **General** node.</span></span> <span data-ttu-id="ff2b3-272">在**布局模式**部分中，更改从选择**对齐线**到**网格线对齐**。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-272">In the **Layout Mode** section, change the selection from **SnapLines** to **SnapToGrid**.</span></span>  
  
3.  <span data-ttu-id="ff2b3-273">单击确定以应用设置。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-273">Click OK to apply the setting.</span></span>  
  
4.  <span data-ttu-id="ff2b3-274">选择你的窗体上的控件并将其移动的其他控件周围。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-274">Select a control on your form and move it around the other controls.</span></span> <span data-ttu-id="ff2b3-275">请注意，不会显示对齐线。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-275">Note that snaplines do not appear.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="ff2b3-276">后续步骤</span><span class="sxs-lookup"><span data-stu-id="ff2b3-276">Next Steps</span></span>  
 <span data-ttu-id="ff2b3-277">对齐线提供一种直观的方法来对齐窗体上的控件。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-277">Snaplines offer an intuitive means of aligning controls on your form.</span></span> <span data-ttu-id="ff2b3-278">有关进一步探索的建议包括：</span><span class="sxs-lookup"><span data-stu-id="ff2b3-278">Suggestions for more exploration include:</span></span>  
  
-   <span data-ttu-id="ff2b3-279">请尝试嵌套<xref:System.Windows.Forms.GroupBox>中另一个控件<xref:System.Windows.Forms.GroupBox>控件。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-279">Try nesting a <xref:System.Windows.Forms.GroupBox> control within another <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="ff2b3-280">位置<xref:System.Windows.Forms.Button>内子控件<xref:System.Windows.Forms.GroupBox>控制和另一个父项中<xref:System.Windows.Forms.GroupBox>控件。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-280">Place a <xref:System.Windows.Forms.Button> control within the child <xref:System.Windows.Forms.GroupBox> control, and another within the parent <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="ff2b3-281">移动<xref:System.Windows.Forms.Button>控件以查看如何对齐线跨容器边界。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-281">Move the <xref:System.Windows.Forms.Button> controls around to see how the snaplines cross container boundaries.</span></span>  
  
-   <span data-ttu-id="ff2b3-282">创建一列<xref:System.Windows.Forms.TextBox>控件与相应的列的<xref:System.Windows.Forms.Label>控件。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-282">Create a column of <xref:System.Windows.Forms.TextBox> controls and a corresponding column of <xref:System.Windows.Forms.Label> controls.</span></span> <span data-ttu-id="ff2b3-283">设置的值<xref:System.Windows.Forms.Label>控件的<xref:System.Windows.Forms.Control.AutoSize%2A>属性`true`。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-283">Set the value of the <xref:System.Windows.Forms.Label> controls' <xref:System.Windows.Forms.Control.AutoSize%2A> property to `true`.</span></span> <span data-ttu-id="ff2b3-284">使用对齐线移动<xref:System.Windows.Forms.Label>控制以便与中的文本对齐其显示的文本<xref:System.Windows.Forms.TextBox>控件。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-284">Use snaplines to move the <xref:System.Windows.Forms.Label> controls so their displayed text is aligned with the text in the <xref:System.Windows.Forms.TextBox> controls.</span></span>  
  
 <span data-ttu-id="ff2b3-285">有关 Windows 用户界面设计的信息，请参阅图书*Microsoft Windows 用户体验、 用户界面开发人员和设计器的官方指南*Redmond，WA: Microsoft Press，1999年。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-285">For information about Windows user interface design, see the book *Microsoft Windows User Experience, Official Guidelines for User Interface Developers and Designers* Redmond, WA: Microsoft Press, 1999.</span></span> <span data-ttu-id="ff2b3-286">(USBN: 0-7356-0566年-1)。</span><span class="sxs-lookup"><span data-stu-id="ff2b3-286">(USBN: 0-7356-0566-1).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff2b3-287">请参阅</span><span class="sxs-lookup"><span data-stu-id="ff2b3-287">See Also</span></span>  
 <xref:System.Windows.Forms.Design.Behavior.SnapLine>  
 [<span data-ttu-id="ff2b3-288">演练：使用 FlowLayoutPanel 在 Windows 窗体上排列控件</span><span class="sxs-lookup"><span data-stu-id="ff2b3-288">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)  
 [<span data-ttu-id="ff2b3-289">演练：使用 TableLayoutPanel 在 Windows 窗体上排列控件</span><span class="sxs-lookup"><span data-stu-id="ff2b3-289">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)  
 [<span data-ttu-id="ff2b3-290">演练：使用 Padding、Margins 和 AutoSize 属性对 Windows 窗体控件进行布局</span><span class="sxs-lookup"><span data-stu-id="ff2b3-290">Walkthrough: Laying Out Windows Forms Controls with Padding, Margins, and the AutoSize Property</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-padding-autosize.md)  
 [<span data-ttu-id="ff2b3-291">在 Windows 窗体上排列控件</span><span class="sxs-lookup"><span data-stu-id="ff2b3-291">Arranging Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)
