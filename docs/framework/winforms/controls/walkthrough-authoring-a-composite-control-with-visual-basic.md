---
title: 演练：使用 Visual Basic 创作复合控件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Visual Basic]
- user controls [Visual Basic]
- UserControl class [Windows Forms], walkthroughs
- user controls [Windows Forms], creating with Visual Basic
- controls [Windows Forms], composite controls
- composite controls [Windows Forms], creating
- custom controls [Windows Forms], creating
ms.assetid: f50e270e-4db2-409a-8319-6db6ca5c7daf
ms.openlocfilehash: be2265f62092e6fdf43d8647a71d2c441beeefef
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/03/2018
ms.locfileid: "43482385"
---
# <a name="walkthrough-authoring-a-composite-control-with-visual-basic"></a><span data-ttu-id="ae142-102">演练：使用 Visual Basic 创作复合控件</span><span class="sxs-lookup"><span data-stu-id="ae142-102">Walkthrough: Authoring a Composite Control with Visual Basic</span></span>
<span data-ttu-id="ae142-103">复合控件提供了一种创建和重用自定义图形界面的方法。</span><span class="sxs-lookup"><span data-stu-id="ae142-103">Composite controls provide a means by which custom graphical interfaces can be created and reused.</span></span> <span data-ttu-id="ae142-104">复合控件本质上是具有可视化表示形式的组件。</span><span class="sxs-lookup"><span data-stu-id="ae142-104">A composite control is essentially a component with a visual representation.</span></span> <span data-ttu-id="ae142-105">因此，它可能包含一个或多个 Windows 窗体控件、组件或代码块，它们能够通过验证用户输入、修改显示属性或执行作者所需的其他任务来扩展功能。</span><span class="sxs-lookup"><span data-stu-id="ae142-105">As such, it might consist of one or more Windows Forms controls, components, or blocks of code that can extend functionality by validating user input, modifying display properties, or performing other tasks required by the author.</span></span> <span data-ttu-id="ae142-106">可以按照与其他控件相同的方式将复合控件置于 Windows 窗体中。</span><span class="sxs-lookup"><span data-stu-id="ae142-106">Composite controls can be placed on Windows Forms in the same manner as other controls.</span></span> <span data-ttu-id="ae142-107">在本演练的第一部分，将创建一个名为 `ctlClock` 的简单复合控件。</span><span class="sxs-lookup"><span data-stu-id="ae142-107">In the first part of this walkthrough, you create a simple composite control called `ctlClock`.</span></span> <span data-ttu-id="ae142-108">在本演练的第二部分，将通过继承扩展 `ctlClock` 的功能。</span><span class="sxs-lookup"><span data-stu-id="ae142-108">In the second part of the walkthrough, you extend the functionality of `ctlClock` through inheritance.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ae142-109">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="ae142-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="ae142-110">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="ae142-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="ae142-111">有关详细信息，请参阅[个性化设置 Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)。</span><span class="sxs-lookup"><span data-stu-id="ae142-111">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="ae142-112">创建项目</span><span class="sxs-lookup"><span data-stu-id="ae142-112">Creating the Project</span></span>  
 <span data-ttu-id="ae142-113">创建新的项目时应指定其名称，以设置根命名空间、程序集名称和项目名称，并确保默认组件将位于正确的命名空间中。</span><span class="sxs-lookup"><span data-stu-id="ae142-113">When you create a new project, you specify its name to set the root namespace, assembly name, and project name, and ensure that the default component will be in the correct namespace.</span></span>  
  
#### <a name="to-create-the-ctlclocklib-control-library-and-the-ctlclock-control"></a><span data-ttu-id="ae142-114">创建 ctlClockLib 控件库和 ctlClock 控件</span><span class="sxs-lookup"><span data-stu-id="ae142-114">To create the ctlClockLib control library and the ctlClock control</span></span>  
  
1.  <span data-ttu-id="ae142-115">在“文件”菜单上指向“新建”，然后单击“项目”打开“新建项目”对话框。</span><span class="sxs-lookup"><span data-stu-id="ae142-115">On the **File** menu, point to **New**, and then click **Project** to open the **New Project** dialog box.</span></span>  
  
2.  <span data-ttu-id="ae142-116">从 Visual Basic 项目的列表中选择**Windows 控件库**项目模板中，键入`ctlClockLib`中**名称**框中，然后依次**确定**。</span><span class="sxs-lookup"><span data-stu-id="ae142-116">From the list of Visual Basic projects, select the **Windows Control Library** project template, type `ctlClockLib` in the **Name** box, and then click **OK**.</span></span>  
  
     <span data-ttu-id="ae142-117">默认情况下，项目名称 `ctlClockLib` 也会分配到根命名空间中。</span><span class="sxs-lookup"><span data-stu-id="ae142-117">The project name, `ctlClockLib`, is also assigned to the root namespace by default.</span></span> <span data-ttu-id="ae142-118">根命名空间用于限定程序集中的组件名。</span><span class="sxs-lookup"><span data-stu-id="ae142-118">The root namespace is used to qualify the names of components in the assembly.</span></span> <span data-ttu-id="ae142-119">例如，如果两个程序集都提供名为 `ctlClock` 的组件，则可以使用 `ctlClockLib.ctlClock.` 指定 `ctlClock` 组件</span><span class="sxs-lookup"><span data-stu-id="ae142-119">For example, if two assemblies provide components named `ctlClock`, you can specify your `ctlClock` component using `ctlClockLib.ctlClock.`</span></span>  
  
3.  <span data-ttu-id="ae142-120">在解决方案资源管理器中，右键单击“UserControl1.vb”，然后单击“重命名”。</span><span class="sxs-lookup"><span data-stu-id="ae142-120">In Solution Explorer, right-click **UserControl1.vb**, and then click **Rename**.</span></span> <span data-ttu-id="ae142-121">将文件名更改为 `ctlClock.vb`。</span><span class="sxs-lookup"><span data-stu-id="ae142-121">Change the file name to `ctlClock.vb`.</span></span> <span data-ttu-id="ae142-122">当系统询问是否重命名对代码元素“UserControl1”的所有引用时，单击“是”按钮。</span><span class="sxs-lookup"><span data-stu-id="ae142-122">Click the **Yes** button when you are asked if you want to rename all references to the code element "UserControl1".</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ae142-123">默认情况下，复合控件继承<xref:System.Windows.Forms.UserControl>由系统提供的类。</span><span class="sxs-lookup"><span data-stu-id="ae142-123">By default, a composite control inherits from the <xref:System.Windows.Forms.UserControl> class provided by the system.</span></span> <span data-ttu-id="ae142-124"><xref:System.Windows.Forms.UserControl>类提供了所需的所有复合控件功能并实现标准方法和属性。</span><span class="sxs-lookup"><span data-stu-id="ae142-124">The <xref:System.Windows.Forms.UserControl> class provides functionality required by all composite controls, and implements standard methods and properties.</span></span>  
  
4.  <span data-ttu-id="ae142-125">在“文件”菜单上，单击“全部保存”保存项目。</span><span class="sxs-lookup"><span data-stu-id="ae142-125">On the **File** menu, click **Save All** to save the project.</span></span>  
  
## <a name="adding-windows-controls-and-components-to-the-composite-control"></a><span data-ttu-id="ae142-126">将 Windows 控件和组件添加到复合控件</span><span class="sxs-lookup"><span data-stu-id="ae142-126">Adding Windows Controls and Components to the Composite Control</span></span>  
 <span data-ttu-id="ae142-127">可视化界面是复合控件的基本部分。</span><span class="sxs-lookup"><span data-stu-id="ae142-127">A visual interface is an essential part of your composite control.</span></span> <span data-ttu-id="ae142-128">这种可视化界面通过向设计器图面添加一个或多个 Windows 控件实现。</span><span class="sxs-lookup"><span data-stu-id="ae142-128">This visual interface is implemented by the addition of one or more Windows controls to the designer surface.</span></span> <span data-ttu-id="ae142-129">在下面的演示中，将向复合控件中加入 Windows 控件并编写代码实现功能。</span><span class="sxs-lookup"><span data-stu-id="ae142-129">In the following demonstration, you will incorporate Windows controls into your composite control and write code to implement functionality.</span></span>  
  
#### <a name="to-add-a-label-and-a-timer-to-your-composite-control"></a><span data-ttu-id="ae142-130">将标签和计时器添加到复合控件</span><span class="sxs-lookup"><span data-stu-id="ae142-130">To add a Label and a Timer to your composite control</span></span>  
  
1.  <span data-ttu-id="ae142-131">在解决方案资源管理器中，右键单击“ctlClock.vb”，然后单击“视图设计器”。</span><span class="sxs-lookup"><span data-stu-id="ae142-131">In Solution Explorer, right-click **ctlClock.vb**, and then click **View Designer**.</span></span>  
  
2.  <span data-ttu-id="ae142-132">在“工具箱”中，展开“公共控件”节点，然后双击“标签”。</span><span class="sxs-lookup"><span data-stu-id="ae142-132">In the Toolbox, expand the **Common Controls** node, and then double-click **Label**.</span></span>  
  
     <span data-ttu-id="ae142-133">一个<xref:System.Windows.Forms.Label>名为控件`Label1`添加到设计器图面上的控件。</span><span class="sxs-lookup"><span data-stu-id="ae142-133">A <xref:System.Windows.Forms.Label> control named `Label1` is added to your control on the designer surface.</span></span>  
  
3.  <span data-ttu-id="ae142-134">在设计器中，单击“Label1”。</span><span class="sxs-lookup"><span data-stu-id="ae142-134">In the designer, click **Label1**.</span></span> <span data-ttu-id="ae142-135">在“属性”窗口中，设置下列属性。</span><span class="sxs-lookup"><span data-stu-id="ae142-135">In the Properties window, set the following properties.</span></span>  
  
    |<span data-ttu-id="ae142-136">属性</span><span class="sxs-lookup"><span data-stu-id="ae142-136">Property</span></span>|<span data-ttu-id="ae142-137">更改为</span><span class="sxs-lookup"><span data-stu-id="ae142-137">Change to</span></span>|  
    |--------------|---------------|  
    |<span data-ttu-id="ae142-138">**名称**</span><span class="sxs-lookup"><span data-stu-id="ae142-138">**Name**</span></span>|`lblDisplay`|  
    |<span data-ttu-id="ae142-139">**文本**</span><span class="sxs-lookup"><span data-stu-id="ae142-139">**Text**</span></span>|`(blank space)`|  
    |<span data-ttu-id="ae142-140">**TextAlign**</span><span class="sxs-lookup"><span data-stu-id="ae142-140">**TextAlign**</span></span>|`MiddleCenter`|  
    |<span data-ttu-id="ae142-141">**Font.Size**</span><span class="sxs-lookup"><span data-stu-id="ae142-141">**Font.Size**</span></span>|`14`|  
  
4.  <span data-ttu-id="ae142-142">在“工具箱”中，展开“组件”节点，然后双击“计时器”。</span><span class="sxs-lookup"><span data-stu-id="ae142-142">In the **Toolbox**, expand the **Components** node, and then double-click **Timer**.</span></span>  
  
     <span data-ttu-id="ae142-143">因为<xref:System.Windows.Forms.Timer>是一个组件，它具有在运行时没有可视化表示形式。</span><span class="sxs-lookup"><span data-stu-id="ae142-143">Because a <xref:System.Windows.Forms.Timer> is a component, it has no visual representation at run time.</span></span> <span data-ttu-id="ae142-144">因而它不会和控件一起出现在设计器图面上，而是出现在“组件设计器”（设计器图面底部的一栏）中。</span><span class="sxs-lookup"><span data-stu-id="ae142-144">Therefore, it does not appear with the controls on the designer surface, but rather in the Component Designer (a tray at the bottom of the designer surface).</span></span>  
  
5.  <span data-ttu-id="ae142-145">在组件设计器中，单击**Timer1**，然后设置<xref:System.Windows.Forms.Timer.Interval%2A>属性设置为`1000`并<xref:System.Windows.Forms.Timer.Enabled%2A>属性设置为`True`。</span><span class="sxs-lookup"><span data-stu-id="ae142-145">In the Component Designer, click **Timer1**, and then set the <xref:System.Windows.Forms.Timer.Interval%2A> property to `1000` and the <xref:System.Windows.Forms.Timer.Enabled%2A> property to `True`.</span></span>  
  
     <span data-ttu-id="ae142-146"><xref:System.Windows.Forms.Timer.Interval%2A>属性控制计时器组件的计时的频率。</span><span class="sxs-lookup"><span data-stu-id="ae142-146">The <xref:System.Windows.Forms.Timer.Interval%2A> property controls the frequency with which the timer component ticks.</span></span> <span data-ttu-id="ae142-147">`Timer1` 每走过一个刻度，它都会运行一次 `Timer1_Tick` 事件中的代码。</span><span class="sxs-lookup"><span data-stu-id="ae142-147">Each time `Timer1` ticks, it runs the code in the `Timer1_Tick` event.</span></span> <span data-ttu-id="ae142-148">间隔表示计时之间的毫秒数。</span><span class="sxs-lookup"><span data-stu-id="ae142-148">The interval represents the number of milliseconds between ticks.</span></span>  
  
6.  <span data-ttu-id="ae142-149">在“组件设计器”中，双击“Timer1”转到 `ctlClock` 的 `Timer1_Tick` 事件。</span><span class="sxs-lookup"><span data-stu-id="ae142-149">In the Component Designer, double-click **Timer1** to go to the `Timer1_Tick` event for `ctlClock`.</span></span>  
  
7.  <span data-ttu-id="ae142-150">将代码修改为类似如下所示的代码示例。</span><span class="sxs-lookup"><span data-stu-id="ae142-150">Modify the code so that it resembles the following code sample.</span></span> <span data-ttu-id="ae142-151">确保将访问修饰符从 `Private` 更改为 `Protected`。</span><span class="sxs-lookup"><span data-stu-id="ae142-151">Be sure to change the access modifier from `Private` to `Protected`.</span></span>  
  
    ```vb  
    Protected Sub Timer1_Tick(ByVal sender As Object, ByVal e As _  
        System.EventArgs) Handles Timer1.Tick  
        ' Causes the label to display the current time.    
        lblDisplay.Text = Format(Now, "hh:mm:ss")  
    End Sub  
    ```  
  
     <span data-ttu-id="ae142-152">此代码将使得当前时间显示在 `lblDisplay` 中。</span><span class="sxs-lookup"><span data-stu-id="ae142-152">This code will cause the current time to be shown in `lblDisplay`.</span></span> <span data-ttu-id="ae142-153">因为 `Timer1` 的间隔设置为 `1000`，所以该事件每 1000 毫秒发生一次，从而每一秒更新一次当前时间。</span><span class="sxs-lookup"><span data-stu-id="ae142-153">Because the interval of `Timer1` was set to `1000`, this event will occur every thousand milliseconds, thus updating the current time every second.</span></span>  
  
8.  <span data-ttu-id="ae142-154">修改该方法使其可重写。</span><span class="sxs-lookup"><span data-stu-id="ae142-154">Modify the method to be overridable.</span></span> <span data-ttu-id="ae142-155">有关详细信息，请参阅下面的“从用户控件继承”一节。</span><span class="sxs-lookup"><span data-stu-id="ae142-155">For more information, see the "Inheriting from a User Control" section below.</span></span>  
  
    ```vb  
    Protected Overridable Sub Timer1_Tick(ByVal sender As Object, ByVal _  
        e As System.EventArgs) Handles Timer1.Tick  
    ```  
  
9. <span data-ttu-id="ae142-156">在“文件”菜单上，单击“全部保存”保存项目。</span><span class="sxs-lookup"><span data-stu-id="ae142-156">On the **File** menu, click **Save All** to save the project.</span></span>  
  
## <a name="adding-properties-to-the-composite-control"></a><span data-ttu-id="ae142-157">将属性添加到复合控件</span><span class="sxs-lookup"><span data-stu-id="ae142-157">Adding Properties to the Composite Control</span></span>  
 <span data-ttu-id="ae142-158">现在，时钟控件封装<xref:System.Windows.Forms.Label>控件和一个<xref:System.Windows.Forms.Timer>组件，每个都有其自己的固有属性集。</span><span class="sxs-lookup"><span data-stu-id="ae142-158">Your clock control now encapsulates a <xref:System.Windows.Forms.Label> control and a <xref:System.Windows.Forms.Timer> component, each with its own set of inherent properties.</span></span> <span data-ttu-id="ae142-159">尽管控件的后续用户无法访问这些控件的单个属性，但可以通过编写适当的代码块来创建和公开自定义属性。</span><span class="sxs-lookup"><span data-stu-id="ae142-159">While the individual properties of these controls will not be accessible to subsequent users of your control, you can create and expose custom properties by writing the appropriate blocks of code.</span></span> <span data-ttu-id="ae142-160">在下面的过程中，将向控件添加属性，这些属性可使用户能够更改背景和文本的颜色。</span><span class="sxs-lookup"><span data-stu-id="ae142-160">In the following procedure, you will add properties to your control that enable the user to change the color of the background and text.</span></span>  
  
#### <a name="to-add-a-property-to-your-composite-control"></a><span data-ttu-id="ae142-161">将属性添加到复合控件</span><span class="sxs-lookup"><span data-stu-id="ae142-161">To add a property to your composite control</span></span>  
  
1.  <span data-ttu-id="ae142-162">在解决方案资源管理器中，右键单击“ctlClock.vb”，然后单击“查看代码”。</span><span class="sxs-lookup"><span data-stu-id="ae142-162">In Solution Explorer, right-click **ctlClock.vb**, and then click **View Code**.</span></span>  
  
     <span data-ttu-id="ae142-163">控件的“代码编辑器”随即打开。</span><span class="sxs-lookup"><span data-stu-id="ae142-163">The Code Editor for your control opens.</span></span>  
  
2.  <span data-ttu-id="ae142-164">找到 `Public Class ctlClock` 语句。</span><span class="sxs-lookup"><span data-stu-id="ae142-164">Locate the `Public Class ctlClock` statement.</span></span> <span data-ttu-id="ae142-165">在其下方键入以下代码。</span><span class="sxs-lookup"><span data-stu-id="ae142-165">Beneath it, type the following code.</span></span>  
  
    ```vb  
    Private colFColor as Color  
    Private colBColor as Color  
    ```  
  
     <span data-ttu-id="ae142-166">这些语句会创建私有变量，用来存储要创建的属性的值。</span><span class="sxs-lookup"><span data-stu-id="ae142-166">These statements create the private variables that you will use to store the values for the properties you are about to create.</span></span>  
  
3.  <span data-ttu-id="ae142-167">在步骤 2 中的变量声明下方插入以下代码。</span><span class="sxs-lookup"><span data-stu-id="ae142-167">Insert the following code beneath the variable declarations from step 2.</span></span>  
  
    ```vb  
    ' Declares the name and type of the property.  
    Property ClockBackColor() as Color  
        ' Retrieves the value of the private variable colBColor.  
        Get  
            Return colBColor  
        End Get  
        ' Stores the selected value in the private variable colBColor, and   
        ' updates the background color of the label control lblDisplay.  
        Set(ByVal value as Color)  
            colBColor = value  
            lblDisplay.BackColor = colBColor     
        End Set  
  
    End Property  
    ' Provides a similar set of instructions for the foreground color.  
    Property ClockForeColor() as Color  
        Get  
            Return colFColor  
        End Get  
        Set(ByVal value as Color)  
            colFColor = value  
            lblDisplay.ForeColor = colFColor  
        End Set  
    End Property  
    ```  
  
     <span data-ttu-id="ae142-168">通过调用 `Property` 语句，上述代码使得此控件的后续用户能够使用 `ClockForeColor` 和 `ClockBackColor` 这两个自定义属性。</span><span class="sxs-lookup"><span data-stu-id="ae142-168">The preceding code makes two custom properties, `ClockForeColor` and `ClockBackColor`, available to subsequent users of this control by invoking the `Property` statement.</span></span> <span data-ttu-id="ae142-169">`Get` 和 `Set` 语句提供了该属性值的存储和检索，还提供了实现适合于该属性的功能的代码。</span><span class="sxs-lookup"><span data-stu-id="ae142-169">The `Get` and `Set` statements provide for storage and retrieval of the property value, as well as code to implement functionality appropriate to the property.</span></span>  
  
4.  <span data-ttu-id="ae142-170">在“文件”菜单上，单击“全部保存”保存项目。</span><span class="sxs-lookup"><span data-stu-id="ae142-170">On the **File** menu, click **Save All** to save the project.</span></span>  
  
## <a name="testing-the-control"></a><span data-ttu-id="ae142-171">测试控件</span><span class="sxs-lookup"><span data-stu-id="ae142-171">Testing the Control</span></span>  
 <span data-ttu-id="ae142-172">控件不是独立的项目，它们必须托管在容器中。</span><span class="sxs-lookup"><span data-stu-id="ae142-172">Controls are not stand-alone projects; they must be hosted in a container.</span></span> <span data-ttu-id="ae142-173">测试控件的运行时行为，并使用“UserControl 测试容器”运用其属性。</span><span class="sxs-lookup"><span data-stu-id="ae142-173">Test your control's run-time behavior and exercise its properties with the **UserControl Test Container**.</span></span> <span data-ttu-id="ae142-174">有关详细信息，请参阅[如何：测试 UserControl 的运行时行为](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md)。</span><span class="sxs-lookup"><span data-stu-id="ae142-174">For more information, see [How to: Test the Run-Time Behavior of a UserControl](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>  
  
#### <a name="to-test-your-control"></a><span data-ttu-id="ae142-175">测试控件</span><span class="sxs-lookup"><span data-stu-id="ae142-175">To test your control</span></span>  
  
1.  <span data-ttu-id="ae142-176">按 F5 生成项目并在“UserControl 测试容器”中运行该控件。</span><span class="sxs-lookup"><span data-stu-id="ae142-176">Press F5 to build the project and run your control in the **UserControl Test Container**.</span></span>  
  
2.  <span data-ttu-id="ae142-177">在测试容器的属性网格中，选择 `ClockBackColor` 属性，然后单击下拉箭头显示调色板。</span><span class="sxs-lookup"><span data-stu-id="ae142-177">In the test container's property grid, select the `ClockBackColor` property, and then click the drop-down arrow to display the color palette.</span></span>  
  
3.  <span data-ttu-id="ae142-178">通过单击选择颜色。</span><span class="sxs-lookup"><span data-stu-id="ae142-178">Choose a color by clicking it.</span></span>  
  
     <span data-ttu-id="ae142-179">控件的背景颜色更改为你选择的颜色。</span><span class="sxs-lookup"><span data-stu-id="ae142-179">The background color of your control changes to the color you selected.</span></span>  
  
4.  <span data-ttu-id="ae142-180">使用类似的事件序列来验证 `ClockForeColor` 属性的功能是否与预期的相符。</span><span class="sxs-lookup"><span data-stu-id="ae142-180">Use a similar sequence of events to verify that the `ClockForeColor` property is functioning as expected.</span></span>  
  
5.  <span data-ttu-id="ae142-181">单击“关闭”以关闭“UserControl 测试容器”。</span><span class="sxs-lookup"><span data-stu-id="ae142-181">Click **Close** to close the **UserControl Test Container**.</span></span>  
  
     <span data-ttu-id="ae142-182">本节和前面的几节演示了如何将组件和 Windows 控件与代码和打包相结合，以复合控件的形式提供自定义功能。</span><span class="sxs-lookup"><span data-stu-id="ae142-182">In this section and the preceding sections, you have seen how components and Windows controls can be combined with code and packaging to provide custom functionality in the form of a composite control.</span></span> <span data-ttu-id="ae142-183">你现已了解如何在复合控件中公开属性，以及如何在完成后对控件进行测试。</span><span class="sxs-lookup"><span data-stu-id="ae142-183">You have learned to expose properties in your composite control, and how to test your control after it is complete.</span></span> <span data-ttu-id="ae142-184">下一节将介绍如何以 `ctlClock` 为基础构造继承的复合控件。</span><span class="sxs-lookup"><span data-stu-id="ae142-184">In the next section you will learn how to construct an inherited composite control using `ctlClock` as a base.</span></span>  
  
## <a name="inheriting-from-a-composite-control"></a><span data-ttu-id="ae142-185">从复合控件继承</span><span class="sxs-lookup"><span data-stu-id="ae142-185">Inheriting from a Composite Control</span></span>  
 <span data-ttu-id="ae142-186">前面的章节中介绍了如何将 Windows 控件、组件和代码组合成可重用的复合控件。</span><span class="sxs-lookup"><span data-stu-id="ae142-186">In the previous sections, you learned how to combine Windows controls, components, and code into reusable composite controls.</span></span> <span data-ttu-id="ae142-187">现在即可将复合控件用作生成其他控件的基础。</span><span class="sxs-lookup"><span data-stu-id="ae142-187">Your composite control can now be used as a base upon which other controls can be built.</span></span> <span data-ttu-id="ae142-188">从基类派生类的过程称为继承。</span><span class="sxs-lookup"><span data-stu-id="ae142-188">The process of deriving a class from a base class is called *inheritance*.</span></span> <span data-ttu-id="ae142-189">在本节中，将创建一个称为 `ctlAlarmClock` 的复合控件。</span><span class="sxs-lookup"><span data-stu-id="ae142-189">In this section, you will create a composite control called `ctlAlarmClock`.</span></span> <span data-ttu-id="ae142-190">此控件将从其父控件 `ctlClock` 派生。</span><span class="sxs-lookup"><span data-stu-id="ae142-190">This control will be derived from its parent control, `ctlClock`.</span></span> <span data-ttu-id="ae142-191">将介绍如何通过重写父级方法并添加新的方法和属性来扩展 `ctlClock` 的功能。</span><span class="sxs-lookup"><span data-stu-id="ae142-191">You will learn to extend the functionality of `ctlClock` by overriding parent methods and adding new methods and properties.</span></span>  
  
 <span data-ttu-id="ae142-192">创建继承控件的第一步是从它的父控件派生。</span><span class="sxs-lookup"><span data-stu-id="ae142-192">The first step in creating an inherited control is to derive it from its parent.</span></span> <span data-ttu-id="ae142-193">该操作创建一个新控件，它具有父控件的所有属性、方法和图形特征，但也可以用作添加新功能或修改过的功能的基础。</span><span class="sxs-lookup"><span data-stu-id="ae142-193">This action creates a new control that has all of the properties, methods, and graphical characteristics of the parent control, but can also act as a base for the addition of new or modified functionality.</span></span>  
  
#### <a name="to-create-the-inherited-control"></a><span data-ttu-id="ae142-194">创建继承的控件</span><span class="sxs-lookup"><span data-stu-id="ae142-194">To create the inherited control</span></span>  
  
1.  <span data-ttu-id="ae142-195">在解决方案资源管理器中，右键单击“ctlClockLib”，指向“添加”，然后单击“用户控件”。</span><span class="sxs-lookup"><span data-stu-id="ae142-195">In Solution Explorer, right-click **ctlClockLib**, point to **Add**, and then click **User Control**.</span></span>  
  
     <span data-ttu-id="ae142-196">此时将打开“添加新项”对话框。</span><span class="sxs-lookup"><span data-stu-id="ae142-196">The **Add New Item** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="ae142-197">选择“继承的用户控件”模板。</span><span class="sxs-lookup"><span data-stu-id="ae142-197">Select the **Inherited User Control** template.</span></span>  
  
3.  <span data-ttu-id="ae142-198">在“名称”框中，键入 `ctlAlarmClock.vb`，然后单击“添加”。</span><span class="sxs-lookup"><span data-stu-id="ae142-198">In the **Name** box, type `ctlAlarmClock.vb`, and then click **Add**.</span></span>  
  
     <span data-ttu-id="ae142-199">“继承选择器”对话框将出现。</span><span class="sxs-lookup"><span data-stu-id="ae142-199">The **Inheritance Picker** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="ae142-200">在“组件名称”下，双击“ctlClock”。</span><span class="sxs-lookup"><span data-stu-id="ae142-200">Under **Component Name**, double-click **ctlClock**.</span></span>  
  
5.  <span data-ttu-id="ae142-201">在解决方案资源管理器中，浏览当前项目。</span><span class="sxs-lookup"><span data-stu-id="ae142-201">In Solution Explorer, browse through the current projects.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ae142-202">当前项目中添加了一个名为“ctlAlarmClock.vb”的文件。</span><span class="sxs-lookup"><span data-stu-id="ae142-202">A file called **ctlAlarmClock.vb** has been added to the current project.</span></span>  
  
### <a name="adding-the-alarm-properties"></a><span data-ttu-id="ae142-203">添加警报属性</span><span class="sxs-lookup"><span data-stu-id="ae142-203">Adding the Alarm Properties</span></span>  
 <span data-ttu-id="ae142-204">将属性添加到继承的控件的方法与将其添加到复合控件的方法相同。</span><span class="sxs-lookup"><span data-stu-id="ae142-204">Properties are added to an inherited control in the same way they are added to a composite control.</span></span> <span data-ttu-id="ae142-205">现在将使用属性声明语法向控件中添加两个属性：`AlarmTime` 和 `AlarmSet`，前者将存储发出警报的日期和时间值，后者指示是否设置了警报。</span><span class="sxs-lookup"><span data-stu-id="ae142-205">You will now use the property declaration syntax to add two properties to your control: `AlarmTime`, which will store the value of the date and time the alarm is to go off, and `AlarmSet`, which will indicate whether the alarm is set.</span></span>  
  
##### <a name="to-add-properties-to-your-composite-control"></a><span data-ttu-id="ae142-206">将属性添加到复合控件</span><span class="sxs-lookup"><span data-stu-id="ae142-206">To add properties to your composite control</span></span>  
  
1.  <span data-ttu-id="ae142-207">在解决方案资源管理器中，右键单击“ctlAlarmClock”，然后单击“查看代码”。</span><span class="sxs-lookup"><span data-stu-id="ae142-207">In Solution Explorer, right-click **ctlAlarmClock**, and then click **View Code**.</span></span>  
  
2.  <span data-ttu-id="ae142-208">找到 ctlAlarmClock 控件（显示为 `Public Class ctlAlarmClock`）的类声明。</span><span class="sxs-lookup"><span data-stu-id="ae142-208">Locate the class declaration for the ctlAlarmClock control, which appears as `Public Class ctlAlarmClock`.</span></span>  <span data-ttu-id="ae142-209">在类声明中插入以下代码。</span><span class="sxs-lookup"><span data-stu-id="ae142-209">In the class declaration, insert the following code.</span></span>  
  
    ```vb  
    Private dteAlarmTime As Date  
    Private blnAlarmSet As Boolean  
    ' These properties will be declared as Public to allow future   
    ' developers to access them.  
    Public Property AlarmTime() As Date  
        Get  
            Return dteAlarmTime  
        End Get  
        Set(ByVal value as Date)  
            dteAlarmTime = value  
        End Set  
    End Property  
    Public Property AlarmSet() As Boolean  
        Get  
            Return blnAlarmSet  
        End Get  
        Set(ByVal value as Boolean)  
            blnAlarmSet = value  
        End Set  
    End Property  
    ```  
  
### <a name="adding-to-the-graphical-interface-of-the-control"></a><span data-ttu-id="ae142-210">添加到控件的图形界面</span><span class="sxs-lookup"><span data-stu-id="ae142-210">Adding to the Graphical Interface of the Control</span></span>  
 <span data-ttu-id="ae142-211">继承的控件具有可视化界面，该界面与它从中继承的控件的界面完全相同。</span><span class="sxs-lookup"><span data-stu-id="ae142-211">Your inherited control has a visual interface that is identical to the control it inherits from.</span></span> <span data-ttu-id="ae142-212">它与其父控件拥有相同的构成控件，但除非将构成控件的属性特别公开，否则它们将不可用。</span><span class="sxs-lookup"><span data-stu-id="ae142-212">It possesses the same constituent controls as its parent control, but the properties of the constituent controls will not be available unless they were specifically exposed.</span></span> <span data-ttu-id="ae142-213">可以向继承的复合控件的图形界面进行添加，方法与向任意复合控件进行添加相同。</span><span class="sxs-lookup"><span data-stu-id="ae142-213">You may add to the graphical interface of an inherited composite control in the same manner as you would add to any composite control.</span></span> <span data-ttu-id="ae142-214">若要继续向警报时钟的可视化界面进行添加，请添加一个标签控件，它将在警报响起时闪烁。</span><span class="sxs-lookup"><span data-stu-id="ae142-214">To continue adding to your alarm clock's visual interface, you will add a label control that will flash when the alarm is sounding.</span></span>  
  
##### <a name="to-add-the-label-control"></a><span data-ttu-id="ae142-215">添加标签控件</span><span class="sxs-lookup"><span data-stu-id="ae142-215">To add the label control</span></span>  
  
1.  <span data-ttu-id="ae142-216">在解决方案资源管理器中，右键单击“ctlAlarmClock”，然后单击“视图设计器”。</span><span class="sxs-lookup"><span data-stu-id="ae142-216">In Solution Explorer, right-click **ctlAlarmClock**, and click **View Designer**.</span></span>  
  
     <span data-ttu-id="ae142-217">`ctlAlarmClock` 的设计器将在主窗口中打开。</span><span class="sxs-lookup"><span data-stu-id="ae142-217">The designer for `ctlAlarmClock` opens in the main window.</span></span>  
  
2.  <span data-ttu-id="ae142-218">单击 `lblDisplay`（该控件的显示部分），然后查看“属性”窗口。</span><span class="sxs-lookup"><span data-stu-id="ae142-218">Click `lblDisplay` (the display portion of the control), and view the Properties window.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ae142-219">当显示所有属性时，属性是浅灰色的。</span><span class="sxs-lookup"><span data-stu-id="ae142-219">While all the properties are displayed, they are dimmed.</span></span> <span data-ttu-id="ae142-220">这表示这些属性是 `lblDisplay` 所固有的，不能在“属性”窗口中修改或访问。</span><span class="sxs-lookup"><span data-stu-id="ae142-220">This indicates that these properties are native to `lblDisplay` and cannot be modified or accessed in the Properties window.</span></span> <span data-ttu-id="ae142-221">默认情况下，复合控件中所包含的控件为 `Private`，通过任何途径都无法访问其属性。</span><span class="sxs-lookup"><span data-stu-id="ae142-221">By default, controls contained in a composite control are `Private`, and their properties are not accessible by any means.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ae142-222">如果希望复合控件的后续用户可以访问其内部控件，则可将其声明为 `Public` 或 `Protected`。</span><span class="sxs-lookup"><span data-stu-id="ae142-222">If you want subsequent users of your composite control to have access to its internal controls, declare them as `Public` or `Protected`.</span></span> <span data-ttu-id="ae142-223">如此即可使用适当的代码设置和修改复合控件内所包含控件的属性。</span><span class="sxs-lookup"><span data-stu-id="ae142-223">This will allow you to set and modify properties of controls contained within your composite control by using the appropriate code.</span></span>  
  
3.  <span data-ttu-id="ae142-224">添加<xref:System.Windows.Forms.Label>到复合控件的控件。</span><span class="sxs-lookup"><span data-stu-id="ae142-224">Add a <xref:System.Windows.Forms.Label> control to your composite control.</span></span>  
  
4.  <span data-ttu-id="ae142-225">使用鼠标拖动<xref:System.Windows.Forms.Label>紧跟在显示框下方的控件。</span><span class="sxs-lookup"><span data-stu-id="ae142-225">Using the mouse, drag the <xref:System.Windows.Forms.Label> control immediately beneath the display box.</span></span> <span data-ttu-id="ae142-226">在“属性”窗口中，设置下列属性。</span><span class="sxs-lookup"><span data-stu-id="ae142-226">In the Properties window, set the following properties.</span></span>  
  
    |<span data-ttu-id="ae142-227">属性</span><span class="sxs-lookup"><span data-stu-id="ae142-227">Property</span></span>|<span data-ttu-id="ae142-228">设置</span><span class="sxs-lookup"><span data-stu-id="ae142-228">Setting</span></span>|  
    |--------------|-------------|  
    |<span data-ttu-id="ae142-229">**名称**</span><span class="sxs-lookup"><span data-stu-id="ae142-229">**Name**</span></span>|`lblAlarm`|  
    |<span data-ttu-id="ae142-230">**文本**</span><span class="sxs-lookup"><span data-stu-id="ae142-230">**Text**</span></span>|<span data-ttu-id="ae142-231">**Alarm!**</span><span class="sxs-lookup"><span data-stu-id="ae142-231">**Alarm!**</span></span>|  
    |<span data-ttu-id="ae142-232">**TextAlign**</span><span class="sxs-lookup"><span data-stu-id="ae142-232">**TextAlign**</span></span>|`MiddleCenter`|  
    |<span data-ttu-id="ae142-233">**可见**</span><span class="sxs-lookup"><span data-stu-id="ae142-233">**Visible**</span></span>|`False`|  
  
### <a name="adding-the-alarm-functionality"></a><span data-ttu-id="ae142-234">添加警报功能</span><span class="sxs-lookup"><span data-stu-id="ae142-234">Adding the Alarm Functionality</span></span>  
 <span data-ttu-id="ae142-235">在前面的章节中，已经添加了一些属性和一个控件，它们将启用复合控件中的警报功能。</span><span class="sxs-lookup"><span data-stu-id="ae142-235">In the previous procedures, you added properties and a control that will enable alarm functionality in your composite control.</span></span> <span data-ttu-id="ae142-236">在本过程中，将添加代码以比较当前时间和警报时间，如果两者相同，则发出警报并闪烁。</span><span class="sxs-lookup"><span data-stu-id="ae142-236">In this procedure, you will add code to compare the current time to the alarm time and, if they are the same, to sound and flash an alarm.</span></span> <span data-ttu-id="ae142-237">通过重写 `ctlClock` 的 `Timer1_Tick` 方法并向其中添加其他代码，可扩展 `ctlAlarmClock` 的功能，同时会保留 `ctlClock` 的所有固有功能。</span><span class="sxs-lookup"><span data-stu-id="ae142-237">By overriding the `Timer1_Tick` method of `ctlClock` and adding additional code to it, you will extend the capability of `ctlAlarmClock` while retaining all of the inherent functionality of `ctlClock`.</span></span>  
  
##### <a name="to-override-the-timer1tick-method-of-ctlclock"></a><span data-ttu-id="ae142-238">重写 ctlClock 的 Timer1_Tick 方法</span><span class="sxs-lookup"><span data-stu-id="ae142-238">To override the Timer1_Tick method of ctlClock</span></span>  
  
1.  <span data-ttu-id="ae142-239">在解决方案资源管理器中，右键单击“ctlAlarmClock.vb”，然后单击“查看代码”。</span><span class="sxs-lookup"><span data-stu-id="ae142-239">In Solution Explorer, right-click **ctlAlarmClock.vb**, and then click **View Code**.</span></span>  
  
2.  <span data-ttu-id="ae142-240">找到 `Private blnAlarmSet As Boolean` 语句。</span><span class="sxs-lookup"><span data-stu-id="ae142-240">Locate the `Private blnAlarmSet As Boolean` statement.</span></span> <span data-ttu-id="ae142-241">在其紧下方添加下列语句。</span><span class="sxs-lookup"><span data-stu-id="ae142-241">Immediately beneath it, add the following statement.</span></span>  
  
    ```vb  
    Dim blnColorTicker as Boolean  
    ```  
  
3.  <span data-ttu-id="ae142-242">在该页的底部找到 `End Class` 语句。</span><span class="sxs-lookup"><span data-stu-id="ae142-242">Locate the `End Class` statement at the bottom of the page.</span></span> <span data-ttu-id="ae142-243">在紧接 `End Class` 语句的前方，添加以下代码。</span><span class="sxs-lookup"><span data-stu-id="ae142-243">Just before the `End Class` statement, add the following code.</span></span>  
  
    ```vb  
    Protected Overrides Sub Timer1_Tick(ByVal sender As Object, ByVal e _  
        As System.EventArgs)  
        ' Calls the Timer1_Tick method of ctlClock.  
        MyBase.Timer1_Tick(sender, e)  
        ' Checks to see if the Alarm is set.  
        If AlarmSet = False Then  
            Exit Sub  
        End If  
        ' If the date, hour, and minute of the alarm time are the same as  
        ' now, flash and beep an alarm.   
        If AlarmTime.Date = Now.Date And AlarmTime.Hour = Now.Hour And _  
            AlarmTime.Minute = Now.Minute Then  
            ' Sounds an audible beep.  
            Beep()  
            ' Sets lblAlarmVisible to True, and changes the background color based on the   
            ' value of blnColorTicker. The background color of the label will   
            ' flash once per tick of the clock.  
            lblAlarm.Visible = True  
            If blnColorTicker = False Then  
                lblAlarm.BackColor = Color.PeachPuff  
                blnColorTicker = True  
            Else  
                lblAlarm.BackColor = Color.Plum  
                blnColorTicker = False  
            End If  
        Else  
            ' Once the alarm has sounded for a minute, the label is made   
            ' invisible again.  
            lblAlarm.Visible = False  
        End If  
    End Sub  
    ```  
  
     <span data-ttu-id="ae142-244">添加此代码将完成多项任务。</span><span class="sxs-lookup"><span data-stu-id="ae142-244">The addition of this code accomplishes several tasks.</span></span> <span data-ttu-id="ae142-245">`Overrides` 语句指示控件使用此方法替换从基控件继承的方法。</span><span class="sxs-lookup"><span data-stu-id="ae142-245">The `Overrides` statement directs the control to use this method in place of the method that was inherited from the base control.</span></span> <span data-ttu-id="ae142-246">调用此方法时，它通过调用 `MyBase.Timer1_Tick` 语句来调用它重写的方法，从而确保在该控件中重现原始控件包含的所有功能。</span><span class="sxs-lookup"><span data-stu-id="ae142-246">When this method is called, it calls the method it overrides by invoking the `MyBase.Timer1_Tick` statement, ensuring that all of the functionality incorporated in the original control is reproduced in this control.</span></span> <span data-ttu-id="ae142-247">然后，运行附加代码以合并警报功能。</span><span class="sxs-lookup"><span data-stu-id="ae142-247">It then runs additional code to incorporate the alarm functionality.</span></span> <span data-ttu-id="ae142-248">发出警报时，将会出现闪烁的标签控件，并且能够听到提示音。</span><span class="sxs-lookup"><span data-stu-id="ae142-248">A flashing label control will appear when the alarm occurs, and an audible beep will be heard.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ae142-249">因为是重写继承的事件处理程序，所以不必使用 `Handles` 关键字来指定事件。</span><span class="sxs-lookup"><span data-stu-id="ae142-249">Because you are overriding an inherited event handler, you do not have to specify the event with the `Handles` keyword.</span></span> <span data-ttu-id="ae142-250">事件已挂钩。</span><span class="sxs-lookup"><span data-stu-id="ae142-250">The event is already hooked up.</span></span> <span data-ttu-id="ae142-251">需要重写的只是处理程序的实现。</span><span class="sxs-lookup"><span data-stu-id="ae142-251">All you are overriding is the implementation of the handler.</span></span>  
  
     <span data-ttu-id="ae142-252">警报时钟控件已基本完成。</span><span class="sxs-lookup"><span data-stu-id="ae142-252">Your alarm clock control is almost complete.</span></span> <span data-ttu-id="ae142-253">剩下的唯一事情是实现关闭它的方法。</span><span class="sxs-lookup"><span data-stu-id="ae142-253">The only thing that remains is to implement a way to turn it off.</span></span> <span data-ttu-id="ae142-254">为此，将向 `lblAlarm_Click` 方法添加代码。</span><span class="sxs-lookup"><span data-stu-id="ae142-254">To do this, you will add code to the `lblAlarm_Click` method.</span></span>  
  
##### <a name="to-implement-the-shutoff-method"></a><span data-ttu-id="ae142-255">实现关闭方法</span><span class="sxs-lookup"><span data-stu-id="ae142-255">To implement the shutoff method</span></span>  
  
1.  <span data-ttu-id="ae142-256">在解决方案资源管理器中，右键单击“ctlAlarmClock.vb”，然后单击“视图设计器”。</span><span class="sxs-lookup"><span data-stu-id="ae142-256">In Solution Explorer, right-click **ctlAlarmClock.vb**, and then click **View Designer**.</span></span>  
  
2.  <span data-ttu-id="ae142-257">在设计器中，双击“lblAlarm”。</span><span class="sxs-lookup"><span data-stu-id="ae142-257">In the designer, double-click **lblAlarm**.</span></span> <span data-ttu-id="ae142-258">“代码编辑器”随即打开并显示 `Private Sub lblAlarm_Click` 行。</span><span class="sxs-lookup"><span data-stu-id="ae142-258">The **Code Editor** opens to the `Private Sub lblAlarm_Click` line.</span></span>  
  
3.  <span data-ttu-id="ae142-259">将此方法修改为类似如下所示的代码。</span><span class="sxs-lookup"><span data-stu-id="ae142-259">Modify this method so that it resembles the following code.</span></span>  
  
    ```vb  
    Private Sub lblAlarm_Click(ByVal sender As Object, ByVal e As _  
     System.EventArgs) Handles lblAlarm.Click  
        ' Turns off the alarm.  
        AlarmSet = False  
        ' Hides the flashing label.  
        lblAlarm.Visible = False  
    End Sub  
    ```  
  
4.  <span data-ttu-id="ae142-260">在“文件”菜单上，单击“全部保存”保存项目。</span><span class="sxs-lookup"><span data-stu-id="ae142-260">On the **File** menu, click **Save All** to save the project.</span></span>  
  
### <a name="using-the-inherited-control-on-a-form"></a><span data-ttu-id="ae142-261">在窗体上使用继承的控件</span><span class="sxs-lookup"><span data-stu-id="ae142-261">Using the Inherited Control on a Form</span></span>  
 <span data-ttu-id="ae142-262">可按测试基类控件 `ctlClock` 相同的方法测试继承的控件：按 F5 生成项目并在“UserControl 测试容器”中运行控件。</span><span class="sxs-lookup"><span data-stu-id="ae142-262">You can test your inherited control the same way you tested the base class control, `ctlClock`: Press F5 to build the project and run your control in the **UserControl Test Container**.</span></span> <span data-ttu-id="ae142-263">有关详细信息，请参阅[如何：测试 UserControl 的运行时行为](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md)。</span><span class="sxs-lookup"><span data-stu-id="ae142-263">For more information, see [How to: Test the Run-Time Behavior of a UserControl](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>  
  
 <span data-ttu-id="ae142-264">若要使用控件，还需要将其放入窗体中。</span><span class="sxs-lookup"><span data-stu-id="ae142-264">To put your control to use, you will need to host it on a form.</span></span> <span data-ttu-id="ae142-265">与标准复合控件一样，继承的复合控件不能独立存在，而必须承载在窗体或其他容器中。</span><span class="sxs-lookup"><span data-stu-id="ae142-265">As with a standard composite control, an inherited composite control cannot stand alone and must be hosted in a form or other container.</span></span> <span data-ttu-id="ae142-266">由于 `ctlAlarmClock` 的功能更加深入，因此需要附加代码以对其进行测试。</span><span class="sxs-lookup"><span data-stu-id="ae142-266">Since `ctlAlarmClock` has a greater depth of functionality, additional code is required to test it.</span></span> <span data-ttu-id="ae142-267">在本过程中，将编写一个简单的程序来测试 `ctlAlarmClock` 的功能。</span><span class="sxs-lookup"><span data-stu-id="ae142-267">In this procedure, you will write a simple program to test the functionality of `ctlAlarmClock`.</span></span> <span data-ttu-id="ae142-268">将编写代码来设置和显示 `ctlAlarmClock` 的 `AlarmTime` 属性，并测试其固有功能。</span><span class="sxs-lookup"><span data-stu-id="ae142-268">You will write code to set and display the `AlarmTime` property of `ctlAlarmClock`, and will test its inherent functions.</span></span>  
  
##### <a name="to-build-and-add-your-control-to-a-test-form"></a><span data-ttu-id="ae142-269">生成测试窗体并将控件添加到该窗体</span><span class="sxs-lookup"><span data-stu-id="ae142-269">To build and add your control to a test form</span></span>  
  
1.  <span data-ttu-id="ae142-270">在解决方案资源管理器中，右键单击“ctlClockLib”，然后单击“生成”。</span><span class="sxs-lookup"><span data-stu-id="ae142-270">In Solution Explorer, right-click **ctlClockLib**, and then click **Build**.</span></span>  
  
2.  <span data-ttu-id="ae142-271">在“文件”  菜单上，指向“添加” ，然后单击“新建项目” 。</span><span class="sxs-lookup"><span data-stu-id="ae142-271">On the **File** menu, point to **Add**, and then click **New Project**.</span></span>  
  
3.  <span data-ttu-id="ae142-272">将一个新的“Windows 应用程序”项目添加到解决方案，并将其命名为 `Test`。</span><span class="sxs-lookup"><span data-stu-id="ae142-272">Add a new **Windows Application** project to the solution, and name it `Test`.</span></span>  
  
     <span data-ttu-id="ae142-273">“测试”项目随即添加到解决方案资源管理器中。</span><span class="sxs-lookup"><span data-stu-id="ae142-273">The **Test** project is added to Solution Explorer.</span></span>  
  
4.  <span data-ttu-id="ae142-274">在解决方案资源管理器中，右键单击 `Test` 项目节点，然后单击“添加引用”显示“添加引用”对话框。</span><span class="sxs-lookup"><span data-stu-id="ae142-274">In Solution Explorer, right-click the `Test` project node, and then click **Add Reference** to display the **Add Reference** dialog box.</span></span>  
  
5.  <span data-ttu-id="ae142-275">单击标记为“项目”的选项卡。</span><span class="sxs-lookup"><span data-stu-id="ae142-275">Click the tab labeled **Projects**.</span></span> <span data-ttu-id="ae142-276">“项目名称”下将列出项目“ctlClockLib”。</span><span class="sxs-lookup"><span data-stu-id="ae142-276">The project **ctlClockLib** will be listed under **Project Name**.</span></span> <span data-ttu-id="ae142-277">双击“ctlClockLib”将引用添加到测试项目。</span><span class="sxs-lookup"><span data-stu-id="ae142-277">Double-click **ctlClockLib** to add the reference to the test project.</span></span>  
  
6.  <span data-ttu-id="ae142-278">在解决方案资源管理器中，右键单击“测试”，然后单击“生成”。</span><span class="sxs-lookup"><span data-stu-id="ae142-278">In Solution Explorer, right-click **Test**, and then click **Build**.</span></span>  
  
7.  <span data-ttu-id="ae142-279">在“工具箱”中，展开“ctlClockLib 组件”节点。</span><span class="sxs-lookup"><span data-stu-id="ae142-279">In the **Toolbox**, expand the **ctlClockLib Components** node.</span></span>  
  
8.  <span data-ttu-id="ae142-280">双击“ctlAlarmClock”向窗体添加 `ctlAlarmClock` 的实例。</span><span class="sxs-lookup"><span data-stu-id="ae142-280">Double-click **ctlAlarmClock** to add an instance of `ctlAlarmClock` to your form.</span></span>  
  
9. <span data-ttu-id="ae142-281">在**工具箱**，找到并双击**DateTimePicker**若要添加<xref:System.Windows.Forms.DateTimePicker>控制向窗体，以及如何将<xref:System.Windows.Forms.Label>通过双击控件**标签**.</span><span class="sxs-lookup"><span data-stu-id="ae142-281">In the **Toolbox**, locate and double-click **DateTimePicker** to add a <xref:System.Windows.Forms.DateTimePicker> control to your form, and then add a <xref:System.Windows.Forms.Label> control by double-clicking **Label**.</span></span>  
  
10. <span data-ttu-id="ae142-282">使用鼠标将这些控件放置在窗体上合适的位置。</span><span class="sxs-lookup"><span data-stu-id="ae142-282">Use the mouse to position the controls in a convenient place on the form.</span></span>  
  
11. <span data-ttu-id="ae142-283">按下述方法设置这些控件的属性。</span><span class="sxs-lookup"><span data-stu-id="ae142-283">Set the properties of these controls in the following manner.</span></span>  
  
    |<span data-ttu-id="ae142-284">控件</span><span class="sxs-lookup"><span data-stu-id="ae142-284">Control</span></span>|<span data-ttu-id="ae142-285">属性</span><span class="sxs-lookup"><span data-stu-id="ae142-285">Property</span></span>|<span data-ttu-id="ae142-286">“值”</span><span class="sxs-lookup"><span data-stu-id="ae142-286">Value</span></span>|  
    |-------------|--------------|-----------|  
    |`label1`|<span data-ttu-id="ae142-287">**文本**</span><span class="sxs-lookup"><span data-stu-id="ae142-287">**Text**</span></span>|`(blank space)`|  
    ||<span data-ttu-id="ae142-288">**名称**</span><span class="sxs-lookup"><span data-stu-id="ae142-288">**Name**</span></span>|`lblTest`|  
    |`dateTimePicker1`|<span data-ttu-id="ae142-289">**名称**</span><span class="sxs-lookup"><span data-stu-id="ae142-289">**Name**</span></span>|`dtpTest`|  
    ||<span data-ttu-id="ae142-290">**格式**</span><span class="sxs-lookup"><span data-stu-id="ae142-290">**Format**</span></span>|<xref:System.Windows.Forms.DateTimePickerFormat.Time>|  
  
12. <span data-ttu-id="ae142-291">在设计器中，双击“dtpTest”。</span><span class="sxs-lookup"><span data-stu-id="ae142-291">In the designer, double-click **dtpTest**.</span></span>  
  
     <span data-ttu-id="ae142-292">“代码编辑器”随即打开并显示 `Private Sub dtpTest_ValueChanged`。</span><span class="sxs-lookup"><span data-stu-id="ae142-292">The **Code Editor** opens to `Private Sub dtpTest_ValueChanged`.</span></span>  
  
13. <span data-ttu-id="ae142-293">像如下所示修改代码。</span><span class="sxs-lookup"><span data-stu-id="ae142-293">Modify the code so that it resembles the following.</span></span>  
  
    ```vb  
    Private Sub dtpTest_ValueChanged(ByVal sender As Object, ByVal e As _  
        System.EventArgs) Handles dtpTest.ValueChanged  
        ctlAlarmClock1.AlarmTime = dtpTest.Value  
        ctlAlarmClock1.AlarmSet = True  
        lblTest.Text = "Alarm Time is " & Format(ctlAlarmClock1.AlarmTime, _  
            "hh:mm")  
    End Sub  
    ```  
  
14. <span data-ttu-id="ae142-294">在解决方案资源管理器中，右键单击“测试”，然后单击“设为启动项目”。</span><span class="sxs-lookup"><span data-stu-id="ae142-294">In Solution Explorer, right-click **Test**, and then click **Set as StartUp Project**.</span></span>  
  
15. <span data-ttu-id="ae142-295">在“调试”菜单上，单击“启动调试”。</span><span class="sxs-lookup"><span data-stu-id="ae142-295">On the **Debug** menu, click **Start Debugging**.</span></span>  
  
     <span data-ttu-id="ae142-296">测试程序随即启动。</span><span class="sxs-lookup"><span data-stu-id="ae142-296">The test program starts.</span></span> <span data-ttu-id="ae142-297">请注意，在更新的当前时间`ctlAlarmClock`控制和开始时间所示<xref:System.Windows.Forms.DateTimePicker>控件。</span><span class="sxs-lookup"><span data-stu-id="ae142-297">Note that the current time is updated in the `ctlAlarmClock` control, and that the starting time is shown in the <xref:System.Windows.Forms.DateTimePicker> control.</span></span>  
  
16. <span data-ttu-id="ae142-298">单击<xref:System.Windows.Forms.DateTimePicker>其中显示小时的分钟。</span><span class="sxs-lookup"><span data-stu-id="ae142-298">Click the <xref:System.Windows.Forms.DateTimePicker> where the minutes of the hour are displayed.</span></span>  
  
17. <span data-ttu-id="ae142-299">使用键盘设置一个分钟值，使它比 `ctlAlarmClock` 显示的当前时间快一分钟。</span><span class="sxs-lookup"><span data-stu-id="ae142-299">Using the keyboard, set a value for minutes that is one minute greater than the current time shown by `ctlAlarmClock`.</span></span>  
  
     <span data-ttu-id="ae142-300">警报设置的时间在 `lblTest` 中显示。</span><span class="sxs-lookup"><span data-stu-id="ae142-300">The time for the alarm setting is shown in `lblTest`.</span></span> <span data-ttu-id="ae142-301">等候显示的时间到达警报设置时间。</span><span class="sxs-lookup"><span data-stu-id="ae142-301">Wait for the displayed time to reach the alarm setting time.</span></span> <span data-ttu-id="ae142-302">显示时间到达警报设置的时间时，将发出提示音并闪出 `lblAlarm`。</span><span class="sxs-lookup"><span data-stu-id="ae142-302">When the displayed time reaches the time to which the alarm is set, the beep will sound and `lblAlarm` will flash.</span></span>  
  
18. <span data-ttu-id="ae142-303">单击 `lblAlarm` 关闭警报。</span><span class="sxs-lookup"><span data-stu-id="ae142-303">Turn off the alarm by clicking `lblAlarm`.</span></span> <span data-ttu-id="ae142-304">现在可以重置警报。</span><span class="sxs-lookup"><span data-stu-id="ae142-304">You may now reset the alarm.</span></span>  
  
     <span data-ttu-id="ae142-305">本演练涵盖了多个关键概念。</span><span class="sxs-lookup"><span data-stu-id="ae142-305">This walkthrough has covered a number of key concepts.</span></span> <span data-ttu-id="ae142-306">现已应了解如何通过将控件和组件组合到复合控件容器中来创建复合控件。</span><span class="sxs-lookup"><span data-stu-id="ae142-306">You have learned to create a composite control by combining controls and components into a composite control container.</span></span> <span data-ttu-id="ae142-307">还应了解图和将属性添加到控件，以及如何编写代码以实现自定义功能。</span><span class="sxs-lookup"><span data-stu-id="ae142-307">You have learned to add properties to your control, and to write code to implement custom functionality.</span></span> <span data-ttu-id="ae142-308">在最后一节中，应了解到如何通过继承来扩展给定复合控件的功能，以及如何通过重写承载方法来改变这些方法的功能。</span><span class="sxs-lookup"><span data-stu-id="ae142-308">In the last section, you learned to extend the functionality of a given composite control through inheritance, and to alter the functionality of host methods by overriding those methods.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae142-309">请参阅</span><span class="sxs-lookup"><span data-stu-id="ae142-309">See Also</span></span>  
 [<span data-ttu-id="ae142-310">各种自定义控件</span><span class="sxs-lookup"><span data-stu-id="ae142-310">Varieties of Custom Controls</span></span>](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)  
 [<span data-ttu-id="ae142-311">如何：创作复合控件</span><span class="sxs-lookup"><span data-stu-id="ae142-311">How to: Author Composite Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-author-composite-controls.md)  
 [<span data-ttu-id="ae142-312">如何：在“选择工具箱项”对话框中显示控件</span><span class="sxs-lookup"><span data-stu-id="ae142-312">How to: Display a Control in the Choose Toolbox Items Dialog Box</span></span>](../../../../docs/framework/winforms/controls/how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)  
 [<span data-ttu-id="ae142-313">组件创作演练</span><span class="sxs-lookup"><span data-stu-id="ae142-313">Component Authoring Walkthroughs</span></span>](https://msdn.microsoft.com/library/c414cca9-2489-4208-8b38-954586d91c13)
