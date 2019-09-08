---
title: 数据绑定和 LINQ to DataSet
ms.date: 03/30/2017
ms.assetid: 310bff4a-32dd-4f20-a271-6dbd82912631
ms.openlocfilehash: 563d57249daa3aa720da1d9654866727f770afb3
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786702"
---
# <a name="data-binding-and-linq-to-dataset"></a>数据绑定和 LINQ to DataSet
*数据绑定*是在应用程序 UI 和业务逻辑之间建立连接的过程。 如果绑定具有正确的设置，并且数据提供适当的通知，则在数据更改其值时，绑定到该数据的元素会自动反映更改。 <xref:System.Data.DataSet> 是数据驻留在内存中的表示形式，不管包含的数据来自什么数据源，它都可以提供一致的关系编程模型。 使用 ADO.NET 2.0 <xref:System.Data.DataView> 可以对存储在 <xref:System.Data.DataTable> 中的数据进行排序和筛选。 数据绑定应用程序中经常会使用此功能。 通过使用 <xref:System.Data.DataView>，您可以使用不同的排序顺序公开表中的数据，并且可以按行状态或基于筛选器表达式来筛选数据。 有关<xref:System.Data.DataView>对象的详细信息，请参阅[dataview](./dataset-datatable-dataview/dataviews.md)。  
  
 LINQ to DataSet 允许开发人员通过使用<xref:System.Data.DataSet> [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)]创建复杂、功能强大的查询。 但是，LINQ to DataSet 查询返回<xref:System.Data.DataRow>对象的枚举，这在绑定方案中是不容易使用的。 为了更轻松地进行绑定，可以<xref:System.Data.DataView>从 LINQ to DataSet 查询创建。 这<xref:System.Data.DataView>将使用查询中指定的筛选和排序，但更适合用于数据绑定。 LINQ to DataSet 通过提供[!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]基于表达式的<xref:System.Data.DataView>筛选和排序来扩展的功能，这允许执行比基于字符串的筛选和排序更复杂、功能更强大的筛选和排序操作。  
  
 请注意，<xref:System.Data.DataView> 表示查询本身，而不是处于查询前面的视图。 <xref:System.Data.DataView> 绑定到 UI 控件（如 <xref:System.Windows.Forms.DataGrid> 或 <xref:System.Windows.Forms.DataGridView>），提供简单的数据绑定模型。 也可以从 <xref:System.Data.DataView> 创建 <xref:System.Data.DataTable>，从而提供该表的默认视图。  
  
## <a name="in-this-section"></a>本节内容  
 [创建 DataView 对象](creating-a-dataview-object-linq-to-dataset.md)  
 提供有关创建 <xref:System.Data.DataView> 的信息。  
  
 [使用 DataView 进行筛选](filtering-with-dataview-linq-to-dataset.md)  
 说明如何使用 <xref:System.Data.DataView> 进行筛选。  
  
 [使用 DataView 进行排序](sorting-with-dataview-linq-to-dataset.md)  
 说明如何使用 <xref:System.Data.DataView> 进行排序。  
  
 [在 DataView 中查询 DataRowView 集合](querying-the-datarowview-collection-in-a-dataview.md)  
 提供有关查询由 <xref:System.Data.DataRowView> 公开的 <xref:System.Data.DataView> 集合的信息。  
  
 [DataView 性能](dataview-performance.md)  
 提供有关 <xref:System.Data.DataView> 和性能的信息。  
  
 [如何：将 DataView 对象绑定到 Windows 窗体 DataGridView 控件](how-to-bind-a-dataview-object-to-a-winforms-datagridview-control.md)  
 说明如何将 <xref:System.Data.DataView> 对象绑定到 <xref:System.Windows.Forms.DataGridView>。  
  
## <a name="see-also"></a>请参阅

- [编程指南](programming-guide-linq-to-dataset.md)
