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
ms.openlocfilehash: 3dbd2ccca607869a6f28bc5b3bd1c9f0769db9f5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69950084"
---
# <a name="how-to-view-errors-within-a-dataset-with-the-windows-forms-errorprovider-component"></a>如何：使用 Windows 窗体 ErrorProvider 组件查看数据集中的错误
您可以使用 Windows 窗体<xref:System.Windows.Forms.ErrorProvider>组件来查看数据集或其他数据源中的列错误。 为了使<xref:System.Windows.Forms.ErrorProvider>组件能够在窗体上显示数据错误, 无需直接与控件关联。 绑定到数据源后, 它可以在绑定到同一个数据源的任何控件旁显示错误图标。  
  
> [!NOTE]
> 如果在运行时更改错误提供<xref:System.Windows.Forms.ErrorProvider.DataSource%2A>程序<xref:System.Windows.Forms.ErrorProvider.DataMember%2A>的和属性<xref:System.Windows.Forms.ErrorProvider.BindToDataAndErrors%2A> , 则应使用方法以避免冲突。  
  
### <a name="to-display-data-errors"></a>显示数据错误  
  
1. 将组件绑定到数据表中的特定列。  
  
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
  
2. <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A>将属性设置为窗体。  
  
    ```vb  
    ErrorProvider1.ContainerControl = Me  
    ```  
  
    ```csharp  
    errorProvider1.ContainerControl = this;  
    ```  
  
3. 将当前记录的位置设置为包含列错误的行。  
  
    ```vb  
    DataTable1.Rows(5).SetColumnError("Name", "Bad data in this row.")  
    Me.BindingContext(DataTable1).Position = 5  
    ```  
  
    ```csharp  
    DataTable1.Rows[5].SetColumnError("Name", "Bad data in this row.");  
    this.BindingContext [DataTable1].Position = 5;  
    ```  
  
## <a name="see-also"></a>请参阅

- [ErrorProvider 组件概述](errorprovider-component-overview-windows-forms.md)
- [如何：显示用于通过 Windows 窗体 ErrorProvider 组件进行的窗体验证的错误图标](display-error-icons-for-form-validation-with-wf-errorprovider.md)
