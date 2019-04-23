---
title: 入门
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: db8a557a-fef8-4f4f-bb91-8cff7250ee25
ms.openlocfilehash: 506257c13bbaada98dffa9d3a15c834037c1d971
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59155228"
---
# <a name="getting-started"></a><span data-ttu-id="f60dd-102">入门</span><span class="sxs-lookup"><span data-stu-id="f60dd-102">Getting Started</span></span>
<span data-ttu-id="f60dd-103">通过使用[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]，可以使用[!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)]技术访问 SQL 数据库，就像你访问的内存中集合。</span><span class="sxs-lookup"><span data-stu-id="f60dd-103">By using [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], you can use the [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] technology to access SQL databases just as you would access an in-memory collection.</span></span>  
  
 <span data-ttu-id="f60dd-104">例如，在下面的代码中，创建了 `nw` 对象来表示 `Northwind` 数据库，将 `Customers` 表作为目标，筛选出了来自 `Customers` 的 `London` 行，并选择了一个表示 `CompanyName` 的字符串以进行检索。</span><span class="sxs-lookup"><span data-stu-id="f60dd-104">For example, the `nw` object in the following code is created to represent the `Northwind` database, the `Customers` table is targeted, the rows are filtered for `Customers` from `London`, and a string for `CompanyName` is selected for retrieval.</span></span>  
  
 <span data-ttu-id="f60dd-105">执行循环时，将检索到 `CompanyName` 值的集合。</span><span class="sxs-lookup"><span data-stu-id="f60dd-105">When the loop is executed, the collection of `CompanyName` values is retrieved.</span></span>  
  
 [!code-csharp[DLinqGettingStarted#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#1)]
 [!code-vb[DLinqGettingStarted#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#1)]  
  
## <a name="next-steps"></a><span data-ttu-id="f60dd-106">后续步骤</span><span class="sxs-lookup"><span data-stu-id="f60dd-106">Next Steps</span></span>  
 <span data-ttu-id="f60dd-107">有关其他的一些示例，包括插入和更新，请参阅[内容您可以执行与 LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/what-you-can-do-with-linq-to-sql.md)。</span><span class="sxs-lookup"><span data-stu-id="f60dd-107">For some additional examples, including inserting and updating, see [What You Can Do With LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/what-you-can-do-with-linq-to-sql.md).</span></span>  
  
 <span data-ttu-id="f60dd-108">接下来，请试着按一些演练和教程中的说明动手操作，实际体验一下 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 的使用。</span><span class="sxs-lookup"><span data-stu-id="f60dd-108">Next, try some walkthroughs and tutorials to have a hands-on experience of using [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="f60dd-109">请参阅[通过演练学习](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)。</span><span class="sxs-lookup"><span data-stu-id="f60dd-109">See [Learning by Walkthroughs](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md).</span></span>  
  
 <span data-ttu-id="f60dd-110">最后，了解如何开始您自己[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]通过读取项目[使用 LINQ to SQL 的典型步骤](../../../../../../docs/framework/data/adonet/sql/linq/typical-steps-for-using-linq-to-sql.md)。</span><span class="sxs-lookup"><span data-stu-id="f60dd-110">Finally, learn how to get started on your own [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] project by reading [Typical Steps for Using LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/typical-steps-for-using-linq-to-sql.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f60dd-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="f60dd-111">See also</span></span>

- [<span data-ttu-id="f60dd-112">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="f60dd-112">LINQ to SQL</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="f60dd-113">LINQ 简介 (C#)</span><span class="sxs-lookup"><span data-stu-id="f60dd-113">Introduction to LINQ (C#)</span></span>](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq.md)
- [<span data-ttu-id="f60dd-114">LINQ 简介 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f60dd-114">Introduction to LINQ (Visual Basic)</span></span>](../../../../../visual-basic/programming-guide/concepts/linq/introduction-to-linq.md)
- [<span data-ttu-id="f60dd-115">LINQ to SQL 对象模型</span><span class="sxs-lookup"><span data-stu-id="f60dd-115">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
