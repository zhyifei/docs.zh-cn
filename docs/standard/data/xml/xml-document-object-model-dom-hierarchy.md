---
title: "XML 文档对象模型 (DOM) 层次结构"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9d187d4f-c76e-4223-a670-cc290783ce47
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 6dec61860fba5815b1dae802d280e8df6628ab91
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="xml-document-object-model-dom-hierarchy"></a>XML 文档对象模型 (DOM) 层次结构
下图显示了 XML 文档对象模型 (DOM) 的类层次结构，其中万维网联合会 (W3C) 名称用括号括起来，另外还有相关的类名。  
  
 ![XML 文档对象模型 &#40; DOM &#41;层次结构](../../../../docs/standard/data/xml/media/dom-class-hierarchy.gif "Dom_class_hierarchy")  
XML 文档对象模型 (DOM) 层次结构  
  
 以下类不是继承自**XmlNode**:  
  
-   **XmlImplementation**  
  
-   **XmlNamedNodeMap**  
  
-   **XmlNodeList**  
  
-   **XmlNodeChangedEventArgs**  
  
 **XmlImplementation**类用于创建 XML 文档。 有关详细信息，请参阅[XML 文档创建](../../../../docs/standard/data/xml/xml-document-creation.md)。  
  
 **XmlNamedNodeMap**类处理节点的无序的集。 有关详细信息，请参阅[按名称或索引检索未排序节点](../../../../docs/standard/data/xml/unordered-node-retrieval-by-name-or-index.md)。  
  
 **XmlNodeList**类处理已排序的节点列表。 有关详细信息，请参阅[按索引检索已排序节点](../../../../docs/standard/data/xml/ordered-node-retrieval-by-index.md)。  
  
 **XmlNodeChangedEventArgs**类处理上注册的事件处理程序**XmlDocument**。 有关详细信息，请参阅[使用 XmlNodeChangedEventArgs 的 XML 文档中的事件处理](../../../../docs/standard/data/xml/event-handling-in-an-xml-document-using-the-xmlnodechangedeventargs.md)。  
  
 **XmlLinkedNode**类继承自**XmlNode**。 其目的是重写中的两个方法**XmlNode**: **PreviousSibling**和**NextSibling**方法。 然后再继承并使用这些重写的方法**XmlCharacterData**， **XmlDeclaration**， **XmlDocumentType**， **XmlElement**， **XmlEntityReference**，和**XmlProcessingInstruction**，这是上一个和下一个同级的类。  
  
## <a name="see-also"></a>另请参阅  
 [XML 文档对象模型 (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
