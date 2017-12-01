---
title: "NodeList 和 NamedNodeMap 的动态更新"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 76c511fd-6704-4ca4-8078-860a68d898ad
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 459d746ff278ac4affa0318c1fad0aeb6a73e560
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="dynamic-updates-to-nodelists-and-namednodemaps"></a>NodeList 和 NamedNodeMap 的动态更新
因为**XmlNodeList**和**XmlNamedNodeMap**包含一组节点，而 XML 文档加载到内存中并被修改，因此万维网联合会 (W3C) 规定这些对象包含一系列节点需要是动态。 也就是说，如果基础文档更改，则这两个对象中的数据也应更改。 因此，如果你有**XmlNodeList** ，其中包含特定元素 （例如，元素 X） 的所有子元素，然后，将添加到元素 X 下文档元素 Q，附加的元素。**XmlNodeList**也应将该新元素 Q 添加到其集合。 反过来也一样。 如果一个节点添加到**XmlNodeList**，基础文档同样也更新。  
  
## <a name="see-also"></a>另请参阅  
 [XML 文档对象模型 (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
