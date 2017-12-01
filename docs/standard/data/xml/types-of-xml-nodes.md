---
title: "XML 节点类型"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 71d03b78-6898-4ce7-b0fc-1282573f31f7
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 3914a2c5c06a2cc73f14bc473984094b474d537e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="types-of-xml-nodes"></a>XML 节点类型
当将 XML 文档作为节点树读入内存时，这些节点的节点类型在创建节点时确定。 XML 文档对象模型 (DOM) 具有多种节点类型，这些类型由万维网联合会 (W3C) 确定并在 1.1.1 节“The DOM Structure Model”中列出。 下表列出了节点类型、分配给该节点类型的对象以及每种节点类型的简短说明。  
  
|DOM 节点类型|对象|描述|  
|-------------------|------------|-----------------|  
|Document|<xref:System.Xml.XmlDocument>|树中所有节点的容器。 它也称作文档根，文档根并非总是与根元素相同。|  
|DocumentFragment|<xref:System.Xml.XmlDocumentFragment>|包含一个或多个不带任何树结构的节点的临时袋。|  
|DocumentType|<xref:System.Xml.XmlDocumentType>|表示 `<!DOCTYPE…>` 节点。|  
|EntityReference|<xref:System.Xml.XmlEntityReference>|表示非扩展的实体引用文本。|  
|元素|<xref:System.Xml.XmlElement>|表示元素节点。|  
|Attr|<xref:System.Xml.XmlAttribute>|为元素的属性。|  
|ProcessingInstruction|<xref:System.Xml.XmlProcessingInstruction>|为处理指令节点。|  
|注释|<xref:System.Xml.XmlComment>|注释节点。|  
|Text|<xref:System.Xml.XmlText>|属于某个元素或属性的文本。|  
|CDATASection|<xref:System.Xml.XmlCDataSection>|表示 CDATA。|  
|实体|<xref:System.Xml.XmlEntity>|表示 XML 文档（来自内部文档类型定义 (DTD) 子集或来自外部 DTD 和参数实体）中的 `<!ENTITY…>` 声明。|  
|Notation|<xref:System.Xml.XmlNotation>|表示 DTD 中声明的表示法。|  
  
 尽管属性 (*attr*) 列出在 W3C DOM 级别 1 1.2 节 Fundamental Interfaces 作为节点，它不被视为任何元素节点的子节点。  
  
 下表显示，w3c 未定义的其他节点类型，但是它们可用于将 Microsoft.NET Framework 对象模型作为**XmlNodeType**枚举。 因此，这些节点类型不存在匹配的 DOM 节点类型列。  
  
|节点类型|描述|  
|---------------|-----------------|  
|<xref:System.Xml.XmlDeclaration>|表示声明节点 `<?xml version="1.0"…>`。|  
|<xref:System.Xml.XmlSignificantWhitespace>|表示有效空白（混合内容中的空白）。|  
|<xref:System.Xml.XmlWhitespace>|表示元素内容中的空白。|  
|EndElement|返回时**XmlReader**到达元素的末尾。<br /><br /> 示例 XML:  **\< /项 >**<br /><br /> 有关更多信息，请参见<xref:System.Xml.XmlNodeType>。|  
|EndEntity|返回时**XmlReader**到达实体替换由于调用末尾<xref:System.Xml.XmlReader.ResolveEntity%2A>。 有关更多信息，请参见<xref:System.Xml.XmlNodeType>。|  
  
 若要查看读入 XML 并使用 case 构造以打印有关节点及其内容的信息对节点类型的代码示例，请参阅<xref:System.Xml.XmlSignificantWhitespace.NodeType%2A>。  
  
 在对象层次结构上的节点类型，以及及其等效对象名的详细信息，请参阅[XML 文档对象模型 (DOM) 层次结构](../../../../docs/standard/data/xml/xml-document-object-model-dom-hierarchy.md)。 有关在节点树中创建的对象的详细信息，请参阅[对象层次结构映射到 XML 数据](../../../../docs/standard/data/xml/mapping-the-object-hierarchy-to-xml-data.md)。  
  
## <a name="see-also"></a>另请参阅  
 [XML 文档对象模型 (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
