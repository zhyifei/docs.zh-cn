---
title: 演练：向窗体提供标准菜单项
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- menu items [Windows Forms], standard
- toolbars [Windows Forms], walkthroughs
- StatusStrip control [Windows Forms]
- ToolStrip control [Windows Forms]
ms.assetid: dac37d98-589e-4d6d-9673-6437e8943122
ms.openlocfilehash: ee80aad445c00bb4b98b49c80495fa512150bcef
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628769"
---
# <a name="walkthrough-providing-standard-menu-items-to-a-form"></a>演练：向窗体提供标准菜单项

可使用 <xref:System.Windows.Forms.MenuStrip> 控件向窗体提供标准菜单。

本演练演示如何使用 <xref:System.Windows.Forms.MenuStrip> 控件创建标准菜单。 窗体还在用户选择菜单项时做出响应。 此演练演示了下列任务：

- 创建 Windows 窗体项目。

- 创建标准菜单。

- 创建 <xref:System.Windows.Forms.StatusStrip> 控件。

- 处理菜单项选择。

完成后，将获得一个带有标准菜单的窗体，其中显示了 <xref:System.Windows.Forms.StatusStrip> 控件中的菜单项选择。

若要将本主题中的代码复制为单个列表，请参阅[如何：向窗体提供标准菜单项](how-to-provide-standard-menu-items-to-a-form.md)。

## <a name="prerequisites"></a>必备条件

需要 Visual Studio 才能完成此演练。

## <a name="create-the-project"></a>创建项目

1. 在 visual Studio 中，创建一个名为 " **StandardMenuForm** " 的 Windows 应用程序项目（**文件** > **新**的 > **项目** > **视觉C#对象**或**Visual Basic** > **经典桌面** > **Windows 窗体应用程序**）。

2. 在 Windows 窗体设计器中，选择窗体。

## <a name="create-a-standard-menu"></a>创建标准菜单

Windows 窗体设计器可以使用标准菜单项自动填充 <xref:System.Windows.Forms.MenuStrip> 控件。

1. 从 "**工具箱**" 中，将 "<xref:System.Windows.Forms.MenuStrip>" 控件拖动到窗体上。

2. 单击 <xref:System.Windows.Forms.MenuStrip> 控件的设计器操作标志符号（![小黑色箭头](./media/designer-actions-glyph.gif)），然后选择 "**插入标准项**"。

     <xref:System.Windows.Forms.MenuStrip> 控件将用标准菜单项进行填充。

3. 单击 "**文件**" 菜单项可查看其默认菜单项和相应的图标。

## <a name="create-a-statusstrip-control"></a>创建 StatusStrip 控件

使用 <xref:System.Windows.Forms.StatusStrip> 控件显示 Windows 窗体应用程序的状态。 在当前的示例中，用户选择的菜单项显示在 <xref:System.Windows.Forms.StatusStrip> 控件中。

1. 从 "**工具箱**" 中，将 "<xref:System.Windows.Forms.StatusStrip>" 控件拖动到窗体上。

     <xref:System.Windows.Forms.StatusStrip> 控件会自动停靠到窗体的底部。

2. 单击 <xref:System.Windows.Forms.StatusStrip> 控件的下拉按钮，然后选择 " **statuslabel 设置**"，将 <xref:System.Windows.Forms.ToolStripStatusLabel> 控件添加到 <xref:System.Windows.Forms.StatusStrip> 控件。

## <a name="handle-item-selection"></a>处理项选择

处理 <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> 事件，以便在用户选择菜单项时做出响应。

1. 单击在创建标准菜单部分中创建的 "**文件**" 菜单项。

2. 在“属性”窗口中，单击“事件”。

3. 双击 "<xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked>" 事件。

     Windows 窗体设计器生成 <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> 事件的事件处理程序。

4. 将以下代码插入到事件处理程序中。

     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#3)]

5. 将 `UpdateStatus` 实用工具方法定义插入窗体中。

     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#2)]

## <a name="checkpoint--test-your-form"></a>检查点-测试窗体

1. 按**F5**编译并运行您的窗体。

2. 单击 "**文件**" 菜单项，打开菜单。

3. 在 "**文件**" 菜单上，单击其中一个项目以将其选中。

     <xref:System.Windows.Forms.StatusStrip> 控件显示选定项。

## <a name="next-steps"></a>后续步骤

在本演练中，您已创建了一个带有标准菜单的窗体。 您可以使用 <xref:System.Windows.Forms.ToolStrip> 系列控件来实现多种其他用途：

- 创建具有 <xref:System.Windows.Forms.ContextMenuStrip>的控件的快捷菜单。 有关详细信息，请参阅[ContextMenu 组件概述](contextmenu-component-overview-windows-forms.md)。

- 使用停靠 <xref:System.Windows.Forms.ToolStrip> 控件创建多文档界面（MDI）窗体。 有关详细信息，请参阅[演练：创建具有菜单合并和 ToolStrip 控件的 MDI 窗体](walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md)。

- 为您的 <xref:System.Windows.Forms.ToolStrip> 控制专业外观。 有关详细信息，请参阅[如何：为应用程序设置 ToolStrip 呈现](how-to-set-the-toolstrip-renderer-for-an-application.md)器。

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [MenuStrip 控件](menustrip-control-windows-forms.md)
