---
title: DataTableReader
ms.date: 03/30/2017
ms.assetid: 97546ae2-0e42-4d26-961d-e0b244d81ded
ms.openlocfilehash: 1ff7868b59c6fdc4e6c443be1b831accc84f36a6
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203818"
---
# <a name="datatablereaders"></a><span data-ttu-id="33643-102">DataTableReader</span><span class="sxs-lookup"><span data-stu-id="33643-102">DataTableReaders</span></span>
<span data-ttu-id="33643-103"><xref:System.Data.DataTableReader> 以一个或多个只读、只进结果集的形式提供 <xref:System.Data.DataTable> 或的 <xref:System.Data.DataSet> 的内容。</span><span class="sxs-lookup"><span data-stu-id="33643-103">The <xref:System.Data.DataTableReader> presents the contents of a <xref:System.Data.DataTable> or a <xref:System.Data.DataSet> in the form of one or more read-only, forward-only result sets.</span></span>  
  
 <span data-ttu-id="33643-104">从**DataTable**创建**DataTableReader**时, 生成的**DataTableReader**对象包含一个结果集, 该结果集的数据与创建它时所用的**数据表**相同, 但任何已标记为删除.</span><span class="sxs-lookup"><span data-stu-id="33643-104">When you create a **DataTableReader** from a **DataTable**, the resulting **DataTableReader** object contains one result set with the same data as the **DataTable** from which it was created, except for any rows that have been marked as deleted.</span></span> <span data-ttu-id="33643-105">列的显示顺序与原始**DataTable**中的顺序相同。</span><span class="sxs-lookup"><span data-stu-id="33643-105">The columns appear in the same order as in the original **DataTable**.</span></span>  
  
 <span data-ttu-id="33643-106">如果**DataTableReader**是通过调用<xref:System.Data.DataSet.CreateDataReader%2A>创建的, 则可以包含多个结果集。</span><span class="sxs-lookup"><span data-stu-id="33643-106">A **DataTableReader** may contain multiple result sets if it was created by calling <xref:System.Data.DataSet.CreateDataReader%2A>.</span></span> <span data-ttu-id="33643-107">结果与**DataSet**对象的<xref:System.Data.DataSet.Tables%2A>集合中的**数据表**顺序相同。</span><span class="sxs-lookup"><span data-stu-id="33643-107">The results are in the same order as the **DataTables** in the **DataSet** object's <xref:System.Data.DataSet.Tables%2A> collection.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="33643-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="33643-108">In This Section</span></span>  
 [<span data-ttu-id="33643-109">创建 DataReader</span><span class="sxs-lookup"><span data-stu-id="33643-109">Creating a DataReader</span></span>](creating-a-datareader.md)  
 <span data-ttu-id="33643-110">讨论如何创建**DataTableReader**对象。</span><span class="sxs-lookup"><span data-stu-id="33643-110">Discusses how to create a **DataTableReader** object.</span></span>  
  
 [<span data-ttu-id="33643-111">导航数据表</span><span class="sxs-lookup"><span data-stu-id="33643-111">Navigating DataTables</span></span>](navigating-datatables.md)  
 <span data-ttu-id="33643-112">介绍如何使用**Read**方法在**DataTableReader**的内容中移动。</span><span class="sxs-lookup"><span data-stu-id="33643-112">Describes the use of the **Read** method to move through the contents of a **DataTableReader**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33643-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="33643-113">See also</span></span>

- [<span data-ttu-id="33643-114">在 ADO.NET 中检索和修改数据</span><span class="sxs-lookup"><span data-stu-id="33643-114">Retrieving and Modifying Data in ADO.NET</span></span>](../retrieving-and-modifying-data.md)
- [<span data-ttu-id="33643-115">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="33643-115">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
