---
title: 如何：管理 ToolStrip 溢出
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], managing overflow
- toolbars [Windows Forms], managing overflow
- examples [Windows Forms], toolbars
- CanOverflow property
ms.assetid: fa10e0ad-4cbf-4c0d-9082-359c2f855d4e
ms.openlocfilehash: 52cc02e626bee2d2457355028ecddc17e462d8fa
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736144"
---
# <a name="how-to-manage-toolstrip-overflow-in-windows-forms"></a>如何：在 Windows 窗体中管理 ToolStrip 溢出

如果 <xref:System.Windows.Forms.ToolStrip> 控件中的所有项都不适合于分配的空间，则可以对 <xref:System.Windows.Forms.ToolStrip> 启用溢出功能，并确定特定 <xref:System.Windows.Forms.ToolStripItem>的溢出行为。

如果添加的 <xref:System.Windows.Forms.ToolStripItem>需要的空间超过了给定窗体的当前大小所分配到的 <xref:System.Windows.Forms.ToolStrip>，则 <xref:System.Windows.Forms.ToolStripOverflowButton> 会自动显示在 <xref:System.Windows.Forms.ToolStrip>上。 <xref:System.Windows.Forms.ToolStripOverflowButton> 随即出现，启用溢出的项将移至下拉溢出菜单。 这使你可以自定义 <xref:System.Windows.Forms.ToolStrip> 项如何正确调整到不同的窗体大小并设置其优先级。 还可以通过使用 "<xref:System.Windows.Forms.ToolStripItem.Placement%2A>" 和 "<xref:System.Windows.Forms.ToolStripOverflow.DisplayedItems%2A?displayProperty=nameWithType> 属性" 和 "<xref:System.Windows.Forms.ToolStrip.LayoutCompleted>" 事件，更改项目在溢出时的外观。 如果您在设计时或运行时放大窗体，则主 <xref:System.Windows.Forms.ToolStrip> 上可以显示更多 <xref:System.Windows.Forms.ToolStripItem>，<xref:System.Windows.Forms.ToolStripOverflowButton> 即使您减小了窗体的大小，也可能消失。

## <a name="to-enable-overflow-on-a-toolstrip-control"></a>对 ToolStrip 控件启用溢出

- 确保 <xref:System.Windows.Forms.ToolStrip><xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> 属性未设置为 `false`。 默认为 `True`。

     当 <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> 为 `True` （默认值）时，当 <xref:System.Windows.Forms.ToolStripItem> 的内容超出水平 <xref:System.Windows.Forms.ToolStrip> 的宽度或垂直 <xref:System.Windows.Forms.ToolStrip>的高度时，会将 <xref:System.Windows.Forms.ToolStripItem> 发送到下拉溢出菜单。

## <a name="to-specify-overflow-behavior-of-a-specific-toolstripitem"></a>指定特定 ToolStripItem 的溢出行为

- 将 <xref:System.Windows.Forms.ToolStripItem> 的 <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> 属性设置为所需的值。 可能 `Always`、`Never`和 `AsNeeded`。 默认为 `AsNeeded`。

    ```vb
    toolStripTextBox1.Overflow = _
    System.Windows.Forms.ToolStripItemOverflow.Never
    ```

    ```csharp
    toolStripTextBox1.Overflow = _
    System.Windows.Forms.ToolStripItemOverflow.Never;
    ```

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripOverflowButton>
- <xref:System.Windows.Forms.ToolStripItem.Overflow%2A>
- <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>
- [ToolStrip 控件概述](toolstrip-control-overview-windows-forms.md)
- [ToolStrip 控件体系结构](toolstrip-control-architecture.md)
- [ToolStrip 技术摘要](toolstrip-technology-summary.md)
