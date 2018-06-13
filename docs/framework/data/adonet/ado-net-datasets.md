---
title: ADO.NET 数据集
ms.date: 03/30/2017
ms.assetid: 82b641bb-6001-4512-bf1a-2830acdd92ab
ms.openlocfilehash: d7a73b11cae02abf8f61372c8d8684499781dda4
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32758511"
---
# <a name="adonet-datasets"></a>ADO.NET 数据集
<xref:System.Data.DataSet> 对象对于支持 [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] 中的断开连接的分布式数据方案起到至关重要的作用。 **数据集**是的内存驻留表示形式提供一致的关系编程模型，而不考虑数据源的数据。 它可以用于多种不同的数据源，用于 XML 数据，或用于管理应用程序本地的数据。 **数据集**表示一组完整的数据，包括相关的表、 约束和表之间的关系。 下图显示**数据集**对象模型。  
  
 ![ADO.Net 图](../../../../docs/framework/data/adonet/media/ado-1-bpuedev11.png "ado_1_bpuedev11")  
DataSet 对象模型  
  
 方法和中的对象**数据集**与关系数据库模型中保持一致。  
  
 **数据集**还可以保存并重新加载其内容作为 XML 使用，且其架构作为 XML 架构定义语言 (XSD) 架构。 有关详细信息，请参阅[在数据集中使用 XML](../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)。  
  
## <a name="the-datatablecollection"></a>DataTableCollection  
 [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] **数据集**包含一套所表示的零个或多个表<xref:System.Data.DataTable>对象。 <xref:System.Data.DataTableCollection>包含所有**DataTable**中的对象**数据集**。  
  
 A **DataTable**中定义<xref:System.Data>命名空间和表示内存驻留数据的单个表。 其中包含由 <xref:System.Data.DataColumnCollection> 表示的列集合以及由 <xref:System.Data.ConstraintCollection> 表示的约束集合，这两个集合共同定义表的架构。 A **DataTable**还包含一个所表示的行集合<xref:System.Data.DataRowCollection>，其中包含表中的数据。 除了其当前状态之前，<xref:System.Data.DataRow> 还会保留其当前版本和初始版本，以标识对行中存储的值的更改。  
  
## <a name="the-dataview-class"></a>DataView 类  
 您可以利用 <xref:System.Data.DataView> 创建存储在 <xref:System.Data.DataTable>（一种通常在数据绑定应用程序中使用的功能）中的数据的不同视图。 通过使用 <xref:System.Data.DataView>，您可以使用不同的排序顺序公开表中的数据，并且可以按行状态或基于筛选器表达式来筛选数据。 有关详细信息，请参阅[Dataview](../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)。  
  
## <a name="the-datarelationcollection"></a>DataRelationCollection  
 A**数据集**包含中的关系及其<xref:System.Data.DataRelationCollection>对象。 一种关系，由表示<xref:System.Data.DataRelation>对象，其中一个中的行相关联**DataTable**与另一个中的行**DataTable**。 关系类似于可能存在于关系数据库中的主键列和外键列之间的联接路径。 A **DataRelation**标识的两个表中的匹配列**数据集**。  
  
 关系可以从一个表导航到另一种**数据集**。 重要元素**DataRelation**是关系的名称、 相关表的名称和每个表中的相关的列。 关系可以通过一个表的多个列来生成，方法是将一组 <xref:System.Data.DataColumn> 对象指定为键列。 当你添加到关系<xref:System.Data.DataRelationCollection>，你可以选择添加**UniqueKeyConstraint**和**ForeignKeyConstraint**相关列发生更改时强制执行完整性约束值。  
  
 有关详细信息，请参阅[添加 Datarelation](../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-datarelations.md)。  
  
## <a name="xml"></a>XML  
 你可以填写**数据集**从 XML 流或文档。 你可以使用 XML 流或文档要提供给**数据集**数据、 架构信息或两者。 从 XML 流或文档中提供的信息可以与现有数据或架构信息已存在于组合**数据集**。 有关详细信息，请参阅[在数据集中使用 XML](../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)。  
  
## <a name="extendedproperties"></a>ExtendedProperties  
 **数据集**， **DataTable**，和**DataColumn**所有具有**ExtendedProperties**属性。 **ExtendedProperties**是**PropertyCollection**可以放置自定义的信息，如 SELECT 语句用于生成结果集或生成数据的时间。 **ExtendedProperties**架构信息一起持久化集合**数据集**。  
  
## <a name="linq-to-dataset"></a>LINQ to DataSet  
 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]为数据集中存储的已断开连接的数据提供语言集成查询功能。 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 使用标准[!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]语法，并使用 Visual Studio IDE 时提供编译时语法检查、 静态类型和 IntelliSense 支持。  
  
 有关详细信息，请参阅 [LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset.md)。  
  
## <a name="see-also"></a>请参阅  
 [ADO.NET 概述](../../../../docs/framework/data/adonet/ado-net-overview.md)  
 [数据集、数据表和数据视图](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [在 ADO.NET 中检索和修改数据](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [ADO.NET 托管提供程序和数据集开发人员中心](http://go.microsoft.com/fwlink/?LinkId=217917)
