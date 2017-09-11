---
title: "LINQ 简介 (C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 54874feb-55e5-4ca8-a9d6-1c1127fd7fb1
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: d90ea2503ba94df8ddb750b6f328168ddf22a65a
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="introduction-to-linq-c"></a><span data-ttu-id="f5b3c-102">LINQ 简介 (C#)</span><span class="sxs-lookup"><span data-stu-id="f5b3c-102">Introduction to LINQ (C#)</span></span>
<span data-ttu-id="f5b3c-103">语言集成查询 (LINQ) 是 .NET Framework 3.5 版中引入的一项创新功能，它在对象领域和数据领域之间架起了一座桥梁。</span><span class="sxs-lookup"><span data-stu-id="f5b3c-103">Language-Integrated Query (LINQ) is an innovation introduced in the .NET Framework version 3.5 that bridges the gap between the world of objects and the world of data.</span></span>  
  
 <span data-ttu-id="f5b3c-104">传统上，针对数据的查询都以简单的字符串表示，而没有编译时类型检查或 IntelliSense 支持。</span><span class="sxs-lookup"><span data-stu-id="f5b3c-104">Traditionally, queries against data are expressed as simple strings without type checking at compile time or IntelliSense support.</span></span> <span data-ttu-id="f5b3c-105">此外，还需要针对每种数据源学习一种不同的查询语言：SQL 数据库、XML 文档、各种 Web 服务等等。</span><span class="sxs-lookup"><span data-stu-id="f5b3c-105">Furthermore, you have to learn a different query language for each type of data source: SQL databases, XML documents, various Web services, and so on.</span></span> <span data-ttu-id="f5b3c-106">LINQ 使查询成为 C# 中的一流语言构造。</span><span class="sxs-lookup"><span data-stu-id="f5b3c-106">LINQ makes a *query* a first-class language construct in C#.</span></span> <span data-ttu-id="f5b3c-107">可以使用语言关键字和熟悉的运算符针对强类型化对象集合编写查询。</span><span class="sxs-lookup"><span data-stu-id="f5b3c-107">You write queries against strongly typed collections of objects by using language keywords and familiar operators.</span></span>  
  
 <span data-ttu-id="f5b3c-108">在 C# 中可为以下对象编写 LINQ 查询：SQL Server 数据库、XML 文档、ADO.NET 数据集以及支持 <xref:System.Collections.IEnumerable> 或泛型 <xref:System.Collections.Generic.IEnumerable%601> 接口的任何对象集合。</span><span class="sxs-lookup"><span data-stu-id="f5b3c-108">You can write LINQ queries in C# for SQL Server databases, XML documents, ADO.NET Datasets, and any collection of objects that supports <xref:System.Collections.IEnumerable> or the generic <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="f5b3c-109">此外，第三方也为许多 Web 服务和其他数据库实现提供了 LINQ 支持。</span><span class="sxs-lookup"><span data-stu-id="f5b3c-109">LINQ support is also provided by third parties for many Web services and other database implementations.</span></span>  
  
 <span data-ttu-id="f5b3c-110">LINQ 查询既可在新项目中使用，也可在现有项目中与非 LINQ 查询一起使用。</span><span class="sxs-lookup"><span data-stu-id="f5b3c-110">You can use LINQ queries in new projects, or alongside non-LINQ queries in existing projects.</span></span> <span data-ttu-id="f5b3c-111">唯一的要求是项目应面向 .NET Framework 3.5 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="f5b3c-111">The only requirement is that the project target .NET Framework 3.5 or later.</span></span>  
  
 <span data-ttu-id="f5b3c-112">下图为 Visual Studio 中的图例，显示了使用 C# 和 Visual Basic 针对 SQL Server 数据库编写的不完整 LINQ 查询，并具有完全类型检查和 IntelliSense 支持。</span><span class="sxs-lookup"><span data-stu-id="f5b3c-112">The following illustration from Visual Studio shows a partially-completed LINQ query against a SQL Server database in both C# and Visual Basic with full type checking and IntelliSense support.</span></span>  
  
 <span data-ttu-id="f5b3c-113">![具有 Intellisense 的 LINQ 查询](../../../../csharp/programming-guide/concepts/linq/media/query_intell.png "Query_Intell")</span><span class="sxs-lookup"><span data-stu-id="f5b3c-113">![LINQ query with Intellisense](../../../../csharp/programming-guide/concepts/linq/media/query_intell.png "Query_Intell")</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="f5b3c-114">后续步骤</span><span class="sxs-lookup"><span data-stu-id="f5b3c-114">Next Steps</span></span>  
 <span data-ttu-id="f5b3c-115">若要了解有关 LINQ 的详细信息，请先熟悉入门部分 [C# 中的 LINQ 入门](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)中的一些基本概念，然后阅读你感兴趣的 LINQ 技术的文档：</span><span class="sxs-lookup"><span data-stu-id="f5b3c-115">To learn more details about LINQ, start by becoming familiar with some basic concepts in the Getting Started section [Getting Started with LINQ in C#](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md), and then read the documentation for the LINQ technology in which you are interested:</span></span>  
  
-   <span data-ttu-id="f5b3c-116">SQL Server 数据库：[LINQ to SQL](https://msdn.microsoft.com/library/bb386976)</span><span class="sxs-lookup"><span data-stu-id="f5b3c-116">SQL Server databases: [LINQ to SQL](https://msdn.microsoft.com/library/bb386976)</span></span>  
  
-   <span data-ttu-id="f5b3c-117">XML 文档：[LINQ to XML (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml.md)</span><span class="sxs-lookup"><span data-stu-id="f5b3c-117">XML documents: [LINQ to XML (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml.md)</span></span>  
  
-   <span data-ttu-id="f5b3c-118">ADO.NET 数据集：[LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)</span><span class="sxs-lookup"><span data-stu-id="f5b3c-118">ADO.NET Datasets: [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)</span></span>  
  
-   <span data-ttu-id="f5b3c-119">.NET 集合、文件、字符串等：[LINQ to Objects (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-objects.md)</span><span class="sxs-lookup"><span data-stu-id="f5b3c-119">.NET collections, files, strings and so on: [LINQ to Objects (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-objects.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5b3c-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="f5b3c-120">See Also</span></span>  
 [<span data-ttu-id="f5b3c-121">语言集成查询 (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="f5b3c-121">Language-Integrated Query (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/index.md)

