---
title: 演练：使用自定义组件自动填充工具箱
ms.date: 03/30/2017
helpviewer_keywords:
- IToolboxService interface
- Toolbox [Windows Forms], populating
- custom components [Windows Forms], adding to Toolbox
ms.assetid: 2fa1e3e8-6b9f-42b2-97c0-2be57444dba4
ms.openlocfilehash: 6ecf69350b8337dc6049b73251809192b47dc2fb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61759903"
---
# <a name="walkthrough-automatically-populating-the-toolbox-with-custom-components"></a><span data-ttu-id="30681-102">演练：使用自定义组件自动填充工具箱</span><span class="sxs-lookup"><span data-stu-id="30681-102">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>
<span data-ttu-id="30681-103">如果由当前打开的解决方案中的项目定义您的组件，它们将自动显示在**工具箱**，由你需执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="30681-103">If your components are defined by a project in the currently open solution, they will automatically appear in the **Toolbox**, with no action required by you.</span></span> <span data-ttu-id="30681-104">可以手动填充**工具箱**与使用自定义组件[选择工具箱项对话框 (Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dyca0t6t(v=vs.100))，但**工具箱**考虑在解决方案中的项的生成包含所有以下特征的输出结果：</span><span class="sxs-lookup"><span data-stu-id="30681-104">You can also manually populate the **Toolbox** with your custom components by using the [Choose Toolbox Items Dialog Box (Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dyca0t6t(v=vs.100)), but the **Toolbox** takes account of items in your solution's build outputs with all the following characteristics:</span></span>  
  
- <span data-ttu-id="30681-105">实现<xref:System.ComponentModel.IComponent>;</span><span class="sxs-lookup"><span data-stu-id="30681-105">Implements <xref:System.ComponentModel.IComponent>;</span></span>  
  
- <span data-ttu-id="30681-106">不具有<xref:System.ComponentModel.ToolboxItemAttribute>设置为`false`;</span><span class="sxs-lookup"><span data-stu-id="30681-106">Does not have <xref:System.ComponentModel.ToolboxItemAttribute> set to `false`;</span></span>  
  
- <span data-ttu-id="30681-107">不具有<xref:System.ComponentModel.DesignTimeVisibleAttribute>设置为`false`。</span><span class="sxs-lookup"><span data-stu-id="30681-107">Does not have <xref:System.ComponentModel.DesignTimeVisibleAttribute> set to `false`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="30681-108">**工具箱**不遵循引用链，因此它将不显示并非由你的解决方案中的项目生成的项。</span><span class="sxs-lookup"><span data-stu-id="30681-108">The **Toolbox** does not follow reference chains, so it will not display items that are not built by a project in your solution.</span></span>  
  
 <span data-ttu-id="30681-109">本演练演示如何自定义组件自动出现在**工具箱**生成组件后。</span><span class="sxs-lookup"><span data-stu-id="30681-109">This walkthrough demonstrates how a custom component automatically appears in the **Toolbox** once the component is built.</span></span> <span data-ttu-id="30681-110">本演练涉及以下任务：</span><span class="sxs-lookup"><span data-stu-id="30681-110">Tasks illustrated in this walkthrough include:</span></span>  
  
- <span data-ttu-id="30681-111">创建一个 Windows 窗体项目。</span><span class="sxs-lookup"><span data-stu-id="30681-111">Creating a Windows Forms project.</span></span>  
  
- <span data-ttu-id="30681-112">创建自定义组件。</span><span class="sxs-lookup"><span data-stu-id="30681-112">Creating a custom component.</span></span>  
  
- <span data-ttu-id="30681-113">创建自定义组件的实例。</span><span class="sxs-lookup"><span data-stu-id="30681-113">Creating an instance of a custom component.</span></span>  
  
- <span data-ttu-id="30681-114">卸载并重新加载自定义组件。</span><span class="sxs-lookup"><span data-stu-id="30681-114">Unloading and reloading a custom component.</span></span>  
  
 <span data-ttu-id="30681-115">完成后，你将看到**工具箱**填充了已创建的组件。</span><span class="sxs-lookup"><span data-stu-id="30681-115">When you are finished, you will see that the **Toolbox** is populated with a component that you have created.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="30681-116">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="30681-116">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="30681-117">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="30681-117">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="30681-118">有关详细信息，请参阅[个性化设置 Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)。</span><span class="sxs-lookup"><span data-stu-id="30681-118">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="30681-119">创建项目</span><span class="sxs-lookup"><span data-stu-id="30681-119">Creating the Project</span></span>  
 <span data-ttu-id="30681-120">第一步是创建项目并设置窗体。</span><span class="sxs-lookup"><span data-stu-id="30681-120">The first step is to create the project and to set up the form.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="30681-121">要创建项目</span><span class="sxs-lookup"><span data-stu-id="30681-121">To create the project</span></span>  
  
1. <span data-ttu-id="30681-122">创建一个名为基于 Windows 的应用程序项目`ToolboxExample`(**文件** > **新建** > **项目** >  **Visual C#** 或**Visual Basic** > **经典桌面** > **Windows 窗体应用程序**)。</span><span class="sxs-lookup"><span data-stu-id="30681-122">Create a Windows-based application project called `ToolboxExample` (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>  
  
2. <span data-ttu-id="30681-123">向项目添加新组件。</span><span class="sxs-lookup"><span data-stu-id="30681-123">Add a new component to the project.</span></span> <span data-ttu-id="30681-124">将其命名为 `DemoComponent`。</span><span class="sxs-lookup"><span data-stu-id="30681-124">Call it `DemoComponent`.</span></span>  
  
     <span data-ttu-id="30681-125">有关详细信息，请参阅[如何：添加新项目项](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w0572c5b(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="30681-125">For more information, see [How to: Add New Project Items](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w0572c5b(v=vs.100)).</span></span>  
  
3. <span data-ttu-id="30681-126">生成项目。</span><span class="sxs-lookup"><span data-stu-id="30681-126">Build the project.</span></span>  
  
4. <span data-ttu-id="30681-127">从**工具**菜单上，单击**选项**项。</span><span class="sxs-lookup"><span data-stu-id="30681-127">From the **Tools** menu, click the **Options** item.</span></span> <span data-ttu-id="30681-128">单击**常规**下**Windows 窗体设计器**项，然后确保**AutoToolboxPopulate**选项设置为**True**。</span><span class="sxs-lookup"><span data-stu-id="30681-128">Click **General** under the **Windows Forms Designer** item and ensure that the **AutoToolboxPopulate** option is set to **True**.</span></span>  
  
## <a name="creating-an-instance-of-a-custom-component"></a><span data-ttu-id="30681-129">创建自定义组件的实例</span><span class="sxs-lookup"><span data-stu-id="30681-129">Creating an Instance of a Custom Component</span></span>  
 <span data-ttu-id="30681-130">下一步是在窗体上创建自定义组件的实例。</span><span class="sxs-lookup"><span data-stu-id="30681-130">The next step is to create an instance of the custom component on the form.</span></span> <span data-ttu-id="30681-131">因为**工具箱**自动为新的组件的帐户，这非常简单，只创建任何其他组件或控件。</span><span class="sxs-lookup"><span data-stu-id="30681-131">Because the **Toolbox** automatically accounts for the new component, this is as easy as creating any other component or control.</span></span>  
  
#### <a name="to-create-an-instance-of-a-custom-component"></a><span data-ttu-id="30681-132">若要创建自定义组件的实例</span><span class="sxs-lookup"><span data-stu-id="30681-132">To create an instance of a custom component</span></span>  
  
1. <span data-ttu-id="30681-133">打开中的项目的窗体**窗体设计器**。</span><span class="sxs-lookup"><span data-stu-id="30681-133">Open the project's form in the **Forms Designer**.</span></span>  
  
2. <span data-ttu-id="30681-134">在中**工具箱**，单击名为的新选项卡**ToolboxExample 组件**。</span><span class="sxs-lookup"><span data-stu-id="30681-134">In the **Toolbox**, click the new tab called **ToolboxExample Components**.</span></span>  
  
     <span data-ttu-id="30681-135">单击选项卡，会看到**DemoComponent**。</span><span class="sxs-lookup"><span data-stu-id="30681-135">Once you click the tab, you will see **DemoComponent**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="30681-136">出于性能原因中的自动填充区域的组件**工具箱**不显示自定义位图和<xref:System.Drawing.ToolboxBitmapAttribute>不受支持。</span><span class="sxs-lookup"><span data-stu-id="30681-136">For performance reasons, components in the auto-populated area of the **Toolbox** do not display custom bitmaps, and the <xref:System.Drawing.ToolboxBitmapAttribute> is not supported.</span></span> <span data-ttu-id="30681-137">若要显示的图标中的自定义组件**工具箱**，使用**选择工具箱项**对话框以加载该组件。</span><span class="sxs-lookup"><span data-stu-id="30681-137">To display an icon for a custom component in the **Toolbox**, use the **Choose Toolbox Items** dialog box to load your component.</span></span>  
  
3. <span data-ttu-id="30681-138">将组件拖到窗体上。</span><span class="sxs-lookup"><span data-stu-id="30681-138">Drag your component onto your form.</span></span>  
  
     <span data-ttu-id="30681-139">创建并添加到组件的实例**组件栏**。</span><span class="sxs-lookup"><span data-stu-id="30681-139">An instance of the component is created and added to the **Component Tray**.</span></span>  
  
## <a name="unloading-and-reloading-a-custom-component"></a><span data-ttu-id="30681-140">卸载并重新加载自定义组件</span><span class="sxs-lookup"><span data-stu-id="30681-140">Unloading and Reloading a Custom Component</span></span>  
 <span data-ttu-id="30681-141">**工具箱**项目，会考虑在每个组件的加载和卸载一个项目时，它会删除对项目的组件的引用。</span><span class="sxs-lookup"><span data-stu-id="30681-141">The **Toolbox** takes account of the components in each loaded project, and when a project is unloaded, it removes references to the project's components.</span></span>  
  
#### <a name="to-experiment-with-the-effect-on-the-toolbox-of-unloading-and-reloading-components"></a><span data-ttu-id="30681-142">尝试卸载和重新加载组件的工具箱上的效果</span><span class="sxs-lookup"><span data-stu-id="30681-142">To experiment with the effect on the Toolbox of unloading and reloading components</span></span>  
  
1. <span data-ttu-id="30681-143">卸载该解决方案中的项目。</span><span class="sxs-lookup"><span data-stu-id="30681-143">Unload the project from the solution.</span></span>  
  
     <span data-ttu-id="30681-144">有关卸载的项目的详细信息，请参阅[如何：卸载并重新加载项目](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/tt479x1t(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="30681-144">For more information about unloading projects, see [How to: Unload and Reload Projects](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/tt479x1t(v=vs.100)).</span></span> <span data-ttu-id="30681-145">如果系统提示您保存时，选择**是**。</span><span class="sxs-lookup"><span data-stu-id="30681-145">If you are prompted to save, choose **Yes**.</span></span>  
  
2. <span data-ttu-id="30681-146">添加一个新**Windows 应用程序**到解决方案。</span><span class="sxs-lookup"><span data-stu-id="30681-146">Add a new **Windows Application** project to the solution.</span></span> <span data-ttu-id="30681-147">打开中的窗体**设计器**。</span><span class="sxs-lookup"><span data-stu-id="30681-147">Open the form in the **Designer**.</span></span>  
  
     <span data-ttu-id="30681-148">**ToolboxExample 组件**选项卡上一个项目现已消失了。</span><span class="sxs-lookup"><span data-stu-id="30681-148">The **ToolboxExample Components** tab from the previous project is now gone.</span></span>  
  
3. <span data-ttu-id="30681-149">重新加载`ToolboxExample`项目。</span><span class="sxs-lookup"><span data-stu-id="30681-149">Reload the `ToolboxExample` project.</span></span>  
  
     <span data-ttu-id="30681-150">**ToolboxExample 组件**选项卡现在再次出现。</span><span class="sxs-lookup"><span data-stu-id="30681-150">The **ToolboxExample Components** tab now reappears.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="30681-151">后续步骤</span><span class="sxs-lookup"><span data-stu-id="30681-151">Next Steps</span></span>  
 <span data-ttu-id="30681-152">本演练演示**工具箱**会考虑项目的组件，但**工具箱**同时也会考虑的控件。</span><span class="sxs-lookup"><span data-stu-id="30681-152">This walkthrough demonstrates that the **Toolbox** takes account of a project's components, but the **Toolbox** is also takes account of controls.</span></span> <span data-ttu-id="30681-153">通过添加和删除控件项目从解决方案来测试您自己的自定义控件。</span><span class="sxs-lookup"><span data-stu-id="30681-153">Experiment with your own custom controls by adding and removing control projects from your solution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30681-154">请参阅</span><span class="sxs-lookup"><span data-stu-id="30681-154">See also</span></span>

- <span data-ttu-id="30681-155">[通常，Windows 窗体设计器选项对话框](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/5aazxs78(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="30681-155">[General, Windows Forms Designer, Options Dialog Box](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/5aazxs78(v=vs.100))</span></span>
- <span data-ttu-id="30681-156">[如何：操作工具箱选项卡](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/66kwe227(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="30681-156">[How to: Manipulate Toolbox Tabs](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/66kwe227(v=vs.100))</span></span>
- <span data-ttu-id="30681-157">[“选择工具箱项”对话框 (Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dyca0t6t(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="30681-157">[Choose Toolbox Items Dialog Box (Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dyca0t6t(v=vs.100))</span></span>
- [<span data-ttu-id="30681-158">将控件置于 Windows 窗体上</span><span class="sxs-lookup"><span data-stu-id="30681-158">Putting Controls on Windows Forms</span></span>](putting-controls-on-windows-forms.md)
