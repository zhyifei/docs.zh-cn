---
title: "DataSet、DataTable 和 DataView | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6d4c4b69-8919-4224-8a65-6cca1c61b48f
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# DataSet、DataTable 和 DataView
ADO.NET <xref:System.Data.DataSet> 是数据的一种内存驻留表示形式，无论它包含的数据来自什么数据源，都会提供一致的关系编程模型。  <xref:System.Data.DataSet> 表示整个数据集，其中包含对数据进行包含、排序和约束的表以及表间的关系。  
  
 使用 <xref:System.Data.DataSet> 的方法有若干种，这些方法可以单独应用，也可以结合应用。  你可以：  
  
-   以编程方式在 <xref:System.Data.DataSet> 中创建 <xref:System.Data.DataTable>、<xref:System.Data.DataRelation> 和 <xref:System.Data.Constraint>，并使用数据填充表。  
  
-   通过 `DataAdapter` 用现有关系数据源中的数据表填充 <xref:System.Data.DataSet>。  
  
-   使用 XML 加载和保持 <xref:System.Data.DataSet> 内容。  有关详细信息，请参阅[在 DataSet 中使用 XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)。  
  
 强类型化的 <xref:System.Data.DataSet> 也可以使用 XML Web services 来进行传输。  <xref:System.Data.DataSet> 的设计使其成为使用 XML Web services 传输数据的理想选择。  有关 XML Web services 的概述，请参见 [XML Web Services Overview](http://msdn.microsoft.com/zh-cn/9db0c7b8-bca6-462b-9be5-f5f9a7f05a4d)。  有关通过 XML Web services 使用 <xref:System.Data.DataSet> 的示例，请参见[通过 XML Web services 使用 DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/consuming-a-dataset-from-an-xml-web-service.md)。  
  
## 本节内容  
 [创建 DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-dataset.md)  
 描述创建 <xref:System.Data.DataSet> 实例的语法。  
  
 [向 DataSet 添加 DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-a-datatable-to-a-dataset.md)  
 描述如何创建表和列并将其添加到 <xref:System.Data.DataSet> 中。  
  
 [添加 DataRelation](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-datarelations.md)  
 描述如何创建 <xref:System.Data.DataSet> 中表之间的关系。  
  
 [导航 DataRelation](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/navigating-datarelations.md)  
 描述如何使用 <xref:System.Data.DataSet> 中表之间的关系来返回具有父子关系的子行或父行。  
  
 [合并 DataSet 内容](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/merging-dataset-contents.md)  
 描述如何将一个 <xref:System.Data.DataSet>、<xref:System.Data.DataTable> 或 <xref:System.Data.DataRow> 数组的内容合并到另一个 <xref:System.Data.DataSet> 中。  
  
 [复制 DataSet 内容](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/copying-dataset-contents.md)  
 描述如何创建可包含架构和指定数据的 <xref:System.Data.DataSet> 副本。  
  
 [处理数据集事件](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-dataset-events.md)  
 描述 <xref:System.Data.DataSet> 的事件并说明如何使用这些事件。  
  
 [类型化数据集](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)  
 描述类型化 <xref:System.Data.DataSet> 的定义并说明如何创建和使用。  
  
 [DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 描述如何创建 <xref:System.Data.DataTable>、定义架构和处理数据。  
  
 [DataTableReader](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatablereaders.md)  
 描述如何创建和使用 <xref:System.Data.DataTableReader>。  
  
 [DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 描述如何创建和使用 `DataViews` 以及如何使用 <xref:System.Data.DataView> 事件。  
  
 [在 DataSet 中使用 XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 描述 <xref:System.Data.DataSet> 如何作为数据源与 XML 进行交互（包括以 XML 数据的形式加载和保持 <xref:System.Data.DataSet> 的内容）。  
  
 [通过 XML Web services 使用 DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/consuming-a-dataset-from-an-xml-web-service.md)  
 描述如何创建使用 <xref:System.Data.DataSet> 来传输数据的 XML Web services。  
  
## 相关章节  
 [ADO.NET 中的新增功能](../../../../../docs/framework/data/adonet/whats-new.md)  
 介绍 ADO.NET 中的新增功能。  
  
 [ADO.NET 概述](../../../../../docs/framework/data/adonet/ado-net-overview.md)  
 提供对 ADO.NET 设计和组件的介绍。  
  
 [从 DataAdapter 填充数据集](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)  
 描述如何从数据源加载包含数据的 **DataSet**。  
  
 [使用 DataAdapter 更新数据源](../../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md)  
 描述如何将对 **DataSet** 中数据的更改解析回数据源。  
  
 [向 DataSet 添加现有约束](../../../../../docs/framework/data/adonet/adding-existing-constraints-to-a-dataset.md)  
 描述如何使用数据源中的主键信息填充 **DataSet**。  
  
## 请参阅  
 [ADO.NET](../../../../../docs/framework/data/adonet/index.md)   
 [ADO.NET 托管提供程序和数据集开发人员中心](http://go.microsoft.com/fwlink/?LinkId=217917)