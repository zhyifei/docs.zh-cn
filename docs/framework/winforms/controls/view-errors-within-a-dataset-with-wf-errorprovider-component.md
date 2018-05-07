---
title: 如何：使用 Windows 窗体 ErrorProvider 组件查看数据集中的错误
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- errors [Windows Forms], dataset errors
- error messages [Windows Forms], viewing in datasets
- ErrorProvider component [Windows Forms], dataset errors
ms.assetid: cbae023f-d651-4210-bdea-bcc5f037e321
ms.openlocfilehash: f00d874f2a4afcea3498a64fe946a93c83eb7b9e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-view-errors-within-a-dataset-with-the-windows-forms-errorprovider-component"></a>如何：使用 Windows 窗体 ErrorProvider 组件查看数据集中的错误
你可以使用 Windows 窗体<xref:System.Windows.Forms.ErrorProvider>组件以便查看的数据集或其他数据源中的列错误。 有关<xref:System.Windows.Forms.ErrorProvider>组件以在窗体上显示数据错误它不必是直接与控件关联。 一旦它绑定到数据源，它可以显示错误图标旁边任何绑定到同一数据源的控件。  
  
> [!NOTE]
>  如果更改错误提供程序的<xref:System.Windows.Forms.ErrorProvider.DataSource%2A>和<xref:System.Windows.Forms.ErrorProvider.DataMember%2A>属性在运行时，应使用<xref:System.Windows.Forms.ErrorProvider.BindToDataAndErrors%2A>方法，以避免冲突。  
  
### <a name="to-display-data-errors"></a>若要显示数据错误  
  
1.  将组件绑定到数据表中的特定列。  
  
    ```vb  
    ' Assumes existence of DataSet1, DataTable1  
    TextBox1.DataBindings.Add("Text", DataSet1, "Customers.Name")  
    ErrorProvider1.DataSource = DataSet1  
    ErrorProvider1.DataMember = "Customers"  
    ```  
  
    ```csharp  
    // Assumes existence of DataSet1, DataTable1  
    textBox1.DataBindings.Add("Text", DataSet1, "Customers.Name");  
    errorProvider1.DataSource = DataSet1;  
    errorProvider1.DataMember = "Customers";  
    ```  
  
2.  设置<xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A>到窗体的属性。  
  
    ```vb  
    ErrorProvider1.ContainerControl = Me  
    ```  
  
    ```csharp  
    errorProvider1.ContainerControl = this;  
    ```  
  
3.  设置为包含列错误的行的当前记录的位置。  
  
    ```vb  
    DataTable1.Rows(5).SetColumnError("Name", "Bad data in this row.")  
    Me.BindingContext(DataTable1).Position = 5  
    ```  
  
    ```csharp  
    DataTable1.Rows[5].SetColumnError("Name", "Bad data in this row.");  
    this.BindingContext [DataTable1].Position = 5;  
    ```  
  
## <a name="see-also"></a>请参阅  
 [ErrorProvider 组件概述](../../../../docs/framework/winforms/controls/errorprovider-component-overview-windows-forms.md)  
 [如何：使用 Windows 窗体 ErrorProvider 组件显示窗体验证的错误图标](../../../../docs/framework/winforms/controls/display-error-icons-for-form-validation-with-wf-errorprovider.md)
