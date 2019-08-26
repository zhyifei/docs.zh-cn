---
title: 如何：在 Windows 窗体上定位控件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- Location
- Location.Y
- Location.X
helpviewer_keywords:
- controls [Windows Forms]
- controls [Windows Forms], moving
- snaplines
- controls [Windows Forms], positioning
ms.assetid: 4693977e-34a4-4f19-8221-68c3120c2b2b
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 1cc2cb4c749b7290a6edf914a8e6a697006ef43c
ms.sourcegitcommit: 37616676fde89153f563a485fc6159fc57326fc2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2019
ms.locfileid: "69987081"
---
# <a name="how-to-position-controls-on-windows-forms"></a>如何：将控件置于 Windows 窗体

若要定位控件, 请使用 Visual Studio 中的 Windows 窗体设计器或<xref:System.Windows.Forms.Control.Location%2A>指定属性。

## <a name="position-a-control-on-the-design-surface-of-the-windows-forms-designer"></a>在 Windows 窗体设计器的设计图面上放置控件

在 Visual Studio 中, 用鼠标将控件拖到适当的位置。

> [!NOTE]
> 选择控件, 并将其与箭头键一起移动, 以便更精确地定位。 此外,*对齐线*还有助于在窗体上准确放置控件。 有关详细信息，请参见[演练：使用对齐线](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)排列 Windows 窗体上的控件。

## <a name="position-a-control-using-the-properties-window"></a>使用属性窗口定位控件

1. 在 Visual Studio 中, 选择要定位的控件。

2. 在 "**属性**" 窗口中, 输入<xref:System.Windows.Forms.Control.Location%2A>属性的值 (用逗号分隔), 以将控件放置在其容器中。

   第一个数字 (X) 是距容器左边框的距离;第二个数字 (Y) 是与容器区域的上边框的距离 (以像素为单位)。

   > [!NOTE]
   > 您可以展开<xref:System.Windows.Forms.Control.Location%2A>属性以单独键入**X**和**Y**值。

## <a name="position-a-control-programmatically"></a>以编程方式定位控件

1. 将控件<xref:System.Windows.Forms.Control.Location%2A>的属性设置<xref:System.Drawing.Point>为。

    ```vb
    Button1.Location = New Point(100, 100)
    ```

    ```csharp
    button1.Location = new Point(100, 100);
    ```

    ```cpp
    button1->Location = Point(100, 100);
    ```

2. 使用<xref:System.Windows.Forms.Control.Left%2A>子属性更改控件位置的 X 坐标。

    ```vb
    Button1.Left = 300
    ```

    ```csharp
    button1.Left = 300;
    ```

    ```cpp
    button1->Left = 300;
    ```

## <a name="increment-a-controls-location-programmatically"></a>以编程方式递增控件的位置

设置子<xref:System.Windows.Forms.Control.Left%2A>属性以增加控件的 X 坐标。

```vb
Button1.Left += 200
```

```csharp
button1.Left += 200;
```

```cpp
button1->Left += 200;
```

> [!NOTE]
> <xref:System.Windows.Forms.Control.Location%2A>使用属性同时设置控件的 X 和 Y 位置。 若要单独设置位置, 请使用控件的<xref:System.Windows.Forms.Control.Left%2A> (**X**) 或<xref:System.Windows.Forms.Control.Top%2A> (**Y**) 子属性。 不要尝试隐式设置表示按钮位置的<xref:System.Drawing.Point>结构的 X 和 Y 坐标, 因为此结构包含按钮坐标的副本。

## <a name="see-also"></a>请参阅

- [Windows 窗体控件](index.md)
- [演练：使用对齐线排列 Windows 窗体上的控件](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [演练：使用 TableLayoutPanel 排列 Windows 窗体上的控件](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [演练：使用 FlowLayoutPanel 排列 Windows 窗体上的控件](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [标记各个 Windows 窗体控件并创建它们的快捷键](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [在 Windows 窗体上使用的控件](controls-to-use-on-windows-forms.md)
- [按功能列出的 Windows 窗体控件](windows-forms-controls-by-function.md)
- [如何：设置屏幕位置 Windows 窗体](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/52aha046(v=vs.100))
