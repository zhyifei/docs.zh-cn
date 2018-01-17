---
title: "如何：将 Windows 窗体 DataGrid 控件绑定到数据源"
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
- cpp
helpviewer_keywords:
- datasets [Windows Forms], binding to DataGrid control
- data binding [Windows Forms], DataGrid control
- DataGrid control [Windows Forms], data binding
- bound controls [Windows Forms], DataGrid control
- Windows Forms controls, data binding
- bound controls [Windows Forms]
- data-bound controls [Windows Forms], DataGrid
ms.assetid: 128cdb07-dfd3-4d60-9d6a-902847667c36
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c136aca0eda9ea906ad8bf6853a263adf6130609
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-bind-the-windows-forms-datagrid-control-to-a-data-source"></a>如何：将 Windows 窗体 DataGrid 控件绑定到数据源
> [!NOTE]
>  <xref:System.Windows.Forms.DataGridView> 控件取代了 <xref:System.Windows.Forms.DataGrid> 控件并添加了功能；但是，可以选择保留 <xref:System.Windows.Forms.DataGrid> 控件以实现向后兼容并供将来使用。 有关详细信息，请参阅 [Windows 窗体 DataGridView 控件与 DataGrid 控件之间的区别](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)。  
  
 Windows 窗体<xref:System.Windows.Forms.DataGrid>控件专门用于显示数据源中的信息。 你在运行时将控件绑定通过调用<xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>方法。 尽管可以显示来自各种数据源数据，最典型的源是数据集和数据的视图。  
  
### <a name="to-data-bind-the-datagrid-control-programmatically"></a>若要将数据绑定的 DataGrid 控件以编程方式  
  
1.  编写代码以填充数据集。  
  
     如果数据源的数据集或数据视图基于数据集表，请将代码添加到窗体来填充数据集。  
  
     你使用的确切代码取决于数据集从何处获取数据。 如果要直接从数据库填充数据集，则通常会调用`Fill`数据适配器，如以下示例中，它填充数据集调用中所示方法`DsCategories1`:  
  
    ```vb  
    sqlDataAdapter1.Fill(DsCategories1)  
    ```  
  
    ```csharp  
    sqlDataAdapter1.Fill(DsCategories1);  
    ```  
  
    ```cpp  
    sqlDataAdapter1->Fill(dsCategories1);  
    ```  
  
     如果从 XML Web 服务填充的数据集，你通常在你的代码中创建的服务实例，然后调用其方法来返回数据集之一。 然后，你将从 XML Web 服务的数据集合并到你本地的数据集中。 下面的示例演示如何创建名为的 XML Web 服务的实例`CategoriesService`，调用其`GetCategories`方法，并合并到本地数据集生成的数据集调用`DsCategories1`:  
  
    ```vb  
    Dim ws As New MyProject.localhost.CategoriesService()  
    ws.Credentials = System.Net.CredentialCache.DefaultCredentials  
    DsCategories1.Merge(ws.GetCategories())  
    ```  
  
    ```csharp  
    MyProject.localhost.CategoriesService ws = new MyProject.localhost.CategoriesService();  
    ws.Credentials = System.Net.CredentialCache.DefaultCredentials;  
    DsCategories1.Merge(ws.GetCategories());  
    ```  
  
    ```cpp  
    MyProject::localhost::CategoriesService^ ws =   
       new MyProject::localhost::CategoriesService();  
    ws->Credentials = System::Net::CredentialCache::DefaultCredentials;  
    dsCategories1->Merge(ws->GetCategories());  
    ```  
  
2.  调用<xref:System.Windows.Forms.DataGrid>控件的<xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>方法，将其传递数据源和数据成员。 如果你不需要显式传递的数据成员，则传递一个空字符串。  
  
    > [!NOTE]
    >  如果你第一次绑定网格，则可以设置控件的<xref:System.Windows.Forms.DataGrid.DataSource%2A>和<xref:System.Windows.Forms.DataGrid.DataMember%2A>属性。 但是，在设置后无法重置这些属性。 因此，建议您始终使用<xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>方法。  
  
     下面的示例演示如何你可以以编程方式将绑定到数据集调用中的 Customers 表`DsCustomers1`:  
  
    ```vb  
    DataGrid1.SetDataBinding(DsCustomers1, "Customers")  
    ```  
  
    ```csharp  
    DataGrid1.SetDataBinding(DsCustomers1, "Customers");  
    ```  
  
    ```cpp  
    dataGrid1->SetDataBinding(dsCustomers1, "Customers");  
    ```  
  
     如果客户表中数据集的唯一表，你无法或者将绑定网格这种方式：  
  
    ```vb  
    DataGrid1.SetDataBinding(DsCustomers1, "")  
    ```  
  
    ```csharp  
    DataGrid1.SetDataBinding(DsCustomers1, "");  
    ```  
  
    ```cpp  
    dataGrid1->SetDataBinding(dsCustomers1, "");  
    ```  
  
3.  （可选）将适当的表样式和列样式添加到网格中。 如果不有任何表样式，你将看到表，但其格式设置很少，且所有列均可见。  
  
## <a name="see-also"></a>请参阅  
 [DataGrid 控件概述](../../../../docs/framework/winforms/controls/datagrid-control-overview-windows-forms.md)  
 [如何：向 Windows 窗体 DataGrid 控件添加表和列](../../../../docs/framework/winforms/controls/how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)  
 [DataGrid 控件](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)  
 [Windows 窗体数据绑定](../../../../docs/framework/winforms/windows-forms-data-binding.md)
