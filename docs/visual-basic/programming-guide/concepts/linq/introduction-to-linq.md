---
title: "LINQ (Visual Basic) 简介"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c6339c12-9b2d-433e-961c-0d2b7f0091c2
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3edb26616bf53be8a26522775effd079fafbac97
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="introduction-to-linq-visual-basic"></a><span data-ttu-id="80de6-102">LINQ (Visual Basic) 简介</span><span class="sxs-lookup"><span data-stu-id="80de6-102">Introduction to LINQ (Visual Basic)</span></span>
<span data-ttu-id="80de6-103">语言集成查询 (LINQ) 是 .NET Framework 3.5 版中引入的一项创新功能，它在对象领域和数据领域之间架起了一座桥梁。</span><span class="sxs-lookup"><span data-stu-id="80de6-103">Language-Integrated Query (LINQ) is an innovation introduced in the .NET Framework version 3.5 that bridges the gap between the world of objects and the world of data.</span></span>  
  
 <span data-ttu-id="80de6-104">传统上，针对数据的查询都以简单的字符串表示，而没有编译时类型检查或 IntelliSense 支持。</span><span class="sxs-lookup"><span data-stu-id="80de6-104">Traditionally, queries against data are expressed as simple strings without type checking at compile time or IntelliSense support.</span></span> <span data-ttu-id="80de6-105">此外，对于每种数据源，还需要学习不同的查询语言：SQL 数据库、XML 文档、各种 Web 服务等。</span><span class="sxs-lookup"><span data-stu-id="80de6-105">Furthermore, you have to learn a different query language for each type of data source: SQL databases, XML documents, various Web services, and so on.</span></span> <span data-ttu-id="80de6-106">LINQ 可以*查询*Visual Basic 中的第一类语言构造。</span><span class="sxs-lookup"><span data-stu-id="80de6-106">LINQ makes a *query* a first-class language construct in Visual Basic.</span></span> <span data-ttu-id="80de6-107">可以使用语言关键字和熟悉的运算符针对强类型化对象集合编写查询。</span><span class="sxs-lookup"><span data-stu-id="80de6-107">You write queries against strongly typed collections of objects by using language keywords and familiar operators.</span></span>  
  
 <span data-ttu-id="80de6-108">你可以在 Visual Basic 中为 SQL Server 数据库、 XML 文档、 ADO.NET 数据集和任何支持的对象集合编写 LINQ 查询<xref:System.Collections.IEnumerable>或泛型<xref:System.Collections.Generic.IEnumerable%601>接口。</span><span class="sxs-lookup"><span data-stu-id="80de6-108">You can write LINQ queries in Visual Basic for SQL Server databases, XML documents, ADO.NET Datasets, and any collection of objects that supports <xref:System.Collections.IEnumerable> or the generic <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="80de6-109">此外，第三方也为许多 Web 服务和其他数据库实现提供了 LINQ 支持。</span><span class="sxs-lookup"><span data-stu-id="80de6-109">LINQ support is also provided by third parties for many Web services and other database implementations.</span></span>  
  
 <span data-ttu-id="80de6-110">LINQ 查询既可在新项目中使用，也可在现有项目中与非 LINQ 查询一起使用。</span><span class="sxs-lookup"><span data-stu-id="80de6-110">You can use LINQ queries in new projects, or alongside non-LINQ queries in existing projects.</span></span> <span data-ttu-id="80de6-111">唯一的要求是项目应面向 .NET Framework 3.5 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="80de6-111">The only requirement is that the project target .NET Framework 3.5 or later.</span></span>  
  
 <span data-ttu-id="80de6-112">下图为 Visual Studio 中的图例，显示了使用 C# 和 Visual Basic 针对 SQL Server 数据库编写的不完整 LINQ 查询，并具有完全类型检查和 IntelliSense 支持。</span><span class="sxs-lookup"><span data-stu-id="80de6-112">The following illustration from Visual Studio shows a partially-completed LINQ query against a SQL Server database in both C# and Visual Basic with full type checking and IntelliSense support.</span></span>  
  
 <span data-ttu-id="80de6-113">![具有 Intellisense 的 LINQ 查询](../../../../csharp/programming-guide/concepts/linq/media/query_intell.png "Query_Intell")</span><span class="sxs-lookup"><span data-stu-id="80de6-113">![LINQ query with Intellisense](../../../../csharp/programming-guide/concepts/linq/media/query_intell.png "Query_Intell")</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="80de6-114">后续步骤</span><span class="sxs-lookup"><span data-stu-id="80de6-114">Next Steps</span></span>  
 <span data-ttu-id="80de6-115">若要了解有关 LINQ 的更多详细信息，首先要逐渐熟悉的入门部分中的一些基本概念[在 Visual Basic 中的 LINQ 入门](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)，然后读取您感 LINQ 技术的文档感兴趣：</span><span class="sxs-lookup"><span data-stu-id="80de6-115">To learn more details about LINQ, start by becoming familiar with some basic concepts in the Getting Started section [Getting Started with LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md), and then read the documentation for the LINQ technology in which you are interested:</span></span>  
  
-   <span data-ttu-id="80de6-116">SQL Server 数据库：[LINQ to SQL](https://msdn.microsoft.com/library/bb386976)</span><span class="sxs-lookup"><span data-stu-id="80de6-116">SQL Server databases: [LINQ to SQL](https://msdn.microsoft.com/library/bb386976)</span></span>  
  
-   <span data-ttu-id="80de6-117">XML 文档： [LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md)</span><span class="sxs-lookup"><span data-stu-id="80de6-117">XML documents: [LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md)</span></span>  
  
-   <span data-ttu-id="80de6-118">ADO.NET 数据集：[LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)</span><span class="sxs-lookup"><span data-stu-id="80de6-118">ADO.NET Datasets: [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)</span></span>  
  
-   <span data-ttu-id="80de6-119">.NET 集合、 文件、 字符串等： [LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)</span><span class="sxs-lookup"><span data-stu-id="80de6-119">.NET collections, files, strings and so on: [LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80de6-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="80de6-120">See Also</span></span>  
 [<span data-ttu-id="80de6-121">语言集成查询 (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="80de6-121">Language-Integrated Query (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/index.md)
