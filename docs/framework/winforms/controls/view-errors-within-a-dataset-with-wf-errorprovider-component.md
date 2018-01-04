---
title: "如何：使用 Windows 窗体 ErrorProvider 组件查看数据集中的错误"
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
- errors [Windows Forms], dataset errors
- error messages [Windows Forms], viewing in datasets
- ErrorProvider component [Windows Forms], dataset errors
ms.assetid: cbae023f-d651-4210-bdea-bcc5f037e321
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 27ef4200996108e378273c5f813106d4f82dacd8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-view-errors-within-a-dataset-with-the-windows-forms-errorprovider-component"></a><span data-ttu-id="7b479-102">如何：使用 Windows 窗体 ErrorProvider 组件查看数据集中的错误</span><span class="sxs-lookup"><span data-stu-id="7b479-102">How to: View Errors Within a DataSet with the Windows Forms ErrorProvider Component</span></span>
<span data-ttu-id="7b479-103">你可以使用 Windows 窗体<xref:System.Windows.Forms.ErrorProvider>组件以便查看的数据集或其他数据源中的列错误。</span><span class="sxs-lookup"><span data-stu-id="7b479-103">You can use the Windows Forms <xref:System.Windows.Forms.ErrorProvider> component to view column errors within a dataset or other data source.</span></span> <span data-ttu-id="7b479-104">有关<xref:System.Windows.Forms.ErrorProvider>组件以在窗体上显示数据错误它不必是直接与控件关联。</span><span class="sxs-lookup"><span data-stu-id="7b479-104">For an <xref:System.Windows.Forms.ErrorProvider> component to display data errors on a form, it does not have to be directly associated with a control.</span></span> <span data-ttu-id="7b479-105">一旦它绑定到数据源，它可以显示错误图标旁边任何绑定到同一数据源的控件。</span><span class="sxs-lookup"><span data-stu-id="7b479-105">Once it is bound to a data source, it can display an error icon next to any control that is bound to the same data source.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7b479-106">如果更改错误提供程序的<xref:System.Windows.Forms.ErrorProvider.DataSource%2A>和<xref:System.Windows.Forms.ErrorProvider.DataMember%2A>属性在运行时，应使用<xref:System.Windows.Forms.ErrorProvider.BindToDataAndErrors%2A>方法，以避免冲突。</span><span class="sxs-lookup"><span data-stu-id="7b479-106">If you change the error provider's <xref:System.Windows.Forms.ErrorProvider.DataSource%2A> and <xref:System.Windows.Forms.ErrorProvider.DataMember%2A> properties at run time, you should use the <xref:System.Windows.Forms.ErrorProvider.BindToDataAndErrors%2A> method to avoid conflicts.</span></span>  
  
### <a name="to-display-data-errors"></a><span data-ttu-id="7b479-107">若要显示数据错误</span><span class="sxs-lookup"><span data-stu-id="7b479-107">To display data errors</span></span>  
  
1.  <span data-ttu-id="7b479-108">将组件绑定到数据表中的特定列。</span><span class="sxs-lookup"><span data-stu-id="7b479-108">Bind the component to a specific column within a data table.</span></span>  
  
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
  
2.  <span data-ttu-id="7b479-109">设置<xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A>到窗体的属性。</span><span class="sxs-lookup"><span data-stu-id="7b479-109">Set the <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> property to the form.</span></span>  
  
    ```vb  
    ErrorProvider1.ContainerControl = Me  
    ```  
  
    ```csharp  
    errorProvider1.ContainerControl = this;  
    ```  
  
3.  <span data-ttu-id="7b479-110">设置为包含列错误的行的当前记录的位置。</span><span class="sxs-lookup"><span data-stu-id="7b479-110">Set the position of the current record to a row that contains a column error.</span></span>  
  
    ```vb  
    DataTable1.Rows(5).SetColumnError("Name", "Bad data in this row.")  
    Me.BindingContext(DataTable1).Position = 5  
    ```  
  
    ```csharp  
    DataTable1.Rows[5].SetColumnError("Name", "Bad data in this row.");  
    this.BindingContext [DataTable1].Position = 5;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="7b479-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="7b479-111">See Also</span></span>  
 [<span data-ttu-id="7b479-112">ErrorProvider 组件概述</span><span class="sxs-lookup"><span data-stu-id="7b479-112">ErrorProvider Component Overview</span></span>](../../../../docs/framework/winforms/controls/errorprovider-component-overview-windows-forms.md)  
 [<span data-ttu-id="7b479-113">如何：使用 Windows 窗体 ErrorProvider 组件显示窗体验证的错误图标</span><span class="sxs-lookup"><span data-stu-id="7b479-113">How to: Display Error Icons for Form Validation with the Windows Forms ErrorProvider Component</span></span>](../../../../docs/framework/winforms/controls/display-error-icons-for-form-validation-with-wf-errorprovider.md)
