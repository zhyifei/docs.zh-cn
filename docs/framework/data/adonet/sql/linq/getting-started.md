---
title: 入门
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: db8a557a-fef8-4f4f-bb91-8cff7250ee25
ms.openlocfilehash: 17b014a5a56a2c60359f6fb0b60df29feb97f2a7
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2018
ms.locfileid: "43419020"
---
# <a name="getting-started"></a><span data-ttu-id="ea4fe-102">入门</span><span class="sxs-lookup"><span data-stu-id="ea4fe-102">Getting Started</span></span>
<span data-ttu-id="ea4fe-103">通过使用[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]，可以使用[!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)]技术访问 SQL 数据库，就像你访问的内存中集合。</span><span class="sxs-lookup"><span data-stu-id="ea4fe-103">By using [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], you can use the [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] technology to access SQL databases just as you would access an in-memory collection.</span></span>  
  
 <span data-ttu-id="ea4fe-104">例如，在下面的代码中，创建了 `nw` 对象来表示 `Northwind` 数据库，将 `Customers` 表作为目标，筛选出了来自 `Customers` 的 `London` 行，并选择了一个表示 `CompanyName` 的字符串以进行检索。</span><span class="sxs-lookup"><span data-stu-id="ea4fe-104">For example, the `nw` object in the following code is created to represent the `Northwind` database, the `Customers` table is targeted, the rows are filtered for `Customers` from `London`, and a string for `CompanyName` is selected for retrieval.</span></span>  
  
 <span data-ttu-id="ea4fe-105">执行循环时，将检索到 `CompanyName` 值的集合。</span><span class="sxs-lookup"><span data-stu-id="ea4fe-105">When the loop is executed, the collection of `CompanyName` values is retrieved.</span></span>  
  
 [!code-csharp[DLinqGettingStarted#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#1)]
 [!code-vb[DLinqGettingStarted#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#1)]  
  
## <a name="next-steps"></a><span data-ttu-id="ea4fe-106">后续步骤</span><span class="sxs-lookup"><span data-stu-id="ea4fe-106">Next Steps</span></span>  
 <span data-ttu-id="ea4fe-107">有关其他的一些示例，包括插入和更新，请参阅[内容您可以执行与 LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/what-you-can-do-with-linq-to-sql.md)。</span><span class="sxs-lookup"><span data-stu-id="ea4fe-107">For some additional examples, including inserting and updating, see [What You Can Do With LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/what-you-can-do-with-linq-to-sql.md).</span></span>  
  
 <span data-ttu-id="ea4fe-108">接下来，请试着按一些演练和教程中的说明动手操作，实际体验一下 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 的使用。</span><span class="sxs-lookup"><span data-stu-id="ea4fe-108">Next, try some walkthroughs and tutorials to have a hands-on experience of using [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="ea4fe-109">请参阅[通过演练学习](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)。</span><span class="sxs-lookup"><span data-stu-id="ea4fe-109">See [Learning by Walkthroughs](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md).</span></span>  
  
 <span data-ttu-id="ea4fe-110">最后，了解如何开始您自己[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]通过读取项目[使用 LINQ to SQL 的典型步骤](../../../../../../docs/framework/data/adonet/sql/linq/typical-steps-for-using-linq-to-sql.md)。</span><span class="sxs-lookup"><span data-stu-id="ea4fe-110">Finally, learn how to get started on your own [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] project by reading [Typical Steps for Using LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/typical-steps-for-using-linq-to-sql.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea4fe-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="ea4fe-111">See Also</span></span>  
 [<span data-ttu-id="ea4fe-112">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="ea4fe-112">LINQ to SQL</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/index.md)  
 [<span data-ttu-id="ea4fe-113">LINQ 简介</span><span class="sxs-lookup"><span data-stu-id="ea4fe-113">Introduction to LINQ</span></span>](https://msdn.microsoft.com/library/24dddf19-12a0-4707-a4bc-eba4fa7f219e)  
 [<span data-ttu-id="ea4fe-114">LINQ to SQL 对象模型</span><span class="sxs-lookup"><span data-stu-id="ea4fe-114">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
