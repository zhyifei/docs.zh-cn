---
title: 将 ComboBox 或 ListBox 控件绑定到数据
ms.date: 03/30/2017
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
ms.openlocfilehash: 99d9b53b32d6faae888b134d4ed486980c05a75b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742030"
---
# <a name="how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data"></a>방법: 데이터에 Windows Forms ComboBox 또는 ListBox 컨트롤 바인딩
您可以将 <xref:System.Windows.Forms.ComboBox> 和 <xref:System.Windows.Forms.ListBox> 绑定到数据，以执行诸如浏览数据库中的数据、输入新数据或编辑现有数据等任务。  
  
### <a name="to-bind-a-combobox-or-listbox-control"></a>绑定 ComboBox 或 ListBox 控件  
  
1. 将 `DataSource` 属性设置为数据源对象。 可能的数据源包括绑定到数据、数据表、数据视图、数据集、数据视图管理器、数组或实现 <xref:System.Collections.IList> 接口的任何类的 <xref:System.Windows.Forms.BindingSource>。 有关详细信息，请参阅[Windows 窗体支持的数据源](../data-sources-supported-by-windows-forms.md)。  
  
2. 如果要绑定到表，请将 `DisplayMember` 属性设置为数据源中的列的名称。  
  
     \- 또는 -  
  
     如果要绑定到 <xref:System.Collections.IList>，请在列表中将显示成员设置为该类型的公共属性。  
  
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
    > 如果绑定到不实现 <xref:System.ComponentModel.IBindingList> 接口的数据源（如 <xref:System.Collections.ArrayList>），则在更新数据源时，将不会更新绑定控件的数据。 例如，如果将组合框绑定到 <xref:System.Collections.ArrayList> 并将数据添加到 <xref:System.Collections.ArrayList>中，则这些新项将不会出现在组合框中。 但是，你可以通过调用 <xref:System.Windows.Forms.BindingManagerBase.SuspendBinding%2A>，并 <xref:System.Windows.Forms.BindingManagerBase.ResumeBinding%2A> 方法在控件所绑定到的 <xref:System.Windows.Forms.BindingContext> 类的实例上，来强制更新组合框。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- [Windows Forms 데이터 바인딩](../windows-forms-data-binding.md)
- [데이터 바인딩 및 Windows Forms](../data-binding-and-windows-forms.md)
- [옵션 목록 표시에 사용된 Windows Forms 컨트롤](windows-forms-controls-used-to-list-options.md)
