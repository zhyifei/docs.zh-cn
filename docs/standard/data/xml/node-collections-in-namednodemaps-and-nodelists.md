---
title: "NamedNodeMap 和 NodeList 中的节点集合"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 025954b8-7aa8-47c5-a1c1-f81064fb4d65
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 7eeed46782eb6c55af23559035fb8b6bcb14301f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="node-collections-in-namednodemaps-and-nodelists"></a><span data-ttu-id="692de-102">NamedNodeMap 和 NodeList 中的节点集合</span><span class="sxs-lookup"><span data-stu-id="692de-102">Node Collections in NamedNodeMaps and NodeLists</span></span>
<span data-ttu-id="692de-103">可以检索节点集并将其放在已排序或未排序的集合中。</span><span class="sxs-lookup"><span data-stu-id="692de-103">You can retrieve a set of nodes and put it in an ordered or unordered collection.</span></span> <span data-ttu-id="692de-104">将节点集放在未排序的集合中时，万维网联合会 (W3C) 将此节点集称为 NamedNodeMap；在这种类型的集合中可以按名称或索引检索数据。</span><span class="sxs-lookup"><span data-stu-id="692de-104">When putting a set of nodes into an unordered collection, the set is called a NamedNodeMap by the World Wide Web Consortium (W3C); you can retrieve the data by name or index in this type of collection.</span></span> <span data-ttu-id="692de-105">将节点集放入已排序的集合中时，W3C 将其称为 NodeList；可以按从零开始的索引检索数据。</span><span class="sxs-lookup"><span data-stu-id="692de-105">Putting a set of nodes in an ordered collection is called a NodeList by the W3C, and the data can be retrieved by a zero-based index.</span></span> <span data-ttu-id="692de-106">NamedNodeMap 和 NodeList 由 W3C 描述。</span><span class="sxs-lookup"><span data-stu-id="692de-106">NamedNodeMaps and NodeLists are described by the W3C.</span></span> <span data-ttu-id="692de-107">NamedNodeMap 在 Microsoft.NET Framework 中的实现是**XmlNamedNodeMap**，并由实现 NodeList **XmlNodeList**。</span><span class="sxs-lookup"><span data-stu-id="692de-107">The implementations in the Microsoft .NET Framework for the NamedNodeMap is the **XmlNamedNodeMap**, and the NodeList is implemented by the **XmlNodeList**.</span></span>  
  
 <span data-ttu-id="692de-108">有关未排序集合的信息，请参阅[按名称或索引检索未排序节点](../../../../docs/standard/data/xml/unordered-node-retrieval-by-name-or-index.md)。</span><span class="sxs-lookup"><span data-stu-id="692de-108">For information on the unordered collection, see [Unordered Node Retrieval by Name or Index](../../../../docs/standard/data/xml/unordered-node-retrieval-by-name-or-index.md).</span></span> <span data-ttu-id="692de-109">已排序集合的信息，请参阅[按索引检索已排序节点](../../../../docs/standard/data/xml/ordered-node-retrieval-by-index.md)。</span><span class="sxs-lookup"><span data-stu-id="692de-109">For information on the ordered collection, see [Ordered Node Retrieval by Index](../../../../docs/standard/data/xml/ordered-node-retrieval-by-index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="692de-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="692de-110">See Also</span></span>  
 [<span data-ttu-id="692de-111">XML 文档对象模型 (DOM)</span><span class="sxs-lookup"><span data-stu-id="692de-111">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
