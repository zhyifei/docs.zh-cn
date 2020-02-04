---
title: LINQ 和 ADO.NET
titleSuffix: ''
ms.date: 03/30/2017
ms.assetid: bf0c8f93-3ff7-49f3-8aed-f2b7ac938dec
ms.openlocfilehash: e24473f68fe5ccd993c5d205660ea8f397b6f797
ms.sourcegitcommit: 19014f9c081ca2ff19652ca12503828db8239d48
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "76980088"
---
# <a name="linq-and-adonet"></a>LINQ 和 ADO.NET
如今，许多业务开发人员都必须使用两种或多种编程语言：用于业务逻辑和表示层（如视觉对象C#或 Visual Basic）的高级语言，以及与数据库交互的查询语言（如 transact-sql）。 这要求开发人员精通多种语言才能奏效，同时也导致在开发环境中语言不匹配。 例如，使用数据访问 API 对数据库执行查询的应用程序会将查询指定为用引号括起的字符串。 编译器不能读取此查询字符串，因此不会检查是否有错误，如语法无效或引用的列或行是否实际存在。 不会检查查询参数的类型，也不支持 `IntelliSense`。  
  
 使用语言集成查询（LINQ），开发人员可以在其应用程序代码中形成基于集的查询，而不必使用单独的查询语言。 您可以针对各种可枚举数据源（即实现 <xref:System.Collections.IEnumerable> 接口的数据源）编写 LINQ 查询，例如内存中数据结构、XML 文档、SQL 数据库和 <xref:System.Data.DataSet> 对象。 虽然这些可枚举数据源以多种方式实现，但它们都公开相同的语法和语言构造。 由于可以使用编程语言本身形成查询，因此您不必使用编译器无法理解或验证的以字符串形式嵌入的其他查询语言。 将查询集成到编程语言中，可通过提供编译时类型和语法检查并 `IntelliSense`，使 Visual Studio 程序员提高工作效率。 这些功能降低了对查询调试和错误修复的需求。  
  
 将数据从 SQL 表传输到内存中的对象通常单调乏味并容易出错。 LINQ to DataSet 和 [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] 实现的 LINQ 提供程序将源数据转换为基于 <xref:System.Collections.IEnumerable>的对象集合。 在您查询数据和更新数据时，程序员始终会以 <xref:System.Collections.IEnumerable> 集合的形式查看这些数据。 为编写针对这些集合的查询提供完全的 `IntelliSense` 支持。  
  
 有三个独立的 ADO.NET 语言集成查询（LINQ）技术： LINQ to DataSet、[!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)]和 LINQ to Entities。 LINQ to DataSet 通过 <xref:System.Data.DataSet> 提供更丰富的优化查询，[!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] 使你可以直接查询 SQL Server 的数据库架构，而 LINQ to Entities 允许查询实体数据模型。  
  
 下面的关系图概述了 ADO.NET LINQ 技术如何关联到高级编程语言和启用 LINQ 的数据源。  
  
 ![LINQ to ADO.NET 概述](./media/dpue-linqtoadonetoverview-bpuedev11.gif "DPUE_LinqToAdoNetOverview_bpuedev11")  
  
 有关 LINQ 的详细信息，请参阅[语言集成查询（LINQ）](../../../csharp/programming-guide/concepts/linq/index.md)。
  
 以下各节提供了有关 LINQ to DataSet、[!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)]和 LINQ to Entities 的详细信息。  
  
## <a name="linq-to-dataset"></a>LINQ to DataSet  
 <xref:System.Data.DataSet> 是 ADO.NET 在其上构建的断开连接的编程模型的关键元素，广泛使用。 LINQ to DataSet 使开发人员可以使用可用于许多其他数据源的相同查询表述机制，将更丰富的查询功能构建到 <xref:System.Data.DataSet> 中。 有关详细信息，请参阅 [LINQ to DataSet](linq-to-dataset.md)。  
  
## <a name="linq-to-sql"></a>LINQ to SQL  
 [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] 是适合不需要映射到概念模型的开发人员使用的有用工具。 通过使用 [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)]，可以直接在现有数据库架构上使用 LINQ 编程模型。 [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] 使开发人员能够生成表示数据 .NET Framework 类。 这些生成的类直接映射到数据库表、视图、存储过程和用户定义的函数，而不映射到概念数据模型。  
  
 在 [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)]中，开发人员可以使用与内存中集合和 <xref:System.Data.DataSet>相同的 LINQ 编程模式，以及 XML 等其他数据源，直接针对存储架构编写代码。 有关详细信息，请参阅 [LINQ to SQL](./sql/linq/index.md)。  
  
## <a name="linq-to-entities"></a>LINQ to Entities  
 大多数应用程序目前是在关系数据库之上编写的。 有时这些应用程序将需要与以关系形式表示的数据进行交互。 数据库架构并不总是构建应用程序的理想选择，并且应用程序的概念模型与数据库的逻辑模型不同。 实体数据模型是一种概念数据模型，可用于对特定域的数据进行建模，使应用程序能够以对象的形式与数据进行交互。 有关详细信息，请参阅[ADO.NET 实体框架](./ef/index.md)。  
  
 通过实体数据模型，在 .NET 环境中将关系数据作为对象公开。 这使得对象层成为实现 LINQ 支持的理想目标，开发人员可以采用生成业务逻辑所用的语言来构建数据库查询。 此功能称为 LINQ to Entities。 有关详细信息，请参阅 [LINQ to Entities](./ef/language-reference/linq-to-entities.md)。  
  
## <a name="see-also"></a>另请参阅

- [LINQ to DataSet](linq-to-dataset.md)
- [LINQ to SQL](./sql/linq/index.md)
- [LINQ to Entities](./ef/language-reference/linq-to-entities.md)
- [语言集成查询 (LINQ)](../../../csharp/programming-guide/concepts/linq/index.md)
- [ADO.NET 概述](ado-net-overview.md)
