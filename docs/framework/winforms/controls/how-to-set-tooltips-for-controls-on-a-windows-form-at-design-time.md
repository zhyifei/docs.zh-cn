---
title: 如何：在设计时为 Windows 窗体上的控件设置 ToolTip
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tooltips [Windows Forms], for controls
- examples [Windows Forms], tooltips
ms.assetid: c4b60637-4c0a-44c2-a103-f66dff887936
ms.openlocfilehash: 0d6725fc1a00826870e6400bffce63a1788e802c
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211690"
---
# <a name="how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time"></a>如何：在设计时为 Windows 窗体上的控件设置工具提示

可以设置<xref:System.Windows.Forms.ToolTip>字符串在代码中或在 Visual Studio 中的 Windows 窗体设计器中。 有关详细信息<xref:System.Windows.Forms.ToolTip>组件，请参阅[ToolTip 组件概述](tooltip-component-overview-windows-forms.md)。

## <a name="set-a-tooltip-programmatically"></a>以编程方式设置工具提示

1. 添加控件，将显示工具提示。

2. 使用<xref:System.Windows.Forms.ToolTip.SetToolTip%2A>方法的<xref:System.Windows.Forms.ToolTip>组件。

    ```vb
    ' In this example, Button1 is the control to display the ToolTip.
    ToolTip1.SetToolTip(Button1, "Save changes")
    ```

    ```csharp
    // In this example, button1 is the control to display the ToolTip.
    toolTip1.SetToolTip(button1, "Save changes");
    ```

    ```cpp
    // In this example, button1 is the control to display the ToolTip.
    toolTip1->SetToolTip(button1, "Save changes");
    ```

## <a name="set-a-tooltip-in-the-designer"></a>在设计器中设置工具提示

1. 在 Visual Studio 中，添加<xref:System.Windows.Forms.ToolTip>组件到窗体。

2. 选择将显示工具提示，或将其添加到窗体的控件。

3. 在中**属性**窗口中，将**ToolTip1 上的工具提示**为相应的文本字符串的值。

### <a name="to-remove-a-tooltip-programmatically"></a>若要以编程方式删除工具提示

1. 使用<xref:System.Windows.Forms.ToolTip.SetToolTip%2A>方法的<xref:System.Windows.Forms.ToolTip>组件。

    ```vb
    ' In this example, Button1 is the control displaying the ToolTip.
    ToolTip1.SetToolTip(Button1, Nothing)
    ```

    ```csharp
    // In this example, button1 is the control displaying the ToolTip.
    toolTip1.SetToolTip(button1, null);
    ```

    ```cpp
    // In this example, button1 is the control displaying the ToolTip.
    toolTip1->SetToolTip(button1, NULL);
    ```

## <a name="remove-a-tooltip-in-the-designer"></a>在设计器中删除一个工具提示

1. 在 Visual Studio 中，选择显示工具提示的控件。

2. 在中**属性**窗口中，删除中的文本**ToolTip1 上的工具提示**。

## <a name="see-also"></a>请参阅

- [ToolTip 组件概述](tooltip-component-overview-windows-forms.md)
- [如何：更改 Windows 窗体 ToolTip 组件的延迟](how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)
- [ToolTip 组件](tooltip-component-windows-forms.md)
