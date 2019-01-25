---
title: 如何：在一个数据集中使用 Windows 窗体 ErrorProvider 组件查看错误
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- errors [Windows Forms], dataset errors
- error messages [Windows Forms], viewing in datasets
- ErrorProvider component [Windows Forms], dataset errors
ms.assetid: cbae023f-d651-4210-bdea-bcc5f037e321
ms.openlocfilehash: 48f333fbae816748813b370bccc559cea2714fa5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54694043"
---
# <a name="how-to-view-errors-within-a-dataset-with-the-windows-forms-errorprovider-component"></a>如何：在一个数据集中使用 Windows 窗体 ErrorProvider 组件查看错误
可以使用 Windows 窗体<xref:System.Windows.Forms.ErrorProvider>若要查看的数据集或其他数据源中的列错误的组件。 有关<xref:System.Windows.Forms.ErrorProvider>组件，在窗体上显示数据错误它不一定要直接与控件相关联。 一旦它绑定到数据源，它可以显示绑定到相同的数据源的任何控件旁的错误图标。  
  
> [!NOTE]
>  如果更改错误提供程序<xref:System.Windows.Forms.ErrorProvider.DataSource%2A>并<xref:System.Windows.Forms.ErrorProvider.DataMember%2A>在运行时属性，则应使用<xref:System.Windows.Forms.ErrorProvider.BindToDataAndErrors%2A>方法以避免冲突。  
  
### <a name="to-display-data-errors"></a>若要显示的数据错误  
  
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
- [ErrorProvider 组件概述](../../../../docs/framework/winforms/controls/errorprovider-component-overview-windows-forms.md)
- [如何：对于表格验证使用 Windows 窗体 ErrorProvider 组件显示错误图标](../../../../docs/framework/winforms/controls/display-error-icons-for-form-validation-with-wf-errorprovider.md)
