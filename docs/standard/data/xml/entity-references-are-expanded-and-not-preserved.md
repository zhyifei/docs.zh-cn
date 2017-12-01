---
title: "扩展但不保留实体引用"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ffd97806-ab43-4538-8de2-5828bfbbde57
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 069d3b94a0269917400e75fdbe975ec39dcfdb71
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="entity-references-are-expanded-and-not-preserved"></a>扩展但不保留实体引用
当展开并用其表示的文本替换为实体引用时**XmlEntityReference**不创建节点。 相反，将分析实体声明，并从声明中的内容创建的节点复制的代替**XmlEntityReference**。 因此，在`&publisher;`示例中，`&publisher;`未保存，而是**XmlText**创建节点。  
  
 ![展开树结构](../../../../docs/standard/data/xml/media/xmlentityref-expanded-nodes.gif "xmlentityref_expanded_nodes")  
展开的实体引用的树结构  
  
 不保留 `B` 或 `<` 这类字符实体。 相反，它们总是扩展并表示为文本节点。  
  
 若要保留**XmlEntityReference**节点和子节点的实体引用节点附加到它，请设置**EntityHandling**标志切换为**ExpandCharEntities**。 否则，保持**EntityHandling**标志保持为默认设置，即到**ExpandEntities**。 这种情况下，您在 DOM 中将看不到实体引用节点。 这些节点已被作为实体声明子节点副本的节点取代。  
  
 不保留实体引用的一个副作用是，当保存文档并将其传递给另一个应用程序时，接收应用程序不知道这些节点是由实体引用生成的。 然而，当保留实体引用时，接收应用程序将查看实体引用并读取子节点。 显而易见，这些子节点表示实体声明中的信息。 例如，在保留实体引用的情况下，DOM 理论上包含以下结构。  
  
 XmlElement：发布者  
  
 XmlEntityReference：`&publisher;`  
  
 XmlText：Microsoft Press  
  
 如果在 DOM 中扩展实体引用（这是默认方法），则结构包含此类型树：  
  
 XmlElement：发布者  
  
 XmlText：Microsoft Press  
  
 请注意，实体引用节点将消失，接收应用程序无法告知**XmlText**从实体声明创建包含"Microsoft Press"节点。  
  
 如果你使用的读取器不能解析实体，**负载**方法在遇到实体引用时引发异常。  
  
## <a name="see-also"></a>另请参阅  
 [XML 文档对象模型 (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
