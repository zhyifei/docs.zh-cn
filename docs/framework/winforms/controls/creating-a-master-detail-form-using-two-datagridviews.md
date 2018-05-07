---
title: 演练： 创建主 / 从窗体使用两个 Windows 窗体 DataGridView 控件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], master/detail form
- parent-child tables [Windows Forms], displaying on Windows Forms
- master-details lists [Windows Forms], displaying on Windows Forms
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: c5fa29e8-47f7-4691-829b-0e697a691f36
ms.openlocfilehash: 38f7c6197fb3ee79119e41ab9620bc3aa2b21900
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-creating-a-masterdetail-form-using-two-windows-forms-datagridview-controls"></a>演练：使用两个 Windows 窗体 DataGridView 控件创建一个主/从窗体
使用的最常见方案之一<xref:System.Windows.Forms.DataGridView>控件是*主/从*窗体中，在其中显示两个数据库表之间的父/子关系。 在主表中选择行，则会导致要使用的相应的子数据更新的详细信息表。  
  
 使用之间的交互可以轻松实现主/从窗体进行<xref:System.Windows.Forms.DataGridView>控件和<xref:System.Windows.Forms.BindingSource>组件。 在本演练中，你将生成使用两个窗体<xref:System.Windows.Forms.DataGridView>控件和第二个<xref:System.Windows.Forms.BindingSource>组件。 窗体将显示两个相关的 Northwind SQL Server 示例数据库中的表：`Customers`和`Orders`。 完成后，你将拥有显示在 master 数据库中的所有客户的窗体<xref:System.Windows.Forms.DataGridView>和详细信息中所选客户的所有订单<xref:System.Windows.Forms.DataGridView>。  
  
 若要将代码复制本主题中的一个单独的清单，请参阅[如何： 创建主/从窗体使用两个 Windows 窗体 DataGridView 控件](../../../../docs/framework/winforms/controls/create-a-master-detail-form-using-two-datagridviews.md)。  
  
## <a name="prerequisites"></a>系统必备  
 若要完成本演练，你将需要：  
  
-   到 Northwind SQL Server 示例数据库的服务器的访问。  
  
## <a name="creating-the-form"></a>创建窗体  
  
#### <a name="to-create-a-masterdetail-form"></a>若要创建主/从窗体  
  
1.  创建一个类，派生自<xref:System.Windows.Forms.Form>和包含两个<xref:System.Windows.Forms.DataGridView>控件和第二个<xref:System.Windows.Forms.BindingSource>组件。 下面的代码提供了基本的窗体初始化，并且包含`Main`方法。 如果你使用 Visual Studio 设计器创建你的窗体，则可以使用设计器生成的代码，而不是此代码中，但一定要使用的变量的声明中显示的名称。  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#01](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#01](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#02](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#02](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#02)]  
  
2.  实现用于处理连接到数据库的详细信息窗体的类定义中的方法。 此示例使用`GetData`填充的方法<xref:System.Data.DataSet>对象，将添加<xref:System.Data.DataRelation>对象的数据集和绑定到<xref:System.Windows.Forms.BindingSource>组件。 请确保将 `connectionString` 变量设置为适合数据库的值。  
  
    > [!IMPORTANT]
    >  将敏感信息（如密码）存储在连接字符串中可能会影响应用程序的安全性。 若要控制对数据库的访问，一种较为安全的方法是使用 Windows 身份验证（也称为集成安全性）。 有关详细信息，请参阅[保护连接信息](../../../../docs/framework/data/adonet/protecting-connection-information.md)。  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#20)]  
  
3.  实现你的窗体的处理<xref:System.Windows.Forms.Form.Load>将绑定的事件<xref:System.Windows.Forms.DataGridView>控件添加到<xref:System.Windows.Forms.BindingSource>组件，并调用`GetData`方法。 下面的示例包含调整大小的代码<xref:System.Windows.Forms.DataGridView>列调整为合适显示的数据。  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#10)]  
  
## <a name="testing-the-application"></a>测试应用程序  
 你现在可以测试窗体，以确保其行为与预期相同。  
  
#### <a name="to-test-the-form"></a>若要测试窗体  
  
-   编译并运行该应用程序。  
  
     您将看到两个<xref:System.Windows.Forms.DataGridView>控件，相互。 在最前面都是从 Northwind 客户`Customers`表，并且在底部`Orders`对应于所选客户。 在上面选择不同的行时<xref:System.Windows.Forms.DataGridView>，较低的内容<xref:System.Windows.Forms.DataGridView>相应地更改。  
  
## <a name="next-steps"></a>后续步骤  
 此应用程序提供一个基本的了解<xref:System.Windows.Forms.DataGridView>控件的功能。 你可以自定义的外观和行为<xref:System.Windows.Forms.DataGridView>控制以下几种方式：  
  
-   更改边框和标头的样式。 有关详细信息，请参阅[如何： 更改边框和网格线在 Windows 窗体 DataGridView 控件中的样式](../../../../docs/framework/winforms/controls/change-the-border-and-gridline-styles-in-the-datagrid.md)。  
  
-   允许或限制用户输入到<xref:System.Windows.Forms.DataGridView>控件。 有关详细信息，请参阅[如何： 防止添加和删除行在 Windows 窗体 DataGridView 控件中](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md)，和[如何： 在 Windows 窗体 DataGridView 控件中使列成为只读](../../../../docs/framework/winforms/controls/how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md)。  
  
-   验证用户输入到<xref:System.Windows.Forms.DataGridView>控件。 有关详细信息，请参阅[演练： 验证 Windows 窗体 DataGridView 控件中的数据](../../../../docs/framework/winforms/controls/walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)。  
  
-   处理非常大的数据集使用的虚拟模式。 有关详细信息，请参阅[演练： 在 Windows 窗体 DataGridView 控件中实现虚拟模式](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)。  
  
-   自定义单元格的外观。 有关详细信息，请参阅[如何： 自定义 Windows 窗体 DataGridView 控件中的单元外观](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md)和[如何： 设置 Windows 窗体 DataGridView 控件的默认单元格样式](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.BindingSource>  
 [在 Windows 窗体 DataGridView 控件中显示数据](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 [如何：使用两个 Windows 窗体 DataGridView 控件创建主窗体/详细信息窗体](../../../../docs/framework/winforms/controls/create-a-master-detail-form-using-two-datagridviews.md)  
 [保护连接信息](../../../../docs/framework/data/adonet/protecting-connection-information.md)
