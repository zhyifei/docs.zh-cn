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
ms.openlocfilehash: 641a6c1c99169c6836c33b3e84b2ae02aba298d2
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57707711"
---
# <a name="developing-windows-forms-controls-at-design-time"></a><span data-ttu-id="58b0c-102">设计时开发 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="58b0c-102">Developing Windows Forms Controls at Design Time</span></span>
<span data-ttu-id="58b0c-103">.NET Framework 为控件创作者提供了丰富的控件创作技术。</span><span class="sxs-lookup"><span data-stu-id="58b0c-103">For control authors, the .NET Framework provides a wealth of control authoring technology.</span></span> <span data-ttu-id="58b0c-104">作者不再局限于设计作为现有控件集合的复合控件。</span><span class="sxs-lookup"><span data-stu-id="58b0c-104">Authors are no longer limited to designing composite controls that act as a collection of preexisting controls.</span></span> <span data-ttu-id="58b0c-105">通过继承，可根据现有复合控件或现有 Windows 窗体控件创建自己的控件。</span><span class="sxs-lookup"><span data-stu-id="58b0c-105">Through inheritance, you can create your own controls from preexisting composite controls or preexisting Windows Forms controls.</span></span> <span data-ttu-id="58b0c-106">还可以自己设计实现自定义绘制的控件。</span><span class="sxs-lookup"><span data-stu-id="58b0c-106">You can also design your own controls that implement custom painting.</span></span> <span data-ttu-id="58b0c-107">这些选项对可视化界面的设计和功能赋予了很大的灵活性。</span><span class="sxs-lookup"><span data-stu-id="58b0c-107">These options enable a great deal of flexibility to the design and functionality of the visual interface.</span></span> <span data-ttu-id="58b0c-108">若要利用这些功能，应熟悉基于对象的编程概念。</span><span class="sxs-lookup"><span data-stu-id="58b0c-108">To take advantage of these features, you should be familiar with object-based programming concepts.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="58b0c-109">不需要具有全面了解继承，但你可能会发现可以指代[继承的基础知识 (Visual Basic)](~/docs/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)。</span><span class="sxs-lookup"><span data-stu-id="58b0c-109">It is not necessary to have a thorough understanding of inheritance, but you may find it useful to refer to [Inheritance basics (Visual Basic)](~/docs/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span></span>  
  
 <span data-ttu-id="58b0c-110">如果要创建在 Web 窗体上使用的自定义控件，请参阅[开发自定义 ASP.NET 服务器控件](https://docs.microsoft.com/previous-versions/aspnet/zt27tfhy(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="58b0c-110">If you want to create custom controls to use on Web Forms, see [Developing Custom ASP.NET Server Controls](https://docs.microsoft.com/previous-versions/aspnet/zt27tfhy(v=vs.100)).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="58b0c-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="58b0c-111">In This Section</span></span>  
 [<span data-ttu-id="58b0c-112">演练：创作复合控件使用 Visual Basic</span><span class="sxs-lookup"><span data-stu-id="58b0c-112">Walkthrough: Authoring a Composite Control with Visual Basic</span></span>](walkthrough-authoring-a-composite-control-with-visual-basic.md)  
 <span data-ttu-id="58b0c-113">演示如何在 VisualBasic 中创建简单的复合控件。</span><span class="sxs-lookup"><span data-stu-id="58b0c-113">Shows how to create a simple composite control in Visual Basic.</span></span>  
  
 [<span data-ttu-id="58b0c-114">演练：创作复合控件通过视觉对象C#</span><span class="sxs-lookup"><span data-stu-id="58b0c-114">Walkthrough: Authoring a Composite Control with Visual C#</span></span>](walkthrough-authoring-a-composite-control-with-visual-csharp.md)  
 <span data-ttu-id="58b0c-115">演示如何在 C# 中创建简单的复合控件。</span><span class="sxs-lookup"><span data-stu-id="58b0c-115">Shows how to create a simple composite control in C#.</span></span>  
  
 [<span data-ttu-id="58b0c-116">演练：从使用 Visual Basic 的 Windows 窗体控件继承</span><span class="sxs-lookup"><span data-stu-id="58b0c-116">Walkthrough: Inheriting from a Windows Forms Control with Visual Basic</span></span>](walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic.md)  
 <span data-ttu-id="58b0c-117">演示如何在 VisualBasic 中使用继承创建简单的 Windows 窗体控件。</span><span class="sxs-lookup"><span data-stu-id="58b0c-117">Shows how to create a simple Windows Forms control using inheritance in Visual Basic.</span></span>  
  
 [<span data-ttu-id="58b0c-118">演练：从视觉对象的 Windows 窗体控件继承C#</span><span class="sxs-lookup"><span data-stu-id="58b0c-118">Walkthrough: Inheriting from a Windows Forms Control with Visual C#</span></span>](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)  
 <span data-ttu-id="58b0c-119">演示如何在 C# 中使用继承创建简单的 Windows 窗体控件。</span><span class="sxs-lookup"><span data-stu-id="58b0c-119">Shows how to create a simple Windows Forms control using inheritance in C#.</span></span>  
  
 [<span data-ttu-id="58b0c-120">演练：执行常见任务使用智能标记在 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="58b0c-120">Walkthrough: Performing Common Tasks Using Smart Tags on Windows Forms Controls</span></span>](performing-common-tasks-using-smart-tags-on-wf-controls.md)  
 <span data-ttu-id="58b0c-121">演示如何在 Windows 窗体控件上使用智能标记功能。</span><span class="sxs-lookup"><span data-stu-id="58b0c-121">Shows how to use the smart tag feature on Windows Forms controls.</span></span>  
  
 [<span data-ttu-id="58b0c-122">演练：序列化标准类型使用 DesignerSerializationVisibilityAttribute 集合</span><span class="sxs-lookup"><span data-stu-id="58b0c-122">Walkthrough: Serializing Collections of Standard Types with the DesignerSerializationVisibilityAttribute</span></span>](serializing-collections-designerserializationvisibilityattribute.md)  
 <span data-ttu-id="58b0c-123">演示如何使用<xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content?displayProperty=nameWithType>属性序列化集合。</span><span class="sxs-lookup"><span data-stu-id="58b0c-123">Shows how to use the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content?displayProperty=nameWithType> attribute to serialize a collection.</span></span>  
  
 [<span data-ttu-id="58b0c-124">演练：在设计时调试自定义 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="58b0c-124">Walkthrough: Debugging Custom Windows Forms Controls at Design Time</span></span>](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)  
 <span data-ttu-id="58b0c-125">演示如何调试 Windows 窗体控件的设计时行为。</span><span class="sxs-lookup"><span data-stu-id="58b0c-125">Shows how to debug the design-time behavior of a Windows Forms control.</span></span>  
  
 [<span data-ttu-id="58b0c-126">演练：创建利用 Visual Studio 设计时功能的 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="58b0c-126">Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features</span></span>](creating-a-wf-control-design-time-features.md)  
 <span data-ttu-id="58b0c-127">演示如何将复合控件紧密集成到设计环境中。</span><span class="sxs-lookup"><span data-stu-id="58b0c-127">Shows how to tightly integrate a composite control into the design environment.</span></span>  
  
 [<span data-ttu-id="58b0c-128">如何：Windows 窗体的作者控件</span><span class="sxs-lookup"><span data-stu-id="58b0c-128">How to: Author Controls for Windows Forms</span></span>](how-to-author-controls-for-windows-forms.md)  
 <span data-ttu-id="58b0c-129">概述实现 Windows 窗体控件的注意事项。</span><span class="sxs-lookup"><span data-stu-id="58b0c-129">Provides an overview of considerations for implementing a Windows Forms control.</span></span>  
  
 [<span data-ttu-id="58b0c-130">如何：创作复合控件</span><span class="sxs-lookup"><span data-stu-id="58b0c-130">How to: Author Composite Controls</span></span>](how-to-author-composite-controls.md)  
 <span data-ttu-id="58b0c-131">演示如何通过继承复合控件来创建控件。</span><span class="sxs-lookup"><span data-stu-id="58b0c-131">Shows how to create a control by inheriting from a composite control.</span></span>  
  
 [<span data-ttu-id="58b0c-132">如何：从 UserControl 类继承</span><span class="sxs-lookup"><span data-stu-id="58b0c-132">How to: Inherit from the UserControl Class</span></span>](how-to-inherit-from-the-usercontrol-class.md)  
 <span data-ttu-id="58b0c-133">概述复合控件的创建过程。</span><span class="sxs-lookup"><span data-stu-id="58b0c-133">Provides an overview of the procedure for creating a composite control.</span></span>  
  
 [<span data-ttu-id="58b0c-134">如何：从现有 Windows 窗体控件继承</span><span class="sxs-lookup"><span data-stu-id="58b0c-134">How to: Inherit from Existing Windows Forms Controls</span></span>](how-to-inherit-from-existing-windows-forms-controls.md)  
 <span data-ttu-id="58b0c-135">演示如何创建通过继承扩展的控件<xref:System.Windows.Forms.Button>控件类。</span><span class="sxs-lookup"><span data-stu-id="58b0c-135">Shows how to create an extended control by inheriting from the <xref:System.Windows.Forms.Button> control class.</span></span>  
  
 [<span data-ttu-id="58b0c-136">如何：从 Control 类继承</span><span class="sxs-lookup"><span data-stu-id="58b0c-136">How to: Inherit from the Control Class</span></span>](how-to-inherit-from-the-control-class.md)  
 <span data-ttu-id="58b0c-137">概述如何创建扩展的控件。</span><span class="sxs-lookup"><span data-stu-id="58b0c-137">Provides an overview of creating an extended control.</span></span>  
  
 [<span data-ttu-id="58b0c-138">如何：将控件与窗体边缘对齐在设计时</span><span class="sxs-lookup"><span data-stu-id="58b0c-138">How to: Align a Control to the Edges of Forms at Design Time</span></span>](how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)  
 <span data-ttu-id="58b0c-139">演示如何使用<xref:System.Windows.Forms.Control.Dock%2A>属性以将控件与它所占据窗体的边缘对齐。</span><span class="sxs-lookup"><span data-stu-id="58b0c-139">Shows how to use the <xref:System.Windows.Forms.Control.Dock%2A> property to align your control to the edge of the form it occupies.</span></span>  
  
 [<span data-ttu-id="58b0c-140">如何：中显示控件选择工具箱项对话框</span><span class="sxs-lookup"><span data-stu-id="58b0c-140">How to: Display a Control in the Choose Toolbox Items Dialog Box</span></span>](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)  
 <span data-ttu-id="58b0c-141">演示安装控件以将其显示在“自定义工具箱”对话框中的过程。</span><span class="sxs-lookup"><span data-stu-id="58b0c-141">Shows the procedure for installing your control so that it appears in the **Customize Toolbox** dialog box.</span></span>  
  
 [<span data-ttu-id="58b0c-142">如何：为控件提供工具箱位图</span><span class="sxs-lookup"><span data-stu-id="58b0c-142">How to: Provide a Toolbox Bitmap for a Control</span></span>](how-to-provide-a-toolbox-bitmap-for-a-control.md)  
 <span data-ttu-id="58b0c-143">演示如何使用<xref:System.Drawing.ToolboxBitmapAttribute>若要在自定义控件旁边显示一个图标**工具箱**。</span><span class="sxs-lookup"><span data-stu-id="58b0c-143">Shows how to use the <xref:System.Drawing.ToolboxBitmapAttribute> to display an icon next to your custom control in the **Toolbox**.</span></span>  
  
 [<span data-ttu-id="58b0c-144">如何：测试 UserControl 的运行时行为</span><span class="sxs-lookup"><span data-stu-id="58b0c-144">How to: Test the Run-Time Behavior of a UserControl</span></span>](how-to-test-the-run-time-behavior-of-a-usercontrol.md)  
 <span data-ttu-id="58b0c-145">演示如何使用 **UserControl 测试容器**来测试组合控件的行为。</span><span class="sxs-lookup"><span data-stu-id="58b0c-145">Shows how to use the **UserControl Test Container** to test the behavior of a composite control.</span></span>  
  
 [<span data-ttu-id="58b0c-146">Windows 窗体设计器中的设计时错误</span><span class="sxs-lookup"><span data-stu-id="58b0c-146">Design-Time Errors in the Windows Forms Designer</span></span>](design-time-errors-in-the-windows-forms-designer.md)  
 <span data-ttu-id="58b0c-147">说明 Windows 窗体设计器加载失败时出现在 Microsoft Visual Studio 中的设计时错误列表的含义和用法。</span><span class="sxs-lookup"><span data-stu-id="58b0c-147">Explains the meaning and use of the Design-Time Error List that appears in Microsoft Visual Studio when the Windows Forms designer fails to load.</span></span>  
  
 [<span data-ttu-id="58b0c-148">控件和组件创作疑难解答</span><span class="sxs-lookup"><span data-stu-id="58b0c-148">Troubleshooting Control and Component Authoring</span></span>](troubleshooting-control-and-component-authoring.md)  
 <span data-ttu-id="58b0c-149">演示如何诊断和解决创作自定义组件或控件时可能出现的常见问题。</span><span class="sxs-lookup"><span data-stu-id="58b0c-149">Shows how to diagnose and fix common issues that can occur when you author a custom component or control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="58b0c-150">参考</span><span class="sxs-lookup"><span data-stu-id="58b0c-150">Reference</span></span>  
 <xref:System.Windows.Forms.Control?displayProperty=nameWithType>  
 <span data-ttu-id="58b0c-151">对此类进行描述，并提供指向其所有成员的链接。</span><span class="sxs-lookup"><span data-stu-id="58b0c-151">Describes this class and has links to all of its members.</span></span>  
  
 <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>  
 <span data-ttu-id="58b0c-152">对此类进行描述，并提供指向其所有成员的链接。</span><span class="sxs-lookup"><span data-stu-id="58b0c-152">Describes this class and has links to all of its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="58b0c-153">相关章节</span><span class="sxs-lookup"><span data-stu-id="58b0c-153">Related Sections</span></span>  
 [<span data-ttu-id="58b0c-154">使用 .NET Framework 开发自定义 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="58b0c-154">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](developing-custom-windows-forms-controls.md)  
 <span data-ttu-id="58b0c-155">讨论如何通过 .NET Framework 创建自己的自定义控件。</span><span class="sxs-lookup"><span data-stu-id="58b0c-155">Discusses how to create your own custom controls with the .NET Framework.</span></span>  
  
 [<span data-ttu-id="58b0c-156">语言独立性和与语言无关的组件</span><span class="sxs-lookup"><span data-stu-id="58b0c-156">Language Independence and Language-Independent Components</span></span>](../../../standard/language-independence-and-language-independent-components.md)  
 <span data-ttu-id="58b0c-157">介绍公共语言运行时，它旨在简化组件的创建和使用。</span><span class="sxs-lookup"><span data-stu-id="58b0c-157">Introduces the common language runtime, which is designed to simplify the creation and use of components.</span></span> <span data-ttu-id="58b0c-158">这种简化的一个重要方面是提高了采用不同编程语言编写的组件间的互操作性。</span><span class="sxs-lookup"><span data-stu-id="58b0c-158">An important aspect of this simplification is enhanced interoperability between components written using different programming languages.</span></span> <span data-ttu-id="58b0c-159">通过公共语言规范 (CLS) 可创建使用多个编程语言的工具和组件。</span><span class="sxs-lookup"><span data-stu-id="58b0c-159">The Common Language Specification (CLS) makes it possible to create tools and components that work with multiple programming languages.</span></span>  
  
 [<span data-ttu-id="58b0c-160">演练：自动填充工具箱与自定义组件</span><span class="sxs-lookup"><span data-stu-id="58b0c-160">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)  
 <span data-ttu-id="58b0c-161">描述如何在“自定义工具箱”对话框中显示组件或控件。</span><span class="sxs-lookup"><span data-stu-id="58b0c-161">Describes how to enable your component or control to be displayed in the **Customize Toolbox** dialog box.</span></span>
