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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 8a7abbb7344530ca993b8d07b774da17e6d0349b
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="dynamic-updates-to-nodelists-and-namednodemaps"></a><span data-ttu-id="6a918-102">NodeList 和 NamedNodeMap 的动态更新</span><span class="sxs-lookup"><span data-stu-id="6a918-102">Dynamic Updates to NodeLists and NamedNodeMaps</span></span>
<span data-ttu-id="6a918-103">由于 XmlNodeList 和 XmlNamedNodeMap 包含节点集，而 XML 文档加载到内存中并被修改，因此万维网联合会 (W3C) 规定这些包含节点集的对象必须是动态对象。</span><span class="sxs-lookup"><span data-stu-id="6a918-103">Because the **XmlNodeList** and the **XmlNamedNodeMap** contain a set of nodes, yet the XML document is loaded into memory and is being modified, the World Wide Web Consortium (W3C) states that these objects that contain sets of nodes need to be dynamic.</span></span> <span data-ttu-id="6a918-104">也就是说，如果基础文档更改，则这两个对象中的数据也应更改。</span><span class="sxs-lookup"><span data-stu-id="6a918-104">That is, if the underlying document changes, then the data in these two objects should change also.</span></span> <span data-ttu-id="6a918-105">因此，如果 XmlNodeList 包含特定元素（例如，元素 X）的所有子元素，请在文档中的元素 X 下添加另一个元素 Q。XmlNodeList 也应将新元素 Q 添加到集合中。</span><span class="sxs-lookup"><span data-stu-id="6a918-105">Therefore, if you have an **XmlNodeList** that contains all the child elements of a particular element (for example, element X), then you add an additional element, element Q, to the document under element X. The **XmlNodeList** should also have that new element Q added to its collection.</span></span> <span data-ttu-id="6a918-106">反过来也一样。</span><span class="sxs-lookup"><span data-stu-id="6a918-106">The same is true in reverse.</span></span> <span data-ttu-id="6a918-107">如果将节点添加到 XmlNodeList，那么基础文档也会更新。</span><span class="sxs-lookup"><span data-stu-id="6a918-107">If a node is added to the **XmlNodeList**, the underlying document is updated as well.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a918-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="6a918-108">See Also</span></span>  
 [<span data-ttu-id="6a918-109">XML 文档对象模型 (DOM)</span><span class="sxs-lookup"><span data-stu-id="6a918-109">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
