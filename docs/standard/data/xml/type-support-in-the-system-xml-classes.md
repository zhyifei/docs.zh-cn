---
title: "System.Xml 类中的类型支持"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 63570538-06e3-4401-ad4d-ac50be90c7bf
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 14821ef78f20d1ff303afacb42415e4017a92742
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="type-support-in-the-systemxml-classes"></a>System.Xml 类中的类型支持
在 .NET Framework 2.0 版中，核心 XML 类已得到增强，具有类型支持功能。 <xref:System.Xml.XmlReader>、<xref:System.Xml.XmlWriter> 和 <xref:System.Xml.XPath.XPathNavigator> 类具有类型支持功能，可以在 XML 架构类型和公共语言运行库 (CLR) 类型之间转换。  
  
 在 .NET Framework 2.0 版中，<xref:System.Xml.XmlReader>、<xref:System.Xml.XmlWriter> 和 <xref:System.Xml.XPath.XPathNavigator> 类已得到增强，具有类型支持功能。  
  
-   <xref:System.Xml.XmlReader>和<xref:System.Xml.XPath.XPathNavigator>类分别包括**SchemaInfo**在节点返回的架构信息的属性。  
  
-   **ReadContentAs**和**ReadElementContentAs**和方法的<xref:System.Xml.XmlReader>类读取文本值并将其转换为单个方法调用中的 CLR 值。  
  
-   在写出 XML 时，<xref:System.Xml.XmlWriter.WriteValue%2A> 类的 <xref:System.Xml.XmlWriter> 方法将 CLR 类型转换为 XML 架构类型。  
  
-   **ValueAs**和<xref:System.Xml.XPath.XPathNavigator.TypedValue%2A>属性<xref:System.Xml.XPath.XPathNavigator>类返回节点值并将其转换为单个方法调用中的 CLR 值。  
  
> [!NOTE]
>  在 .NET Framework 1.0 版中，需要使用 <xref:System.Xml.XmlConvert> 类在 XML 架构和 CLR 类型之间进行转换。  
  
## <a name="in-this-section"></a>本节内容  
 [将 XML 数据类型映射到 CLR 类型](../../../../docs/standard/data/xml/mapping-xml-data-types-to-clr-types.md)  
 介绍 XML 数据类型与 CLR 类型的默认映射。  
  
 [XML 类型支持实现说明](../../../../docs/standard/data/xml/xml-type-support-implementation-notes.md)  
 介绍一些类型支持实现的详细信息。  
  
 [XML 数据类型的转换](../../../../docs/standard/data/xml/conversion-of-xml-data-types.md)  
 描述如何使用 <xref:System.Xml.XmlConvert> 类在 XML 架构和 CLR 类型之间进行转换。  
  
## <a name="related-sections"></a>相关章节  
 [访问强类型 XML 数据使用 XPathNavigator](../../../../docs/standard/data/xml/accessing-strongly-typed-xml-data-using-xpathnavigator.md)
