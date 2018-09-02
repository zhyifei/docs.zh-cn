---
title: 创建 DataReader
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 49d4422a-7464-4ab8-8ec7-90185fde3ecf
ms.openlocfilehash: 1ede51ed9119051a647fd27d8d02cd2c93e61bbb
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2018
ms.locfileid: "43442715"
---
# <a name="creating-a-datareader"></a><span data-ttu-id="9bbf8-102">创建 DataReader</span><span class="sxs-lookup"><span data-stu-id="9bbf8-102">Creating a DataReader</span></span>
<span data-ttu-id="9bbf8-103"><xref:System.Data.DataTable> 和 <xref:System.Data.DataSet> 类具有 <xref:System.Data.DataTable.CreateDataReader%2A> 方法，可以将 <xref:System.Data.DataTable> 的内容或 <xref:System.Data.DataSet> 对象的 <xref:System.Data.DataSet.Tables%2A> 集合的内容作为一个或多个只读、只进的结果集返回。</span><span class="sxs-lookup"><span data-stu-id="9bbf8-103">The <xref:System.Data.DataTable> and <xref:System.Data.DataSet> classes have a <xref:System.Data.DataTable.CreateDataReader%2A> method that returns the contents of the <xref:System.Data.DataTable> or the contents of the <xref:System.Data.DataSet> object's <xref:System.Data.DataSet.Tables%2A> collection as one or more read-only, forward-only result sets.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9bbf8-104">示例</span><span class="sxs-lookup"><span data-stu-id="9bbf8-104">Example</span></span>  
 <span data-ttu-id="9bbf8-105">以下控制台应用程序创建一个 <xref:System.Data.DataTable> 实例。</span><span class="sxs-lookup"><span data-stu-id="9bbf8-105">The following console application creates a <xref:System.Data.DataTable> instance.</span></span> <span data-ttu-id="9bbf8-106">该示例然后将已填充<xref:System.Data.DataTable>到调用的过程<xref:System.Data.DataTable.CreateDataReader%2A>方法，该循环中包含的结果方法<xref:System.Data.DataTableReader>。</span><span class="sxs-lookup"><span data-stu-id="9bbf8-106">The example then passes the filled <xref:System.Data.DataTable> to a procedure that calls the <xref:System.Data.DataTable.CreateDataReader%2A> method, which iterates through the results contained within the <xref:System.Data.DataTableReader>.</span></span>  
  
 [!code-csharp[DataWorks DataTable.CreateDataReader#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DataTable.CreateDataReader/CS/source.cs#1)]
 [!code-vb[DataWorks DataTable.CreateDataReader#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DataTable.CreateDataReader/VB/source.vb#1)]  
  
 <span data-ttu-id="9bbf8-107">该示例在控制台窗口中显示以下输出：</span><span class="sxs-lookup"><span data-stu-id="9bbf8-107">The example displays the following output in the console window:</span></span>  
  
```  
1 Mary  
2 Andy  
3 Peter  
4 Russ  
```  
  
## <a name="see-also"></a><span data-ttu-id="9bbf8-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="9bbf8-108">See Also</span></span>  
 <xref:System.Data.DataTable.CreateDataReader%2A>  
 <xref:System.Data.DataSet.CreateDataReader%2A>  
 [<span data-ttu-id="9bbf8-109">DataTableReader</span><span class="sxs-lookup"><span data-stu-id="9bbf8-109">DataTableReaders</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatablereaders.md)  
 [<span data-ttu-id="9bbf8-110">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="9bbf8-110">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
