---
title: LINQ to DataSet 概述
ms.date: 03/30/2017
ms.assetid: dc20a8fb-03f6-4b68-9c2b-7f7299e3070b
ms.openlocfilehash: de49febdc81eaf4f487423c5804d1e5cc897cdce
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70794964"
---
# <a name="linq-to-dataset-overview"></a>LINQ to DataSet 概述
<xref:System.Data.DataSet>是 ADO.NET 的更广泛使用的组件之一。 它是 ADO.NET 所基于的断开连接式编程模型的关键元素，它使你能够从不同的数据源中显式缓存数据。 在表示层上，<xref:System.Data.DataSet> 与 GUI 控件紧密集成，以进行数据绑定。 在中间层上，它提供保留数据关系形状的缓存并包括快速简单查询和层次结构导航服务。 用于减少对数据库的请求数的常用技术是使用 <xref:System.Data.DataSet> 以便在中间层进行缓存。 例如，考虑一个数据驱动的 ASP.NET Web 应用程序。 通常，应用程序的绝大部分数据不会经常更改，属于会话之间或用户之间的公共数据。 此数据可以保存在 Web 服务器的内存中，这会减少对数据库的请求数并加速用户的交互。 的另一个有用方面<xref:System.Data.DataSet>是允许应用程序将一个或多个数据源中的数据子集引入应用程序空间。 然后，应用程序可以在内存中操作这些数据，同时保留其关系形状。  
  
 <xref:System.Data.DataSet> 虽然具有突出的优点，但其查询功能也存在限制。 <xref:System.Data.DataTable.Select%2A> 方法可用于筛选和排序，<xref:System.Data.DataRow.GetChildRows%2A> 和 <xref:System.Data.DataRow.GetParentRow%2A> 方法可用于层次结构导航。 但对于更复杂的情况，开发人员必须编写自定义查询。 这会使应用程序性能低下并且难以维护。  
  
 LINQ to DataSet 可以更轻松、更快速地查询在<xref:System.Data.DataSet>对象中缓存的数据。 这些查询用编程语言本身表示，而不表示为嵌入在应用程序代码中的字符串。 这意味着开发人员不必学习单独的查询语言。 此外，LINQ to DataSet 使 Visual Studio 开发人员能够更高效地工作，因为 Visual Studio IDE 为提供编译时语法检查、静态类型和 IntelliSense 支持[!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]。 LINQ to DataSet 还可以用于查询从一个或多个数据源合并的数据。 这可以使许多需要灵活表示和处理数据的方案能够实现。 具体地说，一般报告、分析和业务智能应用程序将需要这种操作方法。  
  
## <a name="querying-datasets-using-linq-to-dataset"></a>使用 LINQ to DataSet 查询数据集  
 在开始使用 LINQ to DataSet 查询<xref:System.Data.DataSet>对象之前，必须<xref:System.Data.DataSet>填充。 可以<xref:System.Data.DataSet>[通过多种](./sql/linq/index.md)方法将数据加载到中，如使用类或LINQtoSQL。<xref:System.Data.Common.DataAdapter> 将数据加载到 <xref:System.Data.DataSet> 对象后，可以开始查询数据。 使用 LINQ to DataSet 来构建查询类似于对[!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)]其他[!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]启用的数据源使用。 [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]可以通过<xref:System.Data.DataSet> <xref:System.Linq.Enumerable.Join%2A>使用和<xref:System.Linq.Enumerable.GroupJoin%2A>标准查询运算符对中的单个表或针对多个表执行查询。  
  
 支持对类型化和非类型化 [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] 对象执行 <xref:System.Data.DataSet> 查询。 如果在应用程序设计时已知 <xref:System.Data.DataSet> 的架构，则建议使用类型化 <xref:System.Data.DataSet>。 在类型化 <xref:System.Data.DataSet> 中，表和行对每个列都具有类型化成员，从而使查询更简单并且更具可读性。  
  
 除了在 system.exception 中实现的标准查询运算符外，LINQ to DataSet 还添加了多个<xref:System.Data.DataSet>特定的扩展，使你可以更轻松地对一<xref:System.Data.DataRow>组对象进行查询。 这些 <xref:System.Data.DataSet> 特定扩展包括用于比较行序列的运算符以及用于访问 <xref:System.Data.DataRow> 的列值的方法。  
  
## <a name="n-tier-applications-and-linq-to-dataset"></a>N 层应用程序和 LINQ to DataSet  
 N 层数据应用程序是以数据为中心的应用程序，分为多个逻辑层（或层）。 典型的 N 层应用程序包括一个表示层、一个中间层和一个数据层。 将应用程序组件分离到不同的层可提高应用程序的可维护性和可伸缩性。 有关 N 层数据应用程序的详细信息，请参阅[使用 n 层应用程序中的数据集](/visualstudio/data-tools/work-with-datasets-in-n-tier-applications)。  
  
 在 N 层应用程序中，<xref:System.Data.DataSet> 通常用于中间层以缓存 Web 应用程序的信息。 LINQ to DataSet 查询功能通过扩展方法实现，并扩展现有的 ADO.NET 2.0 <xref:System.Data.DataSet>。  
  
## <a name="see-also"></a>请参阅

- [查询数据集](querying-datasets-linq-to-dataset.md)
- [语言集成查询 (LINQ) - C#](../../../csharp/programming-guide/concepts/linq/index.md)
- [语言集成查询 (LINQ) - Visual Basic](../../../visual-basic/programming-guide/concepts/linq/index.md)
- [LINQ to SQL](./sql/linq/index.md)
