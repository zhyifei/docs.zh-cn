---
title: 用 BindingSource 组件对 ADO.NET 数据进行排序和筛选
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sorting data
- data sorting [Windows Forms], ADO.NET
- data [Windows Forms], filtering
- BindingSource component [Windows Forms], sorting and filtering data
- filtering [Windows Forms], ADO.NET
- data [Windows Forms], sorting
- ADO.NET [Windows Forms]
ms.assetid: 6c206daf-d706-4602-9dbe-435343052063
ms.openlocfilehash: cf1da3bb94b26449eb72b0e4930b262236487acc
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742977"
---
# <a name="how-to-sort-and-filter-adonet-data-with-the-windows-forms-bindingsource-component"></a>방법: Windows Forms BindingSource 구성 요소를 사용하여 ADO.NET 데이터 정렬 및 필터링
可以通过 <xref:System.Windows.Forms.BindingSource.Sort%2A> 和 <xref:System.Windows.Forms.BindingSource.Filter%2A> 属性公开 <xref:System.Windows.Forms.BindingSource> 控件的排序和筛选功能。 如果基础数据源是 <xref:System.ComponentModel.IBindingList>，则可以应用简单排序，当数据源为 <xref:System.ComponentModel.IBindingListView>时，可以应用筛选和高级排序。 <xref:System.Windows.Forms.BindingSource.Sort%2A> 属性需要标准 ADO.NET 语法：一个字符串，表示数据源中的数据列的名称，后跟 `ASC` 或 `DESC`，以指示列表是按升序排序还是按降序排序。 您可以通过用逗号分隔符分隔每一列来设置高级排序或多列排序。 <xref:System.Windows.Forms.BindingSource.Filter%2A> 属性采用字符串表达式。  
  
> [!NOTE]
> 암호와 같은 중요한 정보를 연결 문자열 내에 저장하면 애플리케이션 보안 문제가 발생할 수 있습니다. 데이터베이스 액세스를 제어할 경우에는 통합 보안이라고도 하는 Windows 인증을 사용하는 방법이 더 안전합니다. 자세한 내용은 [연결 정보 보호](../../data/adonet/protecting-connection-information.md)를 참조하세요.  
  
### <a name="to-filter-data-with-the-bindingsource"></a>用 BindingSource 筛选数据  
  
- 将 <xref:System.Windows.Forms.BindingSource.Filter%2A> 属性设置为所需的 expression。  
  
     在下面的代码示例中，表达式是列名，后跟要用于该列的值。  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#11)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#11)]  
  
### <a name="to-sort-data-with-the-bindingsource"></a>用 BindingSource 对数据进行排序  
  
1. 将 <xref:System.Windows.Forms.BindingSource.Sort%2A> 属性设置为所需的列名称，`ASC` 或 `DESC` 以指示升序或降序顺序。  
  
2. 用逗号分隔多个列。  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#12)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#12)]  
  
## <a name="example"></a>示例  
 下面的代码示例将 Northwind 示例数据库的 Customers 表中的数据加载到 <xref:System.Windows.Forms.DataGridView> 控件中，并对显示的数据进行筛选和排序。  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 若要运行此示例，请将代码粘贴到包含名为 `BindingSource1` 的 <xref:System.Windows.Forms.BindingSource> 的窗体和名为 `dataGridView1`的 <xref:System.Windows.Forms.DataGridView>。 处理窗体的 <xref:System.Windows.Forms.Form.Load> 事件，并在 load 事件处理程序方法中调用 `InitializeSortedFilteredBindingSource`。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.BindingSource.Sort%2A>
- <xref:System.Windows.Forms.BindingSource.Filter%2A>
- [방법: 샘플 데이터베이스 설치](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/8b6y4c7s(v=vs.120))
- [BindingSource 구성 요소](bindingsource-component.md)
