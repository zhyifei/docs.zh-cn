---
title: "如何：将 Windows 窗体 ComboBox 控件或 ListBox 控件绑定到数据"
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
- data [Windows Forms], binding to controls
- list boxes [Windows Forms], data binding
- ComboBox control [Windows Forms], data binding
- data binding [Windows Forms], combo boxes
- ListBox control [Windows Forms], data binding
- combo boxes [Windows Forms], data binding
- bound controls [Windows Forms], combo boxes
- Windows Forms controls, data binding
- data-bound controls [Windows Forms], Windows Forms
ms.assetid: dfd7f081-8bea-4a41-86a3-86a1934828ef
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6193e4cc86a470f046c220dc21150e0fc0bf792a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data"></a>如何：将 Windows 窗体 ComboBox 控件或 ListBox 控件绑定到数据
你可以将绑定<xref:System.Windows.Forms.ComboBox>和<xref:System.Windows.Forms.ListBox>到数据以执行任务，例如浏览数据库中的数据，输入新数据，或编辑现有数据。  
  
### <a name="to-bind-a-combobox-or-listbox-control"></a>将 ComboBox 或 ListBox 控件  
  
1.  设置`DataSource`绑定到数据源对象的属性。 可能的数据源包括<xref:System.Windows.Forms.BindingSource>绑定到数据、 数据表、 数据视图、 数据集，数据查看管理器、 数组、 或的任何类都实现<xref:System.Collections.IList>接口。 有关详细信息，请参阅[支持 Windows 窗体的数据源](../../../../docs/framework/winforms/data-sources-supported-by-windows-forms.md)。  
  
2.  如果你正在绑定到表，请设置`DisplayMember`为数据源中的列的名称的属性。  
  
     \- 或 -  
  
     如果你正在绑定到<xref:System.Collections.IList>，将显示成员设置为列表中的类型的公共属性。  
  
    ```vb  
    Private Sub BindComboBox()  
      ComboBox1.DataSource = DataSet1.Tables("Suppliers")  
      ComboBox1.DisplayMember = "ProductName"  
    End Sub  
    ```  
  
    ```csharp  
    private void BindComboBox()  
    {  
      comboBox1.DataSource = dataSet1.Tables["Suppliers"];  
      comboBox1.DisplayMember = "ProductName";  
    }  
    ```  
  
    > [!NOTE]
    >  如果绑定到数据源不实现<xref:System.ComponentModel.IBindingList>接口，如<xref:System.Collections.ArrayList>，更新数据源时，将不会更新绑定的控件的数据。 例如，如果你有一个组合框绑定到<xref:System.Collections.ArrayList>和数据添加到<xref:System.Collections.ArrayList>，这些新项将不会出现在组合框中。 不过，你可以强制组合框，以通过调用更新<xref:System.Windows.Forms.BindingManagerBase.SuspendBinding%2A>和<xref:System.Windows.Forms.BindingManagerBase.ResumeBinding%2A>的实例上的方法<xref:System.Windows.Forms.BindingContext>控件所绑定到类。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.Forms.ComboBox>  
 <xref:System.Windows.Forms.ListBox>  
 [Windows 窗体数据绑定](../../../../docs/framework/winforms/windows-forms-data-binding.md)  
 [数据绑定和 Windows 窗体](../../../../docs/framework/winforms/data-binding-and-windows-forms.md)  
 [用于列出选项的 Windows 窗体控件](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)
