---
title: 在 WPF 应用中收集墨迹
ms.date: 08/15/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ink [WPF], collecting
- InkCanvas element [WPF]
- properties [WPF], DrawingAttributes
- collecting digital ink [WPF]
- digital ink [WPF], collecting
- properties [WPF], DefaultDrawingAttributes
- DefaultDrawingAttributes property [WPF]
ms.assetid: 66a3129d-9577-43eb-acbd-56c147282016
ms.openlocfilehash: 8109e0d6a746d6ca23c25643c510014c1a1e656c
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2019
ms.locfileid: "73740873"
---
# <a name="collect-ink"></a>收集墨迹

[Windows Presentation Foundation](../index.md) 平台会收集数字墨迹，这是其功能中的核心部分之一。 本主题讨论 Windows Presentation Foundation （WPF）中的墨迹收集方法。

## <a name="prerequisites"></a>Prerequisites

若要使用以下示例，必须首先安装 Visual Studio 和 Windows SDK。 还应了解如何编写 WPF 应用程序。 有关 WPF 入门的详细信息，请参阅[演练：我的第一个 wpf 桌面应用程序](../getting-started/walkthrough-my-first-wpf-desktop-application.md)。

## <a name="use-the-inkcanvas-element"></a>使用 InkCanvas 元素

<xref:System.Windows.Controls.InkCanvas?displayProperty=fullName> 元素提供了在 WPF 中收集墨迹的最简单方法。 使用 <xref:System.Windows.Controls.InkCanvas> 元素接收并显示墨迹输入。 通常使用触笔（与数字化仪交互产生墨迹笔画）输入墨迹。 此外，还可以使用鼠标代替触笔。 创建的笔划表示为 <xref:System.Windows.Ink.Stroke> 对象，可通过编程方式和用户输入操作。 <xref:System.Windows.Controls.InkCanvas> 使用户能够选择、修改或删除现有 <xref:System.Windows.Ink.Stroke>。

通过使用 XAML，可以轻松地设置墨迹收集，就像向树中添加**InkCanvas**元素一样。 下面的示例将 <xref:System.Windows.Controls.InkCanvas> 添加到在 Visual Studio 中创建的默认 WPF 项目：

[!code-xaml[DigitalInkTopics#6](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#6)]

**InkCanvas**元素还可以包含子元素，这样就可以将墨迹注释功能添加到几乎任何类型的 XAML 元素。 例如，若要将墨迹功能添加到文本元素，只需将其设置为 <xref:System.Windows.Controls.InkCanvas>的子元素：

[!code-xaml[DigitalInkTopics#5](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#5)]

添加对使用墨迹标记图像的支持同样简单：

[!code-xaml[DigitalInkTopics#7](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#7)]

### <a name="inkcollection-modes"></a>InkCollection 模式

<xref:System.Windows.Controls.InkCanvas> 通过其 <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> 属性提供各种输入模式的支持。

### <a name="manipulate-ink"></a>操作墨迹

<xref:System.Windows.Controls.InkCanvas> 提供对许多墨迹编辑操作的支持。 例如，<xref:System.Windows.Controls.InkCanvas> 支持笔背面擦除，并且无需其他代码即可将该功能添加到元素中。

#### <a name="selection"></a>选择

设置选择模式与将 <xref:System.Windows.Controls.InkCanvasEditingMode> 属性设置为**Select**一样简单。

以下代码根据 <xref:System.Windows.Forms.CheckBox>的值设置编辑模式：

[!code-csharp[DigitalInkTopics#8](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#8)]
[!code-vb[DigitalInkTopics#8](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#8)]

#### <a name="drawingattributes"></a>DrawingAttributes

使用 <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> 属性可更改墨笔划的外观。 例如，<xref:System.Windows.Ink.DrawingAttributes> 的 <xref:System.Windows.Ink.DrawingAttributes.Color%2A> 成员设置所呈现 <xref:System.Windows.Ink.Stroke>的颜色。

下面的示例将选定笔画的颜色更改为红色：

[!code-csharp[DigitalInkTopics#9](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#9)]
[!code-vb[DigitalInkTopics#9](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#9)]

### <a name="defaultdrawingattributes"></a>DefaultDrawingAttributes

<xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> 属性提供对要在 <xref:System.Windows.Controls.InkCanvas>中创建的笔划的高度、宽度和颜色等属性的访问。 更改 <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>后，在 <xref:System.Windows.Controls.InkCanvas> 中输入的所有未来笔画都将呈现为新的属性值。

除了修改代码隐藏文件中的 <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> 之外，还可以使用 XAML 语法来指定 <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> 属性。

下一个示例演示如何设置 <xref:System.Windows.Ink.DrawingAttributes.Color%2A> 属性。 若要使用此代码，请在 Visual Studio 中创建一个名为 "HelloInkCanvas" 的新 WPF 项目。 将*mainwindow.xaml*文件中的代码替换为以下代码：

[!code-xaml[HelloInkCanvas#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml#1)]

接下来，将以下按钮事件处理程序添加到 Mainwindow.xaml 类中的代码隐藏文件：

[!code-csharp[HelloInkCanvas#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml.cs#2)]

复制此代码后，在 Visual Studio 中按**F5**以在调试器中运行该程序。

请注意 <xref:System.Windows.Controls.StackPanel> 如何将按钮置于 <xref:System.Windows.Controls.InkCanvas>顶部。 如果尝试在按钮顶部显示墨迹，则 <xref:System.Windows.Controls.InkCanvas> 会收集按钮并呈现墨迹。 这是因为按钮是 <xref:System.Windows.Controls.InkCanvas> 的同级，而不是子级。 此外，这些按钮的 Z 顺序较高，所以墨迹呈现在其后面。

## <a name="see-also"></a>请参阅

- <xref:System.Windows.Ink.DrawingAttributes>
- <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>
- <xref:System.Windows.Ink>
