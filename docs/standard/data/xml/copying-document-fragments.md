---
title: "复制文档片段"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cf424bbe-81b7-40d2-9978-9b727da94d80
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: e90af026db0fc190b2c93e4c751de6600e8fd27a
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="copying-document-fragments"></a><span data-ttu-id="91244-102">复制文档片段</span><span class="sxs-lookup"><span data-stu-id="91244-102">Copying Document Fragments</span></span>
<span data-ttu-id="91244-103">可以先创建 XmlDocumentFragment 节点，再在它下面添加节点。</span><span class="sxs-lookup"><span data-stu-id="91244-103">You can create an **XmlDocumentFragment** node and then add nodes under it.</span></span> <span data-ttu-id="91244-104">如果使用 InsertNode 方法插入 XmlDocumentFragment，不会复制 XmlDocumentFragment 节点，但会在 XML 文档对象模型 (DOM) 中插入它的子节点。</span><span class="sxs-lookup"><span data-stu-id="91244-104">When the **XmlDocumentFragment** is inserted with the **InsertNode** method, the **XmlDocumentFragment** node is not copied, but its child nodes are inserted in the XML Document Object Model (DOM).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91244-105">请参阅</span><span class="sxs-lookup"><span data-stu-id="91244-105">See Also</span></span>  
 [<span data-ttu-id="91244-106">XML 文档对象模型 (DOM)</span><span class="sxs-lookup"><span data-stu-id="91244-106">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
