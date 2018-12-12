---
title: System.Xml 用法
ms.date: 10/22/2008
ms.technology: dotnet-standard
ms.assetid: 82302f0d-a621-4c6f-b57d-999bd61f21a6
author: KrzysztofCwalina
ms.openlocfilehash: fb0e1d3dc851f9726905dc375d50cf211dba8400
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53149531"
---
# <a name="systemxml-usage"></a>System.Xml 用法
本部分介绍 <xref:System.Xml?displayProperty=nameWithType> 命名空间中的可以用于表示 XML 数据的几种类型的用法。  
  
 **X 切忌**使用 <xref:System.Xml.XmlNode> 或 <xref:System.Xml.XmlDocument> 来表示 XML 数据。 相反，倾向使用 <xref:System.Xml.XPath.IXPathNavigable>、<xref:System.Xml.XmlReader>、<xref:System.Xml.XmlWriter> 或 <xref:System.Xml.Linq.XNode> 的子类型。 `XmlNode` 和 `XmlDocument` 不是为在公共 API 中公开而设计的。  
  
 **✓ 务必**使用 `XmlReader`、`IXPathNavigable` 或 `XNode` 的子类型作为接受或返回 XML 的成员的输入或输出。  
  
 使用这些抽象的项，而不是 `XmlDocument`、`XmlNode` 或 <xref:System.Xml.XPath.XPathDocument>，因为这将方法与内存中 XML 文档的特定实现解耦，并允许它们与公开 `XNode`、`XmlReader` 或 <xref:System.Xml.XPath.XPathNavigator> 的虚拟 XML 数据源一起使用。  
  
 **X 切忌**将 `XmlDocument` 子类化，如果想要创建用来表示底层对象模型或数据源的 XML 视图的类型。  
  
 *部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*  
  
 *通过从 Pearson Education，Inc.的权限重新打印[Framework 设计准则：约定、 语法和模式的可重用.NET 库，第 2 版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)Krzysztof Cwalina 和 Brad Abrams，作为 Microsoft Windows 开发系列的一部分发布 2008 年 10 月 22 日由 Addison-wesley 专业人员。*  
  
## <a name="see-also"></a>请参阅

- [框架设计指南](../../../docs/standard/design-guidelines/index.md)  
- [使用准则](../../../docs/standard/design-guidelines/usage-guidelines.md)
