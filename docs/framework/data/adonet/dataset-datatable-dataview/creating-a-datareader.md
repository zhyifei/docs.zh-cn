---
title: 创建 DataReader
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 49d4422a-7464-4ab8-8ec7-90185fde3ecf
ms.openlocfilehash: cb39ead1fe15e3bfcf67370e4675dcae3bbf9801
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203894"
---
# <a name="creating-a-datareader"></a><span data-ttu-id="27d21-102">创建 DataReader</span><span class="sxs-lookup"><span data-stu-id="27d21-102">Creating a DataReader</span></span>
<span data-ttu-id="27d21-103"><xref:System.Data.DataTable> 和 <xref:System.Data.DataSet> 类具有 <xref:System.Data.DataTable.CreateDataReader%2A> 方法，可以将 <xref:System.Data.DataTable> 的内容或 <xref:System.Data.DataSet> 对象的 <xref:System.Data.DataSet.Tables%2A> 集合的内容作为一个或多个只读、只进的结果集返回。</span><span class="sxs-lookup"><span data-stu-id="27d21-103">The <xref:System.Data.DataTable> and <xref:System.Data.DataSet> classes have a <xref:System.Data.DataTable.CreateDataReader%2A> method that returns the contents of the <xref:System.Data.DataTable> or the contents of the <xref:System.Data.DataSet> object's <xref:System.Data.DataSet.Tables%2A> collection as one or more read-only, forward-only result sets.</span></span>  
  
## <a name="example"></a><span data-ttu-id="27d21-104">示例</span><span class="sxs-lookup"><span data-stu-id="27d21-104">Example</span></span>  
 <span data-ttu-id="27d21-105">以下控制台应用程序创建一个 <xref:System.Data.DataTable> 实例。</span><span class="sxs-lookup"><span data-stu-id="27d21-105">The following console application creates a <xref:System.Data.DataTable> instance.</span></span> <span data-ttu-id="27d21-106">然后, 该示例将填充<xref:System.Data.DataTable>的传递给<xref:System.Data.DataTable.CreateDataReader%2A>调用方法的过程, 该过程会循环访问中<xref:System.Data.DataTableReader>包含的结果。</span><span class="sxs-lookup"><span data-stu-id="27d21-106">The example then passes the filled <xref:System.Data.DataTable> to a procedure that calls the <xref:System.Data.DataTable.CreateDataReader%2A> method, which iterates through the results contained within the <xref:System.Data.DataTableReader>.</span></span>  
  
 [!code-csharp[DataWorks DataTable.CreateDataReader#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DataTable.CreateDataReader/CS/source.cs#1)]
 [!code-vb[DataWorks DataTable.CreateDataReader#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DataTable.CreateDataReader/VB/source.vb#1)]  
  
 <span data-ttu-id="27d21-107">该示例在控制台窗口中显示以下输出：</span><span class="sxs-lookup"><span data-stu-id="27d21-107">The example displays the following output in the console window:</span></span>  
  
```  
1 Mary  
2 Andy  
3 Peter  
4 Russ  
```  
  
## <a name="see-also"></a><span data-ttu-id="27d21-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="27d21-108">See also</span></span>

- <xref:System.Data.DataTable.CreateDataReader%2A>
- <xref:System.Data.DataSet.CreateDataReader%2A>
- [<span data-ttu-id="27d21-109">DataTableReader</span><span class="sxs-lookup"><span data-stu-id="27d21-109">DataTableReaders</span></span>](datatablereaders.md)
- [<span data-ttu-id="27d21-110">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="27d21-110">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
