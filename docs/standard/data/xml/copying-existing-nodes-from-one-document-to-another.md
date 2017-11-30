---
title: "将现有节点从一个文档复制到另一个文档"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3caa78c1-3448-4b7b-b83c-228ee857635e
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 0f20e5bd595c8eb49360e58f281a8cf6eda89acf
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="copying-existing-nodes-from-one-document-to-another"></a>将现有节点从一个文档复制到另一个文档
**ImportNode**方法是一种的机制所依据的节点或整个节点子树复制从一个**XmlDocument**到另一个。 该调用返回的节点是源文档节点的副本，其中包括属性值、节点名、节点类型以及所有与命名空间相关的属性，如前缀、本地名称和命名空间统一资源标识符 (URI)。 源文档不更改。 导入该节点后，仍需使用插入节点的方法之一将该节点添加到树中。  
  
 节点附加到新文档后，将归此新文档所有。 原因是每个节点在创建后都具有所属文档，即使节点是在单独的文档片段中创建的。 这是一项要求的 XML 文档对象模型 (DOM)，在上强制执行的工厂创建设计**XmlDocument**类。 例如， **CreateElement**，是唯一的方法来创建新节点。  
  
 具体取决于导入的节点和值的节点类型*深层*将复制适当的参数，其他信息。 此方法尝试镜像当 XML 或 HTML 源代码片断从一个文档复制到另一个文档时的预期行为，并且考虑到对于 XML，两个文档可能具有不同的文档类型定义 (DTD)。  
  
 下表描述了可导入的每种节点类型的特定行为。  
  
|节点类型|*深层*参数为 true|*深层*参数为 false|  
|---------------|------------------------------|-------------------------------|  
|XmlAttribute|<xref:System.Xml.XmlAttribute.Specified%2A>设置为**true**在 XmlAttribute 上。 后代中的源**XmlAttribute**以递归方式导入和生成的节点重新合并以形成相应的子树。|*深层*参数不适用于**XmlAttribute**节点，因为它们始终会包含在导入时及其子节点。|  
|XmlCDataSection|复制该节点，包括复制其数据。|复制该节点，包括复制其数据。|  
|XmlComment|复制该节点，包括复制其数据。|复制该节点，包括复制其数据。|  
|XmlDocumentFragment|递归导入源节点的子代，并重组生成的节点，以构成相应的子树。|一个空**XmlDocumentFragment**创建。|  
|XmlDocumentType|复制该节点，包括复制其数据。*|复制该节点，包括复制其数据。*|  
|XmlElement|递归导入源元素的子代，并重组生成的节点，以构成相应的子树。 **注意：**不复制默认属性。 如果导入到的文档定义该元素名称的默认属性，则分配这些默认属性。|指定的属性导入源元素的节点，并将生成**XmlAttribute**节点附加到新的元素。 不复制子代节点。 **注意：**不复制默认属性。 如果导入到的文档定义该元素名称的默认属性，则分配这些默认属性。|  
|XmlEntityReference|因为源和目标文档可能以不同方式定义实体，该方法仅复制**XmlEntityReference**节点。 不包括替换文本。 如果目标文档定义了实体，则给它赋值。|因为源和目标文档可能以不同方式定义实体，该方法仅复制**XmlEntityReference**节点。 不包括替换文本。 如果目标文档定义了实体，则给它赋值。|  
|XmlProcessingInstruction|从导入的节点复制目标和数据值。|从导入的节点复制目标和数据值。|  
|XmlText|复制该节点，包括复制其数据。|复制该节点，包括复制其数据。|  
|XmlSignificantWhitespace|复制该节点，包括复制其数据。|复制该节点，包括复制其数据。|  
|XmlWhitespace|复制该节点，包括复制其数据。|复制该节点，包括复制其数据。|  
|XmlDeclaration|从导入的节点复制目标和数据值。|从导入的节点复制目标和数据值。|  
|所有其他节点类型|不能导入这些节点类型。|不能导入这些节点类型。|  
  
> [!NOTE]
>  虽然可以导入 DocumentType 节点，但一个文档只能有一个 DocumentType。 因此，导入该文档类型后，在将其插入到树中之前，必须确保文档中没有任何文档类型。 有关删除节点的信息，请参阅[中移除节点、 内容和值从 XML 文档](../../../../docs/standard/data/xml/removing-nodes-content-and-values-from-an-xml-document.md)。  
  
## <a name="see-also"></a>另请参阅  
 [XML 文档对象模型 (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
