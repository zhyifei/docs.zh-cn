---
title: 使用设计器通过 Panel 控件对控件进行分组
ms.date: 03/30/2017
helpviewer_keywords:
- Panel control [Windows Forms], grouping controls
- controls [Windows Forms], grouping
- Windows Forms controls, grouping
ms.assetid: 7e1cd708-fdb1-49d8-9ca2-5640b276bf2e
ms.openlocfilehash: 927aeb5b51bc1ac4e22a45e487b49424b4e67b71
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745649"
---
# <a name="how-to-group-controls-with-the-windows-forms-panel-control-using-the-designer"></a>如何：使用设计器用 Windows 窗体面板控件对控件进行分组
Windows 窗体 <xref:System.Windows.Forms.Panel> 控件用于对其他控件进行分组。 分组控件有三个原因。 一个是清晰用户界面的相关窗体元素的直观分组;另一种是按编程分组，例如单选按钮;最后一种是在设计时将控件作为一个单元移动。

## <a name="to-create-a-group-of-controls"></a>创建一组控件

1. 将 <xref:System.Windows.Forms.Panel> 控件从 "工具箱" 的 " **Windows 窗体**" 选项卡拖到窗体上。

2. 将其他控件添加到面板，在面板中绘制每个控件。

     如果要将现有控件置于面板中，则可以选择所有控件，将它们剪切到剪贴板，选择 <xref:System.Windows.Forms.Panel> 的控件，然后将其粘贴到面板中。 还可以将其拖动到面板中。

3. 可有可无如果要向面板中添加边框，请设置其 <xref:System.Windows.Forms.BorderStyle> 属性。 有三种选择： <xref:System.Windows.Forms.BorderStyle.Fixed3D>、<xref:System.Windows.Forms.BorderStyle.FixedSingle>和 <xref:System.Windows.Forms.BorderStyle.None>。

## <a name="see-also"></a>另请参阅

- [Panel 控件](panel-control-windows-forms.md)
- [Panel 控件概述](panel-control-overview-windows-forms.md)
- [如何：设置 Panel 控件的背景](how-to-set-the-background-of-a-windows-forms-panel.md)
