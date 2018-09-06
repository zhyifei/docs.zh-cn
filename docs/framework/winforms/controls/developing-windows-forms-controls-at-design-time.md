---
title: 设计时开发 Windows 窗体控件
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls [Windows Forms]
- Windows Forms controls, creating
- controls [Windows Forms]
- controls [Windows Forms], creating
- user controls [Windows Forms]
- custom controls [Windows Forms]
ms.assetid: e5a8e088-7ec8-4fd9-bcb3-9078fd134829
ms.openlocfilehash: b58318a3e0e9881725d3c260251288c720fa4132
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2018
ms.locfileid: "43745106"
---
# <a name="developing-windows-forms-controls-at-design-time"></a><span data-ttu-id="82d84-102">设计时开发 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="82d84-102">Developing Windows Forms Controls at Design Time</span></span>
<span data-ttu-id="82d84-103">.NET Framework 为控件创作者提供了丰富的控件创作技术。</span><span class="sxs-lookup"><span data-stu-id="82d84-103">For control authors, the .NET Framework provides a wealth of control authoring technology.</span></span> <span data-ttu-id="82d84-104">作者不再局限于设计作为现有控件集合的复合控件。</span><span class="sxs-lookup"><span data-stu-id="82d84-104">Authors are no longer limited to designing composite controls that act as a collection of preexisting controls.</span></span> <span data-ttu-id="82d84-105">通过继承，可根据现有复合控件或现有 Windows 窗体控件创建自己的控件。</span><span class="sxs-lookup"><span data-stu-id="82d84-105">Through inheritance, you can create your own controls from preexisting composite controls or preexisting Windows Forms controls.</span></span> <span data-ttu-id="82d84-106">还可以自己设计实现自定义绘制的控件。</span><span class="sxs-lookup"><span data-stu-id="82d84-106">You can also design your own controls that implement custom painting.</span></span> <span data-ttu-id="82d84-107">这些选项对可视化界面的设计和功能赋予了很大的灵活性。</span><span class="sxs-lookup"><span data-stu-id="82d84-107">These options enable a great deal of flexibility to the design and functionality of the visual interface.</span></span> <span data-ttu-id="82d84-108">若要利用这些功能，应熟悉基于对象的编程概念。</span><span class="sxs-lookup"><span data-stu-id="82d84-108">To take advantage of these features, you should be familiar with object-based programming concepts.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="82d84-109">不需要具有全面了解继承，但你可能会发现可以指代[继承的基础知识 (Visual Basic)](~/docs/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)。</span><span class="sxs-lookup"><span data-stu-id="82d84-109">It is not necessary to have a thorough understanding of inheritance, but you may find it useful to refer to [Inheritance basics (Visual Basic)](~/docs/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span></span>  
  
 <span data-ttu-id="82d84-110">如果要创建在 Web 窗体上使用的自定义控件，请参阅[开发自定义 ASP.NET 服务器控件](https://msdn.microsoft.com/library/fbe26c16-cff4-4089-b3dd-877411f0c0ef).。</span><span class="sxs-lookup"><span data-stu-id="82d84-110">If you want to create custom controls to use on Web Forms, see [Developing Custom ASP.NET Server Controls](https://msdn.microsoft.com/library/fbe26c16-cff4-4089-b3dd-877411f0c0ef).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="82d84-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="82d84-111">In This Section</span></span>  
 [<span data-ttu-id="82d84-112">演练：使用 Visual Basic 创作复合控件</span><span class="sxs-lookup"><span data-stu-id="82d84-112">Walkthrough: Authoring a Composite Control with Visual Basic</span></span>](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-basic.md)  
 <span data-ttu-id="82d84-113">演示如何在 VisualBasic 中创建简单的复合控件。</span><span class="sxs-lookup"><span data-stu-id="82d84-113">Shows how to create a simple composite control in Visual Basic.</span></span>  
  
 [<span data-ttu-id="82d84-114">演练：使用 Visual C# 创作复合控件</span><span class="sxs-lookup"><span data-stu-id="82d84-114">Walkthrough: Authoring a Composite Control with Visual C#</span></span>](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-csharp.md)  
 <span data-ttu-id="82d84-115">演示如何在 C# 中创建简单的复合控件。</span><span class="sxs-lookup"><span data-stu-id="82d84-115">Shows how to create a simple composite control in C#.</span></span>  
  
 [<span data-ttu-id="82d84-116">演练：使用 Visual Basic 从 Windows 窗体控件继承</span><span class="sxs-lookup"><span data-stu-id="82d84-116">Walkthrough: Inheriting from a Windows Forms Control with Visual Basic</span></span>](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic.md)  
 <span data-ttu-id="82d84-117">演示如何在 VisualBasic 中使用继承创建简单的 Windows 窗体控件。</span><span class="sxs-lookup"><span data-stu-id="82d84-117">Shows how to create a simple Windows Forms control using inheritance in Visual Basic.</span></span>  
  
 [<span data-ttu-id="82d84-118">演练：使用 Visual C# 从 Windows 窗体控件继承</span><span class="sxs-lookup"><span data-stu-id="82d84-118">Walkthrough: Inheriting from a Windows Forms Control with Visual C#</span></span>](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)  
 <span data-ttu-id="82d84-119">演示如何在 C# 中使用继承创建简单的 Windows 窗体控件。</span><span class="sxs-lookup"><span data-stu-id="82d84-119">Shows how to create a simple Windows Forms control using inheritance in C#.</span></span>  
  
 [<span data-ttu-id="82d84-120">演练：使用 Windows 窗体控件上的智能标记执行常规任务</span><span class="sxs-lookup"><span data-stu-id="82d84-120">Walkthrough: Performing Common Tasks Using Smart Tags on Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/performing-common-tasks-using-smart-tags-on-wf-controls.md)  
 <span data-ttu-id="82d84-121">演示如何在 Windows 窗体控件上使用智能标记功能。</span><span class="sxs-lookup"><span data-stu-id="82d84-121">Shows how to use the smart tag feature on Windows Forms controls.</span></span>  
  
 [<span data-ttu-id="82d84-122">演练：使用 DesignerSerializationVisibilityAttribute 序列化标准类型的集合</span><span class="sxs-lookup"><span data-stu-id="82d84-122">Walkthrough: Serializing Collections of Standard Types with the DesignerSerializationVisibilityAttribute</span></span>](../../../../docs/framework/winforms/controls/serializing-collections-designerserializationvisibilityattribute.md)  
 <span data-ttu-id="82d84-123">演示如何使用<xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content?displayProperty=nameWithType>属性序列化集合。</span><span class="sxs-lookup"><span data-stu-id="82d84-123">Shows how to use the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content?displayProperty=nameWithType> attribute to serialize a collection.</span></span>  
  
 [<span data-ttu-id="82d84-124">演练：设计时调试自定义 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="82d84-124">Walkthrough: Debugging Custom Windows Forms Controls at Design Time</span></span>](../../../../docs/framework/winforms/controls/walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)  
 <span data-ttu-id="82d84-125">演示如何调试 Windows 窗体控件的设计时行为。</span><span class="sxs-lookup"><span data-stu-id="82d84-125">Shows how to debug the design-time behavior of a Windows Forms control.</span></span>  
  
 [<span data-ttu-id="82d84-126">演练：创建利用 Visual Studio 设计时功能的 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="82d84-126">Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features</span></span>](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md)  
 <span data-ttu-id="82d84-127">演示如何将复合控件紧密集成到设计环境中。</span><span class="sxs-lookup"><span data-stu-id="82d84-127">Shows how to tightly integrate a composite control into the design environment.</span></span>  
  
 [<span data-ttu-id="82d84-128">如何：创作 Windows 窗体的控件</span><span class="sxs-lookup"><span data-stu-id="82d84-128">How to: Author Controls for Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-author-controls-for-windows-forms.md)  
 <span data-ttu-id="82d84-129">概述实现 Windows 窗体控件的注意事项。</span><span class="sxs-lookup"><span data-stu-id="82d84-129">Provides an overview of considerations for implementing a Windows Forms control.</span></span>  
  
 [<span data-ttu-id="82d84-130">如何：创作复合控件</span><span class="sxs-lookup"><span data-stu-id="82d84-130">How to: Author Composite Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-author-composite-controls.md)  
 <span data-ttu-id="82d84-131">演示如何通过继承复合控件来创建控件。</span><span class="sxs-lookup"><span data-stu-id="82d84-131">Shows how to create a control by inheriting from a composite control.</span></span>  
  
 [<span data-ttu-id="82d84-132">如何：从 UserControl 类继承</span><span class="sxs-lookup"><span data-stu-id="82d84-132">How to: Inherit from the UserControl Class</span></span>](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-usercontrol-class.md)  
 <span data-ttu-id="82d84-133">概述复合控件的创建过程。</span><span class="sxs-lookup"><span data-stu-id="82d84-133">Provides an overview of the procedure for creating a composite control.</span></span>  
  
 [<span data-ttu-id="82d84-134">如何：从现有 Windows 窗体控件继承</span><span class="sxs-lookup"><span data-stu-id="82d84-134">How to: Inherit from Existing Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-inherit-from-existing-windows-forms-controls.md)  
 <span data-ttu-id="82d84-135">演示如何创建通过继承扩展的控件<xref:System.Windows.Forms.Button>控件类。</span><span class="sxs-lookup"><span data-stu-id="82d84-135">Shows how to create an extended control by inheriting from the <xref:System.Windows.Forms.Button> control class.</span></span>  
  
 [<span data-ttu-id="82d84-136">如何：从 Control 类继承</span><span class="sxs-lookup"><span data-stu-id="82d84-136">How to: Inherit from the Control Class</span></span>](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-control-class.md)  
 <span data-ttu-id="82d84-137">概述如何创建扩展的控件。</span><span class="sxs-lookup"><span data-stu-id="82d84-137">Provides an overview of creating an extended control.</span></span>  
  
 [<span data-ttu-id="82d84-138">如何：设计时将控件与窗体边缘对齐</span><span class="sxs-lookup"><span data-stu-id="82d84-138">How to: Align a Control to the Edges of Forms at Design Time</span></span>](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)  
 <span data-ttu-id="82d84-139">演示如何使用<xref:System.Windows.Forms.Control.Dock%2A>属性以将控件与它所占据窗体的边缘对齐。</span><span class="sxs-lookup"><span data-stu-id="82d84-139">Shows how to use the <xref:System.Windows.Forms.Control.Dock%2A> property to align your control to the edge of the form it occupies.</span></span>  
  
 [<span data-ttu-id="82d84-140">如何：在“选择工具箱项”对话框中显示控件</span><span class="sxs-lookup"><span data-stu-id="82d84-140">How to: Display a Control in the Choose Toolbox Items Dialog Box</span></span>](../../../../docs/framework/winforms/controls/how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)  
 <span data-ttu-id="82d84-141">演示安装控件以将其显示在“自定义工具箱”对话框中的过程。</span><span class="sxs-lookup"><span data-stu-id="82d84-141">Shows the procedure for installing your control so that it appears in the **Customize Toolbox** dialog box.</span></span>  
  
 [<span data-ttu-id="82d84-142">如何：为控件提供工具箱位图</span><span class="sxs-lookup"><span data-stu-id="82d84-142">How to: Provide a Toolbox Bitmap for a Control</span></span>](../../../../docs/framework/winforms/controls/how-to-provide-a-toolbox-bitmap-for-a-control.md)  
 <span data-ttu-id="82d84-143">演示如何使用<xref:System.Drawing.ToolboxBitmapAttribute>若要在自定义控件旁边显示一个图标**工具箱**。</span><span class="sxs-lookup"><span data-stu-id="82d84-143">Shows how to use the <xref:System.Drawing.ToolboxBitmapAttribute> to display an icon next to your custom control in the **Toolbox**.</span></span>  
  
 [<span data-ttu-id="82d84-144">如何：测试 UserControl 的运行时行为</span><span class="sxs-lookup"><span data-stu-id="82d84-144">How to: Test the Run-Time Behavior of a UserControl</span></span>](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md)  
 <span data-ttu-id="82d84-145">演示如何使用 **UserControl 测试容器**来测试组合控件的行为。</span><span class="sxs-lookup"><span data-stu-id="82d84-145">Shows how to use the **UserControl Test Container** to test the behavior of a composite control.</span></span>  
  
 [<span data-ttu-id="82d84-146">Windows 窗体设计器中的设计时错误</span><span class="sxs-lookup"><span data-stu-id="82d84-146">Design-Time Errors in the Windows Forms Designer</span></span>](../../../../docs/framework/winforms/controls/design-time-errors-in-the-windows-forms-designer.md)  
 <span data-ttu-id="82d84-147">说明 Windows 窗体设计器加载失败时出现在 Microsoft Visual Studio 中的设计时错误列表的含义和用法。</span><span class="sxs-lookup"><span data-stu-id="82d84-147">Explains the meaning and use of the Design-Time Error List that appears in Microsoft Visual Studio when the Windows Forms designer fails to load.</span></span>  
  
 [<span data-ttu-id="82d84-148">控件和组件创作疑难解答</span><span class="sxs-lookup"><span data-stu-id="82d84-148">Troubleshooting Control and Component Authoring</span></span>](../../../../docs/framework/winforms/controls/troubleshooting-control-and-component-authoring.md)  
 <span data-ttu-id="82d84-149">演示如何诊断和解决创作自定义组件或控件时可能出现的常见问题。</span><span class="sxs-lookup"><span data-stu-id="82d84-149">Shows how to diagnose and fix common issues that can occur when you author a custom component or control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="82d84-150">参考</span><span class="sxs-lookup"><span data-stu-id="82d84-150">Reference</span></span>  
 <xref:System.Windows.Forms.Control?displayProperty=nameWithType>  
 <span data-ttu-id="82d84-151">对此类进行描述，并提供指向其所有成员的链接。</span><span class="sxs-lookup"><span data-stu-id="82d84-151">Describes this class and has links to all of its members.</span></span>  
  
 <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>  
 <span data-ttu-id="82d84-152">对此类进行描述，并提供指向其所有成员的链接。</span><span class="sxs-lookup"><span data-stu-id="82d84-152">Describes this class and has links to all of its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="82d84-153">相关章节</span><span class="sxs-lookup"><span data-stu-id="82d84-153">Related Sections</span></span>  
 [<span data-ttu-id="82d84-154">使用 .NET Framework 开发自定义 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="82d84-154">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)  
 <span data-ttu-id="82d84-155">讨论如何通过 .NET Framework 创建自己的自定义控件。</span><span class="sxs-lookup"><span data-stu-id="82d84-155">Discusses how to create your own custom controls with the .NET Framework.</span></span>  
  
 [<span data-ttu-id="82d84-156">语言独立性和与语言无关的组件</span><span class="sxs-lookup"><span data-stu-id="82d84-156">Language Independence and Language-Independent Components</span></span>](../../../../docs/standard/language-independence-and-language-independent-components.md)  
 <span data-ttu-id="82d84-157">介绍公共语言运行时，它旨在简化组件的创建和使用。</span><span class="sxs-lookup"><span data-stu-id="82d84-157">Introduces the common language runtime, which is designed to simplify the creation and use of components.</span></span> <span data-ttu-id="82d84-158">这种简化的一个重要方面是提高了采用不同编程语言编写的组件间的互操作性。</span><span class="sxs-lookup"><span data-stu-id="82d84-158">An important aspect of this simplification is enhanced interoperability between components written using different programming languages.</span></span> <span data-ttu-id="82d84-159">通过公共语言规范 (CLS) 可创建使用多个编程语言的工具和组件。</span><span class="sxs-lookup"><span data-stu-id="82d84-159">The Common Language Specification (CLS) makes it possible to create tools and components that work with multiple programming languages.</span></span>  
  
 [<span data-ttu-id="82d84-160">演练：使用自定义组件自动填充工具箱</span><span class="sxs-lookup"><span data-stu-id="82d84-160">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)  
 <span data-ttu-id="82d84-161">描述如何在“自定义工具箱”对话框中显示组件或控件。</span><span class="sxs-lookup"><span data-stu-id="82d84-161">Describes how to enable your component or control to be displayed in the **Customize Toolbox** dialog box.</span></span>
