---
title: 为 LINQ Querying2 启用数据源
ms.date: 07/20/2015
ms.assetid: c412f0cf-ff0e-4993-ab3d-1b49e23f00f8
ms.openlocfilehash: ecd43b371a8e907e9bcfc8687c04bdd0350235ac
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636882"
---
# <a name="enabling-a-data-source-for-linq-querying"></a>启用数据源以进行 LINQ 查询

可以通过多种方式来扩展 LINQ，以便能够在 LINQ 模式中查询任何数据源。 数据源可以是数据结构、Web 服务、文件系统或数据库等。 LINQ 模式使客户端可以轻松地查询启用了 LINQ 查询的数据源，因为查询的语法和模式没有更改。 LINQ 可以扩展到这些数据源的方式包括：

- 在类型中实现 <xref:System.Collections.Generic.IEnumerable%601> 接口，以启用对该类型的 LINQ to Objects 查询。

- 创建标准查询运算符方法（如 <xref:System.Linq.Enumerable.Where%2A>）和扩展类型的 <xref:System.Linq.Enumerable.Select%2A>，以启用该类型的自定义 LINQ 查询。

- 为实现 <xref:System.Linq.IQueryable%601> 接口的数据源创建一个提供程序。 实现此接口的提供程序以表达式树的形式接收 LINQ 查询，该查询可以通过自定义方式（例如远程）来执行。

- 为数据源创建一个利用现有 LINQ 技术的提供程序。 这种提供程序不仅能够进行查询，而且能够为用户定义的类型插入、更新和删除操作及映射。

本主题将讨论这些选项。

## <a name="how-to-enable-linq-querying-of-your-data-source"></a>如何使 LINQ 能够查询您的数据源

### <a name="in-memory-data"></a>内存中的数据
 可以通过两种方式来启用对内存中数据的 LINQ 查询。 如果数据是实现 <xref:System.Collections.Generic.IEnumerable%601>的类型，则可以使用 LINQ to Objects 查询数据。 如果通过实现 <xref:System.Collections.Generic.IEnumerable%601> 接口来启用类型的枚举是有意义的，则可以在该类型中定义 LINQ 标准查询运算符方法，或创建用于扩展类型的 LINQ 标准查询运算符方法。 标准查询运算符的自定义实现应使用延迟执行来返回结果。

### <a name="remote-data"></a>远程数据
 启用远程数据源 LINQ 查询的最佳选项是实现 <xref:System.Linq.IQueryable%601> 接口。 但是，这与为数据源扩展提供程序（比如 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)]）有所不同。 Visual Studio 2008 中提供了用于将现有 LINQ 技术（例如 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)]）扩展到其他类型的数据源的提供程序模型。

## <a name="iqueryable-linq-providers"></a>IQueryable LINQ 提供程序
 实现 <xref:System.Linq.IQueryable%601> 的 LINQ 提供程序的复杂性可能会很大。 本节讨论这些不同程度的复杂性。

 复杂性较低的 `IQueryable` 提供程序可与 Web 服务的一个方法交互。 这种类型的提供程序非常具体，因为它需要所处理的查询中有具体信息。 它有封闭的类型系统，可能会公开单一结果类型。 大多数查询都是在本地执行的，例如，通过使用标准查询运算符的 <xref:System.Linq.Enumerable> 实现来执行。 复杂性较低的提供程序可能只会检查表示查询的表达式树中的一个方法调用表达式，并允许在其他地方处理查询的其余逻辑。

 中等复杂性的 `IQueryable` 提供程序可能针对具有部分可表达查询语言的数据源。 如果该提供程序针对 Web 服务，它可以与 Web 服务的多个方法进行交互，并基于查询提出的问题选择要调用的方法。 与简单提供程序相比，中等复杂性的提供程序的类型系统较丰富，但它仍然是固定类型系统。 例如，提供程序可以公开具有可遍历的一对多关系的类型，但将不会为用户定义的类型提供映射技术。

 复杂的 `IQueryable` 提供程序（如 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] 提供程序）可能会将完整的 LINQ 查询转换为可表达查询语言（如 SQL）。 与复杂性较低的提供程序相比，复杂的提供程序更为全面，因为它能在查询中处理各种各样的问题。 它还具有开放的类型系统，因而必须包含广泛的基础结构来映射用户定义的类型。 开发复杂的提供程序需要耗费大量的精力。

## <a name="see-also"></a>另请参阅

- <xref:System.Linq.IQueryable%601>
- <xref:System.Collections.Generic.IEnumerable%601>
- <xref:System.Linq.Enumerable>
- [标准查询运算符概述 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)
