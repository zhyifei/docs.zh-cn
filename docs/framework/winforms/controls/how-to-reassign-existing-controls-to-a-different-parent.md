---
title: 如何：将现有的控件重新分配给不同的父控件
ms.date: 03/30/2017
helpviewer_keywords:
- container controls [Windows Forms], Windows Forms
- layout [Windows Forms], resizing
- layout [Windows Forms], child controls
ms.assetid: 5a5723ff-34e0-4b6f-a57b-be4ebe35cb34
ms.openlocfilehash: a65b3c2b596a2d88ce4236aeadd86993bb268aa6
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039790"
---
# <a name="how-to-reassign-existing-controls-to-a-different-parent"></a>如何：将现有的控件重新分配给不同的父控件
可以将你窗体中的控件分配到新容器控件。

## <a name="to-reassign-existing-controls-to-a-different-parent"></a>若要将现有的控件重新分配给不同的父控件

1. 将三个 <xref:System.Windows.Forms.Button> 控件从“工具箱” 拖到窗体上。

     将其相邻放置，但不用对齐它们。

2. 在“工具箱”中，单击 <xref:System.Windows.Forms.FlowLayoutPanel> 控件图标。

     请勿将该图标拖动到窗体上。

3. 将鼠标指针移至靠近这 3 个 <xref:System.Windows.Forms.Button> 控件。

     指针更改为十字线时就会附上 <xref:System.Windows.Forms.FlowLayoutPanel> 控件图标。

4. 单击并按住鼠标按钮。

5. 拖动鼠标指针以绘制 <xref:System.Windows.Forms.FlowLayoutPanel> 控件的轮廓。

6. 在这三个 <xref:System.Windows.Forms.Button> 控件周围绘制轮廓。

7. 释放鼠标按钮。

     这三种 <xref:System.Windows.Forms.Button> 控件现在插入到 <xref:System.Windows.Forms.FlowLayoutPanel> 控件中。

## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.FlowLayoutPanel>
- <xref:System.Windows.Forms.TableLayoutPanel>
- [在 Windows 窗体上排列控件](arranging-controls-on-windows-forms.md)
- [演练：使用 TableLayoutPanel 排列 Windows 窗体上的控件](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [演练：使用对齐线排列 Windows 窗体上的控件](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
