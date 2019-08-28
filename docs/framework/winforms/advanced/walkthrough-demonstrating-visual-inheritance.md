---
title: 演练：演示可视化继承
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- form inheritance [Windows Forms], walkthroughs
- visual inheritance
- inheritance [Windows Forms], walkthroughs
- walkthroughs [Windows Forms], visual inheritance
- Windows Forms, inheritance
ms.assetid: 01966086-3142-450e-8210-3fd4cb33f591
ms.openlocfilehash: 32df98852b28963ffb748895156f7d9977c74b92
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046141"
---
# <a name="walkthrough-demonstrating-visual-inheritance"></a><span data-ttu-id="c4538-102">演练：演示可视化继承</span><span class="sxs-lookup"><span data-stu-id="c4538-102">Walkthrough: Demonstrating Visual Inheritance</span></span>

<span data-ttu-id="c4538-103">通过 Visual 继承，可以查看基本表单上的控件和添加新控件。</span><span class="sxs-lookup"><span data-stu-id="c4538-103">Visual inheritance enables you to see the controls on the base form and to add new controls.</span></span> <span data-ttu-id="c4538-104">在本演练中，你将创建基窗体，并将其编译到类库。</span><span class="sxs-lookup"><span data-stu-id="c4538-104">In this walkthrough you will create a base form and compile it into a class library.</span></span> <span data-ttu-id="c4538-105">将此类库导入另一个项目，并创建一个从基窗体继承的新窗体。</span><span class="sxs-lookup"><span data-stu-id="c4538-105">You will import this class library into another project and create a new form that inherits from the base form.</span></span> <span data-ttu-id="c4538-106">在本演练中，你将学会如何执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="c4538-106">During this walkthrough, you will learn how to:</span></span>

- <span data-ttu-id="c4538-107">创建包含基窗体的类库项目。</span><span class="sxs-lookup"><span data-stu-id="c4538-107">Create a class library project containing a base form.</span></span>

- <span data-ttu-id="c4538-108">添加具有可修改基窗体的派生类的属性的按钮。</span><span class="sxs-lookup"><span data-stu-id="c4538-108">Add a button with properties that derived classes of the base form can modify.</span></span>

- <span data-ttu-id="c4538-109">添加基窗体的继承者无法修改的按钮。</span><span class="sxs-lookup"><span data-stu-id="c4538-109">Add a button that cannot be modified by inheritors of the base form.</span></span>

- <span data-ttu-id="c4538-110">创建包含从 `BaseForm` 继承的窗体的项目。</span><span class="sxs-lookup"><span data-stu-id="c4538-110">Create a project containing a form that inherits from `BaseForm`.</span></span>

<span data-ttu-id="c4538-111">最后，本演练将显示继承的窗体上私有控件和受保护控件之间的差异。</span><span class="sxs-lookup"><span data-stu-id="c4538-111">Ultimately, this walkthrough will demonstrate the difference between private and protected controls on an inherited form.</span></span>

> [!CAUTION]
> <span data-ttu-id="c4538-112">并非所有控件都支持从基窗体执行 Visual 继承。</span><span class="sxs-lookup"><span data-stu-id="c4538-112">Not all controls support visual inheritance from a base form.</span></span> <span data-ttu-id="c4538-113">以下控件不支持本演练中描述的情景：</span><span class="sxs-lookup"><span data-stu-id="c4538-113">The following controls do not support the scenario described in this walkthrough:</span></span>
>
> - <xref:System.Windows.Forms.WebBrowser>
>
> - <xref:System.Windows.Forms.ToolStrip>
>
> - <xref:System.Windows.Forms.ToolStripPanel>
>
> - <xref:System.Windows.Forms.TableLayoutPanel>
>
> - <xref:System.Windows.Forms.FlowLayoutPanel>
>
> - <xref:System.Windows.Forms.DataGridView>
>
> <span data-ttu-id="c4538-114">无论使用何种修饰符（`private``protected` 或 `public`），继承的窗体中的这些控件始终为只读。</span><span class="sxs-lookup"><span data-stu-id="c4538-114">These controls in the inherited form are always read-only regardless of the modifiers you use (`private`, `protected`, or `public`).</span></span>

## <a name="create-a-class-library-project-containing-a-base-form"></a><span data-ttu-id="c4538-115">创建包含基窗体的类库项目</span><span class="sxs-lookup"><span data-stu-id="c4538-115">Create a class library project containing a base form</span></span>

1. <span data-ttu-id="c4538-116">在 Visual Studio 的 "**文件**" 菜单中, 选择 "**新建** > **项目**" 以打开 "**新建项目**" 对话框。</span><span class="sxs-lookup"><span data-stu-id="c4538-116">In Visual Studio, from the **File** menu, choose **New** > **Project** to open the **New Project** dialog box.</span></span>

2. <span data-ttu-id="c4538-117">创建一个名为`BaseFormLibrary`的 Windows 窗体应用程序。</span><span class="sxs-lookup"><span data-stu-id="c4538-117">Create a Windows Forms application named `BaseFormLibrary`.</span></span>

3. <span data-ttu-id="c4538-118">若要创建类库而不是标准 Windows 窗体应用程序, 请在**解决方案资源管理器**中右键单击 " **BaseFormLibrary** " 项目节点, 然后选择 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="c4538-118">To create a class library instead of a standard Windows Forms application, in **Solution Explorer**, right-click the **BaseFormLibrary** project node and then select **Properties**.</span></span>

4. <span data-ttu-id="c4538-119">在项目的属性中, 将 "**输出类型**" 从 " **Windows 应用程序**" 更改为 "类库"。</span><span class="sxs-lookup"><span data-stu-id="c4538-119">In the properties for the project, change the **Output type** from **Windows Application** to **Class Library**.</span></span>

5. <span data-ttu-id="c4538-120">从 "**文件**" 菜单中, 选择 "**全部保存**" 以将项目和文件保存到默认位置。</span><span class="sxs-lookup"><span data-stu-id="c4538-120">From the **File** menu, choose **Save All** to save the project and files to the default location.</span></span>

<span data-ttu-id="c4538-121">接下来的两步是将按钮添加至基窗体。</span><span class="sxs-lookup"><span data-stu-id="c4538-121">The next two procedures add buttons to the base form.</span></span> <span data-ttu-id="c4538-122">为了演示 visual 继承，请通过设置按钮的 `Modifiers` 属性为它们指定不同的访问级别。</span><span class="sxs-lookup"><span data-stu-id="c4538-122">To demonstrate visual inheritance, you will give the buttons different access levels by setting their `Modifiers` properties.</span></span>

## <a name="add-a-button-that-inheritors-of-the-base-form-can-modify"></a><span data-ttu-id="c4538-123">添加一个按钮, 使基窗体的继承者可以修改</span><span class="sxs-lookup"><span data-stu-id="c4538-123">Add a button that inheritors of the base form can modify</span></span>

1. <span data-ttu-id="c4538-124">在设计器中打开“Form1”。</span><span class="sxs-lookup"><span data-stu-id="c4538-124">Open **Form1** in the designer.</span></span>

2. <span data-ttu-id="c4538-125">在 "**工具箱**" 的 "**所有 Windows 窗体**" 选项卡上, 双击 "**按钮**" 向窗体添加一个按钮。</span><span class="sxs-lookup"><span data-stu-id="c4538-125">On the **All Windows Forms** tab of the **Toolbox**, double-click **Button** to add a button to the form.</span></span> <span data-ttu-id="c4538-126">使用鼠标来定位按钮和调整其大小。</span><span class="sxs-lookup"><span data-stu-id="c4538-126">Use the mouse to position and resize the button.</span></span>

3. <span data-ttu-id="c4538-127">在“属性”窗口中，设置按钮的下列属性：</span><span class="sxs-lookup"><span data-stu-id="c4538-127">In the Properties window, set the following properties of the button:</span></span>

    - <span data-ttu-id="c4538-128">将**Text**属性设置为 " **Hello**"。</span><span class="sxs-lookup"><span data-stu-id="c4538-128">Set the **Text** property to **Say Hello**.</span></span>

    - <span data-ttu-id="c4538-129">将 **(Name)** 属性设置为**btnProtected**。</span><span class="sxs-lookup"><span data-stu-id="c4538-129">Set the **(Name)** property to **btnProtected**.</span></span>

    - <span data-ttu-id="c4538-130">将 "**修饰符**" 属性设置为 "**受保护**"。</span><span class="sxs-lookup"><span data-stu-id="c4538-130">Set the **Modifiers** property to **Protected**.</span></span> <span data-ttu-id="c4538-131">这使得从**Form1**继承的窗体有可能修改**btnProtected**的属性。</span><span class="sxs-lookup"><span data-stu-id="c4538-131">This makes it possible for forms that inherit from **Form1** to modify the properties of **btnProtected**.</span></span>

4. <span data-ttu-id="c4538-132">双击 "**朗读**" 按钮, 为**click**事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="c4538-132">Double-click the **Say Hello** button to add an event handler for the **Click** event.</span></span>

5. <span data-ttu-id="c4538-133">将以下代码行添加到事件处理程序：</span><span class="sxs-lookup"><span data-stu-id="c4538-133">Add the following line of code to the event handler:</span></span>

    ```vb
    MessageBox.Show("Hello, World!")
    ```

    ```csharp
    MessageBox.Show("Hello, World!");
    ```

## <a name="add-a-button-that-cannot-be-modified-by-inheritors-of-the-base-form"></a><span data-ttu-id="c4538-134">添加基窗体的继承者无法修改的按钮</span><span class="sxs-lookup"><span data-stu-id="c4538-134">Add a button that cannot be modified by inheritors of the base form</span></span>

1. <span data-ttu-id="c4538-135">通过单击代码编辑器上方的 " **form1 [design]"、"Form1.cs [design]" 或 "jsl [design]** " 选项卡, 或者按 F7, 切换到 "设计" 视图。</span><span class="sxs-lookup"><span data-stu-id="c4538-135">Switch to design view by clicking the **Form1.vb [Design], Form1.cs [Design], or Form1.jsl [Design]** tab above the code editor, or by pressing F7.</span></span>

2. <span data-ttu-id="c4538-136">按如下方式添加第二个按钮并设置其属性：</span><span class="sxs-lookup"><span data-stu-id="c4538-136">Add a second button and set its properties as follows:</span></span>

    - <span data-ttu-id="c4538-137">将**Text**属性设置为**再见**。</span><span class="sxs-lookup"><span data-stu-id="c4538-137">Set the **Text** property to **Say Goodbye**.</span></span>

    - <span data-ttu-id="c4538-138">将 **(Name)** 属性设置为**btnPrivate**。</span><span class="sxs-lookup"><span data-stu-id="c4538-138">Set the **(Name)** property to **btnPrivate**.</span></span>

    - <span data-ttu-id="c4538-139">将 "**修饰符**" 属性设置为 "**私有**"。</span><span class="sxs-lookup"><span data-stu-id="c4538-139">Set the **Modifiers** property to **Private**.</span></span> <span data-ttu-id="c4538-140">这使得从**Form1**继承的窗体无法修改**btnPrivate**的属性。</span><span class="sxs-lookup"><span data-stu-id="c4538-140">This makes it impossible for forms that inherit from **Form1** to modify the properties of **btnPrivate**.</span></span>

3. <span data-ttu-id="c4538-141">双击 "向**再见**" 按钮, 为**click**事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="c4538-141">Double-click the **Say Goodbye** button to add an event handler for the **Click** event.</span></span> <span data-ttu-id="c4538-142">将以下代码行放入事件过程：</span><span class="sxs-lookup"><span data-stu-id="c4538-142">Place the following line of code in the event procedure:</span></span>

    ```vb
    MessageBox.Show("Goodbye!")
    ```

    ```csharp
    MessageBox.Show("Goodbye!");
    ```

4. <span data-ttu-id="c4538-143">在 "**生成**" 菜单中, 选择 "**生成 BaseForm 库**" 以生成类库。</span><span class="sxs-lookup"><span data-stu-id="c4538-143">From the **Build** menu, choose **Build BaseForm Library** to build the class library.</span></span>

     <span data-ttu-id="c4538-144">构建库后，可创建从刚创建的窗体继承的新项目。</span><span class="sxs-lookup"><span data-stu-id="c4538-144">Once the library is built, you can create a new project that inherits from the form you just created.</span></span>

## <a name="create-a-project-containing-a-form-that-inherits-from-the-base-form"></a><span data-ttu-id="c4538-145">创建一个包含继承自基窗体的窗体的项目</span><span class="sxs-lookup"><span data-stu-id="c4538-145">Create a project containing a form that inherits from the base form</span></span>

1. <span data-ttu-id="c4538-146">从 "**文件**" 菜单中, 依次选择 "**添加**"、"**新建项目**", 以打开 "**添加新项目**" 对话框。</span><span class="sxs-lookup"><span data-stu-id="c4538-146">From the **File** menu, choose **Add** and then **New Project** to open the **Add New Project** dialog box.</span></span>

2. <span data-ttu-id="c4538-147">创建一个名为`InheritanceTest`的 Windows 窗体应用程序。</span><span class="sxs-lookup"><span data-stu-id="c4538-147">Create a Windows Forms application named `InheritanceTest`.</span></span>

## <a name="add-an-inherited-form"></a><span data-ttu-id="c4538-148">添加继承的窗体</span><span class="sxs-lookup"><span data-stu-id="c4538-148">Add an inherited form</span></span>

1. <span data-ttu-id="c4538-149">在**解决方案资源管理器**中, 右键单击**InheritanceTest**项目, 选择 "**添加**", 然后选择 "**新建项**"。</span><span class="sxs-lookup"><span data-stu-id="c4538-149">In **Solution Explorer**, right-click the **InheritanceTest** project, select **Add**, and then select **New Item**.</span></span>

2. <span data-ttu-id="c4538-150">在 "**添加新项**" 对话框中, 选择 " **Windows 窗体**" 类别 (如果有类别的列表), 然后选择 "**继承的窗体**" 模板。</span><span class="sxs-lookup"><span data-stu-id="c4538-150">In the **Add New Item** dialog box, select the **Windows Forms** category (if you have a list of categories) and then select the **Inherited Form** template.</span></span>

3. <span data-ttu-id="c4538-151">保留的默认名称`Form2` , 然后单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="c4538-151">Leave the default name of `Form2` and then click **Add**.</span></span>

4. <span data-ttu-id="c4538-152">在 "**继承选择器**" 对话框中, 从**BaseFormLibrary**项目中选择**Form1**作为要从其继承的表单, 然后单击 **"确定"** 。</span><span class="sxs-lookup"><span data-stu-id="c4538-152">In the **Inheritance Picker** dialog box, select **Form1** from the **BaseFormLibrary** project as the form to inherit from and click **OK**.</span></span>

     <span data-ttu-id="c4538-153">这会在**InheritanceTest**项目中创建一个从**BaseFormLibrary**中的表单派生的窗体。</span><span class="sxs-lookup"><span data-stu-id="c4538-153">This creates a form in the **InheritanceTest** project that derives from the form in **BaseFormLibrary**.</span></span>

5. <span data-ttu-id="c4538-154">如果在设计器中打开了继承窗体 (Form2), 则双击该窗体 (**Form2**) (如果尚未打开)。</span><span class="sxs-lookup"><span data-stu-id="c4538-154">Open the inherited form (**Form2**) in the designer by double-clicking it, if it is not already open.</span></span>

    <span data-ttu-id="c4538-155">在设计器中, 继承的按钮具有符号 (</span><span class="sxs-lookup"><span data-stu-id="c4538-155">In the designer, the inherited buttons have a symbol (</span></span>![Visual Basic 继承符号的屏幕截图。](./media/walkthrough-demonstrating-visual-inheritance/visual-basic-inheritance-glyph.gif)<span data-ttu-id="c4538-157">), 指示它们是继承的。</span><span class="sxs-lookup"><span data-stu-id="c4538-157">) in their upper corner, indicating they are inherited.</span></span>

6. <span data-ttu-id="c4538-158">选择 " **Hello** " 按钮, 并观察调整大小控点。</span><span class="sxs-lookup"><span data-stu-id="c4538-158">Select the **Say Hello** button and observe the resize handles.</span></span> <span data-ttu-id="c4538-159">由于此按钮受保护，继承者可以对其进行移动、调整大小、更改标题和进行其他修改。</span><span class="sxs-lookup"><span data-stu-id="c4538-159">Because this button is protected, the inheritors can move it, resize it, change its caption, and make other modifications.</span></span>

7. <span data-ttu-id="c4538-160">选择 "私有" 表示 "**再见**" 按钮, 请注意, 它没有调整大小控点。</span><span class="sxs-lookup"><span data-stu-id="c4538-160">Select the private **Say Goodbye** button, and notice that it does not have resize handles.</span></span> <span data-ttu-id="c4538-161">此外, 在 "**属性**" 窗口中, 此按钮的属性将灰显, 指示无法修改它们。</span><span class="sxs-lookup"><span data-stu-id="c4538-161">Additionally, in the **Properties** window, the properties of this button are grayed to indicate they cannot be modified.</span></span>

8. <span data-ttu-id="c4538-162">如果使用的是视觉C#对象:</span><span class="sxs-lookup"><span data-stu-id="c4538-162">If you are using Visual C#:</span></span>

    1. <span data-ttu-id="c4538-163">在**解决方案资源管理器**中, 右键单击**InheritanceTest**项目中的 " **Form1** ", 然后选择 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="c4538-163">In **Solution Explorer**, right-click **Form1** in the **InheritanceTest** project and then choose **Delete**.</span></span> <span data-ttu-id="c4538-164">在出现的消息框中, 单击 **"确定"** 以确认删除。</span><span class="sxs-lookup"><span data-stu-id="c4538-164">In the message box that appears, click **OK** to confirm the deletion.</span></span>

    2. <span data-ttu-id="c4538-165">打开 Program.cs 文件并将 `Application.Run(new Form1());` 行更改为 `Application.Run(new Form2());`。</span><span class="sxs-lookup"><span data-stu-id="c4538-165">Open the Program.cs file and change the line `Application.Run(new Form1());` to `Application.Run(new Form2());`.</span></span>

9. <span data-ttu-id="c4538-166">在**解决方案资源管理器**中, 右键单击**InheritanceTest**项目, 然后选择 "**设为启动项目**"。</span><span class="sxs-lookup"><span data-stu-id="c4538-166">In **Solution Explorer**, right-click the **InheritanceTest** project and select **Set As Startup Project**.</span></span>

10. <span data-ttu-id="c4538-167">在**解决方案资源管理器**中, 右键单击**InheritanceTest**项目, 然后选择 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="c4538-167">In **Solution Explorer**, right-click the **InheritanceTest** project and select **Properties**.</span></span>

11. <span data-ttu-id="c4538-168">在**InheritanceTest**属性页中, 将**启动对象**设置为继承的窗体 (**Form2**)。</span><span class="sxs-lookup"><span data-stu-id="c4538-168">In the **InheritanceTest** property pages, set the **Startup object** to be the inherited form (**Form2**).</span></span>

12. <span data-ttu-id="c4538-169">按**F5**运行应用程序, 并观察继承窗体的行为。</span><span class="sxs-lookup"><span data-stu-id="c4538-169">Press **F5** to run the application, and observe the behavior of the inherited form.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c4538-170">后续步骤</span><span class="sxs-lookup"><span data-stu-id="c4538-170">Next steps</span></span>

<span data-ttu-id="c4538-171">用户控件的继承方式大致相同。</span><span class="sxs-lookup"><span data-stu-id="c4538-171">Inheritance for user controls works in much the same way.</span></span> <span data-ttu-id="c4538-172">打开新的类库项目并添加用户控件。</span><span class="sxs-lookup"><span data-stu-id="c4538-172">Open a new class library project and add a user control.</span></span> <span data-ttu-id="c4538-173">在其上放置构成控件，然后编译项目。</span><span class="sxs-lookup"><span data-stu-id="c4538-173">Place constituent controls on it and compile the project.</span></span> <span data-ttu-id="c4538-174">打开另一个新的类库项目，并添加对已编译的类库的引用。</span><span class="sxs-lookup"><span data-stu-id="c4538-174">Open another new class library project and add a reference to the compiled class library.</span></span> <span data-ttu-id="c4538-175">同时, 尝试将继承的控件 (通过 "**添加新项**" 对话框) 添加到项目, 并使用**继承选择器**。</span><span class="sxs-lookup"><span data-stu-id="c4538-175">Also, try adding an inherited control (through the **Add New Items** dialog box) to the project and using the **Inheritance Picker**.</span></span> <span data-ttu-id="c4538-176">添加用户控件, 并更改`Inherits` (`:`在 Visual C#语句中) 语句。</span><span class="sxs-lookup"><span data-stu-id="c4538-176">Add a user control, and change the `Inherits` (`:` in Visual C#) statement.</span></span> <span data-ttu-id="c4538-177">有关详细信息，请参阅[如何：继承 Windows 窗体](how-to-inherit-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="c4538-177">For more information, see [How to: Inherit Windows Forms](how-to-inherit-windows-forms.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c4538-178">请参阅</span><span class="sxs-lookup"><span data-stu-id="c4538-178">See also</span></span>

- [<span data-ttu-id="c4538-179">如何：继承 Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="c4538-179">How to: Inherit Windows Forms</span></span>](how-to-inherit-windows-forms.md)
- [<span data-ttu-id="c4538-180">Windows 窗体可视化继承</span><span class="sxs-lookup"><span data-stu-id="c4538-180">Windows Forms Visual Inheritance</span></span>](windows-forms-visual-inheritance.md)
- [<span data-ttu-id="c4538-181">Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="c4538-181">Windows Forms</span></span>](../index.md)
