---
title: "XML 处理选项"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 33ced8ee-1745-4e71-8dee-ebe70ec067c7
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 18f8f9c76a1842517340eaa3f74b4778f869403e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="xml-processing-options"></a>XML 处理选项
请参见下面的表以获得可用于处理 XML 数据的 Microsoft 技术的列表。  
  
## <a name="net-framework-options"></a>.NET Framework 选项  
  
|**选项**|**处理类型**|**描述**|  
|----------------|-------------------------|---------------------|  
|[LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13) <br />（<xref:System.Xml.Linq> 命名空间）|内存中|-基于.net framework 语言集成查询 (LINQ) 技术。<br />-提供了类似于 SQL 对象、 关系数据和 XML 数据的查询体验。<br />-提供直观的文档创建和转换功能。<br />-如果要编写新代码，则使用此选项。|  
|<xref:System.Xml.XmlReader?displayProperty=nameWithType>|基于流|-提供用于访问 XML 数据的快速、 非缓存、 只进方法。<br />-你可以通过创建对象<xref:System.Xml.XmlReader.Create%2A?displayProperty=nameWithType>方法，并指定要使用该对象上启用的功能集<xref:System.Xml.XmlReaderSettings>类。|  
|<xref:System.Xml.XmlWriter?displayProperty=nameWithType>|基于流|-提供快速、 非缓存、 只进方法生成 XML 数据。<br />-你可以通过创建对象<xref:System.Xml.XmlWriter.Create%2A?displayProperty=nameWithType>方法，并指定要使用该对象上启用的功能集<xref:System.Xml.XmlWriterSettings>类。|  
|<xref:System.Xml.XmlDocument?displayProperty=nameWithType>|内存中|-实现[W3C 文档对象模型 (DOM) 级别 1 核心](http://www.w3.org/TR/REC-DOM-Level-1/level-one-core.html)和[DOM 级别 2 核心](http://www.w3.org/TR/DOM-Level-2-Core/)建议。<br />-你可以创建、 插入、 删除和修改节点通过使用方法和基于熟悉的 DOM 模型的属性。<br />-使用此选项，如果你要修改利用 W3C DOM 的现有代码|  
|<xref:System.Xml.XPath.XPathNavigator?displayProperty=nameWithType>|内存中|-提供多种编辑选项和导航功能使用的游标模型。<br />XML 文档中可包含<xref:System.Xml.XPath.XPathDocument>或<xref:System.Xml.XmlDocument>对象。<br />-提供的 XML 的只读处理很好的性能。<br />-如果要修改现有代码通过 XPath 查询或 XSLT 转换，则使用此选项。|  
|<xref:System.Xml.Xsl.XslCompiledTransform>|内存中|-提供了用于转换使用 XSL 转换的 XML 数据的选项。<br />- [XSLT 编译器 (xsltc.exe)](../../../../docs/standard/data/xml/xslt-compiler-xsltc-exe.md)允许你引用预编译你的应用程序中的转换。|  
  
## <a name="win32-and-com-based-options"></a>基于 Win32 和 COM 的选项  
  
|**选项**|**描述**|  
|----------------|---------------------|  
|[XmlLite](http://go.microsoft.com/fwlink/?LinkId=93723)|-A 快速、 安全的非缓存、 只进 XML 分析器，可帮助你生成高性能的 XML 应用程序。<br />-适用于任何语言，可以使用动态链接库 (Dll);我们建议使用 c + +。|  
|[MSXML](http://go.microsoft.com/fwlink/?LinkId=93722)|-基于 COM 的技术，用于处理 Windows 操作系统附带的 XML。<br />-提供 DOM 的本机实现支持 XPath 和 XSLT。<br />-包含 SAX2 基于事件的分析器。|  
  
## <a name="see-also"></a>另请参阅  
 [使用 DOM 模型处理 XML 数据](../../../../docs/standard/data/xml/process-xml-data-using-the-dom-model.md)  
 [使用 XPath 数据模型处理 XML 数据](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
 [XSLT 编译器 (xsltc.exe)](../../../../docs/standard/data/xml/xslt-compiler-xsltc-exe.md)
