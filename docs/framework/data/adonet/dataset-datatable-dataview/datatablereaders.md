---
title: DataTableReader
ms.date: 03/30/2017
ms.assetid: 97546ae2-0e42-4d26-961d-e0b244d81ded
ms.openlocfilehash: a790335a25327563e3dab6093449345b99afd048
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59213996"
---
# <a name="datatablereaders"></a><span data-ttu-id="ff0dd-102">DataTableReader</span><span class="sxs-lookup"><span data-stu-id="ff0dd-102">DataTableReaders</span></span>
<span data-ttu-id="ff0dd-103"><xref:System.Data.DataTableReader> 以一个或多个只读、只进结果集的形式提供 <xref:System.Data.DataTable> 或的 <xref:System.Data.DataSet> 的内容。</span><span class="sxs-lookup"><span data-stu-id="ff0dd-103">The <xref:System.Data.DataTableReader> presents the contents of a <xref:System.Data.DataTable> or a <xref:System.Data.DataSet> in the form of one or more read-only, forward-only result sets.</span></span>  
  
 <span data-ttu-id="ff0dd-104">当您创建**DataTableReader**从**DataTable**，从而**DataTableReader**对象包含一个结果集具有相同的数据**DataTable**从创建它，但已标记为已删除任何行除外。</span><span class="sxs-lookup"><span data-stu-id="ff0dd-104">When you create a **DataTableReader** from a **DataTable**, the resulting **DataTableReader** object contains one result set with the same data as the **DataTable** from which it was created, except for any rows that have been marked as deleted.</span></span> <span data-ttu-id="ff0dd-105">列的显示顺序与在原始**DataTable**。</span><span class="sxs-lookup"><span data-stu-id="ff0dd-105">The columns appear in the same order as in the original **DataTable**.</span></span>  
  
 <span data-ttu-id="ff0dd-106">一个**DataTableReader**可能包含多个结果集，如果它通过调用创建<xref:System.Data.DataSet.CreateDataReader%2A>。</span><span class="sxs-lookup"><span data-stu-id="ff0dd-106">A **DataTableReader** may contain multiple result sets if it was created by calling <xref:System.Data.DataSet.CreateDataReader%2A>.</span></span> <span data-ttu-id="ff0dd-107">结果采用的顺序相同**DataTables**中**数据集**对象的<xref:System.Data.DataSet.Tables%2A>集合。</span><span class="sxs-lookup"><span data-stu-id="ff0dd-107">The results are in the same order as the **DataTables** in the **DataSet** object's <xref:System.Data.DataSet.Tables%2A> collection.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ff0dd-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="ff0dd-108">In This Section</span></span>  
 [<span data-ttu-id="ff0dd-109">创建 DataReader</span><span class="sxs-lookup"><span data-stu-id="ff0dd-109">Creating a DataReader</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-datareader.md)  
 <span data-ttu-id="ff0dd-110">讨论如何创建**DataTableReader**对象。</span><span class="sxs-lookup"><span data-stu-id="ff0dd-110">Discusses how to create a **DataTableReader** object.</span></span>  
  
 [<span data-ttu-id="ff0dd-111">导航数据表</span><span class="sxs-lookup"><span data-stu-id="ff0dd-111">Navigating DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/navigating-datatables.md)  
 <span data-ttu-id="ff0dd-112">介绍如何使用**读**方法来移动的内容通过**DataTableReader**。</span><span class="sxs-lookup"><span data-stu-id="ff0dd-112">Describes the use of the **Read** method to move through the contents of a **DataTableReader**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff0dd-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="ff0dd-113">See also</span></span>

- [<span data-ttu-id="ff0dd-114">在 ADO.NET 中检索和修改数据</span><span class="sxs-lookup"><span data-stu-id="ff0dd-114">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [<span data-ttu-id="ff0dd-115">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="ff0dd-115">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
