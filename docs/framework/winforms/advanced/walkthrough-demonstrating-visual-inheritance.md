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
ms.openlocfilehash: bc91e3bde54eedb4d9dbcfcb9f7faa0ccc98e397
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43505619"
---
# <a name="walkthrough-demonstrating-visual-inheritance"></a><span data-ttu-id="b21f9-102">演练：演示可视化继承</span><span class="sxs-lookup"><span data-stu-id="b21f9-102">Walkthrough: Demonstrating Visual Inheritance</span></span>
<span data-ttu-id="b21f9-103">通过 Visual 继承，可以查看基本表单上的控件和添加新控件。</span><span class="sxs-lookup"><span data-stu-id="b21f9-103">Visual inheritance enables you to see the controls on the base form and to add new controls.</span></span> <span data-ttu-id="b21f9-104">在本演练中，你将创建基窗体，并将其编译到类库。</span><span class="sxs-lookup"><span data-stu-id="b21f9-104">In this walkthrough you will create a base form and compile it into a class library.</span></span> <span data-ttu-id="b21f9-105">将此类库导入另一个项目，并创建一个从基窗体继承的新窗体。</span><span class="sxs-lookup"><span data-stu-id="b21f9-105">You will import this class library into another project and create a new form that inherits from the base form.</span></span> <span data-ttu-id="b21f9-106">在本演练中，你将学会如何执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="b21f9-106">During this walkthrough, you will learn how to:</span></span>  
  
-   <span data-ttu-id="b21f9-107">创建包含基窗体的类库项目。</span><span class="sxs-lookup"><span data-stu-id="b21f9-107">Create a class library project containing a base form.</span></span>  
  
-   <span data-ttu-id="b21f9-108">添加具有可修改基窗体的派生类的属性的按钮。</span><span class="sxs-lookup"><span data-stu-id="b21f9-108">Add a button with properties that derived classes of the base form can modify.</span></span>  
  
-   <span data-ttu-id="b21f9-109">添加基窗体的继承者无法修改的按钮。</span><span class="sxs-lookup"><span data-stu-id="b21f9-109">Add a button that cannot be modified by inheritors of the base form.</span></span>  
  
-   <span data-ttu-id="b21f9-110">创建包含从 `BaseForm` 继承的窗体的项目。</span><span class="sxs-lookup"><span data-stu-id="b21f9-110">Create a project containing a form that inherits from `BaseForm`.</span></span>  
  
 <span data-ttu-id="b21f9-111">最后，本演练将显示继承的窗体上私有控件和受保护控件之间的差异。</span><span class="sxs-lookup"><span data-stu-id="b21f9-111">Ultimately, this walkthrough will demonstrate the difference between private and protected controls on an inherited form.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b21f9-112">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="b21f9-112">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="b21f9-113">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="b21f9-113">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="b21f9-114">有关详细信息，请参阅[个性化设置 Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)。</span><span class="sxs-lookup"><span data-stu-id="b21f9-114">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="b21f9-115">并非所有控件都支持从基窗体执行 Visual 继承。</span><span class="sxs-lookup"><span data-stu-id="b21f9-115">Not all controls support visual inheritance from a base form.</span></span> <span data-ttu-id="b21f9-116">以下控件不支持本演练中描述的情景：</span><span class="sxs-lookup"><span data-stu-id="b21f9-116">The following controls do not support the scenario described in this walkthrough:</span></span>  
>   
>  <xref:System.Windows.Forms.WebBrowser>  
>   
>  <xref:System.Windows.Forms.ToolStrip>  
>   
>  <xref:System.Windows.Forms.ToolStripPanel>  
>   
>  <xref:System.Windows.Forms.TableLayoutPanel>  
>   
>  <xref:System.Windows.Forms.FlowLayoutPanel>  
>   
>  <xref:System.Windows.Forms.DataGridView>  
>   
>  <span data-ttu-id="b21f9-117">无论使用何种修饰符（`private``protected` 或 `public`），继承的窗体中的这些控件始终为只读。</span><span class="sxs-lookup"><span data-stu-id="b21f9-117">These controls in the inherited form are always read-only regardless of the modifiers you use (`private`, `protected`, or `public`).</span></span>  
  
## <a name="scenario-steps"></a><span data-ttu-id="b21f9-118">方案步骤</span><span class="sxs-lookup"><span data-stu-id="b21f9-118">Scenario Steps</span></span>  
 <span data-ttu-id="b21f9-119">第一步是创建基窗体。</span><span class="sxs-lookup"><span data-stu-id="b21f9-119">The first step is to create the base form.</span></span>  
  
#### <a name="to-create-a-class-library-project-containing-a-base-form"></a><span data-ttu-id="b21f9-120">创建包含基窗体的类库项目</span><span class="sxs-lookup"><span data-stu-id="b21f9-120">To create a class library project containing a base form</span></span>  
  
1.  <span data-ttu-id="b21f9-121">从**文件**菜单中，选择**新建**，然后**项目**以打开**新项目**对话框。</span><span class="sxs-lookup"><span data-stu-id="b21f9-121">From the **File** menu, choose **New**, and then **Project** to open the **New Project** dialog box.</span></span>  
  
2.  <span data-ttu-id="b21f9-122">创建 Windows 窗体应用程序名为`BaseFormLibrary`。</span><span class="sxs-lookup"><span data-stu-id="b21f9-122">Create a Windows Forms application named `BaseFormLibrary`.</span></span>  
  
3.  <span data-ttu-id="b21f9-123">若要创建一个类库，而不是标准的 Windows 窗体应用程序，在**解决方案资源管理器**，右键单击**BaseFormLibrary**项目节点，然后选择**属性**.</span><span class="sxs-lookup"><span data-stu-id="b21f9-123">To create a class library instead of a standard Windows Forms application, in **Solution Explorer**, right-click the **BaseFormLibrary** project node and then select **Properties**.</span></span>  
  
4.  <span data-ttu-id="b21f9-124">在项目属性中，更改**输出类型**从**Windows 应用程序**到**类库**。</span><span class="sxs-lookup"><span data-stu-id="b21f9-124">In the properties for the project, change the **Output type** from **Windows Application** to **Class Library**.</span></span>  
  
5.  <span data-ttu-id="b21f9-125">从**文件**菜单中，选择**全部保存**将项目和文件保存到默认位置。</span><span class="sxs-lookup"><span data-stu-id="b21f9-125">From the **File** menu, choose **Save All** to save the project and files to the default location.</span></span>  
  
 <span data-ttu-id="b21f9-126">接下来的两步是将按钮添加至基窗体。</span><span class="sxs-lookup"><span data-stu-id="b21f9-126">The next two procedures add buttons to the base form.</span></span> <span data-ttu-id="b21f9-127">为了演示 visual 继承，请通过设置按钮的 `Modifiers` 属性为它们指定不同的访问级别。</span><span class="sxs-lookup"><span data-stu-id="b21f9-127">To demonstrate visual inheritance, you will give the buttons different access levels by setting their `Modifiers` properties.</span></span>  
  
#### <a name="to-add-a-button-that-inheritors-of-the-base-form-can-modify"></a><span data-ttu-id="b21f9-128">添加基窗体的继承者可修改的按钮</span><span class="sxs-lookup"><span data-stu-id="b21f9-128">To add a button that inheritors of the base form can modify</span></span>  
  
1.  <span data-ttu-id="b21f9-129">打开**Form1**在设计器中。</span><span class="sxs-lookup"><span data-stu-id="b21f9-129">Open **Form1** in the designer.</span></span>  
  
2.  <span data-ttu-id="b21f9-130">上**所有 Windows 窗体**选项卡**工具箱**，双击**按钮**到窗体添加一个按钮。</span><span class="sxs-lookup"><span data-stu-id="b21f9-130">On the **All Windows Forms** tab of the **Toolbox**, double-click **Button** to add a button to the form.</span></span> <span data-ttu-id="b21f9-131">使用鼠标来定位按钮和调整其大小。</span><span class="sxs-lookup"><span data-stu-id="b21f9-131">Use the mouse to position and resize the button.</span></span>  
  
3.  <span data-ttu-id="b21f9-132">在“属性”窗口中，设置按钮的下列属性：</span><span class="sxs-lookup"><span data-stu-id="b21f9-132">In the Properties window, set the following properties of the button:</span></span>  
  
    -   <span data-ttu-id="b21f9-133">设置**文本**属性设置为**Say Hello**。</span><span class="sxs-lookup"><span data-stu-id="b21f9-133">Set the **Text** property to **Say Hello**.</span></span>  
  
    -   <span data-ttu-id="b21f9-134">设置 **（名称）** 属性设置为**btnProtected**。</span><span class="sxs-lookup"><span data-stu-id="b21f9-134">Set the **(Name)** property to **btnProtected**.</span></span>  
  
    -   <span data-ttu-id="b21f9-135">设置**修饰符**属性设置为**受保护**。</span><span class="sxs-lookup"><span data-stu-id="b21f9-135">Set the**Modifiers** property to **Protected**.</span></span> <span data-ttu-id="b21f9-136">这使得继承的窗体**Form1**若要修改的属性**btnProtected**。</span><span class="sxs-lookup"><span data-stu-id="b21f9-136">This makes it possible for forms that inherit from **Form1** to modify the properties of **btnProtected**.</span></span>  
  
4.  <span data-ttu-id="b21f9-137">双击**Say Hello**按钮添加事件处理程序**单击**事件。</span><span class="sxs-lookup"><span data-stu-id="b21f9-137">Double-click the **Say Hello** button to add an event handler for the **Click** event.</span></span>  
  
5.  <span data-ttu-id="b21f9-138">将以下代码行添加到事件处理程序：</span><span class="sxs-lookup"><span data-stu-id="b21f9-138">Add the following line of code to the event handler:</span></span>  
  
    ```vb  
    MessageBox.Show("Hello, World!")  
    ```  
  
    ```csharp  
    MessageBox.Show("Hello, World!");  
    ```  
  
#### <a name="to-add-a-button-that-cannot-be-modified-by-inheritors-of-the-base-form"></a><span data-ttu-id="b21f9-139">添加基窗体的继承者不能修改的按钮</span><span class="sxs-lookup"><span data-stu-id="b21f9-139">To add a button that cannot be modified by inheritors of the base form</span></span>  
  
1.  <span data-ttu-id="b21f9-140">切换到设计视图，通过单击**Form1.vb [设计]、 Form1.cs [设计] 或 Form1.jsl [Design]** 选项卡上方代码编辑器中，或通过按 F7。</span><span class="sxs-lookup"><span data-stu-id="b21f9-140">Switch to design view by clicking the **Form1.vb [Design], Form1.cs [Design], or Form1.jsl [Design]** tab above the code editor, or by pressing F7.</span></span>  
  
2.  <span data-ttu-id="b21f9-141">按如下方式添加第二个按钮并设置其属性：</span><span class="sxs-lookup"><span data-stu-id="b21f9-141">Add a second button and set its properties as follows:</span></span>  
  
    -   <span data-ttu-id="b21f9-142">设置**文本**属性设置为**Say Goodbye**。</span><span class="sxs-lookup"><span data-stu-id="b21f9-142">Set the **Text** property to **Say Goodbye**.</span></span>  
  
    -   <span data-ttu-id="b21f9-143">设置 **（名称）** 属性设置为**btnPrivate**。</span><span class="sxs-lookup"><span data-stu-id="b21f9-143">Set the **(Name)** property to **btnPrivate**.</span></span>  
  
    -   <span data-ttu-id="b21f9-144">设置**修饰符**属性设置为**专用**。</span><span class="sxs-lookup"><span data-stu-id="b21f9-144">Set the **Modifiers** property to **Private**.</span></span> <span data-ttu-id="b21f9-145">这使得继承的窗体**Form1**若要修改的属性**btnPrivate**。</span><span class="sxs-lookup"><span data-stu-id="b21f9-145">This makes it impossible for forms that inherit from **Form1** to modify the properties of **btnPrivate**.</span></span>  
  
3.  <span data-ttu-id="b21f9-146">双击**Say Goodbye**按钮添加事件处理程序**单击**事件。</span><span class="sxs-lookup"><span data-stu-id="b21f9-146">Double-click the **Say Goodbye** button to add an event handler for the **Click** event.</span></span> <span data-ttu-id="b21f9-147">将以下代码行放入事件过程：</span><span class="sxs-lookup"><span data-stu-id="b21f9-147">Place the following line of code in the event procedure:</span></span>  
  
    ```vb  
    MessageBox.Show("Goodbye!")  
    ```  
  
    ```csharp  
    MessageBox.Show("Goodbye!");  
    ```  
  
4.  <span data-ttu-id="b21f9-148">从**构建**菜单中，选择**构建 BaseForm 库**生成类库。</span><span class="sxs-lookup"><span data-stu-id="b21f9-148">From the **Build** menu, choose **Build BaseForm Library** to build the class library.</span></span>  
  
     <span data-ttu-id="b21f9-149">构建库后，可创建从刚创建的窗体继承的新项目。</span><span class="sxs-lookup"><span data-stu-id="b21f9-149">Once the library is built, you can create a new project that inherits from the form you just created.</span></span>  
  
#### <a name="to-create-a-project-containing-a-form-that-inherits-from-the-base-form"></a><span data-ttu-id="b21f9-150">创建包含继承自基窗体的窗体的项目</span><span class="sxs-lookup"><span data-stu-id="b21f9-150">To create a project containing a form that inherits from the base form</span></span>  
  
1.  <span data-ttu-id="b21f9-151">从**文件**菜单中，选择**添加**，然后**新项目**以打开**添加新项目**对话框。</span><span class="sxs-lookup"><span data-stu-id="b21f9-151">From the **File** menu, choose **Add** and then **New Project** to open the **Add New Project** dialog box.</span></span>  
  
2.  <span data-ttu-id="b21f9-152">创建 Windows 窗体应用程序名为`InheritanceTest`。</span><span class="sxs-lookup"><span data-stu-id="b21f9-152">Create a Windows Forms application named `InheritanceTest`.</span></span>  
  
#### <a name="to-add-an-inherited-form"></a><span data-ttu-id="b21f9-153">添加继承的窗体</span><span class="sxs-lookup"><span data-stu-id="b21f9-153">To add an inherited form</span></span>  
  
1.  <span data-ttu-id="b21f9-154">在中**解决方案资源管理器**，右键单击**InheritanceTest**项目，选择**添加**，然后选择**新项**。</span><span class="sxs-lookup"><span data-stu-id="b21f9-154">In **Solution Explorer**, right-click the **InheritanceTest** project, select **Add**, and then select**New Item**.</span></span>  
  
2.  <span data-ttu-id="b21f9-155">在中**添加新项**对话框中，选择**Windows 窗体**类别 （如果有一个类别列表），然后选择**继承的窗体**模板。</span><span class="sxs-lookup"><span data-stu-id="b21f9-155">In the **Add New Item** dialog box, select the **Windows Forms** category (if you have a list of categories) and then select the **Inherited Form** template.</span></span>  
  
3.  <span data-ttu-id="b21f9-156">保留默认名称的`Form2`，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="b21f9-156">Leave the default name of `Form2` and then click **Add**.</span></span>  
  
4.  <span data-ttu-id="b21f9-157">在中**继承选择器**对话框中，选择**Form1**从**BaseFormLibrary**项目与窗体继承，并单击**确定**.</span><span class="sxs-lookup"><span data-stu-id="b21f9-157">In the **Inheritance Picker** dialog box, select **Form1** from the **BaseFormLibrary** project as the form to inherit from and click **OK**.</span></span>  
  
     <span data-ttu-id="b21f9-158">这将创建中的窗体**InheritanceTest**派生的窗体中的项目**BaseFormLibrary**。</span><span class="sxs-lookup"><span data-stu-id="b21f9-158">This creates a form in the **InheritanceTest** project that derives from the form in **BaseFormLibrary**.</span></span>  
  
5.  <span data-ttu-id="b21f9-159">继承的窗体 (**Form2**) 在设计器中双击它，如果已打开。</span><span class="sxs-lookup"><span data-stu-id="b21f9-159">Open the inherited form (**Form2**) in the designer by double-clicking it, if it is not already open.</span></span>  
  
     <span data-ttu-id="b21f9-160">继承的按钮在设计器中，有一个符号 (![VisualBasicInheritanceSymbol 屏幕截图](../../../../docs/framework/winforms/advanced/media/vbinheritanceglyph.gif "vbInheritanceGlyph")) 在其上角，指示它们继承。</span><span class="sxs-lookup"><span data-stu-id="b21f9-160">In the designer, the inherited buttons have a symbol (![VisualBasicInheritanceSymbol screenshot](../../../../docs/framework/winforms/advanced/media/vbinheritanceglyph.gif "vbInheritanceGlyph")) in their upper corner, indicating they are inherited.</span></span>  
  
6.  <span data-ttu-id="b21f9-161">选择**Say Hello**按钮，然后观察调整大小图柄。</span><span class="sxs-lookup"><span data-stu-id="b21f9-161">Select the **Say Hello** button and observe the resize handles.</span></span> <span data-ttu-id="b21f9-162">由于此按钮受保护，继承者可以对其进行移动、调整大小、更改标题和进行其他修改。</span><span class="sxs-lookup"><span data-stu-id="b21f9-162">Because this button is protected, the inheritors can move it, resize it, change its caption, and make other modifications.</span></span>  
  
7.  <span data-ttu-id="b21f9-163">选择专用网络**Say Goodbye**按钮，然后请注意，它不具有调整大小图柄。</span><span class="sxs-lookup"><span data-stu-id="b21f9-163">Select the private **Say Goodbye** button, and notice that it does not have resize handles.</span></span> <span data-ttu-id="b21f9-164">此外，在**属性**窗口中，此按钮的属性呈灰显，指示不能修改它们。</span><span class="sxs-lookup"><span data-stu-id="b21f9-164">Additionally, in the **Properties** window, the properties of this button are grayed to indicate they cannot be modified.</span></span>  
  
8.  <span data-ttu-id="b21f9-165">如果使用的 Visual C#:</span><span class="sxs-lookup"><span data-stu-id="b21f9-165">If you are using Visual C#:</span></span>  
  
    1.  <span data-ttu-id="b21f9-166">在中**解决方案资源管理器**，右键单击**Form1**中**InheritanceTest**项目，然后选择**删除**。</span><span class="sxs-lookup"><span data-stu-id="b21f9-166">In **Solution Explorer**, right-click **Form1** in the **InheritanceTest** project and then choose **Delete**.</span></span> <span data-ttu-id="b21f9-167">在显示的消息框，单击**确定**以确认删除。</span><span class="sxs-lookup"><span data-stu-id="b21f9-167">In the message box that appears, click **OK** to confirm the deletion.</span></span>  
  
    2.  <span data-ttu-id="b21f9-168">打开 Program.cs 文件并将 `Application.Run(new Form1());` 行更改为 `Application.Run(new Form2());`。</span><span class="sxs-lookup"><span data-stu-id="b21f9-168">Open the Program.cs file and change the line `Application.Run(new Form1());` to `Application.Run(new Form2());`.</span></span>  
  
9. <span data-ttu-id="b21f9-169">在中**解决方案资源管理器**，右键单击**InheritanceTest**项目，然后选择**设为启动项目**。</span><span class="sxs-lookup"><span data-stu-id="b21f9-169">In **Solution Explorer**, right-click the **InheritanceTest** project and select **Set As Startup Project**.</span></span>  
  
10. <span data-ttu-id="b21f9-170">在中**解决方案资源管理器**，右键单击**InheritanceTest**项目，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="b21f9-170">In **Solution Explorer**, right-click the **InheritanceTest** project and select **Properties**.</span></span>  
  
11. <span data-ttu-id="b21f9-171">在中**InheritanceTest**属性页中，设置**启动对象**要继承的窗体 (**Form2**)。</span><span class="sxs-lookup"><span data-stu-id="b21f9-171">In the **InheritanceTest** property pages, set the **Startup object** to be the inherited form (**Form2**).</span></span>  
  
12. <span data-ttu-id="b21f9-172">按 F5 运行此应用程序，并观察继承的窗体的行为。</span><span class="sxs-lookup"><span data-stu-id="b21f9-172">Press F5 to run the application, and observe the behavior of the inherited form.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="b21f9-173">后续步骤</span><span class="sxs-lookup"><span data-stu-id="b21f9-173">Next Steps</span></span>  
 <span data-ttu-id="b21f9-174">用户控件的继承方式大致相同。</span><span class="sxs-lookup"><span data-stu-id="b21f9-174">Inheritance for user controls works in much the same way.</span></span> <span data-ttu-id="b21f9-175">打开新的类库项目并添加用户控件。</span><span class="sxs-lookup"><span data-stu-id="b21f9-175">Open a new class library project and add a user control.</span></span> <span data-ttu-id="b21f9-176">在其上放置构成控件，然后编译项目。</span><span class="sxs-lookup"><span data-stu-id="b21f9-176">Place constituent controls on it and compile the project.</span></span> <span data-ttu-id="b21f9-177">打开另一个新的类库项目，并添加对已编译的类库的引用。</span><span class="sxs-lookup"><span data-stu-id="b21f9-177">Open another new class library project and add a reference to the compiled class library.</span></span> <span data-ttu-id="b21f9-178">此外，请尝试添加继承的控件 (通过**添加新项**对话框的) 到该项目并使用**继承选择器**。</span><span class="sxs-lookup"><span data-stu-id="b21f9-178">Also, try adding an inherited control (through the **Add New Items** dialog box) to the project and using the **Inheritance Picker**.</span></span> <span data-ttu-id="b21f9-179">添加一个用户控件，并将更改`Inherits`(`:`在 Visual C#) 语句。</span><span class="sxs-lookup"><span data-stu-id="b21f9-179">Add a user control, and change the `Inherits` (`:` in Visual C#) statement.</span></span> <span data-ttu-id="b21f9-180">有关详细信息，请参阅[如何： 继承 Windows 窗体](../../../../docs/framework/winforms/advanced/how-to-inherit-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="b21f9-180">For more information, see [How to: Inherit Windows Forms](../../../../docs/framework/winforms/advanced/how-to-inherit-windows-forms.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b21f9-181">请参阅</span><span class="sxs-lookup"><span data-stu-id="b21f9-181">See Also</span></span>  
 [<span data-ttu-id="b21f9-182">如何：继承 Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="b21f9-182">How to: Inherit Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-inherit-windows-forms.md)  
 [<span data-ttu-id="b21f9-183">Windows 窗体可视化继承</span><span class="sxs-lookup"><span data-stu-id="b21f9-183">Windows Forms Visual Inheritance</span></span>](../../../../docs/framework/winforms/advanced/windows-forms-visual-inheritance.md)  
 [<span data-ttu-id="b21f9-184">Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="b21f9-184">Windows Forms</span></span>](../../../../docs/framework/winforms/index.md)
