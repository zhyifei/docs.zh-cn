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
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 110036e5031a2956375b1edf0689237661522d39
ms.sourcegitcommit: dfd612ba454ce775a766bcc6fe93bc1d43dfda47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2019
ms.locfileid: "72180210"
---
# <a name="how-to-test-the-run-time-behavior-of-a-usercontrol"></a>如何：测试 UserControl 的运行时行为

开发 <xref:System.Windows.Forms.UserControl> 时，需要测试其运行时行为。 您可以创建一个单独的基于 Windows 的应用程序项目，并将您的控件置于测试窗体上，但此过程是不方便的。 更快、更简单的方法是使用 Visual Studio 提供的**UserControl 测试容器**。 此测试容器直接从 Windows 控件库项目启动。

> [!IMPORTANT]
> 要使测试容器加载 <xref:System.Windows.Forms.UserControl>，控件必须至少有一个公共构造函数。

> [!NOTE]
> 无法使用C++ **UserControl 测试容器**测试视觉对象控件。

## <a name="test-the-run-time-behavior-of-a-usercontrol"></a>测试 UserControl 的运行时行为

1. 在 Visual Studio 中，创建一个 Windows 控件库项目，并将其命名为**TestContainerExample**。

2. 在**Windows 窗体设计器**中，将 "@no__t" 控件从 "**工具箱**" 拖到控件的设计图面上。

3. 按<kbd>F5</kbd>生成项目，并运行 " **UserControl 测试容器**"。 测试容器在**预览**窗格中显示 <xref:System.Windows.Forms.UserControl>。

4. 选择**预览**窗格右侧 @no__t 控件中显示的 <xref:System.Windows.Forms.Control.BackColor%2A> 属性。 将其值更改为**ControlDark**。 观察控件更改为较暗的颜色。 尝试更改其他属性值并观察控件上的效果。

5. 单击 "**预览**" 窗格下的 "**停靠填充用户控件**" 复选框。 请注意，控件调整大小以填充窗格。 调整测试容器的大小，并观察控件是否随窗格一起调整大小。

6. 关闭测试容器。

7. 向**TestContainerExample**项目添加另一个用户控件。

8. 在**Windows 窗体设计器**中，将 "@no__t" 控件从 "**工具箱**" 拖到控件的设计图面上。

9. 按<kbd>F5</kbd>生成项目并运行测试容器。

10. 单击 "**选择用户控件**<xref:System.Windows.Forms.ComboBox> 以在两个用户控件之间切换。

## <a name="test-user-controls-from-another-project"></a>测试其他项目中的用户控件

可以在当前项目的测试容器中测试其他项目中的用户控件。

1. 在 Visual Studio 中，创建一个 Windows 控件库项目，并将其命名为**TestContainerExample2**。

2. 在**Windows 窗体设计器**中，将 "@no__t" 控件从 "**工具箱**" 拖到控件的设计图面上。

3. 按<kbd>F5</kbd>生成项目并运行测试容器。 测试容器在**预览**窗格中显示 <xref:System.Windows.Forms.UserControl>。

4. 单击 "**加载**" 按钮。

5. 在 "**打开**" 对话框中，导航到在前面的过程中生成的 " *TestContainerExample*"。 选择 " *TestContainerExample* "，并单击 "**打开**" 按钮以加载用户控件。

6. 使用 "**选择用户控件**<xref:System.Windows.Forms.ComboBox> 从**TestContainerExample**项目切换两个用户控件。

## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.UserControl>
- [如何：创作复合控件 @ no__t-0
- [演练：创作复合控件 @ no__t-0
- [用户控件设计器](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/183c3hth(v=vs.100))
