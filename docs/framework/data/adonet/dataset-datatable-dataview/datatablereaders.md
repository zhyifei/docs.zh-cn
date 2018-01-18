---
title: DataTableReader
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 97546ae2-0e42-4d26-961d-e0b244d81ded
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: b5160f5a2c68cab798dde154275c062e2bf31739
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="datatablereaders"></a><span data-ttu-id="2fff5-102">DataTableReader</span><span class="sxs-lookup"><span data-stu-id="2fff5-102">DataTableReaders</span></span>
<span data-ttu-id="2fff5-103"><xref:System.Data.DataTableReader> 以一个或多个只读、只进结果集的形式提供 <xref:System.Data.DataTable> 或的 <xref:System.Data.DataSet> 的内容。</span><span class="sxs-lookup"><span data-stu-id="2fff5-103">The <xref:System.Data.DataTableReader> presents the contents of a <xref:System.Data.DataTable> or a <xref:System.Data.DataSet> in the form of one or more read-only, forward-only result sets.</span></span>  
  
 <span data-ttu-id="2fff5-104">当你创建**DataTableReader**从**DataTable**，生成**DataTableReader**对象包含一个结果集具有相同的数据**DataTable**从创建它，除已标记为删除任何行。</span><span class="sxs-lookup"><span data-stu-id="2fff5-104">When you create a **DataTableReader** from a **DataTable**, the resulting **DataTableReader** object contains one result set with the same data as the **DataTable** from which it was created, except for any rows that have been marked as deleted.</span></span> <span data-ttu-id="2fff5-105">列将显示在相同的顺序与在原始**DataTable**。</span><span class="sxs-lookup"><span data-stu-id="2fff5-105">The columns appear in the same order as in the original **DataTable**.</span></span>  
  
 <span data-ttu-id="2fff5-106">A **DataTableReader**可能包含多个结果集，如果它由调用<xref:System.Data.DataSet.CreateDataReader%2A>。</span><span class="sxs-lookup"><span data-stu-id="2fff5-106">A **DataTableReader** may contain multiple result sets if it was created by calling <xref:System.Data.DataSet.CreateDataReader%2A>.</span></span> <span data-ttu-id="2fff5-107">结果采用的顺序相同**数据表**中**数据集**对象的<xref:System.Data.DataSet.Tables%2A>集合。</span><span class="sxs-lookup"><span data-stu-id="2fff5-107">The results are in the same order as the **DataTables** in the **DataSet** object's <xref:System.Data.DataSet.Tables%2A> collection.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2fff5-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="2fff5-108">In This Section</span></span>  
 [<span data-ttu-id="2fff5-109">创建 DataReader</span><span class="sxs-lookup"><span data-stu-id="2fff5-109">Creating a DataReader</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-datareader.md)  
 <span data-ttu-id="2fff5-110">讨论如何创建**DataTableReader**对象。</span><span class="sxs-lookup"><span data-stu-id="2fff5-110">Discusses how to create a **DataTableReader** object.</span></span>  
  
 [<span data-ttu-id="2fff5-111">导航数据表</span><span class="sxs-lookup"><span data-stu-id="2fff5-111">Navigating DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/navigating-datatables.md)  
 <span data-ttu-id="2fff5-112">描述如何使用**读取**方法来移动的内容通过**DataTableReader**。</span><span class="sxs-lookup"><span data-stu-id="2fff5-112">Describes the use of the **Read** method to move through the contents of a **DataTableReader**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fff5-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="2fff5-113">See Also</span></span>  
 [<span data-ttu-id="2fff5-114">在 ADO.NET 中检索和修改数据</span><span class="sxs-lookup"><span data-stu-id="2fff5-114">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [<span data-ttu-id="2fff5-115">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="2fff5-115">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
