---
title: 如何：将 Windows 窗体 ComboBox 控件或 ListBox 控件绑定到数据
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
ms.openlocfilehash: f361526c44f8fbb9ab282fe15ae109b67e8f01dd
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69922744"
---
# <a name="how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data"></a>如何：将 Windows 窗体 ComboBox 控件或 ListBox 控件绑定到数据
您可以将<xref:System.Windows.Forms.ComboBox>和<xref:System.Windows.Forms.ListBox>绑定到数据来执行任务, 例如, 在数据库中浏览数据、输入新数据或编辑现有数据。  
  
### <a name="to-bind-a-combobox-or-listbox-control"></a>绑定 ComboBox 或 ListBox 控件  
  
1. `DataSource`将属性设置为数据源对象。 可能的<xref:System.Windows.Forms.BindingSource>数据源包括绑定到数据、数据表、数据视图、数据集、数据视图管理器、数组或<xref:System.Collections.IList>实现接口的任何类。 有关详细信息, 请参阅[Windows 窗体支持的数据源](../data-sources-supported-by-windows-forms.md)。  
  
2. 如果要绑定到表, 请将`DisplayMember`属性设置为数据源中的列的名称。  
  
     \- 或 -  
  
     如果要绑定到<xref:System.Collections.IList>, 请在列表中将显示成员设置为该类型的公共属性。  
  
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
    > 如果绑定到不实现<xref:System.ComponentModel.IBindingList>接口的数据源 (例如<xref:System.Collections.ArrayList>), 则在更新数据源时, 将不会更新绑定控件的数据。 例如, 如果您有一个绑定到<xref:System.Collections.ArrayList>的组合框, 并且数据已添加<xref:System.Collections.ArrayList>到, 则这些新项将不会出现在组合框中。 但是, 您可以通过<xref:System.Windows.Forms.BindingManagerBase.SuspendBinding%2A> <xref:System.Windows.Forms.BindingContext>在控件绑定到的类的实例上调用<xref:System.Windows.Forms.BindingManagerBase.ResumeBinding%2A>和方法来强制更新组合框。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- [Windows 窗体数据绑定](../windows-forms-data-binding.md)
- [数据绑定和 Windows 窗体](../data-binding-and-windows-forms.md)
- [用于列出选项的 Windows 窗体控件](windows-forms-controls-used-to-list-options.md)
