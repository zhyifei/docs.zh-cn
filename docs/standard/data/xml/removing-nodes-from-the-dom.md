---
title: 从 DOM 中移除节点
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 0a98e0ca-0555-45c1-ab69-0d8d20ca1abd
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ec786564e6246f10e10d600f4822442884323557
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33568454"
---
# <a name="removing-nodes-from-the-dom"></a>从 DOM 中移除节点
若要移除 XML 文档对象模型 (DOM) 中的节点，请使用 <xref:System.Xml.XmlNode.RemoveChild%2A> 方法移除特定节点。 在移除节点时，方法将移除属于所移除节点的子树；即如果不是叶节点。  
  
 要移除 DOM 中的多个节点，请使用 <xref:System.Xml.XmlNode.RemoveAll%2A> 方法移除当前节点的所有子级和属性（如果适用）。  
  
 如果使用的是 <xref:System.Xml.XmlNamedNodeMap>，可以使用 <xref:System.Xml.XmlNamedNodeMap.RemoveNamedItem%2A> 方法移除节点。  
  
 若要删除属性，请参阅[删除 DOM 中元素节点的属性](../../../../docs/standard/data/xml/removing-attributes-from-an-element-node-in-the-dom.md)。  
  
## <a name="see-also"></a>请参阅  
 [XML 文档对象模型 (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
