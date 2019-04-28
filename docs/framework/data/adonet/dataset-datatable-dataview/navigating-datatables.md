---
title: 导航数据表
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 202026a1-ec79-435e-b507-12a77f5011b2
ms.openlocfilehash: 91db42acb0e09b8fc99b0ee710a60800d40938ce
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61607259"
---
# <a name="navigating-datatables"></a><span data-ttu-id="0838c-102">导航数据表</span><span class="sxs-lookup"><span data-stu-id="0838c-102">Navigating DataTables</span></span>
<span data-ttu-id="0838c-103"><xref:System.Data.DataTableReader> 以一个或多个只读、只进结果集的形式获取一个或多个 <xref:System.Data.DataTable> 对象的内容。</span><span class="sxs-lookup"><span data-stu-id="0838c-103">The <xref:System.Data.DataTableReader> obtains the contents of one or more <xref:System.Data.DataTable> objects in the form of one or more read-only, forward-only result sets.</span></span>  
  
 <span data-ttu-id="0838c-104">如果 <xref:System.Data.DataTableReader> 是使用 <xref:System.Data.DataSet.CreateDataReader%2A> 方法创建，则可以包含多个结果集。</span><span class="sxs-lookup"><span data-stu-id="0838c-104">A <xref:System.Data.DataTableReader> may contain multiple result sets if it is created by using the <xref:System.Data.DataSet.CreateDataReader%2A> method.</span></span> <span data-ttu-id="0838c-105">如果包含多个结果集，<xref:System.Data.DataTableReader.NextResult%2A> 方法会将游标前进到下一个结果集。</span><span class="sxs-lookup"><span data-stu-id="0838c-105">When there is more than one result set, the <xref:System.Data.DataTableReader.NextResult%2A> method advances the cursor to the next result set.</span></span> <span data-ttu-id="0838c-106">这是一个只进过程。</span><span class="sxs-lookup"><span data-stu-id="0838c-106">This is a forward-only process.</span></span> <span data-ttu-id="0838c-107">无法返回到前一个结果集。</span><span class="sxs-lookup"><span data-stu-id="0838c-107">It is not possible to return to a previous result set.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0838c-108">示例</span><span class="sxs-lookup"><span data-stu-id="0838c-108">Example</span></span>  
 <span data-ttu-id="0838c-109">在以下示例中，`TestConstructor`方法创建两个<xref:System.Data.DataTable>实例。</span><span class="sxs-lookup"><span data-stu-id="0838c-109">In the following example, the `TestConstructor` method creates two <xref:System.Data.DataTable> instances.</span></span> <span data-ttu-id="0838c-110">为了演示此构造函数<xref:System.Data.DataTableReader>类，该示例创建一个新**DataTableReader**基于数组包含两个**DataTables**，并执行一个简单的操作，将前几列的内容打印到控制台窗口中。</span><span class="sxs-lookup"><span data-stu-id="0838c-110">In order to demonstrate this constructor for the <xref:System.Data.DataTableReader> class, the sample creates a new **DataTableReader** based on an array that contains the two **DataTables**, and performs a simple operation, printing the contents from the first few columns to the console window.</span></span>  
  
 [!code-csharp[DataWorks DataTableReader.NextResult#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DataTableReader.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks DataTableReader.NextResult#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DataTableReader.NextResult/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="0838c-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="0838c-111">See also</span></span>

- [<span data-ttu-id="0838c-112">DataTableReader</span><span class="sxs-lookup"><span data-stu-id="0838c-112">DataTableReaders</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatablereaders.md)
- [<span data-ttu-id="0838c-113">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="0838c-113">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
