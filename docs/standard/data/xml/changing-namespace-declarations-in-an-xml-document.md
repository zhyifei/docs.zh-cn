---
title: "更改 XML 文档中的命名空间声明"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: a2758f40-e497-4964-8d8d-1bb68af14dcd
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 627882efcbc41310ee177cba984e4add5b07bd15
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="changing-namespace-declarations-in-an-xml-document"></a>更改 XML 文档中的命名空间声明
**XmlDocument**公开命名空间声明和**xmlns**文档对象模型的一部分的属性。 这些模板存储在**XmlDocument**，因此当保存文档时，可以保留这些特性的位置。 更改这些属性没有任何影响**名称**， **NamespaceURI**，和**前缀**属性对树中的其他节点。 例如，如果你加载下面的文档中，则`test`元素具有**NamespaceURI**`123.`  
  
```xml  
<test xmlns="123"/>  
```  
  
 如果你删除`xmlns`属性，如下所示，则`test`元素仍具有**NamespaceURI**的`123`。  
  
```vb  
doc.documentElement.RemoveAttribute("xmlns")  
```  
  
```csharp  
doc.documentElement.RemoveAttribute("xmlns");  
```  
  
 同样，如果你添加为其他`xmlns`属性设为`doc`元素，如下所示，则`test`元素仍具有**NamespaceURI** `123`。  
  
```vb  
doc.documentElement.SetAttribute("xmlns","456");  
```  
  
```csharp  
doc.documentElement.SetAttribute("xmlns","456");  
```  
  
 因此，更改`xmlns`属性会有任何影响，直到保存并重新加载**XmlDocument**对象。  
  
## <a name="see-also"></a>另请参阅  
 [XML 文档对象模型 (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
