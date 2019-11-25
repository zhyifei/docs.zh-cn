---
title: LINQ 介绍
ms.date: 07/20/2015
ms.assetid: c6339c12-9b2d-433e-961c-0d2b7f0091c2
ms.openlocfilehash: add442583bd81665533b704c0c9721b111cddd78
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74338906"
---
# <a name="introduction-to-linq-visual-basic"></a>Introduction to LINQ (Visual Basic)
语言集成查询 (LINQ) 是 .NET Framework 3.5 版中引入的一项创新功能，它在对象领域和数据领域之间架起了一座桥梁。  
  
 数据查询历来都表示为简单的字符串，没有编译时类型检查或 IntelliSense 支持。 此外，对于每种数据源，还需要学习不同的查询语言：SQL 数据库、XML 文档、各种 Web 服务等。 LINQ makes a *query* a first-class language construct in Visual Basic. 可以使用语言关键字和熟悉的运算符针对强类型化对象集合编写查询。  
  
 You can write LINQ queries in Visual Basic for SQL Server databases, XML documents, ADO.NET Datasets, and any collection of objects that supports <xref:System.Collections.IEnumerable> or the generic <xref:System.Collections.Generic.IEnumerable%601> interface. 此外，第三方也为许多 Web 服务和其他数据库实现提供了 LINQ 支持。  
  
 LINQ 查询既可在新项目中使用，也可在现有项目中与非 LINQ 查询一起使用。 唯一的要求是项目应面向 .NET Framework 3.5 或更高版本。  
  
 下图为 Visual Studio 中的图例，显示了使用 C# 和 Visual Basic 针对 SQL Server 数据库编写的不完整 LINQ 查询，并具有完全类型检查和 IntelliSense 支持。  
  
 ![显示具有 Intellisense 的 LINQ 查询的图表。](./media/introduction-to-linq/linq-query-intellisense.png)  
  
## <a name="next-steps"></a>后续步骤  
 To learn more details about LINQ, start by becoming familiar with some basic concepts in the Getting Started section [Getting Started with LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md), and then read the documentation for the LINQ technology in which you are interested:  
  
- SQL Server 数据库：[LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)  
  
- XML documents: [LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md)  
  
- ADO.NET 数据集：[LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)  
  
- .NET collections, files, strings and so on: [LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)  
  
## <a name="see-also"></a>请参阅

- [语言集成查询 (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/index.md)
