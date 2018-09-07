---
title: System.Xml 使用情况
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 82302f0d-a621-4c6f-b57d-999bd61f21a6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5c3eb01e1050bc78d2b31de19a8a728af92777e8
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43863382"
---
# <a name="systemxml-usage"></a>System.Xml 使用情况
本部分介绍几种类型中驻留的使用情况<xref:System.Xml?displayProperty=nameWithType>可以用于表示 XML 数据的命名空间。  
  
 **X DO NOT** 使用<xref:System.Xml.XmlNode>或<xref:System.Xml.XmlDocument>来表示 XML 数据。 倾向于使用的实例<xref:System.Xml.XPath.IXPathNavigable>， <xref:System.Xml.XmlReader>， <xref:System.Xml.XmlWriter>，或子类型的<xref:System.Xml.Linq.XNode>相反。 `XmlNode` 和`XmlDocument`不设计用于在公共 Api 中公开。  
  
 **✓ DO** 使用`XmlReader`， `IXPathNavigable`，或子类型的`XNode`为输入或输出的接受或返回 XML 的成员。  
  
 使用而不是这些抽象`XmlDocument`， `XmlNode`，或<xref:System.Xml.XPath.XPathDocument>，因为这将从内存中 XML 文档的特定实现的方法中分离出来，使他们可以使用虚拟公开的 XML 数据源可以`XNode``XmlReader`，或<xref:System.Xml.XPath.XPathNavigator>。  
  
 **X DO NOT** 子类`XmlDocument`如果你想要创建表示基础对象模型或数据源的 XML 视图的类型。  
  
 *部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*  
  
 *经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*  
  
## <a name="see-also"></a>请参阅

- [框架设计指南](../../../docs/standard/design-guidelines/index.md)  
- [使用准则](../../../docs/standard/design-guidelines/usage-guidelines.md)
