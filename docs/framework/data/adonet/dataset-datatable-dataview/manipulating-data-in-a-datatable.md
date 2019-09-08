---
title: 操作数据表中的数据
ms.date: 03/30/2017
ms.assetid: 5cb86d48-a987-4af4-80e0-8cc2c8373d62
ms.openlocfilehash: 421680a4f39dd68c09dfe20e62f2eec86259b9f0
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786150"
---
# <a name="manipulating-data-in-a-datatable"></a><span data-ttu-id="e986c-102">操作数据表中的数据</span><span class="sxs-lookup"><span data-stu-id="e986c-102">Manipulating Data in a DataTable</span></span>
<span data-ttu-id="e986c-103">在 <xref:System.Data.DataTable> 中创建 <xref:System.Data.DataSet> 之后，您执行的活动可以与使用数据库中的表时执行的活动相同。</span><span class="sxs-lookup"><span data-stu-id="e986c-103">After creating a <xref:System.Data.DataTable> in a <xref:System.Data.DataSet>, you can perform the same activities that you would when using a table in a database.</span></span> <span data-ttu-id="e986c-104">您可以添加、查看、编辑和删除表中的数据；可以监视错误和事件；并且可以查询表中的数据。</span><span class="sxs-lookup"><span data-stu-id="e986c-104">You can add, view, edit, and delete data in the table; you can monitor errors and events; and you can query the data in the table.</span></span> <span data-ttu-id="e986c-105">在修改**DataTable**中的数据时，还可以验证这些更改是否准确，并确定是否以编程方式接受或拒绝更改。</span><span class="sxs-lookup"><span data-stu-id="e986c-105">When modifying data in a **DataTable**, you can also verify whether the changes are accurate, and determine whether to programmatically accept or reject the changes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e986c-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="e986c-106">In This Section</span></span>  
 [<span data-ttu-id="e986c-107">将数据添加到数据表中</span><span class="sxs-lookup"><span data-stu-id="e986c-107">Adding Data to a DataTable</span></span>](adding-data-to-a-datatable.md)  
 <span data-ttu-id="e986c-108">说明如何创建新行并将它们添加到表中。</span><span class="sxs-lookup"><span data-stu-id="e986c-108">Explains how to create new rows and add them to a table.</span></span>  
  
 [<span data-ttu-id="e986c-109">在数据表中查看数据</span><span class="sxs-lookup"><span data-stu-id="e986c-109">Viewing Data in a DataTable</span></span>](viewing-data-in-a-datatable.md)  
 <span data-ttu-id="e986c-110">说明如何访问行中的数据，包括数据的原始版本和当前版本。</span><span class="sxs-lookup"><span data-stu-id="e986c-110">Describes how to access the data in a row, including original and current versions of the data.</span></span>  
  
 [<span data-ttu-id="e986c-111">加载方法</span><span class="sxs-lookup"><span data-stu-id="e986c-111">The Load Method</span></span>](the-load-method.md)  
 <span data-ttu-id="e986c-112">介绍如何使用**Load**方法来填充包含行的**DataTable** 。</span><span class="sxs-lookup"><span data-stu-id="e986c-112">Describes the use of the **Load** method to fill a **DataTable** with rows.</span></span>  
  
 [<span data-ttu-id="e986c-113">数据表编辑</span><span class="sxs-lookup"><span data-stu-id="e986c-113">DataTable Edits</span></span>](datatable-edits.md)  
 <span data-ttu-id="e986c-114">说明如何修改行中的数据，包括挂起对行的更改，直至验证并接受了建议的更改。</span><span class="sxs-lookup"><span data-stu-id="e986c-114">Explains how to modify the data in a row, including suspending the changes to a row until the proposed changes are verified and accepted.</span></span>  
  
 [<span data-ttu-id="e986c-115">行状态和行版本</span><span class="sxs-lookup"><span data-stu-id="e986c-115">Row States and Row Versions</span></span>](row-states-and-row-versions.md)  
 <span data-ttu-id="e986c-116">提供有关行的不同状态的信息。</span><span class="sxs-lookup"><span data-stu-id="e986c-116">Provides information about the different states of a row.</span></span>  
  
 [<span data-ttu-id="e986c-117">DataRow 删除</span><span class="sxs-lookup"><span data-stu-id="e986c-117">DataRow Deletion</span></span>](datarow-deletion.md)  
 <span data-ttu-id="e986c-118">说明如何从表中移除行。</span><span class="sxs-lookup"><span data-stu-id="e986c-118">Describes how to remove a row from a table.</span></span>  
  
 [<span data-ttu-id="e986c-119">行错误信息</span><span class="sxs-lookup"><span data-stu-id="e986c-119">Row Error Information</span></span>](row-error-information.md)  
 <span data-ttu-id="e986c-120">说明如何插入每行的错误信息，帮助解决应用程序中的数据问题。</span><span class="sxs-lookup"><span data-stu-id="e986c-120">Explains how to insert error information per row, to help resolve problems with the data within an application.</span></span>  
  
 [<span data-ttu-id="e986c-121">AcceptChanges 和 RejectChanges</span><span class="sxs-lookup"><span data-stu-id="e986c-121">AcceptChanges and RejectChanges</span></span>](acceptchanges-and-rejectchanges.md)  
 <span data-ttu-id="e986c-122">说明如何接受或拒绝对行的更改。</span><span class="sxs-lookup"><span data-stu-id="e986c-122">Explains how to accept or reject the changes made to a row.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e986c-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="e986c-123">See also</span></span>

- [<span data-ttu-id="e986c-124">数据表</span><span class="sxs-lookup"><span data-stu-id="e986c-124">DataTables</span></span>](datatables.md)
- [<span data-ttu-id="e986c-125">处理数据表事件</span><span class="sxs-lookup"><span data-stu-id="e986c-125">Handling DataTable Events</span></span>](handling-datatable-events.md)
- [<span data-ttu-id="e986c-126">ADO.NET 概述</span><span class="sxs-lookup"><span data-stu-id="e986c-126">ADO.NET Overview</span></span>](../ado-net-overview.md)
