---
title: 不同存储区的 XSLT 转换
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 369850e9-004a-45d2-b5c3-5060d9135adb
ms.openlocfilehash: 490ac30a3e4f0c50cb5d011f1d583c6e5ce9e672
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709655"
---
# <a name="xslt-transformations-over-different-stores"></a>不同存储区的 XSLT 转换
> [!NOTE]
> <xref:System.Xml.Xsl.XslTransform> 类在 .NET Framework 2.0 中已过时。 可以使用 <xref:System.Xml.Xsl.XslCompiledTransform> 类执行可扩展样式表语言转换 (XSLT) 转换。 请参阅[使用 XslCompiledTransform 类](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md)和[从 XslTransform 类迁移](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md)，以获取详细信息。  
  
 .NET Framework 中的 ADO.NET 和 XML 类提供统一的编程模型来访问数据。 这些数据既表示为 XML 数据（由标记分隔的文本）也表示为关系数据（由行和列组成的表）。 .NET Framework 中的 XML 将任何数据流中的 XML 数据读入 XML 文档对象模型 (DOM) 节点树，在节点树中可通过编程方式访问数据；而 ADO.NET 提供访问和处理 <xref:System.Data.DataSet> 对象中的关系数据的方法。  
  
 XML DOM 提供对 XML 文档数据的访问，并且提供了在 XML 文档中进行读取、写入和浏览的附加类。 <xref:System.Xml> 命名空间中支持这些类，这样也将 XML DOM 与 ADO.NET 提供的数据访问服务统一在一起。 <xref:System.Xml.XmlDataDocument> 提供对数据的关系访问。 <xref:System.Xml.XmlDataDocument> 将 XML 映射到 ADO.NET <xref:System.Data.DataSet> 中的关系数据。 任何基于 .NET Framework 的应用程序都可以使用 <xref:System.Xml> 命名空间中的类访问和处理 XML 文档和 <xref:System.Xml.XmlDataDocument> 中的相关数据。 此实现支持用于收集和分发数据的 n 层结构。 有关详细信息，请参阅[与关系数据和 ADO.NET 的 XML 集成](../../../../docs/standard/data/xml/xml-integration-with-relational-data-and-adonet.md)。  
  
## <a name="see-also"></a>请参阅

- [XslTransform 类实现 XSLT 处理器](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)
