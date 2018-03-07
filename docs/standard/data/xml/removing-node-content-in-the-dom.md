---
title: "移除 DOM 中的节点内容"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 615d81a7-f44f-416c-a9ab-bfe03f85e6e4
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 45a8d5006599b23165a174770f4d72974ea0e5ec
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="removing-node-content-in-the-dom"></a><span data-ttu-id="84d99-102">移除 DOM 中的节点内容</span><span class="sxs-lookup"><span data-stu-id="84d99-102">Removing Node Content in the DOM</span></span>
<span data-ttu-id="84d99-103">对于从 <xref:System.Xml.XmlCharacterData> 继承的节点类型，包括 <xref:System.Xml.XmlComment>、<xref:System.Xml.XmlText>、<xref:System.Xml.XmlCDataSection>、<xref:System.Xml.XmlWhitespace> 和 <xref:System.Xml.XmlSignificantWhitespace> 节点类型，可以使用 <xref:System.Xml.XmlCharacterData.DeleteData%2A> 方法移除字符，该方法从节点中删除某个范围的字符。</span><span class="sxs-lookup"><span data-stu-id="84d99-103">For node types that inherit from <xref:System.Xml.XmlCharacterData>, which are the <xref:System.Xml.XmlComment>, <xref:System.Xml.XmlText>, <xref:System.Xml.XmlCDataSection>, <xref:System.Xml.XmlWhitespace>, and <xref:System.Xml.XmlSignificantWhitespace> node types, you can remove characters using the <xref:System.Xml.XmlCharacterData.DeleteData%2A> method, which removes a range of characters from the node.</span></span> <span data-ttu-id="84d99-104">如果要完全移除内容，则移除包含此内容的节点。</span><span class="sxs-lookup"><span data-stu-id="84d99-104">If you want to remove content completely, you remove the node that contains the content.</span></span> <span data-ttu-id="84d99-105">如果要保留节点，但节点内容不正确，则修改内容。</span><span class="sxs-lookup"><span data-stu-id="84d99-105">If you want to keep the node, but the content is incorrect, then modify the content.</span></span> <span data-ttu-id="84d99-106">若要了解如何修改节点内容，请参阅[修改 XML 文档中的节点、内容和值](../../../../docs/standard/data/xml/modifying-nodes-content-and-values-in-an-xml-document.md)。</span><span class="sxs-lookup"><span data-stu-id="84d99-106">For information on modifying the content of a node, see [Modifying Nodes, Content, and Values in an XML Document](../../../../docs/standard/data/xml/modifying-nodes-content-and-values-in-an-xml-document.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84d99-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="84d99-107">See Also</span></span>  
 [<span data-ttu-id="84d99-108">XML 文档对象模型 (DOM)</span><span class="sxs-lookup"><span data-stu-id="84d99-108">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
