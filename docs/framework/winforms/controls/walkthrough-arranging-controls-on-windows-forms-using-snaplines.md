---
title: 演练：使用对齐线在 Windows 窗体上排列控件
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], arranging with snaplines
- snaplines [Windows Forms], arranging Windows Forms controls
- SnapLine class [Windows Forms], walkthroughs
- Windows Forms controls, arranging
ms.assetid: d5c9edc7-cf30-4a97-8ebe-201d569340f8
ms.openlocfilehash: 170b79f03515ab371f7013c267b28ba85dafd0f5
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "47112908"
---
# <a name="walkthrough-arranging-controls-on-windows-forms-using-snaplines"></a><span data-ttu-id="56eec-102">演练：使用对齐线在 Windows 窗体上排列控件</span><span class="sxs-lookup"><span data-stu-id="56eec-102">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>
<span data-ttu-id="56eec-103">在窗体上精确地放置控件对于许多应用程序而言是高优先级。</span><span class="sxs-lookup"><span data-stu-id="56eec-103">Precise placement of controls on your form is a high priority for many applications.</span></span> <span data-ttu-id="56eec-104">Windows 窗体设计器提供许多布局工具来实现此目的。</span><span class="sxs-lookup"><span data-stu-id="56eec-104">The Windows Forms Designer gives you many layout tools to accomplish this.</span></span> <span data-ttu-id="56eec-105">一个最重要的是<xref:System.Windows.Forms.Design.Behavior.SnapLine>功能。</span><span class="sxs-lookup"><span data-stu-id="56eec-105">One of the most important is the <xref:System.Windows.Forms.Design.Behavior.SnapLine> feature.</span></span>  
  
 <span data-ttu-id="56eec-106">对齐线显示精确位置与其他控件的控件对齐。</span><span class="sxs-lookup"><span data-stu-id="56eec-106">Snaplines show you precisely where to line up controls with other controls.</span></span> <span data-ttu-id="56eec-107">它们还显示控件，指定的 Windows 用户界面指南之间的边距的建议的距离。</span><span class="sxs-lookup"><span data-stu-id="56eec-107">They also show you the recommended distances for margins between controls, as specified by the Windows User Interface Guidelines.</span></span> <span data-ttu-id="56eec-108">有关详细信息，请参阅[用户界面设计和开发](https://go.microsoft.com/FWLink/?LinkId=83878)。</span><span class="sxs-lookup"><span data-stu-id="56eec-108">For details, see [User Interface Design and Development](https://go.microsoft.com/FWLink/?LinkId=83878).</span></span>  
  
 <span data-ttu-id="56eec-109">对齐线轻松地对齐您控件，获得简洁、 专业的外观和行为 （外观和感受）。</span><span class="sxs-lookup"><span data-stu-id="56eec-109">Snaplines make it easy to align your controls, for crisp, professional appearance and behavior (look and feel).</span></span>  
  
 <span data-ttu-id="56eec-110">本演练涉及以下任务：</span><span class="sxs-lookup"><span data-stu-id="56eec-110">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="56eec-111">创建 Windows 窗体项目</span><span class="sxs-lookup"><span data-stu-id="56eec-111">Creating a Windows Forms project</span></span>  
  
-   <span data-ttu-id="56eec-112">间距和对齐控件使用对齐线</span><span class="sxs-lookup"><span data-stu-id="56eec-112">Spacing and Aligning Controls Using Snaplines</span></span>  
  
-   <span data-ttu-id="56eec-113">向窗体和容器的边缘对齐</span><span class="sxs-lookup"><span data-stu-id="56eec-113">Aligning to Form and Container Margins</span></span>  
  
-   <span data-ttu-id="56eec-114">对齐到分组后的控件</span><span class="sxs-lookup"><span data-stu-id="56eec-114">Aligning to Grouped Controls</span></span>  
  
-   <span data-ttu-id="56eec-115">使用对齐线将控件的大纲显示其大小</span><span class="sxs-lookup"><span data-stu-id="56eec-115">Using Snaplines to Place a Control by Outlining Its Size</span></span>  
  
-   <span data-ttu-id="56eec-116">从工具箱拖动控件时使用对齐线</span><span class="sxs-lookup"><span data-stu-id="56eec-116">Using Snaplines When Dragging a Control from the Toolbox</span></span>  
  
-   <span data-ttu-id="56eec-117">调整控件使用对齐线的大小</span><span class="sxs-lookup"><span data-stu-id="56eec-117">Resizing Controls Using Snaplines</span></span>  
  
-   <span data-ttu-id="56eec-118">对齐到控件的文本标签</span><span class="sxs-lookup"><span data-stu-id="56eec-118">Aligning a Label to a Control's Text</span></span>  
  
-   <span data-ttu-id="56eec-119">使用对齐线和键盘导航</span><span class="sxs-lookup"><span data-stu-id="56eec-119">Using Snaplines with Keyboard Navigation</span></span>  
  
-   <span data-ttu-id="56eec-120">对齐线和布局面板</span><span class="sxs-lookup"><span data-stu-id="56eec-120">Snaplines and Layout Panels</span></span>  
  
-   <span data-ttu-id="56eec-121">禁用对齐线</span><span class="sxs-lookup"><span data-stu-id="56eec-121">Disabling Snaplines</span></span>  
  
 <span data-ttu-id="56eec-122">完成后，必须了解所发挥的对齐线功能布局作用。</span><span class="sxs-lookup"><span data-stu-id="56eec-122">When you are finished, you will have an understanding of the layout role played by the snaplines feature.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="56eec-123">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="56eec-123">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="56eec-124">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="56eec-124">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="56eec-125">有关详细信息，请参阅[个性化设置 Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)。</span><span class="sxs-lookup"><span data-stu-id="56eec-125">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="56eec-126">创建项目</span><span class="sxs-lookup"><span data-stu-id="56eec-126">Creating the Project</span></span>  
 <span data-ttu-id="56eec-127">第一步是创建项目并设置窗体。</span><span class="sxs-lookup"><span data-stu-id="56eec-127">The first step is to create the project and set up the form.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="56eec-128">要创建项目</span><span class="sxs-lookup"><span data-stu-id="56eec-128">To create the project</span></span>  
  
1.  <span data-ttu-id="56eec-129">创建一个名为"SnaplineExample"的基于 Windows 的应用程序项目 (**文件** > **新建** > **项目** >  **Visual C#** 或**Visual Basic** > **经典桌面** > **Windows 窗体应用程序**)。</span><span class="sxs-lookup"><span data-stu-id="56eec-129">Create a Windows-based application project called "SnaplineExample" (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>  
  
2.  <span data-ttu-id="56eec-130">在窗体设计器中选择窗体。</span><span class="sxs-lookup"><span data-stu-id="56eec-130">Select the form in the Forms Designer.</span></span>  
  
## <a name="spacing-and-aligning-controls-using-snaplines"></a><span data-ttu-id="56eec-131">间距和对齐控件使用对齐线</span><span class="sxs-lookup"><span data-stu-id="56eec-131">Spacing and Aligning Controls Using Snaplines</span></span>  
 <span data-ttu-id="56eec-132">对齐线使您可以在你的窗体上对齐控件准确而直观的方式。</span><span class="sxs-lookup"><span data-stu-id="56eec-132">Snaplines give you an accurate and intuitive way to align controls on your form.</span></span> <span data-ttu-id="56eec-133">它们就符合与另一个控件或一组控件的位置附近移动选定的控件时。</span><span class="sxs-lookup"><span data-stu-id="56eec-133">They appear when you are moving a selected control or controls near a position that would align with another control or set of controls.</span></span> <span data-ttu-id="56eec-134">你的选择将"对齐"到建议的位置为越过其他控件。</span><span class="sxs-lookup"><span data-stu-id="56eec-134">Your selection will "snap" to the suggested position as you move it past the other controls.</span></span>  
  
#### <a name="to-arrange-controls-using-snaplines"></a><span data-ttu-id="56eec-135">使用对齐线排列控件</span><span class="sxs-lookup"><span data-stu-id="56eec-135">To arrange controls using snaplines</span></span>  
  
1.  <span data-ttu-id="56eec-136">拖动<xref:System.Windows.Forms.Button>控件从**工具箱**拖动到窗体。</span><span class="sxs-lookup"><span data-stu-id="56eec-136">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto your form.</span></span>  
  
2.  <span data-ttu-id="56eec-137">移动<xref:System.Windows.Forms.Button>的窗体右下角的控件。</span><span class="sxs-lookup"><span data-stu-id="56eec-137">Move the <xref:System.Windows.Forms.Button> control to the lower-right corner of the form.</span></span> <span data-ttu-id="56eec-138">请注意对齐线显示为<xref:System.Windows.Forms.Button>控件接近下边框和右边框的窗体。</span><span class="sxs-lookup"><span data-stu-id="56eec-138">Note the snaplines that appear as the <xref:System.Windows.Forms.Button> control approaches the bottom and right borders of the form.</span></span> <span data-ttu-id="56eec-139">这些对齐线显示在窗体控件的边框之间的建议的距离。</span><span class="sxs-lookup"><span data-stu-id="56eec-139">These snaplines display the recommended distance between the borders of the control and the form.</span></span>  
  
3.  <span data-ttu-id="56eec-140">移动<xref:System.Windows.Forms.Button>控件周围的边框窗体和注意对齐线的显示位置。</span><span class="sxs-lookup"><span data-stu-id="56eec-140">Move the <xref:System.Windows.Forms.Button> control around the borders of the form and note where the snaplines appear.</span></span> <span data-ttu-id="56eec-141">在完成后，请移动<xref:System.Windows.Forms.Button>窗体的中心附近的控件。</span><span class="sxs-lookup"><span data-stu-id="56eec-141">When you are finished, move the <xref:System.Windows.Forms.Button> control near the center of the form.</span></span>  
  
4.  <span data-ttu-id="56eec-142">将另一个<xref:System.Windows.Forms.Button>控件从**工具箱**拖动到窗体。</span><span class="sxs-lookup"><span data-stu-id="56eec-142">Drag another <xref:System.Windows.Forms.Button> control from the **Toolbox** onto your form.</span></span>  
  
5.  <span data-ttu-id="56eec-143">移动第二个<xref:System.Windows.Forms.Button>控制直到几乎与第一个级别。</span><span class="sxs-lookup"><span data-stu-id="56eec-143">Move the second <xref:System.Windows.Forms.Button> control until it is nearly level with the first.</span></span> <span data-ttu-id="56eec-144">请注意出现在这两个按钮的文本基线对齐线，并记下要移动的控件对齐到的位置，则完全与另一个控件的级别。</span><span class="sxs-lookup"><span data-stu-id="56eec-144">Note the snapline that appears at the text baseline of both buttons, and note that the control you are moving snaps to a position that is exactly level with the other control.</span></span>  
  
6.  <span data-ttu-id="56eec-145">移动第二个<xref:System.Windows.Forms.Button>控件，直到它位于正上方第一个。</span><span class="sxs-lookup"><span data-stu-id="56eec-145">Move the second <xref:System.Windows.Forms.Button> control until it is positioned directly above the first.</span></span> <span data-ttu-id="56eec-146">请注意对齐线沿两个按钮的左侧和右侧边缘显示，请注意，该控件要移动到完全对应与另一个控件的位置的快照。</span><span class="sxs-lookup"><span data-stu-id="56eec-146">Note the snaplines that appear along the left and right edges of both buttons, and note that the control you are moving snaps to a position that is exactly aligned with the other control.</span></span>  
  
7.  <span data-ttu-id="56eec-147">选择其中一个<xref:System.Windows.Forms.Button>控制并将其移近另一个，直到它们几乎触摸。</span><span class="sxs-lookup"><span data-stu-id="56eec-147">Select one of the <xref:System.Windows.Forms.Button> controls and move it close to the other, until they are almost touching.</span></span> <span data-ttu-id="56eec-148">请注意它们之间出现对齐线。</span><span class="sxs-lookup"><span data-stu-id="56eec-148">Note the snapline that appears between them.</span></span> <span data-ttu-id="56eec-149">此距离是控件的边框之间的建议的距离。</span><span class="sxs-lookup"><span data-stu-id="56eec-149">This distance is the recommended distance between the borders of the controls.</span></span> <span data-ttu-id="56eec-150">另请注意要移动的控件对齐到此位置。</span><span class="sxs-lookup"><span data-stu-id="56eec-150">Also note that the control you are moving snaps to this position.</span></span>  
  
8.  <span data-ttu-id="56eec-151">将两个<xref:System.Windows.Forms.Panel>控件从**工具箱**拖动到窗体。</span><span class="sxs-lookup"><span data-stu-id="56eec-151">Drag two <xref:System.Windows.Forms.Panel> controls from the **Toolbox** onto your form.</span></span>  
  
9. <span data-ttu-id="56eec-152">将其中一个移动<xref:System.Windows.Forms.Panel>控件，直到它是几乎与第一个级别。</span><span class="sxs-lookup"><span data-stu-id="56eec-152">Move one of the <xref:System.Windows.Forms.Panel> controls until it is nearly level with the first.</span></span> <span data-ttu-id="56eec-153">请注意这两个控件边缘和下边缘沿显示并记下要移动的控件对齐到的位置，则完全级别与另一个控件的对齐线。</span><span class="sxs-lookup"><span data-stu-id="56eec-153">Note the snaplines that appear along the top and bottom edges of both controls, and note that the control you are moving snaps to a position that is exactly level with the other control.</span></span>  
  
## <a name="aligning-to-form-and-container-margins"></a><span data-ttu-id="56eec-154">向窗体和容器的边缘对齐</span><span class="sxs-lookup"><span data-stu-id="56eec-154">Aligning to Form and Container Margins</span></span>  
 <span data-ttu-id="56eec-155">对齐线帮助您将控件与窗体和容器边缘对齐以一致的方式。</span><span class="sxs-lookup"><span data-stu-id="56eec-155">Snaplines help you to align your controls to form and container margins in a consistent manner.</span></span>  
  
#### <a name="to-align-controls-to-form-and-container-margins"></a><span data-ttu-id="56eec-156">若要将控件添加到窗体和容器边缘对齐</span><span class="sxs-lookup"><span data-stu-id="56eec-156">To align controls to form and container margins</span></span>  
  
1.  <span data-ttu-id="56eec-157">选择其中一个<xref:System.Windows.Forms.Button>控制并将其移近右边框的窗体中，直到显示对齐线。</span><span class="sxs-lookup"><span data-stu-id="56eec-157">Select one of the <xref:System.Windows.Forms.Button> controls and move it close to the right border of the form until a snapline appears.</span></span> <span data-ttu-id="56eec-158">从右边框对齐线的距离是控件的总和<xref:System.Windows.Forms.Control.Margin%2A>属性和窗体的<xref:System.Windows.Forms.Control.Padding%2A>属性值。</span><span class="sxs-lookup"><span data-stu-id="56eec-158">The snapline's distance from the right border is the sum of the control's <xref:System.Windows.Forms.Control.Margin%2A> property and the form's <xref:System.Windows.Forms.Control.Padding%2A> property values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="56eec-159">如果窗体的<xref:System.Windows.Forms.Control.Padding%2A>属性设置为 0,0,0,0、 Windows 窗体设计器将为窗体指定隐藏<xref:System.Windows.Forms.Control.Padding%2A>9,9,9,9 的值。</span><span class="sxs-lookup"><span data-stu-id="56eec-159">If the form's <xref:System.Windows.Forms.Control.Padding%2A> property is set to 0,0,0,0, the Windows Forms Designer gives the form a shadowed <xref:System.Windows.Forms.Control.Padding%2A> value of 9,9,9,9.</span></span> <span data-ttu-id="56eec-160">若要重写此行为，分配 0,0,0,0 以外的值。</span><span class="sxs-lookup"><span data-stu-id="56eec-160">To override this behavior, assign a value other than 0,0,0,0.</span></span>  
  
1.  <span data-ttu-id="56eec-161">更改的值<xref:System.Windows.Forms.Button>控件的<xref:System.Windows.Forms.Control.Margin%2A>展开属性<xref:System.Windows.Forms.Control.Margin%2A>中的条目**属性**窗口和设置<xref:System.Windows.Forms.Padding.All%2A>属性设为 0。</span><span class="sxs-lookup"><span data-stu-id="56eec-161">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Margin%2A> property by expanding the <xref:System.Windows.Forms.Control.Margin%2A> entry in the **Properties** window and setting the <xref:System.Windows.Forms.Padding.All%2A> property to 0.</span></span> <span data-ttu-id="56eec-162">有关详细信息，请参阅[演练： 对进行布局出 Windows 窗体控件与 Padding、 Margins 和 AutoSize 属性](../../../../docs/framework/winforms/controls/windows-forms-controls-padding-autosize.md)。</span><span class="sxs-lookup"><span data-stu-id="56eec-162">For details, see [Walkthrough: Laying Out Windows Forms Controls with Padding, Margins, and the AutoSize Property](../../../../docs/framework/winforms/controls/windows-forms-controls-padding-autosize.md).</span></span>  
  
2.  <span data-ttu-id="56eec-163">移动<xref:System.Windows.Forms.Button>接近直到对齐线显示在窗体的右边框的控件。</span><span class="sxs-lookup"><span data-stu-id="56eec-163">Move the <xref:System.Windows.Forms.Button> control close to the right border of the form until a snapline appears.</span></span> <span data-ttu-id="56eec-164">窗体的值现在提供此距离<xref:System.Windows.Forms.Control.Padding%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="56eec-164">This distance is now given by the value of the form's <xref:System.Windows.Forms.Control.Padding%2A> property.</span></span>  
  
3.  <span data-ttu-id="56eec-165">拖动<xref:System.Windows.Forms.GroupBox>控件从**工具箱**拖动到窗体。</span><span class="sxs-lookup"><span data-stu-id="56eec-165">Drag a <xref:System.Windows.Forms.GroupBox> control from the **Toolbox** onto your form.</span></span>  
  
4.  <span data-ttu-id="56eec-166">更改的值<xref:System.Windows.Forms.GroupBox>控件的<xref:System.Windows.Forms.Control.Padding%2A>展开属性<xref:System.Windows.Forms.Control.Padding%2A>中的条目**属性**窗口和设置<xref:System.Windows.Forms.Padding.All%2A>属性设置为 10。</span><span class="sxs-lookup"><span data-stu-id="56eec-166">Change the value of the <xref:System.Windows.Forms.GroupBox> control's <xref:System.Windows.Forms.Control.Padding%2A> property by expanding the <xref:System.Windows.Forms.Control.Padding%2A> entry in the **Properties** window and setting the <xref:System.Windows.Forms.Padding.All%2A> property to 10.</span></span>  
  
5.  <span data-ttu-id="56eec-167">拖动<xref:System.Windows.Forms.Button>控件从**工具箱**到<xref:System.Windows.Forms.GroupBox>控件。</span><span class="sxs-lookup"><span data-stu-id="56eec-167">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** into the <xref:System.Windows.Forms.GroupBox> control.</span></span>  
  
6.  <span data-ttu-id="56eec-168">移动<xref:System.Windows.Forms.Button>控件的右边框的接近<xref:System.Windows.Forms.GroupBox>控件，直到出现对齐线。</span><span class="sxs-lookup"><span data-stu-id="56eec-168">Move the <xref:System.Windows.Forms.Button> control close to the right border of the <xref:System.Windows.Forms.GroupBox> control until a snapline appears.</span></span> <span data-ttu-id="56eec-169">移动<xref:System.Windows.Forms.Button>控件中<xref:System.Windows.Forms.GroupBox>控件并记下对齐线的显示位置。</span><span class="sxs-lookup"><span data-stu-id="56eec-169">Move the <xref:System.Windows.Forms.Button> control within the <xref:System.Windows.Forms.GroupBox> control and note where the snaplines appear.</span></span>  
  
## <a name="aligning-to-grouped-controls"></a><span data-ttu-id="56eec-170">对齐到分组后的控件</span><span class="sxs-lookup"><span data-stu-id="56eec-170">Aligning to Grouped Controls</span></span>  
 <span data-ttu-id="56eec-171">您可以使用对齐线对齐分组后的控件一样，很好地控制内<xref:System.Windows.Forms.GroupBox>控件。</span><span class="sxs-lookup"><span data-stu-id="56eec-171">You can use snaplines to align grouped controls as well as controls within a <xref:System.Windows.Forms.GroupBox> control.</span></span>  
  
#### <a name="to-align-to-grouped-controls"></a><span data-ttu-id="56eec-172">对齐到一组控件</span><span class="sxs-lookup"><span data-stu-id="56eec-172">To align to grouped controls</span></span>  
  
1.  <span data-ttu-id="56eec-173">选择两个窗体上的控件。</span><span class="sxs-lookup"><span data-stu-id="56eec-173">Select two of the controls on your form.</span></span> <span data-ttu-id="56eec-174">移动所选内容并记下你的选择和其他控件之间显示的对齐线。</span><span class="sxs-lookup"><span data-stu-id="56eec-174">Move the selection around and note the snaplines that appear between your selection and the other controls.</span></span>  
  
2.  <span data-ttu-id="56eec-175">拖动<xref:System.Windows.Forms.GroupBox>控件从**工具箱**拖动到窗体。</span><span class="sxs-lookup"><span data-stu-id="56eec-175">Drag a <xref:System.Windows.Forms.GroupBox> control from the **Toolbox** onto your form.</span></span>  
  
3.  <span data-ttu-id="56eec-176">拖动<xref:System.Windows.Forms.Button>控件从**工具箱**到<xref:System.Windows.Forms.GroupBox>控件。</span><span class="sxs-lookup"><span data-stu-id="56eec-176">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** into the <xref:System.Windows.Forms.GroupBox> control.</span></span>  
  
4.  <span data-ttu-id="56eec-177">选择其中一个<xref:System.Windows.Forms.Button>控制并将其四处移动<xref:System.Windows.Forms.GroupBox>控件。</span><span class="sxs-lookup"><span data-stu-id="56eec-177">Select one of the <xref:System.Windows.Forms.Button> controls and move it around the <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="56eec-178">请注意显示的边缘的对齐线<xref:System.Windows.Forms.GroupBox>控件。</span><span class="sxs-lookup"><span data-stu-id="56eec-178">Note the snaplines that appear at the edges of the <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="56eec-179">另请注意显示的边缘的对齐线<xref:System.Windows.Forms.Button>包含由控件<xref:System.Windows.Forms.GroupBox>控件。</span><span class="sxs-lookup"><span data-stu-id="56eec-179">Also note the snaplines that appear at the edges of the <xref:System.Windows.Forms.Button> control that is contained by the <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="56eec-180">容器控件的子级的控件还支持对齐线。</span><span class="sxs-lookup"><span data-stu-id="56eec-180">Controls that are children of a container control also support snaplines.</span></span>  
  
## <a name="using-snaplines-to-place-a-control-by-outlining-its-size"></a><span data-ttu-id="56eec-181">使用对齐线将控件的大纲显示其大小</span><span class="sxs-lookup"><span data-stu-id="56eec-181">Using Snaplines to Place a Control by Outlining Its Size</span></span>  
 <span data-ttu-id="56eec-182">对齐线帮助您对齐控件时，首先将它们放在窗体上。</span><span class="sxs-lookup"><span data-stu-id="56eec-182">Snaplines help you align controls when you first place them on a form.</span></span>  
  
#### <a name="to-use-snaplines-to-place-a-control-by-outlining-its-size"></a><span data-ttu-id="56eec-183">若要使用对齐线将控件置于大纲显示其大小</span><span class="sxs-lookup"><span data-stu-id="56eec-183">To use snaplines to place a control by outlining its size</span></span>  
  
1.  <span data-ttu-id="56eec-184">在“工具箱” 中，单击 <xref:System.Windows.Forms.Button> 控件图标。</span><span class="sxs-lookup"><span data-stu-id="56eec-184">In the **Toolbox**, click the <xref:System.Windows.Forms.Button> control icon.</span></span> <span data-ttu-id="56eec-185">请勿将其拖到窗体上。</span><span class="sxs-lookup"><span data-stu-id="56eec-185">Do not drag it onto the form.</span></span>  
  
2.  <span data-ttu-id="56eec-186">将鼠标指针移动窗体的设计图面。</span><span class="sxs-lookup"><span data-stu-id="56eec-186">Move the mouse pointer over the form's design surface.</span></span> <span data-ttu-id="56eec-187">请注意，指针会更改为十字形，同时会附上 <xref:System.Windows.Forms.Button> 控件图标。</span><span class="sxs-lookup"><span data-stu-id="56eec-187">Note that the pointer changes to a crosshair with the <xref:System.Windows.Forms.Button> control icon attached.</span></span> <span data-ttu-id="56eec-188">另请注意显示建议的对齐的位置的对齐线<xref:System.Windows.Forms.Button>控件。</span><span class="sxs-lookup"><span data-stu-id="56eec-188">Also note the snaplines that appear to suggest aligned positions for the <xref:System.Windows.Forms.Button> control.</span></span>  
  
3.  <span data-ttu-id="56eec-189">单击并按住鼠标按钮。</span><span class="sxs-lookup"><span data-stu-id="56eec-189">Click and hold the mouse button.</span></span>  
  
4.  <span data-ttu-id="56eec-190">拖动鼠标指针在窗体。</span><span class="sxs-lookup"><span data-stu-id="56eec-190">Drag the mouse pointer around the form.</span></span> <span data-ttu-id="56eec-191">请注意，绘制轮廓，指示的位置和控件的大小。</span><span class="sxs-lookup"><span data-stu-id="56eec-191">Note that an outline is drawn, indicating the position and the size of the control.</span></span>  
  
5.  <span data-ttu-id="56eec-192">拖动指针，直到它与另一个控件在窗体上对齐。</span><span class="sxs-lookup"><span data-stu-id="56eec-192">Drag the pointer until it aligns with another control on the form.</span></span> <span data-ttu-id="56eec-193">请注意，对齐线将出现以指示对齐方式。</span><span class="sxs-lookup"><span data-stu-id="56eec-193">Note that a snapline appears to indicate alignment.</span></span>  
  
6.  <span data-ttu-id="56eec-194">释放鼠标按钮。</span><span class="sxs-lookup"><span data-stu-id="56eec-194">Release the mouse button.</span></span> <span data-ttu-id="56eec-195">在的位置和大小由概要中创建控件。</span><span class="sxs-lookup"><span data-stu-id="56eec-195">The control is created at the position and size indicated by the outline.</span></span>  
  
## <a name="using-snaplines-when-dragging-a-control-from-the-toolbox"></a><span data-ttu-id="56eec-196">从工具箱拖动控件时使用对齐线</span><span class="sxs-lookup"><span data-stu-id="56eec-196">Using Snaplines When Dragging a Control from the Toolbox</span></span>  
 <span data-ttu-id="56eec-197">对齐线帮助您对齐控件时将它们从**工具箱**拖动到窗体。</span><span class="sxs-lookup"><span data-stu-id="56eec-197">Snaplines help you align controls when you drag them from the **Toolbox** onto your form.</span></span>  
  
#### <a name="to-use-snaplines-when-dragging-a-control-from-the-toolbox"></a><span data-ttu-id="56eec-198">若要从工具箱拖动控件时使用对齐线</span><span class="sxs-lookup"><span data-stu-id="56eec-198">To use snaplines when dragging a control from the Toolbox</span></span>  
  
1.  <span data-ttu-id="56eec-199">拖动<xref:System.Windows.Forms.Button>控件从**工具箱**拖动到窗体，但不会释放鼠标按钮。</span><span class="sxs-lookup"><span data-stu-id="56eec-199">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto your form, but do not release the mouse button.</span></span>  
  
2.  <span data-ttu-id="56eec-200">将鼠标指针移动窗体的设计图面。</span><span class="sxs-lookup"><span data-stu-id="56eec-200">Move the mouse pointer over the form's design surface.</span></span> <span data-ttu-id="56eec-201">请注意，指针更改以指示在其位置的新<xref:System.Windows.Forms.Button>将创建控件。</span><span class="sxs-lookup"><span data-stu-id="56eec-201">Note that the pointer changes to indicate the position at which the new <xref:System.Windows.Forms.Button> control will be created.</span></span>  
  
3.  <span data-ttu-id="56eec-202">拖动鼠标指针在窗体。</span><span class="sxs-lookup"><span data-stu-id="56eec-202">Drag the mouse pointer around the form.</span></span> <span data-ttu-id="56eec-203">请注意显示建议的对齐的位置的对齐线<xref:System.Windows.Forms.Button>控件。</span><span class="sxs-lookup"><span data-stu-id="56eec-203">Note the snaplines that appear to suggest aligned positions for the <xref:System.Windows.Forms.Button> control.</span></span> <span data-ttu-id="56eec-204">查找与其他控件对齐位置。</span><span class="sxs-lookup"><span data-stu-id="56eec-204">Find a position that is aligned with other controls.</span></span>  
  
4.  <span data-ttu-id="56eec-205">释放鼠标按钮。</span><span class="sxs-lookup"><span data-stu-id="56eec-205">Release the mouse button.</span></span> <span data-ttu-id="56eec-206">在指示对齐线的位置创建控件。</span><span class="sxs-lookup"><span data-stu-id="56eec-206">The control is created at the position indicated by the snaplines.</span></span>  
  
## <a name="resizing-controls-using-snaplines"></a><span data-ttu-id="56eec-207">调整控件使用对齐线的大小</span><span class="sxs-lookup"><span data-stu-id="56eec-207">Resizing Controls Using Snaplines</span></span>  
 <span data-ttu-id="56eec-208">对齐线帮助您对齐控件调整其大小。</span><span class="sxs-lookup"><span data-stu-id="56eec-208">Snaplines help you align controls as you resize them.</span></span>  
  
#### <a name="to-resize-a-control-using-snaplines"></a><span data-ttu-id="56eec-209">调整控件使用对齐线的大小</span><span class="sxs-lookup"><span data-stu-id="56eec-209">To resize a control using snaplines</span></span>  
  
1.  <span data-ttu-id="56eec-210">拖动<xref:System.Windows.Forms.Button>控件从**工具箱**拖动到窗体。</span><span class="sxs-lookup"><span data-stu-id="56eec-210">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto your form.</span></span>  
  
2.  <span data-ttu-id="56eec-211">重设大小<xref:System.Windows.Forms.Button>抓住角大小调整控点和拖动某个控件。</span><span class="sxs-lookup"><span data-stu-id="56eec-211">Resize the <xref:System.Windows.Forms.Button> control by grabbing one of the corner sizing handles and dragging.</span></span> <span data-ttu-id="56eec-212">有关详细信息，请参阅[如何： 调整 Windows 窗体上的控件](../../../../docs/framework/winforms/controls/how-to-resize-controls-on-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="56eec-212">For details, see [How to: Resize Controls on Windows Forms](../../../../docs/framework/winforms/controls/how-to-resize-controls-on-windows-forms.md).</span></span>  
  
3.  <span data-ttu-id="56eec-213">拖动调整大小控点，直到一位<xref:System.Windows.Forms.Button>与其他控件对齐控件的边框。</span><span class="sxs-lookup"><span data-stu-id="56eec-213">Drag the sizing handle until one of the <xref:System.Windows.Forms.Button> control's borders is aligned with another control.</span></span> <span data-ttu-id="56eec-214">请注意，显示对齐线。</span><span class="sxs-lookup"><span data-stu-id="56eec-214">Note that a snapline appears.</span></span> <span data-ttu-id="56eec-215">另请注意，调整大小控点会对齐到对齐线指示的位置。</span><span class="sxs-lookup"><span data-stu-id="56eec-215">Also note that the sizing handle snaps to the position indicated by the snapline.</span></span>  
  
4.  <span data-ttu-id="56eec-216">重设大小<xref:System.Windows.Forms.Button>控制在不同的方向和对齐到不同的控件的大小调整句柄。</span><span class="sxs-lookup"><span data-stu-id="56eec-216">Resize the <xref:System.Windows.Forms.Button> control in different directions and align the sizing handle to different controls.</span></span> <span data-ttu-id="56eec-217">请注意如何对齐线显示在不同的方向，以指示对齐方式。</span><span class="sxs-lookup"><span data-stu-id="56eec-217">Note how the snaplines appear in various orientations to indicate alignment.</span></span>  
  
## <a name="aligning-a-label-to-a-controls-text"></a><span data-ttu-id="56eec-218">对齐到控件的文本标签</span><span class="sxs-lookup"><span data-stu-id="56eec-218">Aligning a Label to a Control's Text</span></span>  
 <span data-ttu-id="56eec-219">某些控件提供了用于对齐到显示的文本的其他控件的对齐线。</span><span class="sxs-lookup"><span data-stu-id="56eec-219">Some controls offer a snapline for aligning other controls to displayed text.</span></span>  
  
#### <a name="to-align-a-label-to-a-controls-text"></a><span data-ttu-id="56eec-220">若要对齐到控件的文本标签</span><span class="sxs-lookup"><span data-stu-id="56eec-220">To align a label to a control's text</span></span>  
  
1.  <span data-ttu-id="56eec-221">拖动<xref:System.Windows.Forms.TextBox>控件从**工具箱**拖动到窗体。</span><span class="sxs-lookup"><span data-stu-id="56eec-221">Drag a <xref:System.Windows.Forms.TextBox> control from the **Toolbox** onto your form.</span></span> <span data-ttu-id="56eec-222">当 drop<xref:System.Windows.Forms.TextBox>拖到窗体控件，单击智能标记标志符号，选择**将文本设置为 textBox1**选项。</span><span class="sxs-lookup"><span data-stu-id="56eec-222">When you drop the <xref:System.Windows.Forms.TextBox> control onto the form, click the smart-tag glyph and select the **Set text to textBox1** option.</span></span> <span data-ttu-id="56eec-223">有关详细信息，请参阅[演练： 执行常见任务使用智能标记 Windows 窗体控件上](../../../../docs/framework/winforms/controls/performing-common-tasks-using-smart-tags-on-wf-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="56eec-223">For details, see [Walkthrough: Performing Common Tasks Using Smart Tags on Windows Forms Controls](../../../../docs/framework/winforms/controls/performing-common-tasks-using-smart-tags-on-wf-controls.md).</span></span>  
  
2.  <span data-ttu-id="56eec-224">拖动<xref:System.Windows.Forms.Label>控件从**工具箱**拖动到窗体。</span><span class="sxs-lookup"><span data-stu-id="56eec-224">Drag a <xref:System.Windows.Forms.Label> control from the **Toolbox** onto your form.</span></span>  
  
3.  <span data-ttu-id="56eec-225">将 <xref:System.Windows.Forms.Label> 控件的 <xref:System.Windows.Forms.Control.AutoSize%2A> 属性值更改为 `true`。</span><span class="sxs-lookup"><span data-stu-id="56eec-225">Change the value of the <xref:System.Windows.Forms.Label> control's <xref:System.Windows.Forms.Control.AutoSize%2A> property to `true`.</span></span> <span data-ttu-id="56eec-226">请注意该控件的边框调整为适合的显示文本。</span><span class="sxs-lookup"><span data-stu-id="56eec-226">Note that the control's borders are adjusted to fit the display text.</span></span>  
  
4.  <span data-ttu-id="56eec-227">移动<xref:System.Windows.Forms.Label>控件的左侧<xref:System.Windows.Forms.TextBox>控件，以便使用的下边缘对齐<xref:System.Windows.Forms.TextBox>控件。</span><span class="sxs-lookup"><span data-stu-id="56eec-227">Move the <xref:System.Windows.Forms.Label> control to the left of the <xref:System.Windows.Forms.TextBox> control, so it is aligned with the bottom edge of the <xref:System.Windows.Forms.TextBox> control.</span></span> <span data-ttu-id="56eec-228">请注意两个控件的底部边缘的对齐线。</span><span class="sxs-lookup"><span data-stu-id="56eec-228">Note the snapline that appears along the bottom edges of the two controls.</span></span>  
  
5.  <span data-ttu-id="56eec-229">移动<xref:System.Windows.Forms.Label>控制略微向上，直到<xref:System.Windows.Forms.Label>文本和<xref:System.Windows.Forms.TextBox>对齐文本。</span><span class="sxs-lookup"><span data-stu-id="56eec-229">Move the <xref:System.Windows.Forms.Label> control slightly upward, until the <xref:System.Windows.Forms.Label> text and the <xref:System.Windows.Forms.TextBox> text are aligned.</span></span> <span data-ttu-id="56eec-230">请注意以不同的方式应用了样式显示，该值指示当对齐这两个控件的文本字段的对齐线。</span><span class="sxs-lookup"><span data-stu-id="56eec-230">Note the differently styled snapline that appears, indicating when the text fields of both controls are aligned.</span></span>  
  
## <a name="using-snaplines-with-keyboard-navigation"></a><span data-ttu-id="56eec-231">使用对齐线和键盘导航</span><span class="sxs-lookup"><span data-stu-id="56eec-231">Using Snaplines with Keyboard Navigation</span></span>  
 <span data-ttu-id="56eec-232">对齐线帮助您对齐控件时排列它们使用键盘上的箭头键。</span><span class="sxs-lookup"><span data-stu-id="56eec-232">Snaplines help you align controls when you are arranging them using the keyboard's arrow keys.</span></span>  
  
#### <a name="to-use-snaplines-with-keyboard-navigation"></a><span data-ttu-id="56eec-233">若要使用的键盘导航使用对齐线</span><span class="sxs-lookup"><span data-stu-id="56eec-233">To use snaplines with keyboard navigation</span></span>  
  
1.  <span data-ttu-id="56eec-234">拖动<xref:System.Windows.Forms.Button>控件从**工具箱**拖动到窗体。</span><span class="sxs-lookup"><span data-stu-id="56eec-234">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto your form.</span></span> <span data-ttu-id="56eec-235">将其放置在窗体的左上角。</span><span class="sxs-lookup"><span data-stu-id="56eec-235">Place it in the upper-left corner of the form.</span></span>  
  
2.  <span data-ttu-id="56eec-236">按 CTRL + 向下箭头。</span><span class="sxs-lookup"><span data-stu-id="56eec-236">Press CTRL+DOWN ARROW.</span></span> <span data-ttu-id="56eec-237">请注意，控件将向下移动窗体的第一个可用的水平对齐位置。</span><span class="sxs-lookup"><span data-stu-id="56eec-237">Note that the control moves down the form to the first available horizontal alignment position.</span></span>  
  
3.  <span data-ttu-id="56eec-238">按 CTRL + 向下箭头，直到该控件达到窗体的底部。</span><span class="sxs-lookup"><span data-stu-id="56eec-238">Press CTRL+DOWN ARROW until the control reaches the bottom of the form.</span></span> <span data-ttu-id="56eec-239">注意，它占用的是因为它将下移窗体的位置。</span><span class="sxs-lookup"><span data-stu-id="56eec-239">Note the positions it occupies as it moves down the form.</span></span>  
  
4.  <span data-ttu-id="56eec-240">按 CTRL + 向右键。</span><span class="sxs-lookup"><span data-stu-id="56eec-240">Press CTRL+RIGHT ARROW.</span></span> <span data-ttu-id="56eec-241">请注意，该控件在窗体移动到第一个可用的垂直对齐位置。</span><span class="sxs-lookup"><span data-stu-id="56eec-241">Note that the control moves across the form to the first available vertical alignment position.</span></span>  
  
5.  <span data-ttu-id="56eec-242">该控件在窗体左侧直到按 CTRL + 向右键。</span><span class="sxs-lookup"><span data-stu-id="56eec-242">Press CTRL+RIGHT ARROW until the control reaches the side of the form.</span></span> <span data-ttu-id="56eec-243">注意，它占用的是在窗体中移动的位置。</span><span class="sxs-lookup"><span data-stu-id="56eec-243">Note the positions it occupies as it moves across the form.</span></span>  
  
6.  <span data-ttu-id="56eec-244">使用箭头键的组合中移动窗体控件。</span><span class="sxs-lookup"><span data-stu-id="56eec-244">Move the control around the form with a combination of arrow keys.</span></span> <span data-ttu-id="56eec-245">请注意控件所占据的位置并附带有它们的对齐线。</span><span class="sxs-lookup"><span data-stu-id="56eec-245">Note the positions the control occupies and the snaplines that accompany them.</span></span>  
  
7.  <span data-ttu-id="56eec-246">按 SHIFT + 任意箭头键来调整大小<xref:System.Windows.Forms.Button>控件按 1 个像素的增量。</span><span class="sxs-lookup"><span data-stu-id="56eec-246">Press SHIFT+any arrow key to resize the <xref:System.Windows.Forms.Button> control by increments of one pixel.</span></span>  
  
8.  <span data-ttu-id="56eec-247">按 CTRL + SHIFT + 任意箭头键来调整大小<xref:System.Windows.Forms.Button>控件中对齐线的增量。</span><span class="sxs-lookup"><span data-stu-id="56eec-247">Press CTRL+SHIFT+any arrow key to resize the <xref:System.Windows.Forms.Button> control in snapline increments.</span></span>  
  
## <a name="snaplines-and-layout-panels"></a><span data-ttu-id="56eec-248">对齐线和布局面板</span><span class="sxs-lookup"><span data-stu-id="56eec-248">Snaplines and Layout Panels</span></span>  
 <span data-ttu-id="56eec-249">在布局面板内禁用对齐线。</span><span class="sxs-lookup"><span data-stu-id="56eec-249">Snaplines are disabled within layout panels.</span></span>  
  
#### <a name="to-selectively-disable-snaplines"></a><span data-ttu-id="56eec-250">若要有选择性地禁用对齐线</span><span class="sxs-lookup"><span data-stu-id="56eec-250">To selectively disable snaplines</span></span>  
  
1.  <span data-ttu-id="56eec-251">拖动<xref:System.Windows.Forms.TableLayoutPanel>控件从**工具箱**拖动到窗体。</span><span class="sxs-lookup"><span data-stu-id="56eec-251">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>  
  
2.  <span data-ttu-id="56eec-252">在“工具箱” <xref:System.Windows.Forms.Button>**中，双击**控件图标。</span><span class="sxs-lookup"><span data-stu-id="56eec-252">Double-click the <xref:System.Windows.Forms.Button> control icon in the **Toolbox**.</span></span> <span data-ttu-id="56eec-253">请注意，新按钮控件会出现在<xref:System.Windows.Forms.TableLayoutPanel>控件的第一个单元格。</span><span class="sxs-lookup"><span data-stu-id="56eec-253">Note that a new button control appears in the <xref:System.Windows.Forms.TableLayoutPanel> control's first cell.</span></span>  
  
3.  <span data-ttu-id="56eec-254">双击<xref:System.Windows.Forms.Button>中的控件图标**工具箱**两次。</span><span class="sxs-lookup"><span data-stu-id="56eec-254">Double-click the <xref:System.Windows.Forms.Button> control icon in the **Toolbox** twice more.</span></span> <span data-ttu-id="56eec-255">这将使中的一个空单元格<xref:System.Windows.Forms.TableLayoutPanel>控件。</span><span class="sxs-lookup"><span data-stu-id="56eec-255">This leaves one empty cell in the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
4.  <span data-ttu-id="56eec-256">拖动<xref:System.Windows.Forms.Button>控件从**工具箱**到的空单元格中<xref:System.Windows.Forms.TableLayoutPanel>控件。</span><span class="sxs-lookup"><span data-stu-id="56eec-256">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** into the empty cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span> <span data-ttu-id="56eec-257">请注意，会出现不对齐线。</span><span class="sxs-lookup"><span data-stu-id="56eec-257">Note that no snaplines appear.</span></span>  
  
5.  <span data-ttu-id="56eec-258">拖动<xref:System.Windows.Forms.Button>控制共<xref:System.Windows.Forms.TableLayoutPanel>控件并将其四处移动<xref:System.Windows.Forms.TableLayoutPanel>控件。</span><span class="sxs-lookup"><span data-stu-id="56eec-258">Drag the <xref:System.Windows.Forms.Button> control out of the <xref:System.Windows.Forms.TableLayoutPanel> control and move it around the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span> <span data-ttu-id="56eec-259">请注意，对齐线会再次出现。</span><span class="sxs-lookup"><span data-stu-id="56eec-259">Note that snaplines appear again.</span></span>  
  
## <a name="disabling-snaplines"></a><span data-ttu-id="56eec-260">禁用对齐线</span><span class="sxs-lookup"><span data-stu-id="56eec-260">Disabling Snaplines</span></span>  
 <span data-ttu-id="56eec-261">默认情况下启用对齐线。</span><span class="sxs-lookup"><span data-stu-id="56eec-261">Snaplines are turned on by default.</span></span> <span data-ttu-id="56eec-262">您可以有选择地，禁用对齐线或您可以在设计环境中禁用它们。</span><span class="sxs-lookup"><span data-stu-id="56eec-262">You can disable snaplines selectively, or you can disable them in the design environment.</span></span>  
  
#### <a name="to-selectively-disable-snaplines"></a><span data-ttu-id="56eec-263">若要有选择性地禁用对齐线</span><span class="sxs-lookup"><span data-stu-id="56eec-263">To selectively disable snaplines</span></span>  
  
-   <span data-ttu-id="56eec-264">按 ALT 键和而移动一个窗体控件。</span><span class="sxs-lookup"><span data-stu-id="56eec-264">Press the ALT key and while moving a control around the form.</span></span>  
  
     <span data-ttu-id="56eec-265">请注意，没有对齐线显示该控件不会按任何可能的对齐位置。</span><span class="sxs-lookup"><span data-stu-id="56eec-265">Note that no snaplines appear and the control does not snap to any potential alignment positions.</span></span>  
  
#### <a name="to-disable-snaplines-in-the-design-environment"></a><span data-ttu-id="56eec-266">若要禁用设计环境中的对齐线</span><span class="sxs-lookup"><span data-stu-id="56eec-266">To disable snaplines in the design environment</span></span>  
  
1.  <span data-ttu-id="56eec-267">从**工具**菜单中，打开**选项**对话框。</span><span class="sxs-lookup"><span data-stu-id="56eec-267">From the **Tools** menu, open the **Options** dialog box.</span></span> <span data-ttu-id="56eec-268">打开 Windows 窗体设计器对话框。</span><span class="sxs-lookup"><span data-stu-id="56eec-268">Open the Windows Forms Designer dialog box.</span></span> <span data-ttu-id="56eec-269">有关详细信息，请参阅[选项对话框常规 Windows 窗体设计器](https://msdn.microsoft.com/library/8dd170af-72f0-4212-b04b-034ceee92834)。</span><span class="sxs-lookup"><span data-stu-id="56eec-269">For details, see [General, Windows Forms Designer, Options Dialog Box](https://msdn.microsoft.com/library/8dd170af-72f0-4212-b04b-034ceee92834).</span></span>  
  
2.  <span data-ttu-id="56eec-270">选择**常规**节点。</span><span class="sxs-lookup"><span data-stu-id="56eec-270">Select the **General** node.</span></span> <span data-ttu-id="56eec-271">在中**布局模式下**部分中，更改从所选**对齐线**到**网格线对齐**。</span><span class="sxs-lookup"><span data-stu-id="56eec-271">In the **Layout Mode** section, change the selection from **SnapLines** to **SnapToGrid**.</span></span>  
  
3.  <span data-ttu-id="56eec-272">单击确定以应用设置。</span><span class="sxs-lookup"><span data-stu-id="56eec-272">Click OK to apply the setting.</span></span>  
  
4.  <span data-ttu-id="56eec-273">选择你的窗体上的控件，并移动其他控件。</span><span class="sxs-lookup"><span data-stu-id="56eec-273">Select a control on your form and move it around the other controls.</span></span> <span data-ttu-id="56eec-274">请注意，不会显示对齐线。</span><span class="sxs-lookup"><span data-stu-id="56eec-274">Note that snaplines do not appear.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="56eec-275">后续步骤</span><span class="sxs-lookup"><span data-stu-id="56eec-275">Next Steps</span></span>  
 <span data-ttu-id="56eec-276">对齐线提供了直观的窗体上的控件对齐方式。</span><span class="sxs-lookup"><span data-stu-id="56eec-276">Snaplines offer an intuitive means of aligning controls on your form.</span></span> <span data-ttu-id="56eec-277">有关进一步探索的建议包括：</span><span class="sxs-lookup"><span data-stu-id="56eec-277">Suggestions for more exploration include:</span></span>  
  
-   <span data-ttu-id="56eec-278">请尝试嵌套<xref:System.Windows.Forms.GroupBox>在另一个控件<xref:System.Windows.Forms.GroupBox>控件。</span><span class="sxs-lookup"><span data-stu-id="56eec-278">Try nesting a <xref:System.Windows.Forms.GroupBox> control within another <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="56eec-279">位置<xref:System.Windows.Forms.Button>内的子控件<xref:System.Windows.Forms.GroupBox>控件，并在父级内的另一个<xref:System.Windows.Forms.GroupBox>控件。</span><span class="sxs-lookup"><span data-stu-id="56eec-279">Place a <xref:System.Windows.Forms.Button> control within the child <xref:System.Windows.Forms.GroupBox> control, and another within the parent <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="56eec-280">移动<xref:System.Windows.Forms.Button>控件即可看到如何对齐线跨容器边界。</span><span class="sxs-lookup"><span data-stu-id="56eec-280">Move the <xref:System.Windows.Forms.Button> controls around to see how the snaplines cross container boundaries.</span></span>  
  
-   <span data-ttu-id="56eec-281">创建的列<xref:System.Windows.Forms.TextBox>控件与相应的列的<xref:System.Windows.Forms.Label>控件。</span><span class="sxs-lookup"><span data-stu-id="56eec-281">Create a column of <xref:System.Windows.Forms.TextBox> controls and a corresponding column of <xref:System.Windows.Forms.Label> controls.</span></span> <span data-ttu-id="56eec-282">设置的值<xref:System.Windows.Forms.Label>控件的<xref:System.Windows.Forms.Control.AutoSize%2A>属性设置为`true`。</span><span class="sxs-lookup"><span data-stu-id="56eec-282">Set the value of the <xref:System.Windows.Forms.Label> controls' <xref:System.Windows.Forms.Control.AutoSize%2A> property to `true`.</span></span> <span data-ttu-id="56eec-283">使用对齐线将移动<xref:System.Windows.Forms.Label>控制使其显示的文本与中的文本对齐<xref:System.Windows.Forms.TextBox>控件。</span><span class="sxs-lookup"><span data-stu-id="56eec-283">Use snaplines to move the <xref:System.Windows.Forms.Label> controls so their displayed text is aligned with the text in the <xref:System.Windows.Forms.TextBox> controls.</span></span>  
  
 <span data-ttu-id="56eec-284">有关 Windows 用户界面设计的信息，请参阅此书*Microsoft Windows 用户体验、 用户界面开发人员和设计人员的官方指南*Redmond，WA: Microsoft Press，1999年。</span><span class="sxs-lookup"><span data-stu-id="56eec-284">For information about Windows user interface design, see the book *Microsoft Windows User Experience, Official Guidelines for User Interface Developers and Designers* Redmond, WA: Microsoft Press, 1999.</span></span> <span data-ttu-id="56eec-285">(USBN: 0-7356-0566年-1)。</span><span class="sxs-lookup"><span data-stu-id="56eec-285">(USBN: 0-7356-0566-1).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56eec-286">请参阅</span><span class="sxs-lookup"><span data-stu-id="56eec-286">See Also</span></span>  
 <xref:System.Windows.Forms.Design.Behavior.SnapLine>  
 [<span data-ttu-id="56eec-287">演练：使用 FlowLayoutPanel 在 Windows 窗体上排列控件</span><span class="sxs-lookup"><span data-stu-id="56eec-287">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)  
 [<span data-ttu-id="56eec-288">演练：使用 TableLayoutPanel 在 Windows 窗体上排列控件</span><span class="sxs-lookup"><span data-stu-id="56eec-288">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)  
 [<span data-ttu-id="56eec-289">演练：使用 Padding、Margins 和 AutoSize 属性对 Windows 窗体控件进行布局</span><span class="sxs-lookup"><span data-stu-id="56eec-289">Walkthrough: Laying Out Windows Forms Controls with Padding, Margins, and the AutoSize Property</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-padding-autosize.md)  
 [<span data-ttu-id="56eec-290">在 Windows 窗体上排列控件</span><span class="sxs-lookup"><span data-stu-id="56eec-290">Arranging Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)
