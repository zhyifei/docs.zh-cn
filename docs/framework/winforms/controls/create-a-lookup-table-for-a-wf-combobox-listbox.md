---
title: "如何：为 Windows 窗体 ComboBox 控件、ListBox 控件或 CheckedListBox 控件创建查找表"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CheckedListBox control [Windows Forms], creating lookup tables
- lookup tables
- list boxes [Windows Forms], lookup tables
- ListBox control [Windows Forms], lookup tables
- ComboBox control [Windows Forms], lookup table
- lookup tables [Windows Forms], creating for controls
- combo boxes [Windows Forms], lookup tables
- ListBox control [Windows Forms], creating lookup tables
ms.assetid: 4ce35f12-1f4e-4317-92d1-af8686a8cfaa
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cb7ffb8a7f20c1e53b24a1db8bda326d73743a93
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-lookup-table-for-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a>如何：为 Windows 窗体 ComboBox 控件、ListBox 控件或 CheckedListBox 控件创建查找表
有时，在 Windows 窗体上以用户友好格式显示数据，但存储数据时使用对程序而言更有意义的格式会很有帮助。 例如，食品订单窗体可能按列表框中的名称显示菜单项。 但是，记录订单的数据表将包含代表该食品的唯一 ID 号。 下表显示如何存储和显示食品订单窗体数据的示例。  
  
### <a name="orderdetailstable"></a>OrderDetailsTable  
  
|OrderID|ItemID|Quantity|  
|-------------|------------|--------------|  
|4085|12|1|  
|4086|13|3|  
  
### <a name="itemtable"></a>ItemTable  
  
|ID|名称|  
|--------|----------|  
|12|Potato|  
|13|Chicken|  
  
 在此方案中，一个表， **OrderDetailsTable**，存储您担心显示和保存的实际信息。 但为了节省空间，它采用一种很隐秘的方式。 另一个表**ItemTable**，包含有关哪个 ID 号等同于哪个食品名称，以及执行任何操作有关的实际食品订单的唯一与外观相关的信息。  
  
 **ItemTable**连接到<xref:System.Windows.Forms.ComboBox>， <xref:System.Windows.Forms.ListBox>，或<xref:System.Windows.Forms.CheckedListBox>控制通过三个属性。 `DataSource`属性包含此表的名称。 `DisplayMember`属性包含你想要在控件 （食品名称） 中显示的表的数据列。 `ValueMember`属性包含该表中具有存储的信息 （ID 号） 的数据列。  
  
 **OrderDetailsTable**通过其绑定集合，通过访问连接到控件<xref:System.Windows.Forms.Control.DataBindings%2A>属性。 时使用的绑定对象添加到集合时，将控件属性连接到数据源中的特定数据成员 （列的 ID 号） ( **OrderDetailsTable**)。 在控件中进行选择时，窗体输入将保存到此表。  
  
### <a name="to-create-a-lookup-table"></a>创建查找表的步骤  
  
1.  向窗体添加 <xref:System.Windows.Forms.ComboBox><xref:System.Windows.Forms.ListBox> 或 <xref:System.Windows.Forms.CheckedListBox> 控件。  
  
2.  连接到数据源。  
  
3.  在两张表之间建立数据关系。 请参阅[DataRelation 对象介绍](http://msdn.microsoft.com/library/89d8a881-8265-41f2-a88b-61311ab06192)。  
  
4.  设置以下属性： 以下属性可在代码或设计器中设置。  
  
    |属性|设置|  
    |--------------|-------------|  
    |<xref:System.Windows.Forms.ListControl.DataSource%2A>|包含有关哪个 ID 号等同于哪一项的信息的表。 在前面的方案中，这是`ItemTable`。|  
    |<xref:System.Windows.Forms.ListControl.DisplayMember%2A>|你想要在控件中显示的源数据表的列。 在前面的方案中，这是`"Name"`（若要在代码中设置，使用双引号）。|  
    |<xref:System.Windows.Forms.ListControl.ValueMember%2A>|包含所存储信息的源数据表的列。 在前面的方案中，这是`"ID"`（若要在代码中设置，使用双引号）。|  
  
5.  在过程中，调用 <xref:System.Windows.Forms.ControlBindingsCollection> 类的 <xref:System.Windows.Forms.ControlBindingsCollection.Add%2A> 方法，以将控件的 <xref:System.Windows.Forms.ListControl.SelectedValue%2A> 属性绑定到记录窗体输入的表。 你也可以这样做的设计器中而不是在代码中，通过访问控件的<xref:System.Windows.Forms.Control.DataBindings%2A>中的属性**属性**窗口。 在前面的方案中，这是`OrderDetailsTable`，而且列为`"ItemID"`。  
  
    ```vb  
    ListBox1.DataBindings.Add("SelectedValue", OrderDetailsTable, "ItemID")  
    ```  
  
    ```csharp  
    listBox1.DataBindings.Add("SelectedValue", OrderDetailsTable, "ItemID");  
    ```  
  
## <a name="see-also"></a>另请参阅  
 [数据绑定和 Windows 窗体](../../../../docs/framework/winforms/data-binding-and-windows-forms.md)  
 [ListBox 控件概述](../../../../docs/framework/winforms/controls/listbox-control-overview-windows-forms.md)  
 [ComboBox 控件概述](../../../../docs/framework/winforms/controls/combobox-control-overview-windows-forms.md)  
 [CheckedListBox 控件概述](../../../../docs/framework/winforms/controls/checkedlistbox-control-overview-windows-forms.md)  
 [用于列出选项的 Windows 窗体控件](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)
