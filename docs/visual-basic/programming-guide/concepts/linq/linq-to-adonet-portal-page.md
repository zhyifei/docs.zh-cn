---
title: LINQ to ADO.NET（门户网站页）
ms.date: 07/20/2015
ms.assetid: bbbd7c76-2981-4b91-b8d2-437547181f52
ms.openlocfilehash: 850e154b40e69cc655ee1b59161351b0b2898033
ms.sourcegitcommit: b5c59eaaf8bf48ef3ec259f228cb328d6d4c0ceb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2019
ms.locfileid: "67539382"
---
# <a name="linq-to-adonet-portal-page"></a>LINQ to ADO.NET（门户网站页）
LINQ to ADO.NET，可以使用查询在 ADO.NET 中任何可枚举对象[!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]编程模型。  
  
> [!NOTE]
>  LINQ to ADO.NET 文档位于.NET Framework SDK 的 ADO.NET 部分：[LINQ 和 ADO.NET](../../../../framework/data/adonet/linq-and-ado-net.md)。
  
 有三种独立的 ADO.NET [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] 技术：LINQ to DataSet， [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)]，和 LINQ to Entities。 LINQ to DataSet 提供更丰富且经过优化的查询<xref:System.Data.DataSet>，[!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)]使你可直接查询 SQL Server 数据库架构和 LINQ to Entities 可查询实体数据模型。  
  
## <a name="linq-to-dataset"></a>LINQ to DataSet  
 <xref:System.Data.DataSet> 是 ADO.NET 中使用最广泛的某个组件，也是断开编程模型（构建 ADO.NET 的基础）连接的重要元素。 <xref:System.Data.DataSet> 虽然具有突出的优点，但其查询功能也存在限制。  
  
 LINQ to DataSet，可以生成更丰富的查询功能<xref:System.Data.DataSet>使用相同的查询功能，可用于许多其他数据源。  
  
 有关详细信息，请参阅 [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)。  
  
## <a name="linq-to-sql"></a>LINQ to SQL  
 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] 提供用于将关系数据作为对象进行管理的运行时基础结构。 在 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] 中，关系数据库的数据模型映射到用开发人员所用的编程语言表示的对象模型。 执行应用程序时，[!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] 会将对象模型中的语言集成查询转换为 SQL，然后将其发送到数据库进行执行。 数据库返回结果时，[!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] 会将结果转换回可操作对象。  
  
 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] 包括对数据库中的已存储过程和用户定义的函数和对象模型中的继承的支持。  
  
 有关详细信息，请参阅 [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)。  
  
## <a name="linq-to-entities"></a>LINQ to Entities  
 通过实体数据模型，在 .NET 环境中将关系数据作为对象公开。 这使得对象层成为实现 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 支持的理想目标，开发人员可以采用生成业务逻辑所用的语言来构建数据库查询。 此功能称为 LINQ 到实体。 有关详细信息，请参阅 [LINQ to Entities](../../../../framework/data/adonet/ef/language-reference/linq-to-entities.md)。  
  
## <a name="see-also"></a>请参阅

- [LINQ 和 ADO.NET](../../../../framework/data/adonet/linq-and-ado-net.md)
- [语言集成查询 (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/index.md)
