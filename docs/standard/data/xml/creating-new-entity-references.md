---
title: "创建新实体引用"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a42f81b3-0403-4e34-b346-7d2129804e54
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 22e9b66f58275141cf9da154573ca43a0b90affc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="creating-new-entity-references"></a><span data-ttu-id="ba7a6-102">创建新实体引用</span><span class="sxs-lookup"><span data-stu-id="ba7a6-102">Creating New Entity References</span></span>
<span data-ttu-id="ba7a6-103">**CreateEntityReference**方法创建一个新**XmlEntityReference**节点。</span><span class="sxs-lookup"><span data-stu-id="ba7a6-103">The **CreateEntityReference** method creates a new **XmlEntityReference** node.</span></span> <span data-ttu-id="ba7a6-104">XML 文档对象模型 (DOM) 查看是否已声明了引用的实体名称。</span><span class="sxs-lookup"><span data-stu-id="ba7a6-104">The XML Document Object Model (DOM) looks to see if the entity name being referenced has already been declared.</span></span> <span data-ttu-id="ba7a6-105">如果具有的子节点**XmlEntityReference**从实体声明节点复制节点。</span><span class="sxs-lookup"><span data-stu-id="ba7a6-105">If it has, the child nodes of **XmlEntityReference** node are copied from the entity declaration node.</span></span> <span data-ttu-id="ba7a6-106">如果没有匹配的实体声明，则附加一个空的文本节点作为实体引用节点的唯一子级。</span><span class="sxs-lookup"><span data-stu-id="ba7a6-106">If there is no entity declaration that matches, an empty text node is attached as the only child of the entity reference node.</span></span> <span data-ttu-id="ba7a6-107">因为的子节点**XmlEntityReference**节点是其他节点的副本，这些子节点是只读的不能修改。</span><span class="sxs-lookup"><span data-stu-id="ba7a6-107">Because the child nodes of the **XmlEntityReference** node are copies of other nodes, these child nodes are read-only and cannot be modified.</span></span>  
  
 <span data-ttu-id="ba7a6-108">当复制节点时，在实体引用所处的范围内可能存在一个命名空间。</span><span class="sxs-lookup"><span data-stu-id="ba7a6-108">When the nodes are copied, there may be a namespace in scope at the point of the entity reference.</span></span> <span data-ttu-id="ba7a6-109">此命名空间影响生成的任何元素或属性节点的配置。</span><span class="sxs-lookup"><span data-stu-id="ba7a6-109">This namespace affects the configuration of any element or attribute nodes generated.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ba7a6-110">DOM 将添加到的子节点**EntityReference**仅插入**EntityReference**到文档的节点。</span><span class="sxs-lookup"><span data-stu-id="ba7a6-110">The DOM adds child nodes to the **EntityReference** only when you insert the **EntityReference** node to the document.</span></span> <span data-ttu-id="ba7a6-111">新创建的**EntityReference**节点具有任何子节点。</span><span class="sxs-lookup"><span data-stu-id="ba7a6-111">Newly created **EntityReference** nodes have no child nodes.</span></span>  
  
 <span data-ttu-id="ba7a6-112">即使**XmlDataDocument**的是派生类**XmlDocument**、 **XmlDataDocument**不支持实体引用的创建。</span><span class="sxs-lookup"><span data-stu-id="ba7a6-112">Even though the **XmlDataDocument** is a derived class of the **XmlDocument**, the **XmlDataDocument** does not support the creation of entity references.</span></span> <span data-ttu-id="ba7a6-113">这是因为**EntityReference**子级是只读的。</span><span class="sxs-lookup"><span data-stu-id="ba7a6-113">This is because **EntityReference** children are read-only.</span></span> <span data-ttu-id="ba7a6-114">子级**EntityReference**节点可以跨多个区域。</span><span class="sxs-lookup"><span data-stu-id="ba7a6-114">The children of an **EntityReference** node can span more than one region.</span></span> <span data-ttu-id="ba7a6-115">在这种情况下，与包含的一部分的区域相关联的行的一部分**EntityReference**将是只读的。</span><span class="sxs-lookup"><span data-stu-id="ba7a6-115">In this case, part of a row associated with the region that contains a part of an **EntityReference** will be read-only.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba7a6-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ba7a6-116">See Also</span></span>  
 [<span data-ttu-id="ba7a6-117">XML 文档对象模型 (DOM)</span><span class="sxs-lookup"><span data-stu-id="ba7a6-117">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
