---
title: "如何：创作复合控件"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- UserControl class [Windows Forms], creating composite controls
- user controls [Windows Forms], creating
- user controls [Windows Forms], inheriting from
- composite controls [Windows Forms], creating
ms.assetid: 79c9cf05-5ab6-4a18-886d-88a64748b098
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5cf68d4927daa79e160df42f94aff9cbcb611592
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-author-composite-controls"></a><span data-ttu-id="f1e7f-102">如何：创作复合控件</span><span class="sxs-lookup"><span data-stu-id="f1e7f-102">How to: Author Composite Controls</span></span>
<span data-ttu-id="f1e7f-103">可通过多种方式使用复合控件。</span><span class="sxs-lookup"><span data-stu-id="f1e7f-103">Composite controls can be employed in many ways.</span></span> <span data-ttu-id="f1e7f-104">可将其作为 Windows 桌面应用程序项目的一部分创作，并只在该项目的窗体上使用它们。</span><span class="sxs-lookup"><span data-stu-id="f1e7f-104">You can author them as part of a Windows desktop application project, and use them only on forms in the project.</span></span> <span data-ttu-id="f1e7f-105">或者，可在 Windows 控件库项目中创作它们，将该项目编译为程序集，在其他项目中使用这些控件。</span><span class="sxs-lookup"><span data-stu-id="f1e7f-105">Or you can author them in a Windows Control Library project, compile the project into an assembly, and use the controls in other projects.</span></span> <span data-ttu-id="f1e7f-106">甚至可以从它们继承，并针对特殊目的使用视觉对象继承快速对它们进行自定义。</span><span class="sxs-lookup"><span data-stu-id="f1e7f-106">You can even inherit from them, and use visual inheritance to customize them quickly for special purposes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f1e7f-107">如果想要编写在 Web 窗体上使用的复合控件，请参阅[开发自定义 ASP.NET 服务器控件](http://msdn.microsoft.com/library/fbe26c16-cff4-4089-b3dd-877411f0c0ef)。</span><span class="sxs-lookup"><span data-stu-id="f1e7f-107">If you want to author a composite control to use on Web Forms, see [Developing Custom ASP.NET Server Controls](http://msdn.microsoft.com/library/fbe26c16-cff4-4089-b3dd-877411f0c0ef).</span></span>  
>   
>  <span data-ttu-id="f1e7f-108">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="f1e7f-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="f1e7f-109">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="f1e7f-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="f1e7f-110">有关详细信息，请参阅 [在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。</span><span class="sxs-lookup"><span data-stu-id="f1e7f-110">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-author-a-composite-control"></a><span data-ttu-id="f1e7f-111">创作复合控件</span><span class="sxs-lookup"><span data-stu-id="f1e7f-111">To author a composite control</span></span>  
  
1.  <span data-ttu-id="f1e7f-112">打开一个名为 `DemoControlHost` 的新 **Windows 应用程序**项目。</span><span class="sxs-lookup"><span data-stu-id="f1e7f-112">Open a new **Windows Application** project called `DemoControlHost`.</span></span>  
  
2.  <span data-ttu-id="f1e7f-113">在“项目”菜单上，单击“添加用户控件”。</span><span class="sxs-lookup"><span data-stu-id="f1e7f-113">On the **Project**menu, click **Add User Control**.</span></span>  
  
3.  <span data-ttu-id="f1e7f-114">在“添加新项”对话框中，为类文件（.vb 或 .cs 文件）提供希望复合控件具有的名称。</span><span class="sxs-lookup"><span data-stu-id="f1e7f-114">In the **Add New Item** dialog box, give the class file (.vb or .cs file) the name you want the composite control to have.</span></span>  
  
4.  <span data-ttu-id="f1e7f-115">单击“添加”按钮为复合控件创建类文件。</span><span class="sxs-lookup"><span data-stu-id="f1e7f-115">Click the **Add** button to create the class file for the composite control.</span></span>  
  
5.  <span data-ttu-id="f1e7f-116">将控件从“工具箱”添加到复合控件表面。</span><span class="sxs-lookup"><span data-stu-id="f1e7f-116">Add controls from the **Toolbox** to the composite control surface.</span></span>  
  
6.  <span data-ttu-id="f1e7f-117">将代码置于事件过程中，处理由复合控件或其构成控件所引发的事件。</span><span class="sxs-lookup"><span data-stu-id="f1e7f-117">Place code in event procedures, to handle events raised by the composite control or by its constituent controls.</span></span>  
  
7.  <span data-ttu-id="f1e7f-118">关闭复合控件的设计器，并在出现提示时保存文件。</span><span class="sxs-lookup"><span data-stu-id="f1e7f-118">Close the designer for the composite control, and save the file when you are prompted.</span></span>  
  
8.  <span data-ttu-id="f1e7f-119">在 **“生成”** 菜单上，单击 **“生成解决方案”**。</span><span class="sxs-lookup"><span data-stu-id="f1e7f-119">On the **Build** menu, click **Build Solution**.</span></span>  
  
     <span data-ttu-id="f1e7f-120">必须生成项目，自定义控件才可在“工具箱”中显示。</span><span class="sxs-lookup"><span data-stu-id="f1e7f-120">The project must be built in order for custom controls to appear in the **Toolbox**.</span></span>  
  
9. <span data-ttu-id="f1e7f-121">使用“工具箱”的“DemoControlHost”选项卡将控件的实例添加到 `Form1`。</span><span class="sxs-lookup"><span data-stu-id="f1e7f-121">Use the **DemoControlHost** tab of the **Toolbox** to add instances of your control to `Form1`.</span></span>  
  
### <a name="to-author-a-control-class-library"></a><span data-ttu-id="f1e7f-122">创作控件类库</span><span class="sxs-lookup"><span data-stu-id="f1e7f-122">To author a control class library</span></span>  
  
1.  <span data-ttu-id="f1e7f-123">打开新的“Windows 控件库”项目。</span><span class="sxs-lookup"><span data-stu-id="f1e7f-123">Open a new **Windows Control Library** project.</span></span>  
  
     <span data-ttu-id="f1e7f-124">默认情况下，项目包含一个复合控件。</span><span class="sxs-lookup"><span data-stu-id="f1e7f-124">By default, the project contains a composite control.</span></span>  
  
2.  <span data-ttu-id="f1e7f-125">按照上述步骤中的说明添加控件和代码。</span><span class="sxs-lookup"><span data-stu-id="f1e7f-125">Add controls and code as described in the procedure above.</span></span>  
  
3.  <span data-ttu-id="f1e7f-126">选择不想继承类更改的控件，并将此控件的“Modifiers”属性设置为“专用”。</span><span class="sxs-lookup"><span data-stu-id="f1e7f-126">Choose a control you do not want inheriting classes to change, and set the **Modifiers** property of this control to **Private**.</span></span>  
  
4.  <span data-ttu-id="f1e7f-127">生成 DLL。</span><span class="sxs-lookup"><span data-stu-id="f1e7f-127">Build the DLL.</span></span>  
  
### <a name="to-inherit-from-a-composite-control-in-a-control-class-library"></a><span data-ttu-id="f1e7f-128">从控件类库中的复合控件中继承</span><span class="sxs-lookup"><span data-stu-id="f1e7f-128">To inherit from a composite control in a control class library</span></span>  
  
1.  <span data-ttu-id="f1e7f-129">在“文件”菜单上，指向“添加”并选择“新建项目”，将新的“Windows 应用程序”项目添加到解决方案中。</span><span class="sxs-lookup"><span data-stu-id="f1e7f-129">On the **File** menu, point to **Add** and select **New Project** to add a new **Windows Application** project to the solution.</span></span>  
  
2.  <span data-ttu-id="f1e7f-130">在“解决方案资源管理器”中，右键单击新项目的“引用”文件夹，并选择“添加引用”以打开“添加引用”对话框。</span><span class="sxs-lookup"><span data-stu-id="f1e7f-130">In **Solution Explorer**, right-click the **References** folder for the new project and choose **Add Reference** to open the **Add Reference** dialog box.</span></span>  
  
3.  <span data-ttu-id="f1e7f-131">选择“项目”选项卡，然后双击控件库项目。</span><span class="sxs-lookup"><span data-stu-id="f1e7f-131">Select the **Projects** tab and double-click your control library project.</span></span>  
  
4.  <span data-ttu-id="f1e7f-132">在 **“生成”** 菜单上，单击 **“生成解决方案”**。</span><span class="sxs-lookup"><span data-stu-id="f1e7f-132">On the **Build** menu, click **Build Solution**.</span></span>  
  
5.  <span data-ttu-id="f1e7f-133">在“解决方案资源管理器”中，右键单击控件库项目并从快捷菜单中选择“添加新项”。</span><span class="sxs-lookup"><span data-stu-id="f1e7f-133">In **Solution Explorer**, right-click your control library project and select **Add New Item** from the shortcut menu.</span></span>  
  
6.  <span data-ttu-id="f1e7f-134">从“添加新项目”对话框中选择“继承的用户控件”模板。</span><span class="sxs-lookup"><span data-stu-id="f1e7f-134">Select the **Inherited User Control** template from the **Add New Item** dialog box.</span></span>  
  
7.  <span data-ttu-id="f1e7f-135">在“继承选择器”对话框中，双击要继承的控件。</span><span class="sxs-lookup"><span data-stu-id="f1e7f-135">In the **Inheritance Picker** dialog box, double-click the control you want to inherit from.</span></span>  
  
     <span data-ttu-id="f1e7f-136">已将新控件添加到你的项目。</span><span class="sxs-lookup"><span data-stu-id="f1e7f-136">A new control is added to your project.</span></span>  
  
8.  <span data-ttu-id="f1e7f-137">打开新控件的可视化设计器，并添加其他构成控件。</span><span class="sxs-lookup"><span data-stu-id="f1e7f-137">Open the visual designer for the new control and add additional constituent controls.</span></span>  
  
     <span data-ttu-id="f1e7f-138">可看到从 DLL 中的复合控件继承的构成控件，还可以更改“Modifiers”属性为“Public”的控件的属性。</span><span class="sxs-lookup"><span data-stu-id="f1e7f-138">You can see the constituent controls that were inherited from the composite control in your DLL, and you can alter the properties of controls whose **Modifiers** property is **Public**.</span></span> <span data-ttu-id="f1e7f-139">但不能更改“Modifiers”属性为“Private”的控件的属性。</span><span class="sxs-lookup"><span data-stu-id="f1e7f-139">You cannot change the properties of the control whose **Modifiers** property is **Private**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1e7f-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="f1e7f-140">See Also</span></span>  
 [<span data-ttu-id="f1e7f-141">演练：使用 Visual Basic 创作复合控件</span><span class="sxs-lookup"><span data-stu-id="f1e7f-141">Walkthrough: Authoring a Composite Control with Visual Basic</span></span>](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-basic.md)  
 [<span data-ttu-id="f1e7f-142">演练：使用 Visual C# 创作复合控件</span><span class="sxs-lookup"><span data-stu-id="f1e7f-142">Walkthrough: Authoring a Composite Control with Visual C#</span></span>](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-csharp.md)  
 [<span data-ttu-id="f1e7f-143">演练：使用 Visual Basic 从 Windows 窗体控件继承</span><span class="sxs-lookup"><span data-stu-id="f1e7f-143">Walkthrough: Inheriting from a Windows Forms Control with Visual Basic</span></span>](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic.md)  
 [<span data-ttu-id="f1e7f-144">演练：使用 Visual C# 从 Windows 窗体控件继承</span><span class="sxs-lookup"><span data-stu-id="f1e7f-144">Walkthrough: Inheriting from a Windows Forms Control with Visual C#</span></span>](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)  
 [<span data-ttu-id="f1e7f-145">控件类型建议</span><span class="sxs-lookup"><span data-stu-id="f1e7f-145">Control Type Recommendations</span></span>](../../../../docs/framework/winforms/controls/control-type-recommendations.md)  
 [<span data-ttu-id="f1e7f-146">如何：创作 Windows 窗体的控件</span><span class="sxs-lookup"><span data-stu-id="f1e7f-146">How to: Author Controls for Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-author-controls-for-windows-forms.md)  
 [<span data-ttu-id="f1e7f-147">各种自定义控件</span><span class="sxs-lookup"><span data-stu-id="f1e7f-147">Varieties of Custom Controls</span></span>](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)
