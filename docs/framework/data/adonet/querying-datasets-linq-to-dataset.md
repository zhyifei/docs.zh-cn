---
title: 查询数据集 (LINQ to DataSet)
ms.date: 03/30/2017
ms.assetid: bb68d2e4-623d-4d60-85e3-965254f6fee7
ms.openlocfilehash: ddd92b1a95889b44eba2ec582308bf08358eeea7
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53145775"
---
# <a name="querying-datasets-linq-to-dataset"></a><span data-ttu-id="20d09-102">查询数据集 (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="20d09-102">Querying DataSets (LINQ to DataSet)</span></span>
<span data-ttu-id="20d09-103">用数据填充 <xref:System.Data.DataSet> 对象后，您可以开始查询该对象。</span><span class="sxs-lookup"><span data-stu-id="20d09-103">After a <xref:System.Data.DataSet> object has been populated with data, you can begin querying it.</span></span> <span data-ttu-id="20d09-104">使用 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 表述查询类似于对启用 [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] 的其他数据源使用 [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="20d09-104">Formulating queries with [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] is similar to using [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] against other [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]-enabled data sources.</span></span> <span data-ttu-id="20d09-105">但请记住，在对 [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] 对象使用 <xref:System.Data.DataSet> 查询时，所查询的是 <xref:System.Data.DataRow> 对象的枚举，而不是自定义类型的枚举。</span><span class="sxs-lookup"><span data-stu-id="20d09-105">Remember, however, that when you use [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] queries over a <xref:System.Data.DataSet> object you are querying an enumeration of <xref:System.Data.DataRow> objects, instead of an enumeration of a custom type.</span></span> <span data-ttu-id="20d09-106">这意味着可以在 <xref:System.Data.DataRow> 查询中使用 [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] 类的任意成员。</span><span class="sxs-lookup"><span data-stu-id="20d09-106">This means that you can use any of the members of the <xref:System.Data.DataRow> class in your [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] queries.</span></span> <span data-ttu-id="20d09-107">这允许您创建丰富而复杂的查询。</span><span class="sxs-lookup"><span data-stu-id="20d09-107">This lets you to create rich, complex queries.</span></span>  
  
 <span data-ttu-id="20d09-108">其他实现一样[!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]，可以创建[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]中两种不同形式的查询： 查询表达式语法和基于方法的查询语法。</span><span class="sxs-lookup"><span data-stu-id="20d09-108">As with other implementations of [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)], you can create [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] queries in two different forms: query expression syntax and method-based query syntax.</span></span> <span data-ttu-id="20d09-109">您可以使用查询表达式语法或基于方法的查询语法对 <xref:System.Data.DataSet> 中的单个表、对 <xref:System.Data.DataSet> 中的多个表或对类型化 <xref:System.Data.DataSet> 中的表执行查询。</span><span class="sxs-lookup"><span data-stu-id="20d09-109">You can use query expression syntax or method-based query syntax to perform queries against single tables in a <xref:System.Data.DataSet>, against multiple tables in a <xref:System.Data.DataSet>, or against tables in a typed <xref:System.Data.DataSet>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="20d09-110">本节内容</span><span class="sxs-lookup"><span data-stu-id="20d09-110">In This Section</span></span>  
 [<span data-ttu-id="20d09-111">单表查询</span><span class="sxs-lookup"><span data-stu-id="20d09-111">Single-Table Queries</span></span>](../../../../docs/framework/data/adonet/single-table-queries-linq-to-dataset.md)  
 <span data-ttu-id="20d09-112">说明如何执行单表查询。</span><span class="sxs-lookup"><span data-stu-id="20d09-112">Describes how to perform single-table queries.</span></span>  
  
 [<span data-ttu-id="20d09-113">跨表查询</span><span class="sxs-lookup"><span data-stu-id="20d09-113">Cross-Table Queries</span></span>](../../../../docs/framework/data/adonet/cross-table-queries-linq-to-dataset.md)  
 <span data-ttu-id="20d09-114">说明如何执行交叉表查询。</span><span class="sxs-lookup"><span data-stu-id="20d09-114">Describes how to perform cross-table queries.</span></span>  
  
 [<span data-ttu-id="20d09-115">查询类型化数据集</span><span class="sxs-lookup"><span data-stu-id="20d09-115">Querying Typed DataSets</span></span>](../../../../docs/framework/data/adonet/querying-typed-datasets.md)  
 <span data-ttu-id="20d09-116">说明如何查询类型化 <xref:System.Data.DataSet> 对象。</span><span class="sxs-lookup"><span data-stu-id="20d09-116">Describes how to query typed <xref:System.Data.DataSet> objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20d09-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="20d09-117">See Also</span></span>  
 [<span data-ttu-id="20d09-118">LINQ to DataSet 示例</span><span class="sxs-lookup"><span data-stu-id="20d09-118">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)  
 [<span data-ttu-id="20d09-119">将数据加载到数据集中</span><span class="sxs-lookup"><span data-stu-id="20d09-119">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)
