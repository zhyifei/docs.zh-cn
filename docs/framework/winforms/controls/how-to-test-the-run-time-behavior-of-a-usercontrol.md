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
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 110036e5031a2956375b1edf0689237661522d39
ms.sourcegitcommit: dfd612ba454ce775a766bcc6fe93bc1d43dfda47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2019
ms.locfileid: "72180210"
---
# <a name="how-to-test-the-run-time-behavior-of-a-usercontrol"></a><span data-ttu-id="e3264-102">如何：测试 UserControl 的运行时行为</span><span class="sxs-lookup"><span data-stu-id="e3264-102">How to: Test the run-time behavior of a UserControl</span></span>

<span data-ttu-id="e3264-103">开发 <xref:System.Windows.Forms.UserControl> 时，需要测试其运行时行为。</span><span class="sxs-lookup"><span data-stu-id="e3264-103">When you develop a <xref:System.Windows.Forms.UserControl>, you need to test its run-time behavior.</span></span> <span data-ttu-id="e3264-104">您可以创建一个单独的基于 Windows 的应用程序项目，并将您的控件置于测试窗体上，但此过程是不方便的。</span><span class="sxs-lookup"><span data-stu-id="e3264-104">You can create a separate Windows-based application project and place your control on a test form, but this procedure is inconvenient.</span></span> <span data-ttu-id="e3264-105">更快、更简单的方法是使用 Visual Studio 提供的**UserControl 测试容器**。</span><span class="sxs-lookup"><span data-stu-id="e3264-105">A faster and easier way is to use the **UserControl Test Container** provided by Visual Studio.</span></span> <span data-ttu-id="e3264-106">此测试容器直接从 Windows 控件库项目启动。</span><span class="sxs-lookup"><span data-stu-id="e3264-106">This test container starts directly from your Windows control library project.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e3264-107">要使测试容器加载 <xref:System.Windows.Forms.UserControl>，控件必须至少有一个公共构造函数。</span><span class="sxs-lookup"><span data-stu-id="e3264-107">For the test container to load your <xref:System.Windows.Forms.UserControl>, the control must have at least one public constructor.</span></span>

> [!NOTE]
> <span data-ttu-id="e3264-108">无法使用C++ **UserControl 测试容器**测试视觉对象控件。</span><span class="sxs-lookup"><span data-stu-id="e3264-108">A Visual C++ control cannot be tested using the **UserControl Test Container**.</span></span>

## <a name="test-the-run-time-behavior-of-a-usercontrol"></a><span data-ttu-id="e3264-109">测试 UserControl 的运行时行为</span><span class="sxs-lookup"><span data-stu-id="e3264-109">Test the run-time behavior of a UserControl</span></span>

1. <span data-ttu-id="e3264-110">在 Visual Studio 中，创建一个 Windows 控件库项目，并将其命名为**TestContainerExample**。</span><span class="sxs-lookup"><span data-stu-id="e3264-110">In Visual Studio, create a Windows control library project, and name it **TestContainerExample**.</span></span>

2. <span data-ttu-id="e3264-111">在**Windows 窗体设计器**中，将 "@no__t" 控件从 "**工具箱**" 拖到控件的设计图面上。</span><span class="sxs-lookup"><span data-stu-id="e3264-111">In the **Windows Forms Designer**, drag a <xref:System.Windows.Forms.Label> control from the **Toolbox** onto the control's design surface.</span></span>

3. <span data-ttu-id="e3264-112">按<kbd>F5</kbd>生成项目，并运行 " **UserControl 测试容器**"。</span><span class="sxs-lookup"><span data-stu-id="e3264-112">Press <kbd>F5</kbd> to build the project and run the **UserControl Test Container**.</span></span> <span data-ttu-id="e3264-113">测试容器在**预览**窗格中显示 <xref:System.Windows.Forms.UserControl>。</span><span class="sxs-lookup"><span data-stu-id="e3264-113">The test container appears with your <xref:System.Windows.Forms.UserControl> in the **Preview** pane.</span></span>

4. <span data-ttu-id="e3264-114">选择**预览**窗格右侧 @no__t 控件中显示的 <xref:System.Windows.Forms.Control.BackColor%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="e3264-114">Select the <xref:System.Windows.Forms.Control.BackColor%2A> property displayed in the <xref:System.Windows.Forms.PropertyGrid> control to the right of the **Preview** pane.</span></span> <span data-ttu-id="e3264-115">将其值更改为**ControlDark**。</span><span class="sxs-lookup"><span data-stu-id="e3264-115">Change its value to **ControlDark**.</span></span> <span data-ttu-id="e3264-116">观察控件更改为较暗的颜色。</span><span class="sxs-lookup"><span data-stu-id="e3264-116">Observe that the control changes to a darker color.</span></span> <span data-ttu-id="e3264-117">尝试更改其他属性值并观察控件上的效果。</span><span class="sxs-lookup"><span data-stu-id="e3264-117">Try changing other property values and observe the effect on your control.</span></span>

5. <span data-ttu-id="e3264-118">单击 "**预览**" 窗格下的 "**停靠填充用户控件**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="e3264-118">Click the **Dock Fill User Control** check box below the **Preview** pane.</span></span> <span data-ttu-id="e3264-119">请注意，控件调整大小以填充窗格。</span><span class="sxs-lookup"><span data-stu-id="e3264-119">Observe that the control is resized to fill the pane.</span></span> <span data-ttu-id="e3264-120">调整测试容器的大小，并观察控件是否随窗格一起调整大小。</span><span class="sxs-lookup"><span data-stu-id="e3264-120">Resize the test container and observe that the control is resized with the pane.</span></span>

6. <span data-ttu-id="e3264-121">关闭测试容器。</span><span class="sxs-lookup"><span data-stu-id="e3264-121">Close the test container.</span></span>

7. <span data-ttu-id="e3264-122">向**TestContainerExample**项目添加另一个用户控件。</span><span class="sxs-lookup"><span data-stu-id="e3264-122">Add another user control to the **TestContainerExample** project.</span></span>

8. <span data-ttu-id="e3264-123">在**Windows 窗体设计器**中，将 "@no__t" 控件从 "**工具箱**" 拖到控件的设计图面上。</span><span class="sxs-lookup"><span data-stu-id="e3264-123">In the **Windows Forms Designer**, drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto the control's design surface.</span></span>

9. <span data-ttu-id="e3264-124">按<kbd>F5</kbd>生成项目并运行测试容器。</span><span class="sxs-lookup"><span data-stu-id="e3264-124">Press <kbd>F5</kbd> to build the project and run the test container.</span></span>

10. <span data-ttu-id="e3264-125">单击 "**选择用户控件**<xref:System.Windows.Forms.ComboBox> 以在两个用户控件之间切换。</span><span class="sxs-lookup"><span data-stu-id="e3264-125">Click the **Select User Control** <xref:System.Windows.Forms.ComboBox> to switch between the two user controls.</span></span>

## <a name="test-user-controls-from-another-project"></a><span data-ttu-id="e3264-126">测试其他项目中的用户控件</span><span class="sxs-lookup"><span data-stu-id="e3264-126">Test user controls from another project</span></span>

<span data-ttu-id="e3264-127">可以在当前项目的测试容器中测试其他项目中的用户控件。</span><span class="sxs-lookup"><span data-stu-id="e3264-127">You can test user controls from other projects in your current project's test container.</span></span>

1. <span data-ttu-id="e3264-128">在 Visual Studio 中，创建一个 Windows 控件库项目，并将其命名为**TestContainerExample2**。</span><span class="sxs-lookup"><span data-stu-id="e3264-128">In Visual Studio, create a Windows control library project, and name it **TestContainerExample2**.</span></span>

2. <span data-ttu-id="e3264-129">在**Windows 窗体设计器**中，将 "@no__t" 控件从 "**工具箱**" 拖到控件的设计图面上。</span><span class="sxs-lookup"><span data-stu-id="e3264-129">In the **Windows Forms Designer**, drag a <xref:System.Windows.Forms.RadioButton> control from the **Toolbox** onto the control's design surface.</span></span>

3. <span data-ttu-id="e3264-130">按<kbd>F5</kbd>生成项目并运行测试容器。</span><span class="sxs-lookup"><span data-stu-id="e3264-130">Press <kbd>F5</kbd> to build the project and run the test container.</span></span> <span data-ttu-id="e3264-131">测试容器在**预览**窗格中显示 <xref:System.Windows.Forms.UserControl>。</span><span class="sxs-lookup"><span data-stu-id="e3264-131">The test container appears with your <xref:System.Windows.Forms.UserControl> in the **Preview** pane.</span></span>

4. <span data-ttu-id="e3264-132">单击 "**加载**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="e3264-132">Click the **Load** button.</span></span>

5. <span data-ttu-id="e3264-133">在 "**打开**" 对话框中，导航到在前面的过程中生成的 " *TestContainerExample*"。</span><span class="sxs-lookup"><span data-stu-id="e3264-133">In the **Open** dialog box, navigate to *TestContainerExample.dll*, which you built in the previous procedure.</span></span> <span data-ttu-id="e3264-134">选择 " *TestContainerExample* "，并单击 "**打开**" 按钮以加载用户控件。</span><span class="sxs-lookup"><span data-stu-id="e3264-134">Select *TestContainerExample.dll* and click the **Open** button to load the user controls.</span></span>

6. <span data-ttu-id="e3264-135">使用 "**选择用户控件**<xref:System.Windows.Forms.ComboBox> 从**TestContainerExample**项目切换两个用户控件。</span><span class="sxs-lookup"><span data-stu-id="e3264-135">Use the **Select User Control** <xref:System.Windows.Forms.ComboBox> to switch between the two user controls from the **TestContainerExample** project.</span></span>

## <a name="see-also"></a><span data-ttu-id="e3264-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="e3264-136">See also</span></span>

- <xref:System.Windows.Forms.UserControl>
- <span data-ttu-id="e3264-137">[如何：创作复合控件 @ no__t-0</span><span class="sxs-lookup"><span data-stu-id="e3264-137">[How to: Author Composite Controls](how-to-author-composite-controls.md)</span></span>
- <span data-ttu-id="e3264-138">[演练：创作复合控件 @ no__t-0</span><span class="sxs-lookup"><span data-stu-id="e3264-138">[Walkthrough: Authoring a Composite Control](walkthrough-authoring-a-composite-control-with-visual-csharp.md)</span></span>
- <span data-ttu-id="e3264-139">[用户控件设计器](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/183c3hth(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="e3264-139">[User Control Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/183c3hth(v=vs.100))</span></span>
