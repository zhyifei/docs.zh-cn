---
title: 如何：测试 UserControl 的运行时行为
ms.date: 03/30/2017
helpviewer_keywords:
- UserControl class [Windows Forms], testing
- user controls [Windows Forms], testing
- composite controls [Windows Forms], testing
- UserControl Test Container
- UserControl class [Windows Forms], run-time behavior
ms.assetid: 4e4d5c49-1346-40ac-9d96-40211b573583
ms.openlocfilehash: 40ec136a86b52dcb007d15d5a2917212745961f2
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2018
ms.locfileid: "43392898"
---
# <a name="how-to-test-the-run-time-behavior-of-a-usercontrol"></a><span data-ttu-id="5e094-102">如何：测试 UserControl 的运行时行为</span><span class="sxs-lookup"><span data-stu-id="5e094-102">How to: Test the Run-Time Behavior of a UserControl</span></span>
<span data-ttu-id="5e094-103">开发时<xref:System.Windows.Forms.UserControl>，您需要测试其运行时行为。</span><span class="sxs-lookup"><span data-stu-id="5e094-103">When you develop a <xref:System.Windows.Forms.UserControl>, you need to test its run-time behavior.</span></span> <span data-ttu-id="5e094-104">可以创建一个单独的基于 Windows 的应用程序项目，并将你窗体控件的测试，但此过程是不方便。</span><span class="sxs-lookup"><span data-stu-id="5e094-104">You can create a separate Windows-based application project and place your control on a test form, but this procedure is inconvenient.</span></span> <span data-ttu-id="5e094-105">更快、 更轻松的方法是使用**UserControl 测试容器**Visual Studio 提供的。</span><span class="sxs-lookup"><span data-stu-id="5e094-105">A faster and easier way is to use the **UserControl Test Container** provided by Visual Studio.</span></span> <span data-ttu-id="5e094-106">此测试容器开始直接从 Windows 控件库项目。</span><span class="sxs-lookup"><span data-stu-id="5e094-106">This test container starts directly from your Windows control library project.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5e094-107">若要加载的测试容器在<xref:System.Windows.Forms.UserControl>，控件必须具有至少一个公共构造函数。</span><span class="sxs-lookup"><span data-stu-id="5e094-107">For the test container to load your <xref:System.Windows.Forms.UserControl>, the control must have at least one public constructor.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5e094-108">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="5e094-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="5e094-109">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="5e094-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="5e094-110">有关详细信息，请参阅[个性化设置 Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)。</span><span class="sxs-lookup"><span data-stu-id="5e094-110">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5e094-111">不能使用进行测试的 Visual c + + 控件**UserControl 测试容器**。</span><span class="sxs-lookup"><span data-stu-id="5e094-111">A Visual C++ control cannot be tested using the **UserControl Test Container**.</span></span>  
  
### <a name="to-test-the-run-time-behavior-of-a-usercontrol"></a><span data-ttu-id="5e094-112">若要测试 UserControl 的运行时行为</span><span class="sxs-lookup"><span data-stu-id="5e094-112">To test the run-time behavior of a UserControl</span></span>  
  
1.  <span data-ttu-id="5e094-113">创建一个名为的 Windows 控件库项目**TestContainerExample**。</span><span class="sxs-lookup"><span data-stu-id="5e094-113">Create a Windows control library project called **TestContainerExample**.</span></span> <span data-ttu-id="5e094-114">有关详细信息，请参阅[Windows 控件库模板](https://msdn.microsoft.com/library/722f4e2d-1310-4ed5-8f33-593337ab66b4)。</span><span class="sxs-lookup"><span data-stu-id="5e094-114">For details, see [Windows Control Library Template](https://msdn.microsoft.com/library/722f4e2d-1310-4ed5-8f33-593337ab66b4).</span></span>  
  
2.  <span data-ttu-id="5e094-115">在中**Windows 窗体设计器**，拖动<xref:System.Windows.Forms.Label>控件从**工具箱**到控件的设计图面。</span><span class="sxs-lookup"><span data-stu-id="5e094-115">In the **Windows Forms Designer**, drag a <xref:System.Windows.Forms.Label> control from the **Toolbox** onto the control's design surface.</span></span>  
  
3.  <span data-ttu-id="5e094-116">按 F5 以生成项目并运行**UserControl 测试容器**。</span><span class="sxs-lookup"><span data-stu-id="5e094-116">Press F5 to build the project and run the **UserControl Test Container**.</span></span> <span data-ttu-id="5e094-117">测试容器会显示与你<xref:System.Windows.Forms.UserControl>中**预览**窗格。</span><span class="sxs-lookup"><span data-stu-id="5e094-117">The test container appears with your <xref:System.Windows.Forms.UserControl> in the **Preview** pane.</span></span>  
  
4.  <span data-ttu-id="5e094-118">选择<xref:System.Windows.Forms.Control.BackColor%2A>属性中显示<xref:System.Windows.Forms.PropertyGrid>右侧的控件**预览**窗格。</span><span class="sxs-lookup"><span data-stu-id="5e094-118">Select the <xref:System.Windows.Forms.Control.BackColor%2A> property displayed in the <xref:System.Windows.Forms.PropertyGrid> control to the right of the **Preview** pane.</span></span> <span data-ttu-id="5e094-119">其值更改为`ControlDark`。</span><span class="sxs-lookup"><span data-stu-id="5e094-119">Change its value to `ControlDark`.</span></span> <span data-ttu-id="5e094-120">观察控件更改为较深的颜色。</span><span class="sxs-lookup"><span data-stu-id="5e094-120">Observe that the control changes to a darker color.</span></span> <span data-ttu-id="5e094-121">请尝试更改其他属性值，并观察在控件上的效果。</span><span class="sxs-lookup"><span data-stu-id="5e094-121">Try changing other property values and observe the effect on your control.</span></span>  
  
5.  <span data-ttu-id="5e094-122">单击**停靠填充用户控件**下面的复选框**预览**窗格。</span><span class="sxs-lookup"><span data-stu-id="5e094-122">Click the **Dock Fill User Control** check box below the **Preview** pane.</span></span> <span data-ttu-id="5e094-123">观察到该控件调整大小以填充窗格。</span><span class="sxs-lookup"><span data-stu-id="5e094-123">Observe that the control is resized to fill the pane.</span></span> <span data-ttu-id="5e094-124">调整测试容器的大小，并观察调整控件大小与窗格。</span><span class="sxs-lookup"><span data-stu-id="5e094-124">Resize the test container and observe that the control is resized with the pane.</span></span>  
  
6.  <span data-ttu-id="5e094-125">关闭测试容器。</span><span class="sxs-lookup"><span data-stu-id="5e094-125">Close the test container.</span></span>  
  
7.  <span data-ttu-id="5e094-126">另一个用户控件添加到**TestContainerExample**项目。</span><span class="sxs-lookup"><span data-stu-id="5e094-126">Add another user control to the **TestContainerExample** project.</span></span> <span data-ttu-id="5e094-127">有关详细信息，请参阅[NIB： 如何： 添加现有项添加至项目](https://msdn.microsoft.com/library/15f4cfb7-78ab-457f-9f14-099a25a6a2d3)。</span><span class="sxs-lookup"><span data-stu-id="5e094-127">For details, see [NIB:How to: Add Existing Items to a Project](https://msdn.microsoft.com/library/15f4cfb7-78ab-457f-9f14-099a25a6a2d3).</span></span>  
  
8.  <span data-ttu-id="5e094-128">在中**Windows 窗体设计器**，拖动<xref:System.Windows.Forms.Button>控件从**工具箱**到控件的设计图面。</span><span class="sxs-lookup"><span data-stu-id="5e094-128">In the **Windows Forms Designer**, drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto the control's design surface.</span></span>  
  
9. <span data-ttu-id="5e094-129">按 F5 以生成项目并运行测试容器。</span><span class="sxs-lookup"><span data-stu-id="5e094-129">Press F5 to build the project and run the test container.</span></span>  
  
10. <span data-ttu-id="5e094-130">单击**选择用户控件**<xref:System.Windows.Forms.ComboBox>两个用户控件之间进行切换。</span><span class="sxs-lookup"><span data-stu-id="5e094-130">Click the **Select User Control**<xref:System.Windows.Forms.ComboBox> to switch between the two user controls.</span></span>  
  
## <a name="testing-user-controls-from-another-project"></a><span data-ttu-id="5e094-131">从另一个项目的测试用户控件</span><span class="sxs-lookup"><span data-stu-id="5e094-131">Testing User Controls from Another Project</span></span>  
 <span data-ttu-id="5e094-132">在当前项目的测试容器中，可以测试其他项目中的用户控件。</span><span class="sxs-lookup"><span data-stu-id="5e094-132">You can test user controls from other projects in your current project's test container.</span></span>  
  
#### <a name="to-test-user-controls-from-another-project"></a><span data-ttu-id="5e094-133">若要测试从另一个项目的用户控件</span><span class="sxs-lookup"><span data-stu-id="5e094-133">To test user controls from another project</span></span>  
  
1.  <span data-ttu-id="5e094-134">创建一个名为的 Windows 控件库项目**TestContainerExample2**。</span><span class="sxs-lookup"><span data-stu-id="5e094-134">Create a Windows control library project called **TestContainerExample2**.</span></span> <span data-ttu-id="5e094-135">有关详细信息，请参阅[Windows 控件库模板](https://msdn.microsoft.com/library/722f4e2d-1310-4ed5-8f33-593337ab66b4)。</span><span class="sxs-lookup"><span data-stu-id="5e094-135">For details, see [Windows Control Library Template](https://msdn.microsoft.com/library/722f4e2d-1310-4ed5-8f33-593337ab66b4).</span></span>  
  
2.  <span data-ttu-id="5e094-136">在中**Windows 窗体设计器**，拖动<xref:System.Windows.Forms.RadioButton>控件从**工具箱**到控件的设计图面。</span><span class="sxs-lookup"><span data-stu-id="5e094-136">In the **Windows Forms Designer**, drag a <xref:System.Windows.Forms.RadioButton> control from the **Toolbox** onto the control's design surface.</span></span>  
  
3.  <span data-ttu-id="5e094-137">按 F5 以生成项目并运行测试容器。</span><span class="sxs-lookup"><span data-stu-id="5e094-137">Press F5 to build the project and run the test container.</span></span> <span data-ttu-id="5e094-138">测试容器会显示与你<xref:System.Windows.Forms.UserControl>中**预览**窗格。</span><span class="sxs-lookup"><span data-stu-id="5e094-138">The test container appears with your <xref:System.Windows.Forms.UserControl> in the **Preview** pane.</span></span>  
  
4.  <span data-ttu-id="5e094-139">单击**负载**按钮。</span><span class="sxs-lookup"><span data-stu-id="5e094-139">Click the **Load** button.</span></span>  
  
5.  <span data-ttu-id="5e094-140">在中**开放**对话框框中，导航到**TestContainerExample**.dll 上, 一个过程中生成。</span><span class="sxs-lookup"><span data-stu-id="5e094-140">In the **Open** dialog box, navigate to **TestContainerExample**.dll, which you built in the previous procedure.</span></span> <span data-ttu-id="5e094-141">选择**TestContainerExample**.dll，然后单击**打开**按钮以加载用户控件</span><span class="sxs-lookup"><span data-stu-id="5e094-141">Select **TestContainerExample**.dll and click the **Open** button to load the user controls</span></span>  
  
6.  <span data-ttu-id="5e094-142">使用**选择用户控件**<xref:System.Windows.Forms.ComboBox>若要从两个用户控件之间切换**TestContainerExample**项目。</span><span class="sxs-lookup"><span data-stu-id="5e094-142">Use the **Select User Control**<xref:System.Windows.Forms.ComboBox> to switch between the two user controls from the **TestContainerExample** project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e094-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="5e094-143">See Also</span></span>  
 <xref:System.Windows.Forms.UserControl>  
 [<span data-ttu-id="5e094-144">如何：创作复合控件</span><span class="sxs-lookup"><span data-stu-id="5e094-144">How to: Author Composite Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-author-composite-controls.md)  
 [<span data-ttu-id="5e094-145">演练：使用 Visual Basic 创作复合控件</span><span class="sxs-lookup"><span data-stu-id="5e094-145">Walkthrough: Authoring a Composite Control with Visual Basic</span></span>](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-basic.md)  
 [<span data-ttu-id="5e094-146">演练：使用 Visual C# 创作复合控件</span><span class="sxs-lookup"><span data-stu-id="5e094-146">Walkthrough: Authoring a Composite Control with Visual C#</span></span>](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-csharp.md)  
 [<span data-ttu-id="5e094-147">用户控件设计器</span><span class="sxs-lookup"><span data-stu-id="5e094-147">User Control Designer</span></span>](https://msdn.microsoft.com/library/2abb9eec-ba32-45cb-b73d-8b52a8bd6bf1)
