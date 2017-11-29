---
title: "如何：对 Windows 窗体 ComboBox 控件、ListBox 控件或 CheckedListBox 控件的内容排序"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- CheckedListBox control [Windows Forms], sorting
- ComboBox control [Windows Forms], sorting contents
- combo boxes [Windows Forms], sorting contents
- list boxes [Windows Forms], sorting contents
- ListBox control [Windows Forms], sorting contents
ms.assetid: c268e387-3d1d-4d86-a940-19f6673c8d06
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0e43a23d632b397889721373471a8fa165052d7f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-sort-the-contents-of-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a>如何：对 Windows 窗体 ComboBox 控件、ListBox 控件或 CheckedListBox 控件的内容排序
在数据绑定时，Windows 窗体控件不进行排序。 若要显示已排序的数据，使用支持排序的数据源，然后对它进行排序的数据源。 支持排序的数据源是： 数据视图，数据查看管理器，并已排序数组。  
  
 如果控件不是数据绑定，可以对它进行排序。  
  
### <a name="to-sort-the-list"></a>若要对列表进行排序  
  
1.  将 `Sorted` 属性设置为 `true`。  
  
     此设置将按排序顺序重新定位所有现有列表项。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.Forms.ComboBox>  
 <xref:System.Windows.Forms.ListBox>  
 <xref:System.Windows.Forms.CheckedListBox>  
 [Windows 窗体数据绑定](../../../../docs/framework/winforms/windows-forms-data-binding.md)  
 [如何：在 Windows 窗体 ComboBox、ListBox 或 CheckedListBox 控件中添加和删除项](../../../../docs/framework/winforms/controls/add-and-remove-items-from-a-wf-combobox.md)  
 [何时使用 Windows 窗体 ComboBox 而非 ListBox](../../../../docs/framework/winforms/controls/when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)  
 [用于列出选项的 Windows 窗体控件](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)
