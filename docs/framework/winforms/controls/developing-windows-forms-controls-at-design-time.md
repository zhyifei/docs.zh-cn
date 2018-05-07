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
ms.openlocfilehash: 267a56cbfd9025e2e20f1468535e5544146535a9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="developing-windows-forms-controls-at-design-time"></a>设计时开发 Windows 窗体控件
.NET Framework 为控件创作者提供了丰富的控件创作技术。 作者不再局限于设计作为现有控件集合的复合控件。 通过继承，可根据现有复合控件或现有 Windows 窗体控件创建自己的控件。 还可以自己设计实现自定义绘制的控件。 这些选项对可视化界面的设计和功能赋予了很大的灵活性。 若要利用这些功能，应熟悉基于对象的编程概念。  
  
> [!NOTE]
>  不需要透彻理解的继承，但您可能发现有用来指代[继承的基础知识 (Visual Basic 中)](~/docs/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)。  
  
 如果要创建在 Web 窗体上使用的自定义控件，请参阅[开发自定义 ASP.NET 服务器控件](http://msdn.microsoft.com/library/fbe26c16-cff4-4089-b3dd-877411f0c0ef).。  
  
## <a name="in-this-section"></a>本节内容  
 [演练：使用 Visual Basic 创作复合控件](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-basic.md)  
 演示如何在 VisualBasic 中创建简单的复合控件。  
  
 [演练：使用 Visual C# 创作复合控件](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-csharp.md)  
 演示如何在 C# 中创建简单的复合控件。  
  
 [演练：使用 Visual Basic 从 Windows 窗体控件继承](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic.md)  
 演示如何在 VisualBasic 中使用继承创建简单的 Windows 窗体控件。  
  
 [演练：使用 Visual C# 从 Windows 窗体控件继承](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)  
 演示如何在 C# 中使用继承创建简单的 Windows 窗体控件。  
  
 [演练：使用 Windows 窗体控件上的智能标记执行常规任务](../../../../docs/framework/winforms/controls/performing-common-tasks-using-smart-tags-on-wf-controls.md)  
 演示如何在 Windows 窗体控件上使用智能标记功能。  
  
 [演练：使用 DesignerSerializationVisibilityAttribute 序列化标准类型的集合](../../../../docs/framework/winforms/controls/serializing-collections-designerserializationvisibilityattribute.md)  
 演示如何使用<xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content?displayProperty=nameWithType>以序列化集合的属性。  
  
 [演练：设计时调试自定义 Windows 窗体控件](../../../../docs/framework/winforms/controls/walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)  
 演示如何调试 Windows 窗体控件的设计时行为。  
  
 [演练：创建利用 Visual Studio 设计时功能的 Windows 窗体控件](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md)  
 演示如何将复合控件紧密集成到设计环境中。  
  
 [如何：创作 Windows 窗体的控件](../../../../docs/framework/winforms/controls/how-to-author-controls-for-windows-forms.md)  
 概述实现 Windows 窗体控件的注意事项。  
  
 [如何：创作复合控件](../../../../docs/framework/winforms/controls/how-to-author-composite-controls.md)  
 演示如何通过继承复合控件来创建控件。  
  
 [如何：从 UserControl 类继承](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-usercontrol-class.md)  
 概述复合控件的创建过程。  
  
 [如何：从现有 Windows 窗体控件继承](../../../../docs/framework/winforms/controls/how-to-inherit-from-existing-windows-forms-controls.md)  
 演示如何创建通过继承扩展的控件<xref:System.Windows.Forms.Button>控件类。  
  
 [如何：从 Control 类继承](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-control-class.md)  
 概述如何创建扩展的控件。  
  
 [如何：设计时将控件与窗体边缘对齐](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)  
 演示如何使用<xref:System.Windows.Forms.Control.Dock%2A>属性以你控件与它所占据窗体边缘对齐。  
  
 [如何：在“选择工具箱项”对话框中显示控件](../../../../docs/framework/winforms/controls/how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)  
 演示安装控件以将其显示在“自定义工具箱”对话框中的过程。  
  
 [如何：为控件提供工具箱位图](../../../../docs/framework/winforms/controls/how-to-provide-a-toolbox-bitmap-for-a-control.md)  
 演示如何使用<xref:System.Drawing.ToolboxBitmapAttribute>来显示在你自定义控件旁边的图标**工具箱**。  
  
 [如何：测试 UserControl 的运行时行为](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md)  
 演示如何使用 **UserControl 测试容器**来测试组合控件的行为。  
  
 [Windows 窗体设计器中的设计时错误](../../../../docs/framework/winforms/controls/design-time-errors-in-the-windows-forms-designer.md)  
 说明 Windows 窗体设计器加载失败时出现在 Microsoft Visual Studio 中的设计时错误列表的含义和用法。  
  
 [控件和组件创作疑难解答](../../../../docs/framework/winforms/controls/troubleshooting-control-and-component-authoring.md)  
 演示如何诊断和解决创作自定义组件或控件时可能出现的常见问题。  
  
## <a name="reference"></a>参考  
 <xref:System.Windows.Forms.Control?displayProperty=nameWithType>  
 对此类进行描述，并提供指向其所有成员的链接。  
  
 <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>  
 对此类进行描述，并提供指向其所有成员的链接。  
  
## <a name="related-sections"></a>相关章节  
 [使用 .NET Framework 开发自定义 Windows 窗体控件](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)  
 讨论如何通过 .NET Framework 创建自己的自定义控件。  
  
 [语言独立性和与语言无关的组件](../../../../docs/standard/language-independence-and-language-independent-components.md)  
 介绍公共语言运行时，它旨在简化组件的创建和使用。 这种简化的一个重要方面是提高了采用不同编程语言编写的组件间的互操作性。 通过公共语言规范 (CLS) 可创建使用多个编程语言的工具和组件。  
  
 [演练：使用自定义组件自动填充工具箱](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)  
 描述如何在“自定义工具箱”对话框中显示组件或控件。
