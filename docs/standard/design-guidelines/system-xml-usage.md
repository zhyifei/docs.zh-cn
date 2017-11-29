---
title: "System.Xml 使用情况"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 82302f0d-a621-4c6f-b57d-999bd61f21a6
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a9bfa0f984f97e774d00a64fc3fd8489b3d5b40e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="systemxml-usage"></a>System.Xml 使用情况
本部分介绍有关驻留在的几种类型的使用情况<xref:System.Xml?displayProperty=nameWithType>可以用于表示 XML 数据的命名空间。  
  
 **X 不**使用<xref:System.Xml.XmlNode>或<xref:System.Xml.XmlDocument>来表示 XML 数据。 倾向于使用的实例<xref:System.Xml.XPath.IXPathNavigable>， <xref:System.Xml.XmlReader>， <xref:System.Xml.XmlWriter>，或子类型的<xref:System.Xml.Linq.XNode>相反。 `XmlNode`和`XmlDocument`不适用于公共 Api 中公开。  
  
 **✓ 执行**使用`XmlReader`， `IXPathNavigable`，或子类型的`XNode`为输入或输出的接受或返回 XML 的成员。  
  
 使用而不是这些抽象映射`XmlDocument`， `XmlNode`，或<xref:System.Xml.XPath.XPathDocument>，因为这将从内存中 XML 文档的特定实现的方法脱耦，并允许它们可以使用虚拟公开的 XML 数据源`XNode``XmlReader`，或<xref:System.Xml.XPath.XPathNavigator>。  
  
 **X 不**子类`XmlDocument`如果你想要创建表示基础对象模型或数据源的 XML 视图的类型。  
  
 *部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*  
  
 *通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*  
  
## <a name="see-also"></a>另请参阅  
 [框架设计指南](../../../docs/standard/design-guidelines/index.md)  
 [使用准则](../../../docs/standard/design-guidelines/usage-guidelines.md)
