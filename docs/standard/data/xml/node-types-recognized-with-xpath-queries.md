---
title: "XPath 查询识别的节点类型"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1d33e22d-18e5-43f8-a466-2e3d0a8dd094
caps.latest.revision: "2"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 1c1e48bbfd6388686fdb83f08668f7f0234275a5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="node-types-recognized-with-xpath-queries"></a>XPath 查询识别的节点类型
XPath 查询识别的节点类型与文档对象模型 (DOM) 中的节点类型不同。  
  
## <a name="w3c-xpath-node-types"></a>W3C XPath 节点类型  
 XPath 查询识别的节点类型与文档对象模型 (DOM) 中的节点类型不同。 以下是通过 <xref:System.Xml.XPath.XPathNodeType> 枚举表示的 XPath 节点类型。  
  
-   <xref:System.Xml.XPath.XPathNodeType.All>  
  
-   <xref:System.Xml.XPath.XPathNodeType.Attribute>  
  
-   <xref:System.Xml.XPath.XPathNodeType.Comment>  
  
-   <xref:System.Xml.XPath.XPathNodeType.Element>  
  
-   <xref:System.Xml.XPath.XPathNodeType.Namespace>  
  
-   <xref:System.Xml.XPath.XPathNodeType.ProcessingInstruction>  
  
-   <xref:System.Xml.XPath.XPathNodeType.Root>  
  
-   <xref:System.Xml.XPath.XPathNodeType.SignificantWhitespace>  
  
-   <xref:System.Xml.XPath.XPathNodeType.Text>  
  
-   <xref:System.Xml.XPath.XPathNodeType.Whitespace>  
  
 这些节点类型基于 XPath 数据模型，其中的节点从 XML 信息集派生。 <xref:System.Xml.XPath.XPathNodeType.SignificantWhitespace> 和 <xref:System.Xml.XPath.XPathNodeType.Whitespace> 节点类型是 Microsoft .NET Framework 对 XPath 数据模型中所述的基本节点类型的扩展。  
  
 属性节点类型在 XPath 数据模型中的用法与在 DOM 中的用法不同。 在 XPath 数据模型中，元素具有相关的属性节点集，且元素是每个属性节点的父级。 但在 DOM 中，元素节点是所有者，而不是父级。 在这两种模型中，属性和命名空间节点都不被视为元素节点的子节点。  
  
 命名空间节点类型是 XPath 数据模型的补充，并且不是可识别的 DOM 节点类型。  
  
 有关导航元素、 属性和命名空间节点的详细信息，请参阅[节点设置的导航使用 XPathNavigator](../../../../docs/standard/data/xml/node-set-navigation-using-xpathnavigator.md)和[属性和 Namespace 节点导航使用 XPathNavigator](../../../../docs/standard/data/xml/attribute-and-namespace-node-navigation-using-xpathnavigator.md)主题。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Xml.XmlDocument>  
 <xref:System.Xml.XPath.XPathDocument>  
 <xref:System.Xml.XPath.XPathNavigator>  
 [使用 XPath 数据模型处理 XML 数据](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
 [使用 XPathNavigator 选择 XML 数据](../../../../docs/standard/data/xml/select-xml-data-using-xpathnavigator.md)  
 [使用 XPathNavigator 计算 XPath 表达式](../../../../docs/standard/data/xml/evaluate-xpath-expressions-using-xpathnavigator.md)  
 [使用 XPathNavigator 匹配节点](../../../../docs/standard/data/xml/matching-nodes-using-xpathnavigator.md)  
 [XPath 查询和命名空间](../../../../docs/standard/data/xml/xpath-queries-and-namespaces.md)  
 [已编译的 XPath 表达式](../../../../docs/standard/data/xml/compiled-xpath-expressions.md)
