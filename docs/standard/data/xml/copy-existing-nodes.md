---
title: 复制现有节点
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 2aa8f65c-cc62-4638-9c46-129dc15be786
author: mairaw
ms.author: mairaw
ms.openlocfilehash: eda5c9b4851b29c0a76e45414d7c47ba52252455
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/09/2018
ms.locfileid: "44252865"
---
# <a name="copy-existing-nodes"></a><span data-ttu-id="025ac-102">复制现有节点</span><span class="sxs-lookup"><span data-stu-id="025ac-102">Copy Existing Nodes</span></span>
<span data-ttu-id="025ac-103">XML 文档对象模型 (DOM) 包含许多可用于选择节点的方法和属性，如 SelectSingleNode、ChildNodes[int i]、Attributes[int i]。</span><span class="sxs-lookup"><span data-stu-id="025ac-103">There are many methods and properties in the XML Document Object Model (DOM)you can use to select a node, such as **SelectSingleNode**, **ChildNodes[int i]**, **Attributes[int i]**.</span></span> <span data-ttu-id="025ac-104">选择节点后，可以使用适用于特定节点类型的插入方法之一将该节点插入到树中。</span><span class="sxs-lookup"><span data-stu-id="025ac-104">Once the node is selected, you can insert it into the tree using one of the insert methods that work for that particular node type.</span></span> <span data-ttu-id="025ac-105">将节点插入到树中的唯一限制是在插入节点后文档的格式仍必须是正确的。</span><span class="sxs-lookup"><span data-stu-id="025ac-105">The only restriction to inserting a node into the tree is that the document must still be well-formed after the node is inserted.</span></span> <span data-ttu-id="025ac-106">将现有节点插入到 DOM 树中时，该节点从其原始位置移除并添加到它的目标位置。</span><span class="sxs-lookup"><span data-stu-id="025ac-106">When an existing node is inserted into the DOM tree, it is removed from its original position and added to its target position.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="025ac-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="025ac-107">See also</span></span>

- [<span data-ttu-id="025ac-108">XML 文档对象模型 (DOM)</span><span class="sxs-lookup"><span data-stu-id="025ac-108">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
