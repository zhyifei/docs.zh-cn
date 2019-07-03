---
title: LINQ 和 ADO.NET
ms.date: 03/30/2017
ms.assetid: bf0c8f93-3ff7-49f3-8aed-f2b7ac938dec
ms.openlocfilehash: 9c517b3efca8cd2b41782858ef1e18e3cba76c1b
ms.sourcegitcommit: b5c59eaaf8bf48ef3ec259f228cb328d6d4c0ceb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2019
ms.locfileid: "67539412"
---
# <a name="linq-and-adonet"></a>LINQ 和 ADO.NET
如今，许多业务开发人员必须使用两个 （或多个） 的编程语言： 对于业务逻辑和表示层的高级语言 (如视觉对象C#或 Visual Basic)，而使用查询语言与数据库 （如 Transact SQL) 进行交互. 这要求开发人员精通多种语言才能奏效，同时也导致在开发环境中语言不匹配。 例如，使用数据访问 API 对数据库执行查询的应用程序会将查询指定为用引号括起的字符串。 编译器不能读取此查询字符串，因此不会检查是否有错误，如语法无效或引用的列或行是否实际存在。 不会检查查询参数的类型，也不支持 `IntelliSense`。  
  
 [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] 使开发人员能够在应用程序代码中形成基于集合的查询，而不必使用单独的查询语言。 您可以编写针对各种可枚举数据源（即实现 [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] 接口的数据源）的 <xref:System.Collections.IEnumerable> 查询，可枚举数据源包括驻留在内存中的数据结构、XML 文档、SQL 数据库和 <xref:System.Data.DataSet> 对象等。 虽然这些可枚举数据源以多种方式实现，但它们都公开相同的语法和语言构造。 由于可以使用编程语言本身形成查询，因此您不必使用编译器无法理解或验证的以字符串形式嵌入的其他查询语言。 将查询集成到编程语言也使 Visual Studio 编程人员能够通过提供编译时类型和语法检查，提高工作效率和`IntelliSense`。 这些功能降低了对查询调试和错误修复的需求。  
  
 将数据从 SQL 表传输到内存中的对象通常单调乏味并容易出错。 [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]提供程序实现的 LINQ to DataSet 和[!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)]将转换源数据插入<xref:System.Collections.IEnumerable>-基于对象的集合。 在您查询数据和更新数据时，程序员始终会以 <xref:System.Collections.IEnumerable> 集合的形式查看这些数据。 为编写针对这些集合的查询提供完全的 `IntelliSense` 支持。  
  
 有三种独立的 ADO.NET [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] 技术：LINQ to DataSet， [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)]，和 LINQ to Entities。 LINQ to DataSet 提供更丰富且经过优化的查询<xref:System.Data.DataSet>和[!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)]使你可直接查询 SQL Server 数据库架构和 LINQ to Entities 可查询实体数据模型。  
  
 下面的关系图概述了 ADO.NET LINQ 技术如何关联到高级编程语言和启用 LINQ 的数据源。  
  
 ![LINQ to ADO.NET 概述](../../../../docs/framework/data/adonet/media/dpue-linqtoadonetoverview-bpuedev11.gif "DPUE_LinqToAdoNetOverview_bpuedev11")  
  
 有关 LINQ 的详细信息，请参阅[语言集成查询 (LINQ)](../../../csharp/programming-guide/concepts/linq/index.md)。
  
 以下各节提供有关 LINQ 的详细信息到数据集， [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)]，和 LINQ to Entities。  
  
## <a name="linq-to-dataset"></a>LINQ to DataSet  
 <xref:System.Data.DataSet>是断开连接的编程模型，ADO.NET 上，构建，并广泛使用的关键元素。 LINQ 到数据集开发人员可以构建更丰富的查询功能<xref:System.Data.DataSet>使用相同的查询表述机制可用于许多其他数据源。 有关详细信息，请参阅 [LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset.md)。  
  
## <a name="linq-to-sql"></a>LINQ to SQL  
 [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] 是适合不需要映射到概念模型的开发人员使用的有用工具。 通过使用 [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)]，您可以直接在现有数据库架构上直接使用 [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] 编程模型。 [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] 使开发人员能够生成表示数据的.NET Framework 类。 这些生成的类直接映射到数据库表、视图、存储过程和用户定义的函数，而不映射到概念数据模型。  
  
 使用 [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] 时，除了其他数据源（如 XML）外，开发人员还可以使用与内存集合和 [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] 相同的 <xref:System.Data.DataSet> 编程模式直接编写针对存储架构的代码。 有关详细信息，请参阅 [LINQ to SQL](../../../../docs/framework/data/adonet/sql/linq/index.md)。  
  
## <a name="linq-to-entities"></a>LINQ to Entities  
 大多数应用程序目前是在关系数据库之上编写的。 有时这些应用程序将需要与以关系形式表示的数据进行交互。 数据库架构并不总是构建应用程序的理想选择，并且应用程序的概念模型与数据库的逻辑模型不同。 实体数据模型是可用于模型的特定域的数据以使应用程序可以与数据作为对象进行交互的概念数据模型。 请参阅[ADO.NET 实体框架](../../../../docs/framework/data/adonet/ef/index.md)有关详细信息。  
  
 通过实体数据模型，在 .NET 环境中将关系数据作为对象公开。 这使得对象层成为实现 [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] 支持的理想目标，开发人员可以采用生成业务逻辑所用的语言来构建数据库查询。 此功能称为 LINQ 到实体。 有关详细信息，请参阅 [LINQ to Entities](../../../../docs/framework/data/adonet/ef/language-reference/linq-to-entities.md)。  
  
## <a name="see-also"></a>请参阅

- [LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset.md)
- [LINQ to SQL](../../../../docs/framework/data/adonet/sql/linq/index.md)
- [LINQ to Entities](../../../../docs/framework/data/adonet/ef/language-reference/linq-to-entities.md)
- [语言集成查询 (LINQ)](../../../csharp/programming-guide/concepts/linq/index.md)
- [ADO.NET 概述](ado-net-overview.md)
