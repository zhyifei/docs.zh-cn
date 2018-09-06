---
title: LINQ to Objects (Visual Basic)
ms.date: 07/20/2015
ms.assetid: dd4c30bc-1c9b-4781-a482-b5eada38deb2
ms.openlocfilehash: 7e98f5170c69c189bd2071341fa24587ff1cc4e1
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43891975"
---
# <a name="linq-to-objects-visual-basic"></a><span data-ttu-id="363c6-102">LINQ to Objects (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="363c6-102">LINQ to Objects (Visual Basic)</span></span>
<span data-ttu-id="363c6-103">术语“LINQ to Objects”指直接将 LINQ 查询与任何 <xref:System.Collections.IEnumerable> 或 <xref:System.Collections.Generic.IEnumerable%601> 集合一起使用，而不使用中间 LINQ 提供程序或 API，例如 [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md) 或 [LINQ to XML](https://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13)。</span><span class="sxs-lookup"><span data-stu-id="363c6-103">The term "LINQ to Objects" refers to the use of LINQ queries with any <xref:System.Collections.IEnumerable> or <xref:System.Collections.Generic.IEnumerable%601> collection directly, without the use of an intermediate LINQ provider or API such as [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md) or [LINQ to XML](https://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13).</span></span> <span data-ttu-id="363c6-104">可以使用 LINQ 来查询任何可枚举的集合，例如 <xref:System.Collections.Generic.List%601>、<xref:System.Array> 或 <xref:System.Collections.Generic.Dictionary%602>。</span><span class="sxs-lookup"><span data-stu-id="363c6-104">You can use LINQ to query any enumerable collections such as <xref:System.Collections.Generic.List%601>, <xref:System.Array>, or <xref:System.Collections.Generic.Dictionary%602>.</span></span> <span data-ttu-id="363c6-105">该集合可以是用户定义的集合，也可以是由 .NET Framework API 返回的集合。</span><span class="sxs-lookup"><span data-stu-id="363c6-105">The collection may be user-defined or may be returned by a .NET Framework API.</span></span>  
  
 <span data-ttu-id="363c6-106">从根本上说，“LINQ to Objects”表示一种新的处理集合的方法。</span><span class="sxs-lookup"><span data-stu-id="363c6-106">In a basic sense, LINQ to Objects represents a new approach to collections.</span></span> <span data-ttu-id="363c6-107">采用旧方法，必须编写指定如何从集合检索数据的复杂的 `For Each` 循环。</span><span class="sxs-lookup"><span data-stu-id="363c6-107">In the old way, you had to write complex `For Each` loops that specified how to retrieve data from a collection.</span></span> <span data-ttu-id="363c6-108">而采用 LINQ 方法，只需编写描述要检索的内容的声明性代码。</span><span class="sxs-lookup"><span data-stu-id="363c6-108">In the LINQ approach, you write declarative code that describes what you want to retrieve.</span></span>  
  
 <span data-ttu-id="363c6-109">此外，LINQ 查询与传统 `For Each` 循环相比具有三大优势：</span><span class="sxs-lookup"><span data-stu-id="363c6-109">In addition, LINQ queries offer three main advantages over traditional `For Each` loops:</span></span>  
  
1.  <span data-ttu-id="363c6-110">它们更简明、更易读，尤其在筛选多个条件时。</span><span class="sxs-lookup"><span data-stu-id="363c6-110">They are more concise and readable, especially when filtering multiple conditions.</span></span>  
  
2.  <span data-ttu-id="363c6-111">它们使用最少的应用程序代码提供强大的筛选、排序和分组功能。</span><span class="sxs-lookup"><span data-stu-id="363c6-111">They provide powerful filtering, ordering, and grouping capabilities with a minimum of application code.</span></span>  
  
3.  <span data-ttu-id="363c6-112">无需修改或只需做很小的修改即可将它们移植到其他数据源。</span><span class="sxs-lookup"><span data-stu-id="363c6-112">They can be ported to other data sources with little or no modification.</span></span>  
  
 <span data-ttu-id="363c6-113">通常，对数据执行的操作越复杂，就越能体会到 LINQ 相较于传统迭代技术的优势。</span><span class="sxs-lookup"><span data-stu-id="363c6-113">In general, the more complex the operation you want to perform on the data, the more benefit you will realize by using LINQ instead of traditional iteration techniques.</span></span>  
  
 <span data-ttu-id="363c6-114">本节的目的是使用一些精选示例来演示 LINQ 方法。</span><span class="sxs-lookup"><span data-stu-id="363c6-114">The purpose of this section is to demonstrate the LINQ approach with some select examples.</span></span> <span data-ttu-id="363c6-115">并不打算详尽说明。</span><span class="sxs-lookup"><span data-stu-id="363c6-115">It is not intended to be exhaustive.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="363c6-116">本节内容</span><span class="sxs-lookup"><span data-stu-id="363c6-116">In This Section</span></span>  
 [<span data-ttu-id="363c6-117">LINQ 和字符串 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="363c6-117">LINQ and Strings (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)  
 <span data-ttu-id="363c6-118">阐释如何使用 LINQ 来查询和转换字符串和字符串集合。</span><span class="sxs-lookup"><span data-stu-id="363c6-118">Explains how LINQ can be used to query and transform strings and collections of strings.</span></span> <span data-ttu-id="363c6-119">还包括指向演示这些原则的主题的链接。</span><span class="sxs-lookup"><span data-stu-id="363c6-119">Also includes links to topics that demonstrate these principles.</span></span>  
  
 [<span data-ttu-id="363c6-120">LINQ 和反射 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="363c6-120">LINQ and Reflection (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-and-reflection.md)  
 <span data-ttu-id="363c6-121">指向演示 LINQ 如何使用反射的示例的链接。</span><span class="sxs-lookup"><span data-stu-id="363c6-121">Links to a sample that demonstrates how LINQ uses reflection.</span></span>  
  
 [<span data-ttu-id="363c6-122">LINQ 和文件目录 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="363c6-122">LINQ and File Directories (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)  
 <span data-ttu-id="363c6-123">阐释如何使用 LINQ 来与文件系统进行交互。</span><span class="sxs-lookup"><span data-stu-id="363c6-123">Explains how LINQ can be used to interact with file systems.</span></span> <span data-ttu-id="363c6-124">还包括指向演示这些概念的主题的链接。</span><span class="sxs-lookup"><span data-stu-id="363c6-124">Also includes links to topics that demonstrate these concepts.</span></span>  
  
 [<span data-ttu-id="363c6-125">如何： 使用 LINQ (Visual Basic) 查询 ArrayList</span><span class="sxs-lookup"><span data-stu-id="363c6-125">How to: Query an ArrayList with LINQ (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-an-arraylist-with-linq.md)  
 <span data-ttu-id="363c6-126">演示如何使用 C# 查询 ArrayList。</span><span class="sxs-lookup"><span data-stu-id="363c6-126">Demonstrates how to query an ArrayList in C#.</span></span>  
  
 [<span data-ttu-id="363c6-127">如何： 为 LINQ 查询 (Visual Basic 中) 添加自定义方法</span><span class="sxs-lookup"><span data-stu-id="363c6-127">How to: Add Custom Methods for LINQ Queries (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-add-custom-methods-for-linq-queries.md)  
 <span data-ttu-id="363c6-128">阐释如何通过向 <xref:System.Collections.Generic.IEnumerable%601> 接口中添加扩展方法来扩展可用于 LINQ 查询的方法集。</span><span class="sxs-lookup"><span data-stu-id="363c6-128">Explains how to extend the set of methods that you can use for LINQ queries by adding extension methods to the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span>  
  
 [<span data-ttu-id="363c6-129">语言集成查询 (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="363c6-129">Language-Integrated Query (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/index.md)  
 <span data-ttu-id="363c6-130">提供指向阐释 LINQ 并提供执行查询的代码示例的主题的链接。</span><span class="sxs-lookup"><span data-stu-id="363c6-130">Provides links to topics that explain LINQ and provide examples of code that perform queries.</span></span>
