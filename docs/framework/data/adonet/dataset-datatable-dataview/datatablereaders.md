---
title: DataTableReader
ms.date: 03/30/2017
ms.assetid: 97546ae2-0e42-4d26-961d-e0b244d81ded
ms.openlocfilehash: 8305629bb267805cd79455e2edf990e72a12dc10
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="datatablereaders"></a><span data-ttu-id="48c60-102">DataTableReader</span><span class="sxs-lookup"><span data-stu-id="48c60-102">DataTableReaders</span></span>
<span data-ttu-id="48c60-103"><xref:System.Data.DataTableReader> 以一个或多个只读、只进结果集的形式提供 <xref:System.Data.DataTable> 或的 <xref:System.Data.DataSet> 的内容。</span><span class="sxs-lookup"><span data-stu-id="48c60-103">The <xref:System.Data.DataTableReader> presents the contents of a <xref:System.Data.DataTable> or a <xref:System.Data.DataSet> in the form of one or more read-only, forward-only result sets.</span></span>  
  
 <span data-ttu-id="48c60-104">当你创建**DataTableReader**从**DataTable**，生成**DataTableReader**对象包含一个结果集具有相同的数据**DataTable**从创建它，除已标记为删除任何行。</span><span class="sxs-lookup"><span data-stu-id="48c60-104">When you create a **DataTableReader** from a **DataTable**, the resulting **DataTableReader** object contains one result set with the same data as the **DataTable** from which it was created, except for any rows that have been marked as deleted.</span></span> <span data-ttu-id="48c60-105">列将显示在相同的顺序与在原始**DataTable**。</span><span class="sxs-lookup"><span data-stu-id="48c60-105">The columns appear in the same order as in the original **DataTable**.</span></span>  
  
 <span data-ttu-id="48c60-106">A **DataTableReader**可能包含多个结果集，如果它由调用<xref:System.Data.DataSet.CreateDataReader%2A>。</span><span class="sxs-lookup"><span data-stu-id="48c60-106">A **DataTableReader** may contain multiple result sets if it was created by calling <xref:System.Data.DataSet.CreateDataReader%2A>.</span></span> <span data-ttu-id="48c60-107">结果采用的顺序相同**数据表**中**数据集**对象的<xref:System.Data.DataSet.Tables%2A>集合。</span><span class="sxs-lookup"><span data-stu-id="48c60-107">The results are in the same order as the **DataTables** in the **DataSet** object's <xref:System.Data.DataSet.Tables%2A> collection.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="48c60-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="48c60-108">In This Section</span></span>  
 [<span data-ttu-id="48c60-109">创建 DataReader</span><span class="sxs-lookup"><span data-stu-id="48c60-109">Creating a DataReader</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-datareader.md)  
 <span data-ttu-id="48c60-110">讨论如何创建**DataTableReader**对象。</span><span class="sxs-lookup"><span data-stu-id="48c60-110">Discusses how to create a **DataTableReader** object.</span></span>  
  
 [<span data-ttu-id="48c60-111">导航数据表</span><span class="sxs-lookup"><span data-stu-id="48c60-111">Navigating DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/navigating-datatables.md)  
 <span data-ttu-id="48c60-112">描述如何使用**读取**方法来移动的内容通过**DataTableReader**。</span><span class="sxs-lookup"><span data-stu-id="48c60-112">Describes the use of the **Read** method to move through the contents of a **DataTableReader**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48c60-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="48c60-113">See Also</span></span>  
 [<span data-ttu-id="48c60-114">在 ADO.NET 中检索和修改数据</span><span class="sxs-lookup"><span data-stu-id="48c60-114">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [<span data-ttu-id="48c60-115">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="48c60-115">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
