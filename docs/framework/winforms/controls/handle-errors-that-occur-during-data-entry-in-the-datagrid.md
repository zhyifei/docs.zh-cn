---
title: 处理 DataGridView 控件中的数据输入过程中出现的错误
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- error handling [Windows Forms], dataGridView control
- data grids [Windows Forms], error handling
- DataGridView control [Windows Forms], error handling
- data entry [Windows Forms], error handling
- error handling [Windows Forms], data entry
ms.assetid: 9004e72f-fdec-4264-a37d-2c99764efc13
ms.openlocfilehash: 03a13957c80b0ab62afb11efc57cf31e059e5942
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745615"
---
# <a name="how-to-handle-errors-that-occur-during-data-entry-in-the-windows-forms-datagridview-control"></a>如何：处理在 Windows 窗体 DataGridView 控件中输入数据时发生的错误
下面的代码示例演示如何使用 <xref:System.Windows.Forms.DataGridView> 控件将数据输入错误报告给用户。  
  
 有关此代码示例的完整说明，请参阅[演练：处理 Windows 窗体 DataGridView 控件中的数据输入期间发生的错误](handling-errors-that-occur-during-data-entry-in-the-datagrid.md)。  
  
## <a name="example"></a>示例  
 [!code-csharp[System.Windows.Forms.DataGridView.DataError#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridView.DataError#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#00)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
- 引用 System、System.Data、System.Windows.Forms 和 System.XML 程序集。  
  
## <a name="net-framework-security"></a>.NET Framework 安全性  
 将敏感信息（如密码）存储在连接字符串中可能会影响应用程序的安全性。 若要控制对数据库的访问，一种较为安全的方法是使用 Windows 身份验证（也称为集成安全性）。 有关详细信息，请参阅[保护连接信息](../../data/adonet/protecting-connection-information.md)。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [演练：处理在 Windows 窗体 DataGridView 控件有数据输入时发生的错误](handling-errors-that-occur-during-data-entry-in-the-datagrid.md)
- [Windows 窗体 DataGridView 控件中的数据输入](data-entry-in-the-windows-forms-datagridview-control.md)
- [演练：在 Windows 窗体 DataGridView 控件中验证数据](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)
- [保护连接信息](../../data/adonet/protecting-connection-information.md)
