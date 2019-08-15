---
title: 如何：创作复合控件
ms.date: 03/30/2017
helpviewer_keywords:
- UserControl class [Windows Forms], creating composite controls
- user controls [Windows Forms], creating
- user controls [Windows Forms], inheriting from
- composite controls [Windows Forms], creating
ms.assetid: 79c9cf05-5ab6-4a18-886d-88a64748b098
ms.openlocfilehash: 7b0ee8efa62175e2ced2a810ca6dd76e8adc103b
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039886"
---
# <a name="how-to-author-composite-controls"></a><span data-ttu-id="fa202-102">如何：创作复合控件</span><span class="sxs-lookup"><span data-stu-id="fa202-102">How to: Author Composite Controls</span></span>

<span data-ttu-id="fa202-103">可通过多种方式使用复合控件。</span><span class="sxs-lookup"><span data-stu-id="fa202-103">Composite controls can be employed in many ways.</span></span> <span data-ttu-id="fa202-104">可将其作为 Windows 桌面应用程序项目的一部分创作，并只在该项目的窗体上使用它们。</span><span class="sxs-lookup"><span data-stu-id="fa202-104">You can author them as part of a Windows desktop application project, and use them only on forms in the project.</span></span> <span data-ttu-id="fa202-105">或者，可在 Windows 控件库项目中创作它们，将该项目编译为程序集，在其他项目中使用这些控件。</span><span class="sxs-lookup"><span data-stu-id="fa202-105">Or you can author them in a Windows Control Library project, compile the project into an assembly, and use the controls in other projects.</span></span> <span data-ttu-id="fa202-106">甚至可以从它们继承, 并使用可视继承快速自定义它们以用于特殊用途。</span><span class="sxs-lookup"><span data-stu-id="fa202-106">You can even inherit from them and use visual inheritance to customize them quickly for special purposes.</span></span>

> [!NOTE]
> <span data-ttu-id="fa202-107">如果想要编写在 Web 窗体上使用的复合控件，请参阅[开发自定义 ASP.NET 服务器控件](https://docs.microsoft.com/previous-versions/aspnet/zt27tfhy(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="fa202-107">If you want to author a composite control to use on Web Forms, see [Developing Custom ASP.NET Server Controls](https://docs.microsoft.com/previous-versions/aspnet/zt27tfhy(v=vs.100)).</span></span>

## <a name="to-author-a-composite-control"></a><span data-ttu-id="fa202-108">创作复合控件</span><span class="sxs-lookup"><span data-stu-id="fa202-108">To author a composite control</span></span>

1. <span data-ttu-id="fa202-109">在 Visual Studio 中, 创建一个名`DemoControlHost`为的新**Windows 应用程序**项目。</span><span class="sxs-lookup"><span data-stu-id="fa202-109">In Visual Studio, create a new **Windows Application** project called `DemoControlHost`.</span></span>

2. <span data-ttu-id="fa202-110">在 **“项目”** 菜单上，单击 **“添加用户控件”** 。</span><span class="sxs-lookup"><span data-stu-id="fa202-110">On the **Project** menu, click **Add User Control**.</span></span>

3. <span data-ttu-id="fa202-111">在“添加新项”对话框中，为类文件（.vb 或 .cs 文件）提供希望复合控件具有的名称。</span><span class="sxs-lookup"><span data-stu-id="fa202-111">In the **Add New Item** dialog box, give the class file (.vb or .cs file) the name you want the composite control to have.</span></span>

4. <span data-ttu-id="fa202-112">选择 "**添加**" 按钮, 为复合控件创建类文件。</span><span class="sxs-lookup"><span data-stu-id="fa202-112">Select the **Add** button to create the class file for the composite control.</span></span>

5. <span data-ttu-id="fa202-113">将控件从“工具箱”添加到复合控件表面。</span><span class="sxs-lookup"><span data-stu-id="fa202-113">Add controls from the **Toolbox** to the composite control surface.</span></span>

6. <span data-ttu-id="fa202-114">将代码置于事件过程中，处理由复合控件或其构成控件所引发的事件。</span><span class="sxs-lookup"><span data-stu-id="fa202-114">Place code in event procedures, to handle events raised by the composite control or by its constituent controls.</span></span>

7. <span data-ttu-id="fa202-115">关闭复合控件的设计器，并在出现提示时保存文件。</span><span class="sxs-lookup"><span data-stu-id="fa202-115">Close the designer for the composite control, and save the file when you are prompted.</span></span>

8. <span data-ttu-id="fa202-116">在 **“生成”** 菜单上，单击 **“生成解决方案”** 。</span><span class="sxs-lookup"><span data-stu-id="fa202-116">On the **Build** menu, click **Build Solution**.</span></span>

     <span data-ttu-id="fa202-117">必须生成项目，自定义控件才可在“工具箱”中显示。</span><span class="sxs-lookup"><span data-stu-id="fa202-117">The project must be built in order for custom controls to appear in the **Toolbox**.</span></span>

9. <span data-ttu-id="fa202-118">使用“工具箱”的“DemoControlHost”选项卡将控件的实例添加到 `Form1`。</span><span class="sxs-lookup"><span data-stu-id="fa202-118">Use the **DemoControlHost** tab of the **Toolbox** to add instances of your control to `Form1`.</span></span>

## <a name="to-author-a-control-class-library"></a><span data-ttu-id="fa202-119">创作控件类库</span><span class="sxs-lookup"><span data-stu-id="fa202-119">To author a control class library</span></span>

1. <span data-ttu-id="fa202-120">打开新的“Windows 控件库”项目。</span><span class="sxs-lookup"><span data-stu-id="fa202-120">Open a new **Windows Control Library** project.</span></span>

     <span data-ttu-id="fa202-121">默认情况下，项目包含一个复合控件。</span><span class="sxs-lookup"><span data-stu-id="fa202-121">By default, the project contains a composite control.</span></span>

2. <span data-ttu-id="fa202-122">按照上述步骤中的说明添加控件和代码。</span><span class="sxs-lookup"><span data-stu-id="fa202-122">Add controls and code as described in the procedure above.</span></span>

3. <span data-ttu-id="fa202-123">选择不想继承类更改的控件，并将此控件的“Modifiers”属性设置为“专用”。</span><span class="sxs-lookup"><span data-stu-id="fa202-123">Choose a control you do not want inheriting classes to change, and set the **Modifiers** property of this control to **Private**.</span></span>

4. <span data-ttu-id="fa202-124">生成 DLL。</span><span class="sxs-lookup"><span data-stu-id="fa202-124">Build the DLL.</span></span>

## <a name="to-inherit-from-a-composite-control-in-a-control-class-library"></a><span data-ttu-id="fa202-125">从控件类库中的复合控件中继承</span><span class="sxs-lookup"><span data-stu-id="fa202-125">To inherit from a composite control in a control class library</span></span>

1. <span data-ttu-id="fa202-126">在“文件”菜单上，指向“添加”并选择“新建项目”，将新的“Windows 应用程序”项目添加到解决方案中。</span><span class="sxs-lookup"><span data-stu-id="fa202-126">On the **File** menu, point to **Add** and select **New Project** to add a new **Windows Application** project to the solution.</span></span>

2. <span data-ttu-id="fa202-127">在“解决方案资源管理器”中，右键单击新项目的“引用”文件夹，并选择“添加引用”以打开“添加引用”对话框。</span><span class="sxs-lookup"><span data-stu-id="fa202-127">In **Solution Explorer**, right-click the **References** folder for the new project and choose **Add Reference** to open the **Add Reference** dialog box.</span></span>

3. <span data-ttu-id="fa202-128">选择“项目”选项卡，然后双击控件库项目。</span><span class="sxs-lookup"><span data-stu-id="fa202-128">Select the **Projects** tab and double-click your control library project.</span></span>

4. <span data-ttu-id="fa202-129">在 **“生成”** 菜单上，单击 **“生成解决方案”** 。</span><span class="sxs-lookup"><span data-stu-id="fa202-129">On the **Build** menu, click **Build Solution**.</span></span>

5. <span data-ttu-id="fa202-130">在“解决方案资源管理器”中，右键单击控件库项目并从快捷菜单中选择“添加新项”。</span><span class="sxs-lookup"><span data-stu-id="fa202-130">In **Solution Explorer**, right-click your control library project and select **Add New Item** from the shortcut menu.</span></span>

6. <span data-ttu-id="fa202-131">从“添加新项目”对话框中选择“继承的用户控件”模板。</span><span class="sxs-lookup"><span data-stu-id="fa202-131">Select the **Inherited User Control** template from the **Add New Item** dialog box.</span></span>

7. <span data-ttu-id="fa202-132">在“继承选择器”对话框中，双击要继承的控件。</span><span class="sxs-lookup"><span data-stu-id="fa202-132">In the **Inheritance Picker** dialog box, double-click the control you want to inherit from.</span></span>

     <span data-ttu-id="fa202-133">已将新控件添加到你的项目。</span><span class="sxs-lookup"><span data-stu-id="fa202-133">A new control is added to your project.</span></span>

8. <span data-ttu-id="fa202-134">打开新控件的可视化设计器，并添加其他构成控件。</span><span class="sxs-lookup"><span data-stu-id="fa202-134">Open the visual designer for the new control and add additional constituent controls.</span></span>

     <span data-ttu-id="fa202-135">可看到从 DLL 中的复合控件继承的构成控件，还可以更改“Modifiers”属性为“Public”的控件的属性。</span><span class="sxs-lookup"><span data-stu-id="fa202-135">You can see the constituent controls that were inherited from the composite control in your DLL, and you can alter the properties of controls whose **Modifiers** property is **Public**.</span></span> <span data-ttu-id="fa202-136">但不能更改“Modifiers”属性为“Private”的控件的属性。</span><span class="sxs-lookup"><span data-stu-id="fa202-136">You cannot change the properties of the control whose **Modifiers** property is **Private**.</span></span>

## <a name="see-also"></a><span data-ttu-id="fa202-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="fa202-137">See also</span></span>

- [<span data-ttu-id="fa202-138">演练：使用 Visual Basic 创作复合控件</span><span class="sxs-lookup"><span data-stu-id="fa202-138">Walkthrough: Authoring a Composite Control with Visual Basic</span></span>](walkthrough-authoring-a-composite-control-with-visual-basic.md)
- [<span data-ttu-id="fa202-139">演练：使用视觉对象创作复合控件C#</span><span class="sxs-lookup"><span data-stu-id="fa202-139">Walkthrough: Authoring a Composite Control with Visual C#</span></span>](walkthrough-authoring-a-composite-control-with-visual-csharp.md)
- [<span data-ttu-id="fa202-140">演练：使用 Visual Basic 从 Windows 窗体控件继承</span><span class="sxs-lookup"><span data-stu-id="fa202-140">Walkthrough: Inheriting from a Windows Forms Control with Visual Basic</span></span>](walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic.md)
- [<span data-ttu-id="fa202-141">演练：使用 Visual 从 Windows 窗体控件继承C#</span><span class="sxs-lookup"><span data-stu-id="fa202-141">Walkthrough: Inheriting from a Windows Forms Control with Visual C#</span></span>](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)
- [<span data-ttu-id="fa202-142">控件类型建议</span><span class="sxs-lookup"><span data-stu-id="fa202-142">Control Type Recommendations</span></span>](control-type-recommendations.md)
- [<span data-ttu-id="fa202-143">如何：Windows 窗体的创作控件</span><span class="sxs-lookup"><span data-stu-id="fa202-143">How to: Author Controls for Windows Forms</span></span>](how-to-author-controls-for-windows-forms.md)
- [<span data-ttu-id="fa202-144">各种自定义控件</span><span class="sxs-lookup"><span data-stu-id="fa202-144">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
