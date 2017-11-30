---
title: "复制现有节点"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2aa8f65c-cc62-4638-9c46-129dc15be786
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 11f3915dfebd7ad9d3144c9bedcd7f42b4754359
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="copy-existing-nodes"></a>复制现有节点
有许多方法和属性在 XML 文档对象模型 (DOM) 可用于选择一个节点，如**SelectSingleNode**， **ChildNodes [int i]**，**属性 [int i]**. 选择节点后，可以使用适用于特定节点类型的插入方法之一将该节点插入到树中。 将节点插入到树中的唯一限制是在插入节点后文档的格式仍必须是正确的。 将现有节点插入到 DOM 树中时，该节点从其原始位置移除并添加到它的目标位置。  
  
## <a name="see-also"></a>另请参阅  
 [XML 文档对象模型 (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
