---
title: "关系数据和 ADO.NET 的 XML 集成"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f6ebb1a1-f2ca-49b9-92c9-0150940cf6e6
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5d03a0ca7518b06c08d98967d7c5ae864f1c04ac
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="xml-integration-with-relational-data-and-adonet"></a>关系数据和 ADO.NET 的 XML 集成
**XmlDataDocument**类是派生的类的**XmlDocument**，并且包含 XML 数据。 利用**XmlDataDocument**在于，它提供关系和分层数据之间的桥梁。 它是**XmlDocument** ，可以绑定到**数据集**，这两个类可以同步对两个类中包含的数据所做的更改。 **XmlDocument** ，它绑定到**数据集**允许 XML 与关系数据集成和无需具有将数据表示为 XML 格式或以关系格式。 您可以用这两种格式表示数据，而不是限于一种数据表示形式。  
  
 让数据可以以两种视图呈现的好处是：  
  
-   XML 文档的结构化部分可以映射到一个数据集，并可以有效地存储、索引和搜索。  
  
-   转换、验证和导航可以通过以关系形式存储的 XML 数据上的游标模型有效地进行。 有时，可以更有效地对比如果 XML 存储在关系结构**XmlDocument**模型。  
  
-   **数据集**可以存储 XML 的一部分。 也就是说，你可以使用**XPath**或**XslTransform**以存储到**数据集**只元素和感兴趣的属性。 在这里，可以对进行更改的数据较小的、 经过筛选的子集传播到更大的数据中的更改**XmlDataDocument**。  
  
 你还可以对已加载到的数据运行转换**数据集**从 SQL Server。 另一种方法是将.NET Framework 类样式管理的 WinForm 和 WebForm 控件绑定到**数据集**从 XML 输入流填充。  
  
 除了支持**XslTransform**、 **XmlDataDocument**公开关系数据向**XPath**查询和验证。  一般地，所有 XML 服务都可以对关系数据使用，而关系功能（如控件绑定、代码生成等）可以对 XML 的结构化映射使用，不会使 XML 失真。  
  
 因为**XmlDataDocument**继承自**XmlDocument**，它提供了 W3C DOM 的实现 这一事实， **XmlDataDocument**相关联，并将存储内，其数据的子集**数据集**并未限制或改变其用作**XmlDocument**以任何方式。 编写用来使用代码**XmlDocument** works 原封不动地针对**XmlDataDocument**。 **数据集**通过定义表、 列、 关系和约束，提供相同的数据的关系视图和是独立的、 内存中的用户数据存储区。  
  
 下图显示的不同关联了 XML 数据与**数据集**和**XmlDataDocument**。  
  
 ![XML 数据集](../../../../docs/standard/data/xml/media/xmlintegrationwithrelationaldataandadodotnet.gif "xmlIntegrationWithRelationalDataAndADOdotNet")  
  
 图中显示 XML 数据，可以加载直接到**数据集**，这样，以关系型的方式与 XML 的直接操作。 或者，XML 可以加载到 DOM 的派生类**XmlDataDocument**，随后加载和与同步**数据集**。 因为**数据集**和**XmlDataDocument**通过一组同步的数据，对一个存储中的数据所做更改会反映其他区中。  
  
 **XmlDataDocument**继承中的所有编辑和浏览功能**XmlDocument**。 有时间使用时**XmlDataDocument**其继承的功能，与同步**数据集**，为更适当的选项比 XML 直接加载到**数据集**. 下表显示的项时选择要使用加载的方法要考虑**数据集**。  
  
|何时将 XML 直接加载到数据集中|何时将 XmlDataDocument 与 DataSet 同步|  
|----------------------------------------------|-----------------------------------------------------------|  
|中的数据的查询**数据集**来更方便地使用 SQL 比用 XPath。|XPath 查询中的数据所需**数据集**。|  
|保留源 XML 中的元素顺序并不重要。|保留源 XML 中的元素顺序很重要。|  
|源 XML 中元素间的空白和格式设置不需要保留。|保留源 XML 中的空白和格式设置很重要。|  
  
 如果加载和编写 XML，直接进入和退出**数据集**满足您的需要，请参阅[从 XML 加载数据集](../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)和[编写以 XML 数据形式的数据集](../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md)。  
  
 如果加载**数据集**从**XmlDataDocument**满足您的需要，请参阅[同步 dataset 与 XML 文档](../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataset-and-xmldatadocument-synchronization.md)。  
  
## <a name="see-also"></a>另请参阅  
 [在数据集中使用 XML](../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)
