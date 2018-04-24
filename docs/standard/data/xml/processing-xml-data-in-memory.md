---
title: 内存中 XML 数据处理
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1bbb4d05-ead7-4bda-8ece-f86d35c57ad4
caps.latest.revision: 2
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 1c451e4015e37c118f475ec1e7c099566e28767f
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="processing-xml-data-in-memory"></a>内存中 XML 数据处理
Microsoft .NET Framework 包括三个 XML 数据处理模型：<xref:System.Xml.XmlDocument> 类、<xref:System.Xml.XPath.XPathDocument> 类和 [LINQ to XML](https://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13)。  
  
 <xref:System.Xml.XmlDocument> 类实现 W3C 文档对象模型 (DOM) 级别 1 核心和 DOM 级别 2 核心建议。 DOM 是 XML 文档的内存中（缓存）树表示形式。 使用 <xref:System.Xml.XmlDocument> 及其相关的类，可以构造 XML 文档、加载和访问数据、修改数据以及保存更改。  
  
 <xref:System.Xml.XPath.XPathDocument> 类是基于 XPath 数据模型的只读的、内存中的数据存储区。 <xref:System.Xml.XPath.XPathNavigator> 类使用 XML 文档的游标模型提供多种编辑选项和浏览功能，该模型包含在只读的 <xref:System.Xml.XPath.XPathDocument> 类以及 <xref:System.Xml.XmlDocument> 类中。  
  
 [LINQ to XML](https://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13) 是 .NET Framework 版本 3.5 中用于处理 XML 数据的新模型。 这是利用 [LINQ （语言集成查询）](https://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)的内存中模型。 LINQ 扩展 C# 和 Visual Basic 的语言语法以提供新的查询功能。  
  
## <a name="in-this-section"></a>本节内容  
 [使用 DOM 模型处理 XML 数据](../../../../docs/standard/data/xml/process-xml-data-using-the-dom-model.md)  
 讨论如何使用 <xref:System.Xml.XmlDocument> 及其相关的类来处理 XML 数据。  
  
 [使用 XPath 数据模型处理 XML 数据](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
 讨论如何使用 <xref:System.Xml.XPath.XPathDocument>、<xref:System.Xml.XmlDocument> 和 <xref:System.Xml.XPath.XPathNavigator> 类来处理 XML 数据。  
  
 [使用 LINQ to XML 处理 XML 数据](../../../../docs/standard/data/xml/process-xml-data-using-linq-to-xml.md)  
 简要概述 LINQ to XML 并提供到 LINQ to XML 文档的链接。  
  
## <a name="related-sections"></a>相关章节  
 [XML 文档和数据](../../../../docs/standard/data/xml/index.md)
