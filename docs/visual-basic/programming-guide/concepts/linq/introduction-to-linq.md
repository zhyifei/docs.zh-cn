---
title: "(Visual Basic 中) 的 LINQ 简介 |Microsoft 文档"
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
ms.assetid: c6339c12-9b2d-433e-961c-0d2b7f0091c2
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: d2c02daacc2674da31715e5fda027b97e6b7bc97
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="introduction-to-linq-visual-basic"></a><span data-ttu-id="dc80c-102">(Visual Basic 中) 的 LINQ 简介</span><span class="sxs-lookup"><span data-stu-id="dc80c-102">Introduction to LINQ (Visual Basic)</span></span>
<span data-ttu-id="dc80c-103">语言集成查询 (LINQ) 是一项新技术引入.NET Framework 3.5 版中，桥世界上的对象和数据领域之间的差距。</span><span class="sxs-lookup"><span data-stu-id="dc80c-103">Language-Integrated Query (LINQ) is an innovation introduced in the .NET Framework version 3.5 that bridges the gap between the world of objects and the world of data.</span></span>  
  
 <span data-ttu-id="dc80c-104">传统上，针对数据的查询表示为简单的字符串，而无需类型检查在编译时间或 IntelliSense 支持。</span><span class="sxs-lookup"><span data-stu-id="dc80c-104">Traditionally, queries against data are expressed as simple strings without type checking at compile time or IntelliSense support.</span></span> <span data-ttu-id="dc80c-105">此外，您还必须学习每种类型的数据源不同的查询语言︰ SQL 数据库、 XML 文档、 各种 Web 服务等。</span><span class="sxs-lookup"><span data-stu-id="dc80c-105">Furthermore, you have to learn a different query language for each type of data source: SQL databases, XML documents, various Web services, and so on.</span></span> <span data-ttu-id="dc80c-106">LINQ 可以*查询*在 Visual Basic 中的一流语言构造。</span><span class="sxs-lookup"><span data-stu-id="dc80c-106">LINQ makes a *query* a first-class language construct in Visual Basic.</span></span> <span data-ttu-id="dc80c-107">使用语言关键字和熟悉的运算符编写针对的对象的强类型化集合的查询。</span><span class="sxs-lookup"><span data-stu-id="dc80c-107">You write queries against strongly typed collections of objects by using language keywords and familiar operators.</span></span>  
  
 <span data-ttu-id="dc80c-108">您可以在 Visual Basic 中编写 LINQ 查询，用于 SQL Server 数据库、 XML 文档、 ADO.NET 数据集和任何支持的对象集合<xref:System.Collections.IEnumerable>或泛型<xref:System.Collections.Generic.IEnumerable%601>接口。</xref:System.Collections.Generic.IEnumerable%601> </xref:System.Collections.IEnumerable></span><span class="sxs-lookup"><span data-stu-id="dc80c-108">You can write LINQ queries in Visual Basic for SQL Server databases, XML documents, ADO.NET Datasets, and any collection of objects that supports <xref:System.Collections.IEnumerable> or the generic <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="dc80c-109">LINQ 支持还由第三方提供的许多 Web 服务和其他数据库实现。</span><span class="sxs-lookup"><span data-stu-id="dc80c-109">LINQ support is also provided by third parties for many Web services and other database implementations.</span></span>  
  
 <span data-ttu-id="dc80c-110">您可以在新项目中，或在现有项目中的非 LINQ 查询以及使用 LINQ 查询。</span><span class="sxs-lookup"><span data-stu-id="dc80c-110">You can use LINQ queries in new projects, or alongside non-LINQ queries in existing projects.</span></span> <span data-ttu-id="dc80c-111">唯一要求是项目面向.NET Framework 3.5 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="dc80c-111">The only requirement is that the project target .NET Framework 3.5 or later.</span></span>  
  
 <span data-ttu-id="dc80c-112">从 Visual Studio 下的图显示部分完成的 LINQ 查询针对 SQL Server 数据库 C# 和 Visual Basic 中使用完整的类型检查和 IntelliSense 支持。</span><span class="sxs-lookup"><span data-stu-id="dc80c-112">The following illustration from Visual Studio shows a partially-completed LINQ query against a SQL Server database in both C# and Visual Basic with full type checking and IntelliSense support.</span></span>  
  
 <span data-ttu-id="dc80c-113">![具有 Intellisense 的 LINQ 查询](../../../../csharp/programming-guide/concepts/linq/media/query_intell.png "Query_Intell")</span><span class="sxs-lookup"><span data-stu-id="dc80c-113">![LINQ query with Intellisense](../../../../csharp/programming-guide/concepts/linq/media/query_intell.png "Query_Intell")</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="dc80c-114">后续步骤</span><span class="sxs-lookup"><span data-stu-id="dc80c-114">Next Steps</span></span>  
 <span data-ttu-id="dc80c-115">若要了解有关 LINQ 的更多详细信息，请首先熟悉的入门部分中的一些基本概念[在 Visual Basic 中的 LINQ 入门](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)，然后阅读您感兴趣的 LINQ 技术的文档︰</span><span class="sxs-lookup"><span data-stu-id="dc80c-115">To learn more details about LINQ, start by becoming familiar with some basic concepts in the Getting Started section [Getting Started with LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md), and then read the documentation for the LINQ technology in which you are interested:</span></span>  
  
-   <span data-ttu-id="dc80c-116">SQL Server 数据库︰ [LINQ to SQL](https://msdn.microsoft.com/library/bb386976)</span><span class="sxs-lookup"><span data-stu-id="dc80c-116">SQL Server databases: [LINQ to SQL](https://msdn.microsoft.com/library/bb386976)</span></span>  
  
-   <span data-ttu-id="dc80c-117">XML 文档︰ [LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md)</span><span class="sxs-lookup"><span data-stu-id="dc80c-117">XML documents: [LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md)</span></span>  
  
-   <span data-ttu-id="dc80c-118">ADO.NET 数据集︰ [LINQ to DataSet](http://msdn.microsoft.com/library/743e3755-3ecb-45a2-8d9b-9ed41f0dcf17)</span><span class="sxs-lookup"><span data-stu-id="dc80c-118">ADO.NET Datasets: [LINQ to DataSet](http://msdn.microsoft.com/library/743e3755-3ecb-45a2-8d9b-9ed41f0dcf17)</span></span>  
  
-   <span data-ttu-id="dc80c-119">.NET 集合、 文件、 字符串等︰ [LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)</span><span class="sxs-lookup"><span data-stu-id="dc80c-119">.NET collections, files, strings and so on: [LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc80c-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dc80c-120">See Also</span></span>  
 [<span data-ttu-id="dc80c-121">语言集成查询 (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dc80c-121">Language-Integrated Query (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/index.md)
