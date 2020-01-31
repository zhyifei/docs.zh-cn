---
title: ComboBox 与 ListBox
ms.date: 03/30/2017
helpviewer_keywords:
- ListBox control [Windows Forms], adding and removing items
- ListBox control [Windows Forms], vs. ComboBox
- bound controls [Windows Forms], combo boxes
- Windows Forms controls, data binding
- ComboBox control [Windows Forms], compared to ListBox
- combo boxes [Windows Forms], compared to list boxes
- ListBox control [Windows Forms], accessing items
- ListCount property
ms.assetid: 7bcaea58-1cfa-46db-9baf-b75a69d8f9ec
ms.openlocfilehash: 7087760a393bb58d83d899c1741c745fb28585bb
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739927"
---
# <a name="when-to-use-a-windows-forms-combobox-instead-of-a-listbox"></a>何时使用 Windows 窗体 ComboBox 而非 ListBox
<xref:System.Windows.Forms.ComboBox> 和 <xref:System.Windows.Forms.ListBox> 控件具有相似的行为，并且在某些情况下，可以互换。 但有时，当其中一项或其他项更适合某个任务时。  
  
 通常，当存在建议的选项列表时，组合框是适当的，当你想要将输入限制为列表上的内容时，可使用列表框。 组合框包含文本框字段，因此可以在列表中键入不是在列表中的选项。 当 <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> 属性设置为 <xref:System.Windows.Forms.ComboBoxStyle.DropDownList>时，例外。 在这种情况下，如果键入第一个字母，控件将选择一项。  
  
 此外，组合框还节省了窗体上的空间。 因为在用户单击向下箭头后，不显示完整列表，所以，组合框可以轻松地放入列表框无法容纳的小空间。 当 <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> 属性设置为 <xref:System.Windows.Forms.ComboBoxStyle.Simple>时，例外：显示完整列表，组合框占用的空间比列表框多。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- [如何：在 Windows 窗体 ComboBox、ListBox 或 CheckedListBox 控件中添加和删除项](add-and-remove-items-from-a-wf-combobox.md)
- [如何：对 Windows 窗体 ComboBox、ListBox 或 CheckedListBox 控件的内容进行排序](sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)
- [用于列出选项的 Windows 窗体控件](windows-forms-controls-used-to-list-options.md)
