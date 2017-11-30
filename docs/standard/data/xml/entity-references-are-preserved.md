---
title: "保留实体引用"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 000a6cae-5972-40d6-bd6c-a9b7d9649b3c
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 770c714e8f5942ea733c417ae9b06f69e4acf1a5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="entity-references-are-preserved"></a>保留实体引用
XML 文档对象模型 (DOM) 在未展开，而保留实体引用，生成**XmlEntityReference**时遇到实体引用节点。  
  
 使用以下 XML，  
  
```xml  
<author>Fred</author>  
<pubinfo>Published by &publisher;</pubinfo>  
```  
  
 DOM 生成**XmlEntityReference**节点时遇到`&publisher;`引用。 **XmlEntityReference**包含从实体声明中的内容复制的子节点。 前面的代码示例包含实体声明中的文本，因此**XmlText**创建节点作为实体引用节点的子节点。  
  
 ![保留的实体引用的树结构](../../../../docs/standard/data/xml/media/xmlentityref-notexpanded-nodes.gif "xmlentityref_notexpanded_nodes")  
保留的实体引用的树结构  
  
 子节点**XmlEntityReference**是从创建的节点的副本的所有子**XmlEntity**节点时遇到实体声明。  
  
> [!NOTE]
>  从复制的节点**XmlEntity**不始终是曾放置在实体引用节点下的精确副本。 可以有在实体引用节点范围内并影响子节点的最终配置的命名空间。  
  
 默认情况下，例如常规实体`&abc;`保留和**XmlEntityReference**始终创建的节点。  
  
## <a name="see-also"></a>另请参阅  
 [XML 文档对象模型 (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
