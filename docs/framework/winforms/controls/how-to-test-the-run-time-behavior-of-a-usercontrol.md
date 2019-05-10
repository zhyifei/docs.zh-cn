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
ms.openlocfilehash: 48531ab1ef3b30b6516e3f2e7b5858a8884cbfe8
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211715"
---
# <a name="how-to-test-the-run-time-behavior-of-a-usercontrol"></a><span data-ttu-id="46313-102">如何：测试 UserControl 的运行时行为</span><span class="sxs-lookup"><span data-stu-id="46313-102">How to: Test the run-time behavior of a UserControl</span></span>

<span data-ttu-id="46313-103">开发时<xref:System.Windows.Forms.UserControl>，您需要测试其运行时行为。</span><span class="sxs-lookup"><span data-stu-id="46313-103">When you develop a <xref:System.Windows.Forms.UserControl>, you need to test its run-time behavior.</span></span> <span data-ttu-id="46313-104">可以创建一个单独的基于 Windows 的应用程序项目，并将你窗体控件的测试，但此过程是不方便。</span><span class="sxs-lookup"><span data-stu-id="46313-104">You can create a separate Windows-based application project and place your control on a test form, but this procedure is inconvenient.</span></span> <span data-ttu-id="46313-105">更快、 更轻松的方法是使用**UserControl 测试容器**Visual Studio 提供的。</span><span class="sxs-lookup"><span data-stu-id="46313-105">A faster and easier way is to use the **UserControl Test Container** provided by Visual Studio.</span></span> <span data-ttu-id="46313-106">此测试容器开始直接从 Windows 控件库项目。</span><span class="sxs-lookup"><span data-stu-id="46313-106">This test container starts directly from your Windows control library project.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="46313-107">若要加载的测试容器在<xref:System.Windows.Forms.UserControl>，控件必须具有至少一个公共构造函数。</span><span class="sxs-lookup"><span data-stu-id="46313-107">For the test container to load your <xref:System.Windows.Forms.UserControl>, the control must have at least one public constructor.</span></span>

> [!NOTE]
> <span data-ttu-id="46313-108">视觉对象C++控件不能使用测试**UserControl 测试容器**。</span><span class="sxs-lookup"><span data-stu-id="46313-108">A Visual C++ control cannot be tested using the **UserControl Test Container**.</span></span>

## <a name="test-the-run-time-behavior-of-a-usercontrol"></a><span data-ttu-id="46313-109">测试 UserControl 的运行时行为</span><span class="sxs-lookup"><span data-stu-id="46313-109">Test the run-time behavior of a UserControl</span></span>

1. <span data-ttu-id="46313-110">在 Visual Studio 中，创建一个名为的 Windows 控件库项目**TestContainerExample**。</span><span class="sxs-lookup"><span data-stu-id="46313-110">In Visual Studio, create a Windows control library project called **TestContainerExample**.</span></span> <span data-ttu-id="46313-111">有关详细信息，请参阅[Windows 控件库模板](https://docs.microsoft.com/previous-versions/kxczf775(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="46313-111">For details, see [Windows Control Library Template](https://docs.microsoft.com/previous-versions/kxczf775(v=vs.100)).</span></span>

2. <span data-ttu-id="46313-112">在中**Windows 窗体设计器**，拖动<xref:System.Windows.Forms.Label>控件从**工具箱**到控件的设计图面。</span><span class="sxs-lookup"><span data-stu-id="46313-112">In the **Windows Forms Designer**, drag a <xref:System.Windows.Forms.Label> control from the **Toolbox** onto the control's design surface.</span></span>

3. <span data-ttu-id="46313-113">按**F5**生成项目并运行**UserControl 测试容器**。</span><span class="sxs-lookup"><span data-stu-id="46313-113">Press **F5** to build the project and run the **UserControl Test Container**.</span></span> <span data-ttu-id="46313-114">测试容器会显示与你<xref:System.Windows.Forms.UserControl>中**预览**窗格。</span><span class="sxs-lookup"><span data-stu-id="46313-114">The test container appears with your <xref:System.Windows.Forms.UserControl> in the **Preview** pane.</span></span>

4. <span data-ttu-id="46313-115">选择<xref:System.Windows.Forms.Control.BackColor%2A>属性中显示<xref:System.Windows.Forms.PropertyGrid>右侧的控件**预览**窗格。</span><span class="sxs-lookup"><span data-stu-id="46313-115">Select the <xref:System.Windows.Forms.Control.BackColor%2A> property displayed in the <xref:System.Windows.Forms.PropertyGrid> control to the right of the **Preview** pane.</span></span> <span data-ttu-id="46313-116">其值更改为`ControlDark`。</span><span class="sxs-lookup"><span data-stu-id="46313-116">Change its value to `ControlDark`.</span></span> <span data-ttu-id="46313-117">观察控件更改为较深的颜色。</span><span class="sxs-lookup"><span data-stu-id="46313-117">Observe that the control changes to a darker color.</span></span> <span data-ttu-id="46313-118">请尝试更改其他属性值，并观察在控件上的效果。</span><span class="sxs-lookup"><span data-stu-id="46313-118">Try changing other property values and observe the effect on your control.</span></span>

5. <span data-ttu-id="46313-119">单击**停靠填充用户控件**下面的复选框**预览**窗格。</span><span class="sxs-lookup"><span data-stu-id="46313-119">Click the **Dock Fill User Control** check box below the **Preview** pane.</span></span> <span data-ttu-id="46313-120">观察到该控件调整大小以填充窗格。</span><span class="sxs-lookup"><span data-stu-id="46313-120">Observe that the control is resized to fill the pane.</span></span> <span data-ttu-id="46313-121">调整测试容器的大小，并观察调整控件大小与窗格。</span><span class="sxs-lookup"><span data-stu-id="46313-121">Resize the test container and observe that the control is resized with the pane.</span></span>

6. <span data-ttu-id="46313-122">关闭测试容器。</span><span class="sxs-lookup"><span data-stu-id="46313-122">Close the test container.</span></span>

7. <span data-ttu-id="46313-123">另一个用户控件添加到**TestContainerExample**项目。</span><span class="sxs-lookup"><span data-stu-id="46313-123">Add another user control to the **TestContainerExample** project.</span></span> <span data-ttu-id="46313-124">有关详细信息，请参阅[如何：向项目添加现有项](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/9f4t9t92(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="46313-124">For details, see [How to: Add Existing Items to a Project](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/9f4t9t92(v=vs.100)).</span></span>

8. <span data-ttu-id="46313-125">在中**Windows 窗体设计器**，拖动<xref:System.Windows.Forms.Button>控件从**工具箱**到控件的设计图面。</span><span class="sxs-lookup"><span data-stu-id="46313-125">In the **Windows Forms Designer**, drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto the control's design surface.</span></span>

9. <span data-ttu-id="46313-126">按 F5 以生成项目并运行测试容器。</span><span class="sxs-lookup"><span data-stu-id="46313-126">Press F5 to build the project and run the test container.</span></span>

10. <span data-ttu-id="46313-127">单击**选择用户控件**<xref:System.Windows.Forms.ComboBox>两个用户控件之间进行切换。</span><span class="sxs-lookup"><span data-stu-id="46313-127">Click the **Select User Control**<xref:System.Windows.Forms.ComboBox> to switch between the two user controls.</span></span>

## <a name="test-user-controls-from-another-project"></a><span data-ttu-id="46313-128">从另一个项目的测试用户控件</span><span class="sxs-lookup"><span data-stu-id="46313-128">Test user controls from another project</span></span>

<span data-ttu-id="46313-129">在当前项目的测试容器中，可以测试其他项目中的用户控件。</span><span class="sxs-lookup"><span data-stu-id="46313-129">You can test user controls from other projects in your current project's test container.</span></span>

1. <span data-ttu-id="46313-130">创建一个名为的 Windows 控件库项目**TestContainerExample2**。</span><span class="sxs-lookup"><span data-stu-id="46313-130">Create a Windows control library project called **TestContainerExample2**.</span></span> <span data-ttu-id="46313-131">有关详细信息，请参阅[Windows 控件库模板](https://docs.microsoft.com/previous-versions/kxczf775(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="46313-131">For details, see [Windows Control Library Template](https://docs.microsoft.com/previous-versions/kxczf775(v=vs.100)).</span></span>

2. <span data-ttu-id="46313-132">在中**Windows 窗体设计器**，拖动<xref:System.Windows.Forms.RadioButton>控件从**工具箱**到控件的设计图面。</span><span class="sxs-lookup"><span data-stu-id="46313-132">In the **Windows Forms Designer**, drag a <xref:System.Windows.Forms.RadioButton> control from the **Toolbox** onto the control's design surface.</span></span>

3. <span data-ttu-id="46313-133">按 F5 以生成项目并运行测试容器。</span><span class="sxs-lookup"><span data-stu-id="46313-133">Press F5 to build the project and run the test container.</span></span> <span data-ttu-id="46313-134">测试容器会显示与你<xref:System.Windows.Forms.UserControl>中**预览**窗格。</span><span class="sxs-lookup"><span data-stu-id="46313-134">The test container appears with your <xref:System.Windows.Forms.UserControl> in the **Preview** pane.</span></span>

4. <span data-ttu-id="46313-135">单击**负载**按钮。</span><span class="sxs-lookup"><span data-stu-id="46313-135">Click the **Load** button.</span></span>

5. <span data-ttu-id="46313-136">在中**开放**对话框框中，导航到**TestContainerExample**.dll 上, 一个过程中生成。</span><span class="sxs-lookup"><span data-stu-id="46313-136">In the **Open** dialog box, navigate to **TestContainerExample**.dll, which you built in the previous procedure.</span></span> <span data-ttu-id="46313-137">选择**TestContainerExample**.dll，然后单击**打开**按钮以加载用户控件</span><span class="sxs-lookup"><span data-stu-id="46313-137">Select **TestContainerExample**.dll and click the **Open** button to load the user controls</span></span>

6. <span data-ttu-id="46313-138">使用**选择用户控件**<xref:System.Windows.Forms.ComboBox>若要从两个用户控件之间切换**TestContainerExample**项目。</span><span class="sxs-lookup"><span data-stu-id="46313-138">Use the **Select User Control**<xref:System.Windows.Forms.ComboBox> to switch between the two user controls from the **TestContainerExample** project.</span></span>

## <a name="see-also"></a><span data-ttu-id="46313-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="46313-139">See also</span></span>

- <xref:System.Windows.Forms.UserControl>
- [<span data-ttu-id="46313-140">如何：创作复合控件</span><span class="sxs-lookup"><span data-stu-id="46313-140">How to: Author Composite Controls</span></span>](how-to-author-composite-controls.md)
- [<span data-ttu-id="46313-141">演练：创作复合控件使用 Visual Basic</span><span class="sxs-lookup"><span data-stu-id="46313-141">Walkthrough: Authoring a Composite Control with Visual Basic</span></span>](walkthrough-authoring-a-composite-control-with-visual-basic.md)
- [<span data-ttu-id="46313-142">演练：创作复合控件通过视觉对象C#</span><span class="sxs-lookup"><span data-stu-id="46313-142">Walkthrough: Authoring a Composite Control with Visual C#</span></span>](walkthrough-authoring-a-composite-control-with-visual-csharp.md)
- <span data-ttu-id="46313-143">[用户控件设计器](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/183c3hth(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="46313-143">[User Control Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/183c3hth(v=vs.100))</span></span>
