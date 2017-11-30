---
title: "创建新实体引用"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a42f81b3-0403-4e34-b346-7d2129804e54
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 22e9b66f58275141cf9da154573ca43a0b90affc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="creating-new-entity-references"></a>创建新实体引用
**CreateEntityReference**方法创建一个新**XmlEntityReference**节点。 XML 文档对象模型 (DOM) 查看是否已声明了引用的实体名称。 如果具有的子节点**XmlEntityReference**从实体声明节点复制节点。 如果没有匹配的实体声明，则附加一个空的文本节点作为实体引用节点的唯一子级。 因为的子节点**XmlEntityReference**节点是其他节点的副本，这些子节点是只读的不能修改。  
  
 当复制节点时，在实体引用所处的范围内可能存在一个命名空间。 此命名空间影响生成的任何元素或属性节点的配置。  
  
> [!NOTE]
>  DOM 将添加到的子节点**EntityReference**仅插入**EntityReference**到文档的节点。 新创建的**EntityReference**节点具有任何子节点。  
  
 即使**XmlDataDocument**的是派生类**XmlDocument**、 **XmlDataDocument**不支持实体引用的创建。 这是因为**EntityReference**子级是只读的。 子级**EntityReference**节点可以跨多个区域。 在这种情况下，与包含的一部分的区域相关联的行的一部分**EntityReference**将是只读的。  
  
## <a name="see-also"></a>另请参阅  
 [XML 文档对象模型 (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
