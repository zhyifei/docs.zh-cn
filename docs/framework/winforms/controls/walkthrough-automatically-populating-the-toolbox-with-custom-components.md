---
title: 演练：使用自定义组件自动填充工具箱
ms.date: 03/30/2017
helpviewer_keywords:
- IToolboxService interface
- Toolbox [Windows Forms], populating
- custom components [Windows Forms], adding to Toolbox
ms.assetid: 2fa1e3e8-6b9f-42b2-97c0-2be57444dba4
ms.openlocfilehash: d446ab84cfe135e56483b8b309b696f7f15044fa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33540041"
---
# <a name="walkthrough-automatically-populating-the-toolbox-with-custom-components"></a><span data-ttu-id="47699-102">演练：使用自定义组件自动填充工具箱</span><span class="sxs-lookup"><span data-stu-id="47699-102">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>
<span data-ttu-id="47699-103">如果你的组件定义的那样当前打开的解决方案中的项目中，它们将会自动出现在**工具箱**，而需要你执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="47699-103">If your components are defined by a project in the currently open solution, they will automatically appear in the **Toolbox**, with no action required by you.</span></span> <span data-ttu-id="47699-104">你可以手动填充**工具箱**与通过使用你自定义组件[选择工具箱项对话框 (Visual Studio)](http://msdn.microsoft.com/library/bd07835f-18a8-433e-bccc-7141f65263bb)，但**工具箱**采用帐户你的解决方案中的项的生成包含所有以下特征的输出结果：</span><span class="sxs-lookup"><span data-stu-id="47699-104">You can also manually populate the **Toolbox** with your custom components by using the [Choose Toolbox Items Dialog Box (Visual Studio)](http://msdn.microsoft.com/library/bd07835f-18a8-433e-bccc-7141f65263bb), but the **Toolbox** takes account of items in your solution's build outputs with all the following characteristics:</span></span>  
  
-   <span data-ttu-id="47699-105">实现<xref:System.ComponentModel.IComponent>;</span><span class="sxs-lookup"><span data-stu-id="47699-105">Implements <xref:System.ComponentModel.IComponent>;</span></span>  
  
-   <span data-ttu-id="47699-106">没有<xref:System.ComponentModel.ToolboxItemAttribute>设置为`false`;</span><span class="sxs-lookup"><span data-stu-id="47699-106">Does not have <xref:System.ComponentModel.ToolboxItemAttribute> set to `false`;</span></span>  
  
-   <span data-ttu-id="47699-107">没有<xref:System.ComponentModel.DesignTimeVisibleAttribute>设置为`false`。</span><span class="sxs-lookup"><span data-stu-id="47699-107">Does not have <xref:System.ComponentModel.DesignTimeVisibleAttribute> set to `false`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="47699-108">**工具箱**不遵循引用链，因此它将不显示并非由你的解决方案中的项目生成的项。</span><span class="sxs-lookup"><span data-stu-id="47699-108">The **Toolbox** does not follow reference chains, so it will not display items that are not built by a project in your solution.</span></span>  
  
 <span data-ttu-id="47699-109">本演练演示如何自定义组件会自动出现在**工具箱**后生成组件。</span><span class="sxs-lookup"><span data-stu-id="47699-109">This walkthrough demonstrates how a custom component automatically appears in the **Toolbox** once the component is built.</span></span> <span data-ttu-id="47699-110">本演练涉及以下任务：</span><span class="sxs-lookup"><span data-stu-id="47699-110">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="47699-111">创建 Windows 窗体项目。</span><span class="sxs-lookup"><span data-stu-id="47699-111">Creating a Windows Forms project.</span></span>  
  
-   <span data-ttu-id="47699-112">创建自定义组件。</span><span class="sxs-lookup"><span data-stu-id="47699-112">Creating a custom component.</span></span>  
  
-   <span data-ttu-id="47699-113">创建自定义组件的实例。</span><span class="sxs-lookup"><span data-stu-id="47699-113">Creating an instance of a custom component.</span></span>  
  
-   <span data-ttu-id="47699-114">卸载并重新加载自定义组件。</span><span class="sxs-lookup"><span data-stu-id="47699-114">Unloading and reloading a custom component.</span></span>  
  
 <span data-ttu-id="47699-115">完成后，你将看到**工具箱**填充了你创建的组件。</span><span class="sxs-lookup"><span data-stu-id="47699-115">When you are finished, you will see that the **Toolbox** is populated with a component that you have created.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="47699-116">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="47699-116">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="47699-117">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="47699-117">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="47699-118">有关详细信息，请参阅[在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。</span><span class="sxs-lookup"><span data-stu-id="47699-118">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="47699-119">创建项目</span><span class="sxs-lookup"><span data-stu-id="47699-119">Creating the Project</span></span>  
 <span data-ttu-id="47699-120">第一步是创建项目并设置窗体。</span><span class="sxs-lookup"><span data-stu-id="47699-120">The first step is to create the project and to set up the form.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="47699-121">要创建项目</span><span class="sxs-lookup"><span data-stu-id="47699-121">To create the project</span></span>  
  
1.  <span data-ttu-id="47699-122">创建一个名为 `ToolboxExample` 的基于 Windows 的应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="47699-122">Create a Windows-based application project called `ToolboxExample`.</span></span>  
  
     <span data-ttu-id="47699-123">有关详细信息，请参阅[如何：创建 Windows 应用程序项目](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)。</span><span class="sxs-lookup"><span data-stu-id="47699-123">For more information, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).</span></span>  
  
2.  <span data-ttu-id="47699-124">向项目添加新的组件。</span><span class="sxs-lookup"><span data-stu-id="47699-124">Add a new component to the project.</span></span> <span data-ttu-id="47699-125">调用它`DemoComponent`。</span><span class="sxs-lookup"><span data-stu-id="47699-125">Call it `DemoComponent`.</span></span>  
  
     <span data-ttu-id="47699-126">有关详细信息，请参阅[NIB： 如何： 添加新项目项](http://msdn.microsoft.com/library/63d3e16b-de6e-4bb5-a0e3-ecec762201ce)。</span><span class="sxs-lookup"><span data-stu-id="47699-126">For more information, see [NIB:How to: Add New Project Items](http://msdn.microsoft.com/library/63d3e16b-de6e-4bb5-a0e3-ecec762201ce).</span></span>  
  
3.  <span data-ttu-id="47699-127">生成项目。</span><span class="sxs-lookup"><span data-stu-id="47699-127">Build the project.</span></span>  
  
4.  <span data-ttu-id="47699-128">从**工具**菜单上，单击**选项**项。</span><span class="sxs-lookup"><span data-stu-id="47699-128">From the **Tools** menu, click the **Options** item.</span></span> <span data-ttu-id="47699-129">单击**常规**下**Windows 窗体设计器**项，然后确保**AutoToolboxPopulate**选项设置为**True**。</span><span class="sxs-lookup"><span data-stu-id="47699-129">Click **General** under the **Windows Forms Designer** item and ensure that the **AutoToolboxPopulate** option is set to **True**.</span></span>  
  
## <a name="creating-an-instance-of-a-custom-component"></a><span data-ttu-id="47699-130">创建自定义组件的实例</span><span class="sxs-lookup"><span data-stu-id="47699-130">Creating an Instance of a Custom Component</span></span>  
 <span data-ttu-id="47699-131">下一步是在窗体上创建自定义组件的实例。</span><span class="sxs-lookup"><span data-stu-id="47699-131">The next step is to create an instance of the custom component on the form.</span></span> <span data-ttu-id="47699-132">因为**工具箱**自动为新的组件的帐户，这是和创建任何其他组件或控件一样简单。</span><span class="sxs-lookup"><span data-stu-id="47699-132">Because the **Toolbox** automatically accounts for the new component, this is as easy as creating any other component or control.</span></span>  
  
#### <a name="to-create-an-instance-of-a-custom-component"></a><span data-ttu-id="47699-133">若要创建自定义组件的实例</span><span class="sxs-lookup"><span data-stu-id="47699-133">To create an instance of a custom component</span></span>  
  
1.  <span data-ttu-id="47699-134">打开项目的窗体中**窗体设计器**。</span><span class="sxs-lookup"><span data-stu-id="47699-134">Open the project's form in the **Forms Designer**.</span></span>  
  
2.  <span data-ttu-id="47699-135">在**工具箱**，单击新选项卡调用**ToolboxExample 组件**。</span><span class="sxs-lookup"><span data-stu-id="47699-135">In the **Toolbox**, click the new tab called **ToolboxExample Components**.</span></span>  
  
     <span data-ttu-id="47699-136">一旦单击选项卡，你将看到**DemoComponent**。</span><span class="sxs-lookup"><span data-stu-id="47699-136">Once you click the tab, you will see **DemoComponent**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="47699-137">出于性能原因，自动填充的区域中的组件**工具箱**不显示自定义位图和<xref:System.Drawing.ToolboxBitmapAttribute>不支持。</span><span class="sxs-lookup"><span data-stu-id="47699-137">For performance reasons, components in the auto-populated area of the **Toolbox** do not display custom bitmaps, and the <xref:System.Drawing.ToolboxBitmapAttribute> is not supported.</span></span> <span data-ttu-id="47699-138">以显示一个图标中的自定义组件**工具箱**，使用**选择工具箱项**对话框中，以加载你的组件。</span><span class="sxs-lookup"><span data-stu-id="47699-138">To display an icon for a custom component in the **Toolbox**, use the **Choose Toolbox Items** dialog box to load your component.</span></span>  
  
3.  <span data-ttu-id="47699-139">你的组件拖到窗体。</span><span class="sxs-lookup"><span data-stu-id="47699-139">Drag your component onto your form.</span></span>  
  
     <span data-ttu-id="47699-140">创建组件的实例并将其添加到**组件栏**。</span><span class="sxs-lookup"><span data-stu-id="47699-140">An instance of the component is created and added to the **Component Tray**.</span></span>  
  
## <a name="unloading-and-reloading-a-custom-component"></a><span data-ttu-id="47699-141">卸载并重新加载自定义组件</span><span class="sxs-lookup"><span data-stu-id="47699-141">Unloading and Reloading a Custom Component</span></span>  
 <span data-ttu-id="47699-142">**工具箱**会考虑在每个组件的加载项目，并卸载项目时，它将移除对该项目的组件的引用。</span><span class="sxs-lookup"><span data-stu-id="47699-142">The **Toolbox** takes account of the components in each loaded project, and when a project is unloaded, it removes references to the project's components.</span></span>  
  
#### <a name="to-experiment-with-the-effect-on-the-toolbox-of-unloading-and-reloading-components"></a><span data-ttu-id="47699-143">尝试卸载并重新加载组件工具箱上的效果</span><span class="sxs-lookup"><span data-stu-id="47699-143">To experiment with the effect on the Toolbox of unloading and reloading components</span></span>  
  
1.  <span data-ttu-id="47699-144">卸载项目从解决方案。</span><span class="sxs-lookup"><span data-stu-id="47699-144">Unload the project from the solution.</span></span>  
  
     <span data-ttu-id="47699-145">有关卸载的项目的详细信息，请参阅[NIB： 如何： 卸载并重新加载项目](http://msdn.microsoft.com/library/abc0155b-8fcb-4ffc-95b6-698518a7100b)。</span><span class="sxs-lookup"><span data-stu-id="47699-145">For more information about unloading projects, see [NIB:How to: Unload and Reload Projects](http://msdn.microsoft.com/library/abc0155b-8fcb-4ffc-95b6-698518a7100b).</span></span> <span data-ttu-id="47699-146">如果系统提示您保存时，选择**是**。</span><span class="sxs-lookup"><span data-stu-id="47699-146">If you are prompted to save, choose **Yes**.</span></span>  
  
2.  <span data-ttu-id="47699-147">添加新**Windows 应用程序**到解决方案的项目。</span><span class="sxs-lookup"><span data-stu-id="47699-147">Add a new **Windows Application** project to the solution.</span></span> <span data-ttu-id="47699-148">打开的窗体中**设计器**。</span><span class="sxs-lookup"><span data-stu-id="47699-148">Open the form in the **Designer**.</span></span>  
  
     <span data-ttu-id="47699-149">**ToolboxExample 组件**以前的项目中的选项卡现消失。</span><span class="sxs-lookup"><span data-stu-id="47699-149">The **ToolboxExample Components** tab from the previous project is now gone.</span></span>  
  
3.  <span data-ttu-id="47699-150">重新加载`ToolboxExample`项目。</span><span class="sxs-lookup"><span data-stu-id="47699-150">Reload the `ToolboxExample` project.</span></span>  
  
     <span data-ttu-id="47699-151">**ToolboxExample 组件**选项卡现在随即再次显示。</span><span class="sxs-lookup"><span data-stu-id="47699-151">The **ToolboxExample Components** tab now reappears.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="47699-152">后续步骤</span><span class="sxs-lookup"><span data-stu-id="47699-152">Next Steps</span></span>  
 <span data-ttu-id="47699-153">本演练演示**工具箱**会考虑项目的组件，但**工具箱**同时也会考虑控件。</span><span class="sxs-lookup"><span data-stu-id="47699-153">This walkthrough demonstrates that the **Toolbox** takes account of a project's components, but the **Toolbox** is also takes account of controls.</span></span> <span data-ttu-id="47699-154">通过添加和删除控件项目，从你的解决方案来测试你自己的自定义控件。</span><span class="sxs-lookup"><span data-stu-id="47699-154">Experiment with your own custom controls by adding and removing control projects from your solution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47699-155">请参阅</span><span class="sxs-lookup"><span data-stu-id="47699-155">See Also</span></span>  
 [<span data-ttu-id="47699-156">通常，Windows 窗体设计器中，选项对话框</span><span class="sxs-lookup"><span data-stu-id="47699-156">General, Windows Forms Designer, Options Dialog Box</span></span>](http://msdn.microsoft.com/library/8dd170af-72f0-4212-b04b-034ceee92834)  
 [<span data-ttu-id="47699-157">如何：操作工具箱选项卡</span><span class="sxs-lookup"><span data-stu-id="47699-157">How to: Manipulate Toolbox Tabs</span></span>](http://msdn.microsoft.com/library/21285050-cadd-455a-b1f5-a2289a89c4db)  
 [<span data-ttu-id="47699-158">“选择工具箱项”对话框 (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="47699-158">Choose Toolbox Items Dialog Box (Visual Studio)</span></span>](http://msdn.microsoft.com/library/bd07835f-18a8-433e-bccc-7141f65263bb)  
 [<span data-ttu-id="47699-159">将控件置于 Windows 窗体上</span><span class="sxs-lookup"><span data-stu-id="47699-159">Putting Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/putting-controls-on-windows-forms.md)
