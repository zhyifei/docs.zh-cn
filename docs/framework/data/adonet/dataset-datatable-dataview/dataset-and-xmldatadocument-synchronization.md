---
title: "数据集和 XmlDataDocument 同步"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 0ce3793d-54b2-47e4-8cf7-b0591cc4dd21
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 923a6b6cf1523c8a11cb509679443b9658e07ce5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="dataset-and-xmldatadocument-synchronization"></a>数据集和 XmlDataDocument 同步
ADO.NET <xref:System.Data.DataSet> 为您提供了数据的关系表示形式。 若要实现分层数据访问，可以使用 .NET Framework 中的可用 XML 类。 以前，数据的这两种表示形式是单独使用的。 不过，.NET Framework 允许对通过数据的关系和分层表示的实时同步访问**数据集**对象和<xref:System.Xml.XmlDataDocument>对象，分别。  
  
 当**数据集**与同步**XmlDataDocument**，这两个对象都使用一组数据。 这意味着，如果更改到**数据集**，此更改将反映在**XmlDataDocument**，反之亦然。 之间的关系**数据集**和**XmlDataDocument**通过允许单个应用程序，使用一组数据，访问生成的服务的整个套件创建极大的灵活性围绕**数据集**（如 Web 窗体和 Windows 窗体控件和 Visual Studio.NET 设计器），以及包括可扩展样式表语言 (XSL)、 XSL 转换 (XSLT) 和 XML 路径的所有 XML 服务套件语言 (XPath)。 您不必选择使应用程序以哪一组服务为目标，这两组服务都可用。  
  
 有多种方法可以同步**数据集**与**XmlDataDocument**。 你可以：  
  
-   填充**数据集**使用架构 （即关系结构） 和数据，然后使其与新同步**XmlDataDocument**。 这将提供现有关系数据的分层视图。 例如:   
  
    ```vb  
    Dim dataSet As DataSet = New DataSet  
  
    ' Add code here to populate the DataSet with schema and data.  
  
    Dim xmlDoc As XmlDataDocument = New XmlDataDocument(dataSet)  
    ```  
  
    ```csharp  
    DataSet dataSet = new DataSet();  
  
    // Add code here to populate the DataSet with schema and data.  
  
    XmlDataDocument xmlDoc = new XmlDataDocument(dataSet);  
    ```  
  
-   填充**数据集**仅使用架构 (如强类型化**数据集**)，使其与同步**XmlDataDocument**，，然后加载**XmlDataDocument**从 XML 文档。 这将提供现有分层数据的关系视图。 表名称和中的列名称你**数据集**架构必须匹配要与其同步的 XML 元素名称。 该匹配区分大小写。  
  
     请注意的架构**数据集**只需匹配要在关系视图中公开的 XML 元素。 这样，就可以具有非常大的 XML 文档，而该文档上可以有非常小的关系“窗口”。 **XmlDataDocument**即使保留整个 XML 文档**数据集**仅公开它的一小部分。 (这的详细示例，请参阅[使 DataSet 与 XmlDataDocument 同步](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/synchronizing-a-dataset-with-an-xmldatadocument.md)。)  
  
     下面的代码示例演示的步骤创建**数据集**和填充其架构，然后将其与同步**XmlDataDocument**。 请注意，**数据集**架构只需要匹配中的元素**XmlDataDocument**你想要公开使用**数据集**。  
  
    ```vb  
    Dim dataSet As DataSet = New DataSet  
  
    ' Add code here to populate the DataSet with schema, but not data.  
  
    Dim xmlDoc As XmlDataDocument = New XmlDataDocument(dataSet)  
    xmlDoc.Load("XMLDocument.xml")  
    ```  
  
    ```csharp  
    DataSet dataSet = new DataSet();  
  
    // Add code here to populate the DataSet with schema, but not data.  
  
    XmlDataDocument xmlDoc = new XmlDataDocument(dataSet);  
    xmlDoc.Load("XMLDocument.xml");  
    ```  
  
     无法加载**XmlDataDocument**如果与同步**数据集**包含数据。 否则会引发异常。  
  
-   创建一个新**XmlDataDocument**和从 XML 文档，加载它，然后访问的数据使用的关系视图**数据集**属性**XmlDataDocument**。 你需要设置的架构**数据集**你可以查看任何中的数据之前**XmlDataDocument**使用**数据集**。 中的表名称和列的名称同样，你**数据集**架构必须匹配要与其同步的 XML 元素名称。 该匹配区分大小写。  
  
     下面的代码示例演示如何访问中的数据的关系视图**XmlDataDocument**。  
  
    ```vb  
    Dim xmlDoc As XmlDataDocument = New XmlDataDocument  
    Dim dataSet As DataSet = xmlDoc.DataSet  
  
    ' Add code here to create the schema of the DataSet to view the data.  
  
    xmlDoc.Load("XMLDocument.xml")  
    ```  
  
    ```csharp  
    XmlDataDocument xmlDoc = new XmlDataDocument();  
    DataSet dataSet = xmlDoc.DataSet;  
  
    // Add code here to create the schema of the DataSet to view the data.  
  
    xmlDoc.Load("XMLDocument.xml");  
    ```  
  
 同步的另一个优点**XmlDataDocument**与**数据集**是避免了 XML 文档的失真。 如果**数据集**填充从 XML 文档使用**ReadXml**，当将数据写回作为 XML 文档使用**WriteXml**可能大大不同于原始 XML 文档。 这是因为**数据集**不维护格式设置，如空格或分层信息，如元素顺序，从 XML 文档。 **数据集**也不包含 XML 文档中已忽略，因为它们与的架构不匹配的元素**数据集**。 同步**XmlDataDocument**与**数据集**允许在中维护初始 XML 文档的格式设置和分层元素结构**XmlDataDocument**，虽然**数据集**包含唯一的数据和架构信息适用于**数据集**。  
  
 同步时**数据集**与**XmlDataDocument**，结果可能会有所不同，具体取决于是否你<xref:System.Data.DataRelation>对象是否嵌套。 有关详细信息，请参阅[嵌套 Datarelation](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)。  
  
## <a name="in-this-section"></a>本节内容  
 [使 DataSet 与 XmlDataDocument 同步](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/synchronizing-a-dataset-with-an-xmldatadocument.md)  
 演示同步强类型化**数据集**，使用最小的架构与**XmlDataDocument**。  
  
 [对数据集执行 XPath 查询](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/performing-an-xpath-query-on-a-dataset.md)  
 演示的内容执行 XPath 查询**数据集**。  
  
 [将 XSLT 转换应用到数据集](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/applying-an-xslt-transform-to-a-dataset.md)  
 演示将 XSLT 转换应用于的内容**数据集**。  
  
## <a name="related-sections"></a>相关章节  
 [在数据集中使用 XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 描述如何**数据集**作为数据源，包括加载和保持的内容与 XML 进行交互**数据集**以 XML 数据形式。  
  
 [嵌套 Datarelation](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)  
 讨论的重要性嵌套**DataRelation**对象表示的内容时**数据集**作为 XML 数据，并描述如何创建这些关系。  
  
 [数据集、数据表和数据视图](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 描述**数据集**以及如何使用它来管理应用程序数据和与数据源包括关系数据库和 XML 进行交互。  
  
 <xref:System.Xml.XmlDataDocument>  
 包含有关引用信息**XmlDataDocument**类。  
  
## <a name="see-also"></a>另请参阅  
 [ADO.NET 托管提供程序和数据集开发人员中心](http://go.microsoft.com/fwlink/?LinkId=217917)
