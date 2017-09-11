---
title: "如何︰ 使用表达式树来生成动态查询 (Visual Basic 中) |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 16278787-7532-4b65-98b2-7a412406c4ee
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 8d69be78a9f3568535dffe54e21af80c6eb12f70
ms.contentlocale: zh-cn
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-use-expression-trees-to-build-dynamic-queries-visual-basic"></a><span data-ttu-id="2bf18-102">如何︰ 使用表达式树来生成动态查询 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2bf18-102">How to: Use Expression Trees to Build Dynamic Queries (Visual Basic)</span></span>
<span data-ttu-id="2bf18-103">在 LINQ 中，表达式目录树用于表示该目标的数据源实现<xref:System.Linq.IQueryable%601>。</xref:System.Linq.IQueryable%601>的结构化的查询</span><span class="sxs-lookup"><span data-stu-id="2bf18-103">In LINQ, expression trees are used to represent structured queries that target sources of data that implement <xref:System.Linq.IQueryable%601>.</span></span> <span data-ttu-id="2bf18-104">例如，LINQ 提供程序实现<xref:System.Linq.IQueryable%601>接口，用于查询关系数据存储区。</xref:System.Linq.IQueryable%601></span><span class="sxs-lookup"><span data-stu-id="2bf18-104">For example, the LINQ provider implements the <xref:System.Linq.IQueryable%601> interface for querying relational data stores.</span></span> <span data-ttu-id="2bf18-105">Visual Basic 编译器编译成代码，将生成一个表达式树，在运行时针对此类数据源的查询。</span><span class="sxs-lookup"><span data-stu-id="2bf18-105">The Visual Basic compiler compiles queries that target such data sources into code that builds an expression tree at runtime.</span></span> <span data-ttu-id="2bf18-106">然后，查询提供程序可以遍历表达式树数据结构，并将其转换为适用于数据源的查询语言。</span><span class="sxs-lookup"><span data-stu-id="2bf18-106">The query provider can then traverse the expression tree data structure and translate it into a query language appropriate for the data source.</span></span>  
  
 <span data-ttu-id="2bf18-107">表达式树还能用于在 LINQ 中用于表示分配给类型<xref:System.Linq.Expressions.Expression%601>。</xref:System.Linq.Expressions.Expression%601>的变量的 lambda 表达式</span><span class="sxs-lookup"><span data-stu-id="2bf18-107">Expression trees are also used in LINQ to represent lambda expressions that are assigned to variables of type <xref:System.Linq.Expressions.Expression%601>.</span></span>  
  
 <span data-ttu-id="2bf18-108">本主题介绍如何使用表达式树来创建动态 LINQ 查询。</span><span class="sxs-lookup"><span data-stu-id="2bf18-108">This topic describes how to use expression trees to create dynamic LINQ queries.</span></span> <span data-ttu-id="2bf18-109">在查询的细节在编译时未知时，动态查询很有用。</span><span class="sxs-lookup"><span data-stu-id="2bf18-109">Dynamic queries are useful when the specifics of a query are not known at compile time.</span></span> <span data-ttu-id="2bf18-110">例如，应用程序可能会提供一个用户界面，使最终用户若要指定一个或多个谓词来筛选的数据。</span><span class="sxs-lookup"><span data-stu-id="2bf18-110">For example, an application might provide a user interface that enables the end user to specify one or more predicates to filter the data.</span></span> <span data-ttu-id="2bf18-111">若要使用 LINQ 进行查询，这种应用程序必须使用表达式树来在运行时创建 LINQ 查询。</span><span class="sxs-lookup"><span data-stu-id="2bf18-111">In order to use LINQ for querying, this kind of application must use expression trees to create the LINQ query at runtime.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2bf18-112">示例</span><span class="sxs-lookup"><span data-stu-id="2bf18-112">Example</span></span>  
 <span data-ttu-id="2bf18-113">下面的示例演示如何使用表达式树来构造查询针对`IQueryable`数据源，然后执行它。</span><span class="sxs-lookup"><span data-stu-id="2bf18-113">The following example shows you how to use expression trees to construct a query against an `IQueryable` data source and then execute it.</span></span> <span data-ttu-id="2bf18-114">代码将生成表达式树来表示以下查询︰</span><span class="sxs-lookup"><span data-stu-id="2bf18-114">The code builds an expression tree to represent the following query:</span></span>  
  
 `companies.Where(Function(company) company.ToLower() = "coho winery" OrElse company.Length > 16).OrderBy(Function(company) company)`  
  
 <span data-ttu-id="2bf18-115">中的工厂方法<xref:System.Linq.Expressions>命名空间用来创建表达式目录树表示构成总体查询的表达式。</xref:System.Linq.Expressions></span><span class="sxs-lookup"><span data-stu-id="2bf18-115">The factory methods in the <xref:System.Linq.Expressions> namespace are used to create expression trees that represent the expressions that make up the overall query.</span></span> <span data-ttu-id="2bf18-116">表示对标准查询运算符方法的调用的表达式引用<xref:System.Linq.Queryable>这些方法的实现。</xref:System.Linq.Queryable></span><span class="sxs-lookup"><span data-stu-id="2bf18-116">The expressions that represent calls to the standard query operator methods refer to the <xref:System.Linq.Queryable> implementations of these methods.</span></span> <span data-ttu-id="2bf18-117">最终的表达式树传递给<xref:System.Linq.IQueryProvider.CreateQuery%60%601%28System.Linq.Expressions.Expression%29>的提供程序实现`IQueryable`数据源，以创建类型的可执行查询`IQueryable`。</xref:System.Linq.IQueryProvider.CreateQuery%60%601%28System.Linq.Expressions.Expression%29></span><span class="sxs-lookup"><span data-stu-id="2bf18-117">The final expression tree is passed to the <xref:System.Linq.IQueryProvider.CreateQuery%60%601%28System.Linq.Expressions.Expression%29> implementation of the provider of the `IQueryable` data source to create an executable query of type `IQueryable`.</span></span> <span data-ttu-id="2bf18-118">可通过枚举该查询变量获取结果。</span><span class="sxs-lookup"><span data-stu-id="2bf18-118">The results are obtained by enumerating that query variable.</span></span>  
  
<span data-ttu-id="2bf18-119"><CodeContentPlaceHolder>0</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="2bf18-119"><CodeContentPlaceHolder>0</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="2bf18-120">此代码传递给该谓词中使用固定的数量的表达式`Queryable.Where`方法。</span><span class="sxs-lookup"><span data-stu-id="2bf18-120">This code uses a fixed number of expressions in the predicate that is passed to the `Queryable.Where` method.</span></span> <span data-ttu-id="2bf18-121">但是，您可以编写合并可变数量的谓词表达式依赖于用户输入的应用程序。</span><span class="sxs-lookup"><span data-stu-id="2bf18-121">However, you can write an application that combines a variable number of predicate expressions that depends on the user input.</span></span> <span data-ttu-id="2bf18-122">此外可以使用不同的标准查询运算符的调用在查询中，具体取决于用户的输入。</span><span class="sxs-lookup"><span data-stu-id="2bf18-122">You can also vary the standard query operators that are called in the query, depending on the input from the user.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2bf18-123">编译代码</span><span class="sxs-lookup"><span data-stu-id="2bf18-123">Compiling the Code</span></span>  
  
-   <span data-ttu-id="2bf18-124">创建一个新**控制台应用程序**项目。</span><span class="sxs-lookup"><span data-stu-id="2bf18-124">Create a new **Console Application** project.</span></span>  
  
-   <span data-ttu-id="2bf18-125">如果未引用将添加对 System.Core.dll 的引用。</span><span class="sxs-lookup"><span data-stu-id="2bf18-125">Add a reference to System.Core.dll if it is not already referenced.</span></span>  
  
-   <span data-ttu-id="2bf18-126">包括 System.Linq.Expressions 命名空间。</span><span class="sxs-lookup"><span data-stu-id="2bf18-126">Include the System.Linq.Expressions namespace.</span></span>  
  
-   <span data-ttu-id="2bf18-127">从该示例复制代码并将其粘贴到`Main``Sub`过程。</span><span class="sxs-lookup"><span data-stu-id="2bf18-127">Copy the code from the example and paste it into the `Main` `Sub` procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bf18-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2bf18-128">See Also</span></span>  
 <span data-ttu-id="2bf18-129">[表达式树 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md) </span><span class="sxs-lookup"><span data-stu-id="2bf18-129">[Expression Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md) </span></span>  
<span data-ttu-id="2bf18-130"> [如何︰ 执行表达式树 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-execute-expression-trees.md)</span><span class="sxs-lookup"><span data-stu-id="2bf18-130"> [How to: Execute Expression Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-execute-expression-trees.md)</span></span>
