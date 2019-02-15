---
title: 演练：使用 Visual C# 从 Windows 窗体控件继承
ms.date: 03/30/2017
helpviewer_keywords:
- inheritance [Windows Forms], custom controls
- inheritance [Windows Forms], control
- Windows Forms controls, inheritance
- inheritance [Windows Forms], walkthroughs
- custom controls [Windows Forms], inheritance
ms.assetid: 09476da0-8d4c-4a4c-b969-649519dfb438
ms.openlocfilehash: 7d9fbc518d54ab83d517a5c305b171d4b77a664a
ms.sourcegitcommit: bef803e2025642df39f2f1e046767d89031e0304
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2019
ms.locfileid: "56305943"
---
# <a name="walkthrough-inheriting-from-a-windows-forms-control-with-visual-c"></a><span data-ttu-id="ebac5-102">演练：使用 Visual C# 从 Windows 窗体控件继承</span><span class="sxs-lookup"><span data-stu-id="ebac5-102">Walkthrough: Inheriting from a Windows Forms Control with Visual C#</span></span> #
<span data-ttu-id="ebac5-103">使用 [!INCLUDE[csprcslong](../../../../includes/csprcslong-md.md)] 可通过继承来创建功能强大的自定义控件。</span><span class="sxs-lookup"><span data-stu-id="ebac5-103">With [!INCLUDE[csprcslong](../../../../includes/csprcslong-md.md)], you can create powerful custom controls through *inheritance*.</span></span> <span data-ttu-id="ebac5-104">通过继承，可以创建不仅保留了标准 Windows 窗体控件的所有固有功能，而且还包含自定义功能的控件。</span><span class="sxs-lookup"><span data-stu-id="ebac5-104">Through inheritance you are able to create controls that retain all of the inherent functionality of standard Windows Forms controls but also incorporate custom functionality.</span></span> <span data-ttu-id="ebac5-105">在本演练中，将创建一个名为 `ValueButton` 的简单继承控件。</span><span class="sxs-lookup"><span data-stu-id="ebac5-105">In this walkthrough, you will create a simple inherited control called `ValueButton`.</span></span> <span data-ttu-id="ebac5-106">此按钮将继承标准 Windows 窗体的功能<xref:System.Windows.Forms.Button>控件，并将公开一个名为的自定义属性`ButtonValue`。</span><span class="sxs-lookup"><span data-stu-id="ebac5-106">This button will inherit functionality from the standard Windows Forms <xref:System.Windows.Forms.Button> control, and will expose a custom property called `ButtonValue`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ebac5-107">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="ebac5-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="ebac5-108">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="ebac5-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="ebac5-109">有关详细信息，请参阅[个性化设置 Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)。</span><span class="sxs-lookup"><span data-stu-id="ebac5-109">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="ebac5-110">创建项目</span><span class="sxs-lookup"><span data-stu-id="ebac5-110">Creating the Project</span></span>  
 <span data-ttu-id="ebac5-111">创建新的项目时应指定其名称，以设置根命名空间、程序集名称和项目名称，并确保默认组件将位于正确的命名空间中。</span><span class="sxs-lookup"><span data-stu-id="ebac5-111">When you create a new project, you specify its name in order to set the root namespace, assembly name, and project name, and to ensure that the default component will be in the correct namespace.</span></span>  
  
#### <a name="to-create-the-valuebuttonlib-control-library-and-the-valuebutton-control"></a><span data-ttu-id="ebac5-112">创建 ValueButtonLib 控件库和 ValueButton 控件</span><span class="sxs-lookup"><span data-stu-id="ebac5-112">To create the ValueButtonLib control library and the ValueButton control</span></span>  
  
1.  <span data-ttu-id="ebac5-113">在“文件”菜单上指向“新建”，然后单击“项目”打开“新建项目”对话框。</span><span class="sxs-lookup"><span data-stu-id="ebac5-113">On the **File** menu, point to **New** and then click **Project** to open the **New Project** dialog box.</span></span>  
  
2.  <span data-ttu-id="ebac5-114">选择**Windows 窗体控件库**项目模板从列表中的 Visual C# 项目，然后键入`ValueButtonLib`中**名称**框。</span><span class="sxs-lookup"><span data-stu-id="ebac5-114">Select the **Windows Forms Control Library** project template from the list of Visual C# Projects, and type `ValueButtonLib` in the **Name** box.</span></span>  
  
     <span data-ttu-id="ebac5-115">默认情况下，项目名称 `ValueButtonLib` 也会分配到根命名空间中。</span><span class="sxs-lookup"><span data-stu-id="ebac5-115">The project name, `ValueButtonLib`, is also assigned to the root namespace by default.</span></span> <span data-ttu-id="ebac5-116">根命名空间用于限定程序集中的组件名。</span><span class="sxs-lookup"><span data-stu-id="ebac5-116">The root namespace is used to qualify the names of components in the assembly.</span></span> <span data-ttu-id="ebac5-117">例如，如果两个程序集都提供名为 `ValueButton` 的组件，则可以使用 `ValueButtonLib.ValueButton` 指定 `ValueButton` 组件。</span><span class="sxs-lookup"><span data-stu-id="ebac5-117">For example, if two assemblies provide components named `ValueButton`, you can specify your `ValueButton` component using `ValueButtonLib.ValueButton`.</span></span> <span data-ttu-id="ebac5-118">有关详细信息，请参阅[命名空间](../../../csharp/programming-guide/namespaces/index.md)。</span><span class="sxs-lookup"><span data-stu-id="ebac5-118">For more information, see [Namespaces](../../../csharp/programming-guide/namespaces/index.md).</span></span>  
  
3.  <span data-ttu-id="ebac5-119">在“解决方案资源管理器”中，右键单击“UserControl1.cs”，然后从快捷菜单中选择“重命名”。</span><span class="sxs-lookup"><span data-stu-id="ebac5-119">In **Solution Explorer**, right-click **UserControl1.cs**, then choose **Rename** from the shortcut menu.</span></span> <span data-ttu-id="ebac5-120">将文件名更改为 `ValueButton.cs`。</span><span class="sxs-lookup"><span data-stu-id="ebac5-120">Change the file name to `ValueButton.cs`.</span></span> <span data-ttu-id="ebac5-121">询问是否希望重命名对代码元素“**”的所有引用时，单击“是”**`UserControl1`按钮。</span><span class="sxs-lookup"><span data-stu-id="ebac5-121">Click the **Yes** button when you are asked if you want to rename all references to the code element '`UserControl1`'.</span></span>  
  
4.  <span data-ttu-id="ebac5-122">在“解决方案资源管理器”中，右键单击“ValueButton.cs”并选择“查看代码”。</span><span class="sxs-lookup"><span data-stu-id="ebac5-122">In **Solution Explorer**, right-click **ValueButton.cs** and select **View Code**.</span></span>  
  
5.  <span data-ttu-id="ebac5-123">找到`class`语句行`public partial class ValueButton`，并将该控件从从中要继承的类型更改<xref:System.Windows.Forms.UserControl>到<xref:System.Windows.Forms.Button>。</span><span class="sxs-lookup"><span data-stu-id="ebac5-123">Locate the `class` statement line, `public partial class ValueButton`, and change the type from which this control inherits from <xref:System.Windows.Forms.UserControl> to <xref:System.Windows.Forms.Button>.</span></span> <span data-ttu-id="ebac5-124">这允许继承的控件继承的所有功能<xref:System.Windows.Forms.Button>控件。</span><span class="sxs-lookup"><span data-stu-id="ebac5-124">This allows your inherited control to inherit all the functionality of the <xref:System.Windows.Forms.Button> control.</span></span>  
  
6.  <span data-ttu-id="ebac5-125">在“解决方案资源管理器”中打开“ValueButton.cs”节点，以显示设计器生成的代码文件 **ValueButton.Designer.cs**。</span><span class="sxs-lookup"><span data-stu-id="ebac5-125">In **Solution Explorer**, open the **ValueButton.cs** node to display the designer-generated code file, **ValueButton.Designer.cs**.</span></span> <span data-ttu-id="ebac5-126">在“代码编辑器”中打开此文件。</span><span class="sxs-lookup"><span data-stu-id="ebac5-126">Open this file in the **Code Editor**.</span></span>  
  
7.  <span data-ttu-id="ebac5-127">找到`InitializeComponent`方法，并删除的行，将分配<xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="ebac5-127">Locate the `InitializeComponent` method and remove the line that assigns the <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A> property.</span></span> <span data-ttu-id="ebac5-128">此属性中不存在<xref:System.Windows.Forms.Button>控件。</span><span class="sxs-lookup"><span data-stu-id="ebac5-128">This property does not exist in the <xref:System.Windows.Forms.Button> control.</span></span>  
  
8.  <span data-ttu-id="ebac5-129">在“文件”菜单中，选择“全部保存”以保存项目。</span><span class="sxs-lookup"><span data-stu-id="ebac5-129">From the **File** menu, choose **Save All** to save the project.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ebac5-130">可视化设计器不再可用。</span><span class="sxs-lookup"><span data-stu-id="ebac5-130">A visual designer is no longer available.</span></span> <span data-ttu-id="ebac5-131">因为<xref:System.Windows.Forms.Button>控件不自行绘制，则无法在设计器中修改其外观。</span><span class="sxs-lookup"><span data-stu-id="ebac5-131">Because the <xref:System.Windows.Forms.Button> control does its own painting, you are unable to modify its appearance in the designer.</span></span> <span data-ttu-id="ebac5-132">其可视表示形式将完全从它继承的类相同 (即， <xref:System.Windows.Forms.Button>) 除非在代码中修改。</span><span class="sxs-lookup"><span data-stu-id="ebac5-132">Its visual representation will be exactly the same as that of the class it inherits from (that is, <xref:System.Windows.Forms.Button>) unless modified in the code.</span></span> <span data-ttu-id="ebac5-133">但仍然可以向设计器图面添加不含 UI 元素的组件。</span><span class="sxs-lookup"><span data-stu-id="ebac5-133">You can still add components, which have no UI elements, to the design surface.</span></span>  
  
## <a name="adding-a-property-to-your-inherited-control"></a><span data-ttu-id="ebac5-134">将属性添加到继承控件</span><span class="sxs-lookup"><span data-stu-id="ebac5-134">Adding a Property to Your Inherited Control</span></span>  
 <span data-ttu-id="ebac5-135">继承的 Windows 窗体控件的可能用途之一是创建与标准 Windows 窗体控件的外观和感受相同、但公开自定义属性的控件。</span><span class="sxs-lookup"><span data-stu-id="ebac5-135">One possible use of inherited Windows Forms controls is the creation of controls that are identical in look and feel of standard Windows Forms controls, but expose custom properties.</span></span> <span data-ttu-id="ebac5-136">在本节中，将向控件中添加名为 `ButtonValue` 的属性。</span><span class="sxs-lookup"><span data-stu-id="ebac5-136">In this section, you will add a property called `ButtonValue` to your control.</span></span>  
  
#### <a name="to-add-the-value-property"></a><span data-ttu-id="ebac5-137">添加 Value 属性</span><span class="sxs-lookup"><span data-stu-id="ebac5-137">To add the Value property</span></span>  
  
1.  <span data-ttu-id="ebac5-138">在“解决方案资源管理器”中，右键单击“ValueButton.cs”，然后从快捷菜单中单击“查看代码”。</span><span class="sxs-lookup"><span data-stu-id="ebac5-138">In **Solution Explorer**, right-click **ValueButton.cs**, and then click **View Code** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="ebac5-139">找到 `class` 语句。</span><span class="sxs-lookup"><span data-stu-id="ebac5-139">Locate the `class` statement.</span></span> <span data-ttu-id="ebac5-140">紧接 `{` 之后键入以下代码：</span><span class="sxs-lookup"><span data-stu-id="ebac5-140">Immediately after the `{`, type the following code:</span></span>  
  
    ```csharp  
    // Creates the private variable that will store the value of your   
    // property.  
    private int varValue;  
    // Declares the property.  
    public int ButtonValue  
    {  
       // Sets the method for retrieving the value of your property.  
       get  
       {  
          return varValue;  
       }  
       // Sets the method for setting the value of your property.  
       set  
       {  
          varValue = value;  
       }  
    }  
    ```  
  
     <span data-ttu-id="ebac5-141">此代码设置存储和检索 `ButtonValue` 属性的方法。</span><span class="sxs-lookup"><span data-stu-id="ebac5-141">This code sets the methods by which the `ButtonValue` property is stored and retrieved.</span></span> <span data-ttu-id="ebac5-142">`get` 语句将返回的值设置为存储在私有变量 `varValue` 中的值，而 `set` 语句通过使用 `value` 关键字设置该私有变量的值。</span><span class="sxs-lookup"><span data-stu-id="ebac5-142">The `get` statement sets the value returned to the value that is stored in the private variable `varValue`, and the `set` statement sets the value of the private variable by use of the `value` keyword.</span></span>  
  
3.  <span data-ttu-id="ebac5-143">在“文件”菜单中，选择“全部保存”以保存项目。</span><span class="sxs-lookup"><span data-stu-id="ebac5-143">From the **File** menu, choose **Save All** to save the project.</span></span>  
  
## <a name="testing-your-control"></a><span data-ttu-id="ebac5-144">测试控件</span><span class="sxs-lookup"><span data-stu-id="ebac5-144">Testing Your Control</span></span>  
 <span data-ttu-id="ebac5-145">控件不是独立的项目，它们必须托管在容器中。</span><span class="sxs-lookup"><span data-stu-id="ebac5-145">Controls are not stand-alone projects; they must be hosted in a container.</span></span> <span data-ttu-id="ebac5-146">若要测试控件，必须提供一个测试项目，以使控件在其中运行。</span><span class="sxs-lookup"><span data-stu-id="ebac5-146">In order to test your control, you must provide a test project for it to run in.</span></span> <span data-ttu-id="ebac5-147">还必须通过生成（编译）该控件使测试项目能够访问它。</span><span class="sxs-lookup"><span data-stu-id="ebac5-147">You must also make your control accessible to the test project by building (compiling) it.</span></span> <span data-ttu-id="ebac5-148">在本节中，将生成控件并在 Windows 窗体中对其进行测试。</span><span class="sxs-lookup"><span data-stu-id="ebac5-148">In this section, you will build your control and test it in a Windows Form.</span></span>  
  
#### <a name="to-build-your-control"></a><span data-ttu-id="ebac5-149">生成控件</span><span class="sxs-lookup"><span data-stu-id="ebac5-149">To build your control</span></span>  
  
1.  <span data-ttu-id="ebac5-150">在 **“生成”** 菜单上，单击 **“生成解决方案”**。</span><span class="sxs-lookup"><span data-stu-id="ebac5-150">On the **Build** menu, click **Build Solution**.</span></span>  
  
     <span data-ttu-id="ebac5-151">生成应会成功，且没有任何编译器错误或警告。</span><span class="sxs-lookup"><span data-stu-id="ebac5-151">The build should be successful with no compiler errors or warnings.</span></span>  
  
#### <a name="to-create-a-test-project"></a><span data-ttu-id="ebac5-152">创建测试项目</span><span class="sxs-lookup"><span data-stu-id="ebac5-152">To create a test project</span></span>  
  
1.  <span data-ttu-id="ebac5-153">在“文件”菜单上，指向“添加”，然后单击“新建项目”打开“添加新项目”对话框。</span><span class="sxs-lookup"><span data-stu-id="ebac5-153">On the **File** menu, point to **Add** and then click **New Project** to open the **Add New Project** dialog box.</span></span>  
  
2.  <span data-ttu-id="ebac5-154">在“Visual C#”节点下选择“Windows”节点，再单击“Windows 窗体应用程序”。</span><span class="sxs-lookup"><span data-stu-id="ebac5-154">Select the **Windows** node, beneath the **Visual C#** node, and click **Windows Forms Application**.</span></span>  
  
3.  <span data-ttu-id="ebac5-155">在“名称”框中键入 `Test`。</span><span class="sxs-lookup"><span data-stu-id="ebac5-155">In the **Name** box, type `Test`.</span></span>  
  
4.  <span data-ttu-id="ebac5-156">在“解决方案资源管理器”中，右键单击测试项目的“引用”节点，然后从快捷菜单上选择“添加引用”以显示“添加引用”对话框。</span><span class="sxs-lookup"><span data-stu-id="ebac5-156">In **Solution Explorer**, right-click the **References** node for your test project, then select **Add Reference** from the shortcut menu to display the **Add Reference** dialog box.</span></span>  
  
5.  <span data-ttu-id="ebac5-157">单击标记为“项目”的选项卡。</span><span class="sxs-lookup"><span data-stu-id="ebac5-157">Click the tab labeled **Projects**.</span></span> <span data-ttu-id="ebac5-158">“项目名称”下将列出 `ValueButtonLib` 项目。</span><span class="sxs-lookup"><span data-stu-id="ebac5-158">Your `ValueButtonLib` project will be listed under **Project Name**.</span></span> <span data-ttu-id="ebac5-159">双击该项目将引用添加到测试项目。</span><span class="sxs-lookup"><span data-stu-id="ebac5-159">Double-click the project to add the reference to the test project.</span></span>  
  
6.  <span data-ttu-id="ebac5-160">在“解决方案资源管理器”中，右键单击“测试”，然后选择“生成”。</span><span class="sxs-lookup"><span data-stu-id="ebac5-160">In **Solution Explorer,** right-click **Test** and select **Build**.</span></span>  
  
#### <a name="to-add-your-control-to-the-form"></a><span data-ttu-id="ebac5-161">将控件添加到窗体</span><span class="sxs-lookup"><span data-stu-id="ebac5-161">To add your control to the form</span></span>  
  
1.  <span data-ttu-id="ebac5-162">在“解决方案资源管理器”中，右键单击“Form1.cs”，然后从快捷菜单中选择“视图设计器”。</span><span class="sxs-lookup"><span data-stu-id="ebac5-162">In **Solution Explorer**, right-click **Form1.cs** and choose **View Designer** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="ebac5-163">在“工具箱”中单击“ValueButtonLib 组件”。</span><span class="sxs-lookup"><span data-stu-id="ebac5-163">In the **Toolbox**, click **ValueButtonLib Components**.</span></span> <span data-ttu-id="ebac5-164">双击“ValueButton”。</span><span class="sxs-lookup"><span data-stu-id="ebac5-164">Double-click **ValueButton**.</span></span>  
  
     <span data-ttu-id="ebac5-165">窗体上将出现“ValueButton”。</span><span class="sxs-lookup"><span data-stu-id="ebac5-165">A **ValueButton** appears on the form.</span></span>  
  
3.  <span data-ttu-id="ebac5-166">右键单击“ValueButton”，并从快捷菜单中选择“属性”。</span><span class="sxs-lookup"><span data-stu-id="ebac5-166">Right-click the **ValueButton** and select **Properties** from the shortcut menu.</span></span>  
  
4.  <span data-ttu-id="ebac5-167">在“属性”窗口中，检查该控件的属性。</span><span class="sxs-lookup"><span data-stu-id="ebac5-167">In the **Properties** window, examine the properties of this control.</span></span> <span data-ttu-id="ebac5-168">请注意，除增加了一个 `ButtonValue` 属性外，它们与标准按钮公开的属性相同。</span><span class="sxs-lookup"><span data-stu-id="ebac5-168">Note that they are identical to the properties exposed by a standard button, except that there is an additional property, `ButtonValue`.</span></span>  
  
5.  <span data-ttu-id="ebac5-169">将 `ButtonValue` 属性设置为 `5`。</span><span class="sxs-lookup"><span data-stu-id="ebac5-169">Set the `ButtonValue` property to `5`.</span></span>  
  
6.  <span data-ttu-id="ebac5-170">在**所有 Windows 窗体**选项卡**工具箱**，双击**标签**添加<xref:System.Windows.Forms.Label>向窗体控件。</span><span class="sxs-lookup"><span data-stu-id="ebac5-170">In the **All Windows Forms** tab of the **Toolbox**, double-click **Label** to add a <xref:System.Windows.Forms.Label> control to your form.</span></span>  
  
7.  <span data-ttu-id="ebac5-171">将标签重新定位到窗体的中央。</span><span class="sxs-lookup"><span data-stu-id="ebac5-171">Relocate the label to the center of the form.</span></span>  
  
8.  <span data-ttu-id="ebac5-172">双击 `valueButton1`。</span><span class="sxs-lookup"><span data-stu-id="ebac5-172">Double-click `valueButton1`.</span></span>  
  
     <span data-ttu-id="ebac5-173">“代码编辑器”随即打开并显示 `valueButton1_Click` 事件。</span><span class="sxs-lookup"><span data-stu-id="ebac5-173">The **Code Editor** opens to the `valueButton1_Click` event.</span></span>  
  
9. <span data-ttu-id="ebac5-174">插入以下代码行。</span><span class="sxs-lookup"><span data-stu-id="ebac5-174">Insert the following line of code.</span></span>  
  
    ```csharp  
    label1.Text = valueButton1.ButtonValue.ToString();  
    ```  
  
10. <span data-ttu-id="ebac5-175">在“解决方案资源管理器”中，右键单击“测试”，然后从快捷菜单中选择“设为启动项目”。</span><span class="sxs-lookup"><span data-stu-id="ebac5-175">In **Solution Explorer**, right-click **Test**, and choose **Set as Startup Project** from the shortcut menu.</span></span>  
  
11. <span data-ttu-id="ebac5-176">从“调试”菜单中选择“启动调试”。</span><span class="sxs-lookup"><span data-stu-id="ebac5-176">From the **Debug** menu, select **Start Debugging**.</span></span>  
  
     <span data-ttu-id="ebac5-177">`Form1` 将出现。</span><span class="sxs-lookup"><span data-stu-id="ebac5-177">`Form1` appears.</span></span>  
  
12. <span data-ttu-id="ebac5-178">单击 `valueButton1`。</span><span class="sxs-lookup"><span data-stu-id="ebac5-178">Click `valueButton1`.</span></span>  
  
     <span data-ttu-id="ebac5-179">`label1` 中显示数字“5”，表明继承的控件的 `ButtonValue` 属性已通过 `valueButton1_Click` 方法传递给 `label1`。</span><span class="sxs-lookup"><span data-stu-id="ebac5-179">The numeral '5' is displayed in `label1`, demonstrating that the `ButtonValue` property of your inherited control has been passed to `label1` through the `valueButton1_Click` method.</span></span> <span data-ttu-id="ebac5-180">这样，`ValueButton` 控件便继承了标准 Windows 窗体按钮的所有功能，但是公开了一个附加的自定义属性。</span><span class="sxs-lookup"><span data-stu-id="ebac5-180">Thus your `ValueButton` control inherits all the functionality of the standard Windows Forms button, but exposes an additional, custom property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebac5-181">请参阅</span><span class="sxs-lookup"><span data-stu-id="ebac5-181">See also</span></span>
- [<span data-ttu-id="ebac5-182">如何：中显示控件选择工具箱项对话框</span><span class="sxs-lookup"><span data-stu-id="ebac5-182">How to: Display a Control in the Choose Toolbox Items Dialog Box</span></span>](../../../../docs/framework/winforms/controls/how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)
- [<span data-ttu-id="ebac5-183">演练：创作复合控件通过视觉对象C#</span><span class="sxs-lookup"><span data-stu-id="ebac5-183">Walkthrough: Authoring a Composite Control with Visual C#</span></span>](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-csharp.md)
