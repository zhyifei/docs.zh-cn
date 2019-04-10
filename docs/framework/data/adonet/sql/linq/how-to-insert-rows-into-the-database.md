---
title: 如何：将行插入数据库中
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 44d99680-69c7-4879-a732-f6771b334211
ms.openlocfilehash: cc9f276cc278d4a9c376d72f1ab38d89ea6dd5b4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59169593"
---
# <a name="how-to-insert-rows-into-the-database"></a><span data-ttu-id="01a52-102">如何：将行插入数据库中</span><span class="sxs-lookup"><span data-stu-id="01a52-102">How to: Insert Rows Into the Database</span></span>
<span data-ttu-id="01a52-103">将行插入数据库通过将对象添加到关联[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<xref:System.Data.Linq.Table%601>集合，然后将更改提交到数据库。</span><span class="sxs-lookup"><span data-stu-id="01a52-103">You insert rows into a database by adding objects to the associated [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Table%601> collection and then submitting the changes to the database.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="01a52-104">将转换成相应的 SQL 所做的更改`INSERT`命令。</span><span class="sxs-lookup"><span data-stu-id="01a52-104">translates your changes into the appropriate SQL `INSERT` commands.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="01a52-105">您可以重写 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]、`Insert` 和 `Update` 数据库操作的 `Delete` 默认方法。</span><span class="sxs-lookup"><span data-stu-id="01a52-105">You can override [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] default methods for `Insert`, `Update`, and `Delete` database operations.</span></span> <span data-ttu-id="01a52-106">有关详细信息，请参阅[自定义插入、 更新和删除操作](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="01a52-106">For more information, see [Customizing Insert, Update, and Delete Operations](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).</span></span>  
>   
>  <span data-ttu-id="01a52-107">使用 Visual Studio 的开发人员可以使用[!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]来开发用于同一目的的存储的过程。</span><span class="sxs-lookup"><span data-stu-id="01a52-107">Developers using Visual Studio can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to develop stored procedures for the same purpose.</span></span>  
  
 <span data-ttu-id="01a52-108">以下步骤假定您已通过有效的 <xref:System.Data.Linq.DataContext> 连接到 Northwind 数据库。</span><span class="sxs-lookup"><span data-stu-id="01a52-108">The following steps assume that a valid <xref:System.Data.Linq.DataContext> connects you to the Northwind database.</span></span> <span data-ttu-id="01a52-109">有关详细信息，请参阅[如何：连接到数据库](../../../../../../docs/framework/data/adonet/sql/linq/how-to-connect-to-a-database.md)。</span><span class="sxs-lookup"><span data-stu-id="01a52-109">For more information, see [How to: Connect to a Database](../../../../../../docs/framework/data/adonet/sql/linq/how-to-connect-to-a-database.md).</span></span>  
  
### <a name="to-insert-a-row-into-the-database"></a><span data-ttu-id="01a52-110">向数据库中插入行</span><span class="sxs-lookup"><span data-stu-id="01a52-110">To insert a row into the database</span></span>  
  
1.  <span data-ttu-id="01a52-111">创建一个包含要提交的列数据的新对象。</span><span class="sxs-lookup"><span data-stu-id="01a52-111">Create a new object that includes the column data to be submitted.</span></span>  
  
2.  <span data-ttu-id="01a52-112">向其中添加新对象[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]`Table`与数据库中的目标表关联的集合。</span><span class="sxs-lookup"><span data-stu-id="01a52-112">Add the new object to the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] `Table` collection associated with the target table in the database.</span></span>  
  
3.  <span data-ttu-id="01a52-113">将更改提交到数据库。</span><span class="sxs-lookup"><span data-stu-id="01a52-113">Submit the change to the database.</span></span>  
  
## <a name="example"></a><span data-ttu-id="01a52-114">示例</span><span class="sxs-lookup"><span data-stu-id="01a52-114">Example</span></span>  
 <span data-ttu-id="01a52-115">下面的代码示例创建一个类型为 `Order` 的新对象，并用相应的值填充此对象。</span><span class="sxs-lookup"><span data-stu-id="01a52-115">The following code example creates a new object of type `Order` and populates it with appropriate values.</span></span> <span data-ttu-id="01a52-116">然后，它将这个新对象添加到 `Order` 集合中。</span><span class="sxs-lookup"><span data-stu-id="01a52-116">It then adds the new object to the `Order` collection.</span></span> <span data-ttu-id="01a52-117">最后，它将所做的更改提交到数据库中，使之成为 `Orders` 表中的一个新行。</span><span class="sxs-lookup"><span data-stu-id="01a52-117">Finally, it submits the change to the database as a new row in the `Orders` table.</span></span>  
  
 [!code-csharp[System.Data.Linq.Table#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.table/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.Table#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.table/vb/module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="01a52-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="01a52-118">See also</span></span>

- [<span data-ttu-id="01a52-119">如何：管理更改冲突</span><span class="sxs-lookup"><span data-stu-id="01a52-119">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
- [<span data-ttu-id="01a52-120">DataContext 方法（O/R 设计器）</span><span class="sxs-lookup"><span data-stu-id="01a52-120">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
- [<span data-ttu-id="01a52-121">如何：分配存储过程以便执行更新、插入和删除操作（O/R 设计器）</span><span class="sxs-lookup"><span data-stu-id="01a52-121">How to: Assign stored procedures to perform updates, inserts, and deletes (O/R Designer)</span></span>](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
- [<span data-ttu-id="01a52-122">进行和提交数据更改</span><span class="sxs-lookup"><span data-stu-id="01a52-122">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
