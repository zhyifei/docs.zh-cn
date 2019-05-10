---
title: 如何：测试 UserControl 的运行时行为
ms.date: 03/30/2017
helpviewer_keywords:
- UserControl class [Windows Forms], testing
- user controls [Windows Forms], testing
- composite controls [Windows Forms], testing
- UserControl Test Container
- UserControl class [Windows Forms], run-time behavior
ms.assetid: 4e4d5c49-1346-40ac-9d96-40211b573583
ms.openlocfilehash: 48531ab1ef3b30b6516e3f2e7b5858a8884cbfe8
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211715"
---
# <a name="how-to-test-the-run-time-behavior-of-a-usercontrol"></a>如何：测试 UserControl 的运行时行为

开发时<xref:System.Windows.Forms.UserControl>，您需要测试其运行时行为。 可以创建一个单独的基于 Windows 的应用程序项目，并将你窗体控件的测试，但此过程是不方便。 更快、 更轻松的方法是使用**UserControl 测试容器**Visual Studio 提供的。 此测试容器开始直接从 Windows 控件库项目。

> [!IMPORTANT]
> 若要加载的测试容器在<xref:System.Windows.Forms.UserControl>，控件必须具有至少一个公共构造函数。

> [!NOTE]
> 视觉对象C++控件不能使用测试**UserControl 测试容器**。

## <a name="test-the-run-time-behavior-of-a-usercontrol"></a>测试 UserControl 的运行时行为

1. 在 Visual Studio 中，创建一个名为的 Windows 控件库项目**TestContainerExample**。 有关详细信息，请参阅[Windows 控件库模板](https://docs.microsoft.com/previous-versions/kxczf775(v=vs.100))。

2. 在中**Windows 窗体设计器**，拖动<xref:System.Windows.Forms.Label>控件从**工具箱**到控件的设计图面。

3. 按**F5**生成项目并运行**UserControl 测试容器**。 测试容器会显示与你<xref:System.Windows.Forms.UserControl>中**预览**窗格。

4. 选择<xref:System.Windows.Forms.Control.BackColor%2A>属性中显示<xref:System.Windows.Forms.PropertyGrid>右侧的控件**预览**窗格。 其值更改为`ControlDark`。 观察控件更改为较深的颜色。 请尝试更改其他属性值，并观察在控件上的效果。

5. 单击**停靠填充用户控件**下面的复选框**预览**窗格。 观察到该控件调整大小以填充窗格。 调整测试容器的大小，并观察调整控件大小与窗格。

6. 关闭测试容器。

7. 另一个用户控件添加到**TestContainerExample**项目。 有关详细信息，请参阅[如何：向项目添加现有项](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/9f4t9t92(v=vs.100))。

8. 在中**Windows 窗体设计器**，拖动<xref:System.Windows.Forms.Button>控件从**工具箱**到控件的设计图面。

9. 按 F5 以生成项目并运行测试容器。

10. 单击**选择用户控件**<xref:System.Windows.Forms.ComboBox>两个用户控件之间进行切换。

## <a name="test-user-controls-from-another-project"></a>从另一个项目的测试用户控件

在当前项目的测试容器中，可以测试其他项目中的用户控件。

1. 创建一个名为的 Windows 控件库项目**TestContainerExample2**。 有关详细信息，请参阅[Windows 控件库模板](https://docs.microsoft.com/previous-versions/kxczf775(v=vs.100))。

2. 在中**Windows 窗体设计器**，拖动<xref:System.Windows.Forms.RadioButton>控件从**工具箱**到控件的设计图面。

3. 按 F5 以生成项目并运行测试容器。 测试容器会显示与你<xref:System.Windows.Forms.UserControl>中**预览**窗格。

4. 单击**负载**按钮。

5. 在中**开放**对话框框中，导航到**TestContainerExample**.dll 上, 一个过程中生成。 选择**TestContainerExample**.dll，然后单击**打开**按钮以加载用户控件

6. 使用**选择用户控件**<xref:System.Windows.Forms.ComboBox>若要从两个用户控件之间切换**TestContainerExample**项目。

## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.UserControl>
- [如何：创作复合控件](how-to-author-composite-controls.md)
- [演练：创作复合控件使用 Visual Basic](walkthrough-authoring-a-composite-control-with-visual-basic.md)
- [演练：创作复合控件通过视觉对象C#](walkthrough-authoring-a-composite-control-with-visual-csharp.md)
- [用户控件设计器](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/183c3hth(v=vs.100))
