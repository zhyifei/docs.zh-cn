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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: c026d9f825375d74d53d5cc46969ff0f713bab1c
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="copy-existing-nodes"></a><span data-ttu-id="96a13-102">复制现有节点</span><span class="sxs-lookup"><span data-stu-id="96a13-102">Copy Existing Nodes</span></span>
<span data-ttu-id="96a13-103">XML 文档对象模型 (DOM) 包含许多可用于选择节点的方法和属性，如 SelectSingleNode、ChildNodes[int i]、Attributes[int i]。</span><span class="sxs-lookup"><span data-stu-id="96a13-103">There are many methods and properties in the XML Document Object Model (DOM)you can use to select a node, such as **SelectSingleNode**, **ChildNodes[int i]**, **Attributes[int i]**.</span></span> <span data-ttu-id="96a13-104">选择节点后，可以使用适用于特定节点类型的插入方法之一将该节点插入到树中。</span><span class="sxs-lookup"><span data-stu-id="96a13-104">Once the node is selected, you can insert it into the tree using one of the insert methods that work for that particular node type.</span></span> <span data-ttu-id="96a13-105">将节点插入到树中的唯一限制是在插入节点后文档的格式仍必须是正确的。</span><span class="sxs-lookup"><span data-stu-id="96a13-105">The only restriction to inserting a node into the tree is that the document must still be well-formed after the node is inserted.</span></span> <span data-ttu-id="96a13-106">将现有节点插入到 DOM 树中时，该节点从其原始位置移除并添加到它的目标位置。</span><span class="sxs-lookup"><span data-stu-id="96a13-106">When an existing node is inserted into the DOM tree, it is removed from its original position and added to its target position.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96a13-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="96a13-107">See Also</span></span>  
 [<span data-ttu-id="96a13-108">XML 文档对象模型 (DOM)</span><span class="sxs-lookup"><span data-stu-id="96a13-108">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
