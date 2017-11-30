---
title: "命名空间对包含元素和属性的新节点的实体引用扩展的影响"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 64359aee-aab0-4042-9a32-d19789af6ca7
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 39110a9b44e6efbe7ad0331cfdb4fbe6078e7cfc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="namespace-affect-on-entity-reference-expansion-for-new-nodes-containing-elements-and-attributes"></a>命名空间对包含元素和属性的新节点的实体引用扩展的影响
由于实体声明的内容可以包含几乎所有内容，因此该内容有可能包含像 `<!ENTITY aname "<elem>test</elem>">` 这样的元素。  
  
 分析 XML 时，`&aname;` 在分析时不用其替换内容扩展。 不执行 XML 扩展的原因在于对元素的命名空间解析只有在将节点放入文档中时才发生。 在此之前，并不知道范围中存在哪个命名空间。 将节点放入文档中后，将进行命名空间解析，生成的实体内容将被分析为相应节点。  
  
> [!NOTE]
>  新创建的实体引用节点进行扩展后，该扩展永远不会再次进行。 因此，在元素的替换文本中使用的命名空间将在设置父节点时绑定。 但是，可以为现有实体引用节点时移除并插入到其他地方，或与克隆的实体引用节点上更改命名空间**CloneNode**方法。  
  
## <a name="see-also"></a>另请参阅  
 [XML 文档对象模型 (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
