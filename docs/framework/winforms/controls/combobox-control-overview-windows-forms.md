---
title: "ComboBox 控件概述（Windows 窗体）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ComboBox
helpviewer_keywords:
- drop-down lists [Windows Forms], Windows Forms
- ComboBox control [Windows Forms], about ComboBox control
- drop-down lists [Windows Forms], ComboBox control
- combo boxes [Windows Forms], about combo boxes
ms.assetid: a58b393f-a614-45d1-8961-857a024b5acd
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 979a410020ab6e3a1f2c15dcee52b062eb00c1ac
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="combobox-control-overview-windows-forms"></a>ComboBox 控件概述（Windows 窗体）
Windows 窗体<xref:System.Windows.Forms.ComboBox>控件用于在下拉组合框中显示数据。 默认情况下，<xref:System.Windows.Forms.ComboBox>控件出现在两个部分： 顶部是文本框中，用户可以键入列表项。 第二部分是显示的项，用户可以从中选择一个列表的列表框。 有关其他样式组合框的详细信息，请参阅[何时使用 Windows 窗体 ComboBox Instead of ListBox](../../../../docs/framework/winforms/controls/when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)。  
  
 <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A>属性选择的列表项将返回一个对应的整数值。 你可以以编程方式更改选定的项，通过更改<xref:System.Windows.Forms.ComboBox.SelectedIndex%2A>代码中的值; 在列表中相应的项将出现在组合框的文本框部分。 如果未不选定任何项，<xref:System.Windows.Forms.ComboBox.SelectedIndex%2A>值为-1。 如果选择列表中的第一个项，则<xref:System.Windows.Forms.ComboBox.SelectedIndex%2A>值为 0。 <xref:System.Windows.Forms.ComboBox.SelectedItem%2A>属性是类似于<xref:System.Windows.Forms.ComboBox.SelectedIndex%2A>，但它返回项本身，而通常一个字符串值。 <xref:System.Windows.Forms.ComboBox.ObjectCollection.Count%2A>属性反映在列表中，项的数目和的值<xref:System.Windows.Forms.ComboBox.ObjectCollection.Count%2A>属性始终是一个多个是可能的最大<xref:System.Windows.Forms.ComboBox.SelectedIndex%2A>值因为<xref:System.Windows.Forms.ComboBox.SelectedIndex%2A>是从零开始。  
  
 若要添加或删除中的项<xref:System.Windows.Forms.ComboBox>控制，请使用<xref:System.Windows.Forms.ComboBox.ObjectCollection.Add%2A>， <xref:System.Windows.Forms.ComboBox.ObjectCollection.Insert%2A>，<xref:System.Windows.Forms.ComboBox.ObjectCollection.Clear%2A>或<xref:System.Windows.Forms.ComboBox.ObjectCollection.Remove%2A>方法。 或者，你可以向列表添加项使用<xref:System.Windows.Forms.ComboBox.Items%2A>设计器中的属性。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.Forms.ComboBox>  
 [ListBox 控件概述](../../../../docs/framework/winforms/controls/listbox-control-overview-windows-forms.md)  
 [何时使用 Windows 窗体 ComboBox 而非 ListBox](../../../../docs/framework/winforms/controls/when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)  
 [如何：在 Windows 窗体 ComboBox、ListBox 或 CheckedListBox 控件中添加和删除项](../../../../docs/framework/winforms/controls/add-and-remove-items-from-a-wf-combobox.md)  
 [如何：对 Windows 窗体 ComboBox、ListBox 或 CheckedListBox 控件的内容进行排序](../../../../docs/framework/winforms/controls/sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)  
 [如何：在 Windows 窗体 ComboBox、ListBox 或 CheckedListBox 控件中访问特定项](../../../../docs/framework/winforms/controls/access-specific-items-in-a-wf-combobox-listbox-or-checkedlistbox.md)  
 [如何：将 Windows 窗体 ComboBox 或 ListBox 控件绑定到数据](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data.md)  
 [用于列出选项的 Windows 窗体控件](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)  
 [如何：创建 Windows 窗体 ComboBox、ListBox 或 CheckedListBox 控件的查找表](../../../../docs/framework/winforms/controls/create-a-lookup-table-for-a-wf-combobox-listbox.md)
