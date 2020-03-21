---
title: 将数据绑定到数据网格视图控件
ms.date: 02/08/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [Windows Forms], grids
- data binding [Windows Forms], DataGridView control
- DataGridView control [Windows Forms], data binding
ms.assetid: 1660f69c-5711-45d2-abc1-e25bc6779124
ms.openlocfilehash: 643dcd37cd1bb3f8b5938fedff66c67cd68278ff
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182273"
---
# <a name="how-to-bind-data-to-the-windows-forms-datagridview-control"></a>如何：将数据绑定到 Windows 窗体数据网格视图控件

该<xref:System.Windows.Forms.DataGridView>控件支持标准 Windows 窗体数据绑定模型，因此它可以绑定到各种数据源。 通常，您将绑定到管理<xref:System.Windows.Forms.BindingSource>与数据源交互的 。 可以是<xref:System.Windows.Forms.BindingSource>任何 Windows 窗体数据源，这为您提供了在选择或修改数据位置时的巨大灵活性。 有关<xref:System.Windows.Forms.DataGridView>控件支持的数据源的详细信息，请参阅[DataGridView 控件概述](datagridview-control-overview-windows-forms.md)。  

Visual Studio 广泛支持与 DataGridView 控件绑定的数据。 有关详细信息，请参阅[：使用设计器将数据绑定到 Windows 窗体 DataGridView 控件](bind-data-to-the-datagrid-using-the-designer.md)。  

要将 DataGridView 控件连接到数据：

1. 实现一种方法来处理检索数据的详细信息。 以下代码示例实现一个`GetData`方法，该方法初始化<xref:System.Data.SqlClient.SqlDataAdapter>了 ， 并使用它来<xref:System.Data.DataTable>填充 。 然后，它将 绑定<xref:System.Data.DataTable>到<xref:System.Windows.Forms.BindingSource>。

2. 在窗体<xref:System.Windows.Forms.Form.Load>的事件处理程序中，将<xref:System.Windows.Forms.DataGridView>控件绑定到 ，<xref:System.Windows.Forms.BindingSource>并调用`GetData`方法以检索数据。  

## <a name="example"></a>示例

此完整代码示例从数据库中检索数据以在 Windows 窗体中填充 DataGridView 控件。 该窗体还具有重新加载数据和向数据库提交更改的按钮。  

此示例需要：

- 访问北风 SQL Server 示例数据库。 有关安装北风示例数据库的详细信息，请参阅[获取ADO.NET代码示例的示例数据库](../../data/adonet/sql/linq/downloading-sample-databases.md)。

- 对系统、系统.Windows.窗体、系统、数据和系统.Xml 程序集的引用。  

要生成和运行此示例，请将代码粘贴到新 Windows 窗体项目中的*Form1*代码文件中。 有关从 C# 或 Visual Basic 命令行生成的信息，请参阅[使用 csc.exe 的命令行构建](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)或[命令行中的生成](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)。  
  
使用北`connectionString`风 SQL Server 示例数据库连接的值填充示例中的变量。 Windows 身份验证也称为集成安全，与在连接字符串中存储密码相比，是连接到数据库的更安全方法。 有关连接安全性的详细信息，请参阅[保护连接信息](../../data/adonet/protecting-connection-information.md)。  

[!code-csharp[System.Windows.Forms.DataGridViewBoundEditable](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/CS/datagridviewboundeditable.cs)]
[!code-vb[System.Windows.Forms.DataGridViewBoundEditable](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/VB/datagridviewboundeditable.vb)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.BindingSource>
- [在 Windows 窗体数据网格视图控件中显示数据](displaying-data-in-the-windows-forms-datagridview-control.md)
- [保护连接信息](../../data/adonet/protecting-connection-information.md)
