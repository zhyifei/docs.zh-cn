---
title: "演练：使用两个 Windows 窗体 DataGridView 控件创建一个主/从窗体 | Microsoft Docs"
ms.custom: ""
ms.date: "02/15/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "DataGridView 控件 [Windows 窗体], 主/详细信息窗体"
  - "主-详细信息列表, 在 Windows 窗体上显示"
  - "父-子表, 在 Windows 窗体上显示"
  - "演练 [Windows 窗体], DataGridView 控件"
ms.assetid: c5fa29e8-47f7-4691-829b-0e697a691f36
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 演练：使用两个 Windows 窗体 DataGridView 控件创建一个主/从窗体
使用 <xref:System.Windows.Forms.DataGridView> 控件的一种最常见方案是“主\/详细信息”窗体，这样的窗体可显示两个数据库表之间的父\/子关系。  如果选择主表中的行，将导致以相应的子数据来更新详细信息表。  
  
 主\/详细信息窗体很容易实现，这需要使用 <xref:System.Windows.Forms.DataGridView> 控件和 <xref:System.Windows.Forms.BindingSource> 组件之间的交互。  在本演练中，将使用两个 <xref:System.Windows.Forms.DataGridView> 控件和两个 <xref:System.Windows.Forms.BindingSource> 组件来生成窗体。  窗体将显示 Northwind SQL Server 示例数据库中的两个相关表：`Customers` 和 `Orders`。  完成后，将得到一个窗体，它可以在主 <xref:System.Windows.Forms.DataGridView> 中显示数据库中的所有客户，并在详细信息 <xref:System.Windows.Forms.DataGridView> 中显示所选客户的所有订单。  
  
 若要以单个列表的形式复制本主题中的代码，请参见 [如何：使用两个 Windows 窗体 DataGridView 控件创建一个主\/从窗体](../../../../docs/framework/winforms/controls/create-a-master-detail-form-using-two-datagrids.md)。  
  
## 系统必备  
 若要完成本演练，您需要：  
  
-   对 Northwind SQL Server 示例数据库所在的服务器的访问权限。  
  
## 创建窗体  
  
#### 创建主\/详细信息窗体  
  
1.  创建一个从 <xref:System.Windows.Forms.Form> 派生的类，该类包含两个 <xref:System.Windows.Forms.DataGridView> 控件和两个 <xref:System.Windows.Forms.BindingSource> 组件。  下面的代码提供了基本的窗体初始化，并包含一个 `Main` 方法。  如果使用 [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] 设计器来创建窗体，则可以使用设计器生成的代码而不是这里的代码，但一定要使用这里的变量声明中显示的名称。  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#01](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#01](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#02](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#02](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#02)]  
  
2.  在窗体的类定义中实现一个方法，用于处理有关与数据库的连接的详细信息。  此示例使用 `GetData` 方法来填充 <xref:System.Data.DataSet> 对象，并向数据集添加 <xref:System.Data.DataRelation> 对象，还要绑定 <xref:System.Windows.Forms.BindingSource> 组件。  务必将 `connectionString` 变量设置为适用于您的数据库的值。  
  
    > [!IMPORTANT]
    >  将敏感信息（如密码）存储在连接字符串中可能会影响您的应用程序的安全性。  若要控制对数据库的访问，一种较为安全的方法是使用 Windows 身份验证（也称为集成安全性）。  有关更多信息，请参见[保护连接信息](../../../../docs/framework/data/adonet/protecting-connection-information.md)。  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#20)]  
  
3.  为窗体的 <xref:System.Windows.Forms.Form.Load> 事件实现一个处理程序，该事件将 <xref:System.Windows.Forms.DataGridView> 控件绑定到 <xref:System.Windows.Forms.BindingSource> 组件，并调用 `GetData` 方法。  下面的示例所包括的代码可以调整 <xref:System.Windows.Forms.DataGridView> 列的大小，以容纳所显示的数据。  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#10)]  
  
## 测试应用程序  
 现在可以测试窗体，以确保其行为与预期相同。  
  
#### 测试窗体  
  
-   编译并运行应用程序。  
  
     您将看到两个 <xref:System.Windows.Forms.DataGridView> 控件，一个在另一个的上面。  上面一个是来自 Northwind `Customers` 表的客户，下面一个是与所选客户对应的 `Orders`。  在上面的 <xref:System.Windows.Forms.DataGridView> 中选择不同行时，下面的 <xref:System.Windows.Forms.DataGridView> 的内容将相应地发生更改。  
  
## 后续步骤  
 此应用程序使您对 <xref:System.Windows.Forms.DataGridView> 控件的功能有一个基本了解。  您可以通过以下几种方法来自定义 <xref:System.Windows.Forms.DataGridView> 控件的外观和行为：  
  
-   更改边框和标题样式。  有关更多信息，请参见 [如何：更改 Windows 窗体 DataGridView 控件中的边框和网格线的样式](../../../../docs/framework/winforms/controls/change-the-border-and-gridline-styles-in-the-datagrid.md)。  
  
-   允许或限制用户向 <xref:System.Windows.Forms.DataGridView> 控件中输入数据。  有关更多信息，请参见[如何：防止在 Windows 窗体 DataGridView 控件中添加和删除行](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md)和[如何：使 Windows 窗体 DataGridView 控件中的列只读](../../../../docs/framework/winforms/controls/how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md)。  
  
-   对用户在 <xref:System.Windows.Forms.DataGridView> 控件中输入的数据进行验证。  有关更多信息，请参见 [演练：验证 Windows 窗体 DataGridView 控件中的数据](../../../../docs/framework/winforms/controls/walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)。  
  
-   使用虚拟模式处理特大数据集。  有关更多信息，请参见 [演练：在 Windows 窗体 DataGridView 控件中实现虚拟模式](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)。  
  
-   自定义单元格的外观。  有关更多信息，请参见 [如何：自定义 Windows 窗体 DataGridView 控件中单元格的外观](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md) 和 [如何：设置 Windows 窗体 DataGridView 控件的默认单元格样式](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)。  
  
## 请参阅  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.BindingSource>   
 [在 Windows 窗体 DataGridView 控件中显示数据](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)   
 [如何：使用两个 Windows 窗体 DataGridView 控件创建一个主\/从窗体](../../../../docs/framework/winforms/controls/create-a-master-detail-form-using-two-datagrids.md)   
 [保护连接信息](../../../../docs/framework/data/adonet/protecting-connection-information.md)