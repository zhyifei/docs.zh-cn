---
title: 带有分组框控件的组控件
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], grouping
- GroupBox control [Windows Forms], grouping controls
- Windows Forms controls, grouping
ms.assetid: 0bda316d-bd2a-43aa-ac73-342453303169
ms.openlocfilehash: bb7476c410d2802b5d32cc9842a778f290765e32
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736651"
---
# <a name="how-to-group-controls-with-the-windows-forms-groupbox-control"></a>如何：使用 Windows 窗体 GroupBox 控件对控件分组
Windows 窗体 <xref:System.Windows.Forms.GroupBox> 控件用于对其他控件进行分组。 分组控件有三个原因：  
  
- 为清晰的用户界面创建相关窗体元素的可视分组。  
  
- 创建编程分组（例如，单选按钮）。  
  
- 用于在设计时将控件作为一个单元移动。  
  
### <a name="to-create-a-group-of-controls"></a>创建一组控件  
  
1. 在窗体上绘制 <xref:System.Windows.Forms.GroupBox> 控件。  
  
2. 将其他控件添加到分组框，并在组框中绘制每个控件。  
  
     如果要将现有控件置于分组框中，则可以选择所有控件，将它们剪切到剪贴板，选择 <xref:System.Windows.Forms.GroupBox> 的控件，然后将其粘贴到 "分组" 框。 您还可以将其拖动到分组框中。  
  
3. 将组框的 "<xref:System.Windows.Forms.GroupBox.Text%2A>" 属性设置为相应的标题。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.GroupBox>
- [GroupBox 控件](groupbox-control-windows-forms.md)
