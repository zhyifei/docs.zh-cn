---
title: ListBox 控件概述（Windows 窗体）
ms.date: 03/30/2017
f1_keywords:
- ListBox
helpviewer_keywords:
- list boxes [Windows Forms], about list boxes
- ListBox control [Windows Forms], about ListBox control
ms.assetid: 37ea226b-6fc8-4c70-936a-c6af4e0cad4c
ms.openlocfilehash: d4cb423a6f32778695abeae725da9755b610d209
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33537559"
---
# <a name="listbox-control-overview-windows-forms"></a>ListBox 控件概述（Windows 窗体）
Windows 窗体<xref:System.Windows.Forms.ListBox>控件将显示用户可以从中选择一个或多个项的列表。 如果项的总数目超过可以显示的数，滚动条会自动添加到<xref:System.Windows.Forms.ListBox>控件。 当<xref:System.Windows.Forms.ListBox.MultiColumn%2A>属性设置为`true`、 列表框中显示多个列中的项和水平滚动条的显示。 当<xref:System.Windows.Forms.ListBox.MultiColumn%2A>属性设置为`false`、 列表框中显示的单个列中的项和垂直滚动条的显示。 当<xref:System.Windows.Forms.ListBox.ScrollAlwaysVisible%2A>设置为`true`，该滚动条显示而不考虑项的数目。 <xref:System.Windows.Forms.ListBox.SelectionMode%2A>属性确定可以一次选择多少列表项。  
  
## <a name="ways-to-change-the-listbox-control"></a>如何更改 ListBox 控件  
 <xref:System.Windows.Forms.ListBox.SelectedIndex%2A>属性将返回一个整数值，对应的列表框中的第一个选定项。 你可以以编程方式更改选定的项，通过更改<xref:System.Windows.Forms.ListBox.SelectedIndex%2A>代码中的值; 将 Windows 窗体上突出显示列表中的对应项。 如果未不选定任何项，<xref:System.Windows.Forms.ListBox.SelectedIndex%2A>值为-1。 如果选择列表中的第一个项，则<xref:System.Windows.Forms.ListBox.SelectedIndex%2A>值为 0。 当选择多个项时，<xref:System.Windows.Forms.ListBox.SelectedIndex%2A>值反映显示首先在列表中的选定的项。 <xref:System.Windows.Forms.ListBox.SelectedItem%2A>属性是类似于<xref:System.Windows.Forms.ListBox.SelectedIndex%2A>，但它返回项本身，而通常一个字符串值。 <xref:System.Windows.Forms.ListBox.ObjectCollection.Count%2A>属性反映在列表中，项的数目和的值<xref:System.Windows.Forms.ListBox.ObjectCollection.Count%2A>属性始终是一个多个是可能的最大<xref:System.Windows.Forms.ListBox.SelectedIndex%2A>值因为<xref:System.Windows.Forms.ListBox.SelectedIndex%2A>是从零开始。  
  
 若要添加或删除中的项<xref:System.Windows.Forms.ListBox>控制，请使用<xref:System.Windows.Forms.ListBox.ObjectCollection.Add%2A>， <xref:System.Windows.Forms.ListBox.ObjectCollection.Insert%2A>，<xref:System.Windows.Forms.ListBox.ObjectCollection.Clear%2A>或<xref:System.Windows.Forms.ListBox.ObjectCollection.Remove%2A>方法。 或者，你可以向列表添加项使用<xref:System.Windows.Forms.ListBox.Items%2A>在设计时属性。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.ListBox>  
 [如何：在 Windows 窗体 ComboBox、ListBox 或 CheckedListBox 控件中添加和删除项](../../../../docs/framework/winforms/controls/add-and-remove-items-from-a-wf-combobox.md)  
 [如何：对 Windows 窗体 ComboBox、ListBox 或 CheckedListBox 控件的内容进行排序](../../../../docs/framework/winforms/controls/sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)  
 [如何：将 Windows 窗体 ComboBox 或 ListBox 控件绑定到数据](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data.md)  
 [ComboBox 控件概述](../../../../docs/framework/winforms/controls/combobox-control-overview-windows-forms.md)  
 [CheckedListBox 控件概述](../../../../docs/framework/winforms/controls/checkedlistbox-control-overview-windows-forms.md)  
 [用于列出选项的 Windows 窗体控件](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)  
 [如何：创建 Windows 窗体 ComboBox、ListBox 或 CheckedListBox 控件的查找表](../../../../docs/framework/winforms/controls/create-a-lookup-table-for-a-wf-combobox-listbox.md)
