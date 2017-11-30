---
title: "从 DOM 中移除节点"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0a98e0ca-0555-45c1-ab69-0d8d20ca1abd
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 0885d53e737153448fabfd394d49bfdc793e0599
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="removing-nodes-from-the-dom"></a><span data-ttu-id="5b28e-102">从 DOM 中移除节点</span><span class="sxs-lookup"><span data-stu-id="5b28e-102">Removing Nodes from the DOM</span></span>
<span data-ttu-id="5b28e-103">若要移除 XML 文档对象模型 (DOM) 中的节点，请使用 <xref:System.Xml.XmlNode.RemoveChild%2A> 方法移除特定节点。</span><span class="sxs-lookup"><span data-stu-id="5b28e-103">To remove a node from the XML Document Object Model (DOM), use the <xref:System.Xml.XmlNode.RemoveChild%2A> method to remove a specific node.</span></span> <span data-ttu-id="5b28e-104">在移除节点时，方法将移除属于所移除节点的子树；即如果不是叶节点。</span><span class="sxs-lookup"><span data-stu-id="5b28e-104">When you remove a node, the method removes the subtree belonging to the node being removed; that is, if it is not a leaf node.</span></span>  
  
 <span data-ttu-id="5b28e-105">要移除 DOM 中的多个节点，请使用 <xref:System.Xml.XmlNode.RemoveAll%2A> 方法移除当前节点的所有子级和属性（如果适用）。</span><span class="sxs-lookup"><span data-stu-id="5b28e-105">To remove multiple nodes from the DOM, use the <xref:System.Xml.XmlNode.RemoveAll%2A> method to remove all the children and attributes, if applicable, of the current node.</span></span>  
  
 <span data-ttu-id="5b28e-106">如果使用的是 <xref:System.Xml.XmlNamedNodeMap>，可以使用 <xref:System.Xml.XmlNamedNodeMap.RemoveNamedItem%2A> 方法移除节点。</span><span class="sxs-lookup"><span data-stu-id="5b28e-106">If you are working with an <xref:System.Xml.XmlNamedNodeMap>, you can remove a node using the <xref:System.Xml.XmlNamedNodeMap.RemoveNamedItem%2A> method.</span></span>  
  
 <span data-ttu-id="5b28e-107">若要删除属性，请参阅[移除 DOM 中元素节点的属性](../../../../docs/standard/data/xml/removing-attributes-from-an-element-node-in-the-dom.md)。</span><span class="sxs-lookup"><span data-stu-id="5b28e-107">To remove attributes, see [Removing Attributes from an Element Node in the DOM](../../../../docs/standard/data/xml/removing-attributes-from-an-element-node-in-the-dom.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b28e-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5b28e-108">See Also</span></span>  
 [<span data-ttu-id="5b28e-109">XML 文档对象模型 (DOM)</span><span class="sxs-lookup"><span data-stu-id="5b28e-109">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
