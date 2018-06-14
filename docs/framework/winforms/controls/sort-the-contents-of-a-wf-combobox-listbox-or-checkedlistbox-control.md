---
title: 如何：对 Windows 窗体 ComboBox 控件、ListBox 控件或 CheckedListBox 控件的内容排序
ms.date: 03/30/2017
helpviewer_keywords:
- CheckedListBox control [Windows Forms], sorting
- ComboBox control [Windows Forms], sorting contents
- combo boxes [Windows Forms], sorting contents
- list boxes [Windows Forms], sorting contents
- ListBox control [Windows Forms], sorting contents
ms.assetid: c268e387-3d1d-4d86-a940-19f6673c8d06
ms.openlocfilehash: 8b8f9c7ad0ad7d3bbb7f3eeffd44e555207b82c4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33535641"
---
# <a name="how-to-sort-the-contents-of-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a>如何：对 Windows 窗体 ComboBox 控件、ListBox 控件或 CheckedListBox 控件的内容排序
在数据绑定时，Windows 窗体控件不进行排序。 若要显示已排序的数据，使用支持排序的数据源，然后对它进行排序的数据源。 支持排序的数据源是： 数据视图，数据查看管理器，并已排序数组。  
  
 如果控件不是数据绑定，可以对它进行排序。  
  
### <a name="to-sort-the-list"></a>若要对列表进行排序  
  
1.  将 `Sorted` 属性设置为 `true`。  
  
     此设置将按排序顺序重新定位所有现有列表项。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.ComboBox>  
 <xref:System.Windows.Forms.ListBox>  
 <xref:System.Windows.Forms.CheckedListBox>  
 [Windows 窗体数据绑定](../../../../docs/framework/winforms/windows-forms-data-binding.md)  
 [如何：在 Windows 窗体 ComboBox、ListBox 或 CheckedListBox 控件中添加和删除项](../../../../docs/framework/winforms/controls/add-and-remove-items-from-a-wf-combobox.md)  
 [何时使用 Windows 窗体 ComboBox 而非 ListBox](../../../../docs/framework/winforms/controls/when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)  
 [用于列出选项的 Windows 窗体控件](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)
