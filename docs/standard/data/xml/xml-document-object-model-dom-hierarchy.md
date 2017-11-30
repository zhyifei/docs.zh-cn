---
title: "XML 文档对象模型 (DOM) 层次结构"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9d187d4f-c76e-4223-a670-cc290783ce47
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 6dec61860fba5815b1dae802d280e8df6628ab91
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="xml-document-object-model-dom-hierarchy"></a><span data-ttu-id="79d2c-102">XML 文档对象模型 (DOM) 层次结构</span><span class="sxs-lookup"><span data-stu-id="79d2c-102">XML Document Object Model (DOM) Hierarchy</span></span>
<span data-ttu-id="79d2c-103">下图显示了 XML 文档对象模型 (DOM) 的类层次结构，其中万维网联合会 (W3C) 名称用括号括起来，另外还有相关的类名。</span><span class="sxs-lookup"><span data-stu-id="79d2c-103">The following illustration shows the class hierarchy for the XML Document Object Model (DOM), with the World Wide Web Consortium (W3C) name in parenthesis along with the class name where it is relevant.</span></span>  
  
 <span data-ttu-id="79d2c-104">![XML 文档对象模型 &#40; DOM &#41;层次结构](../../../../docs/standard/data/xml/media/dom-class-hierarchy.gif "Dom_class_hierarchy")</span><span class="sxs-lookup"><span data-stu-id="79d2c-104">![XML Document Object Model &#40;DOM&#41; hierarchy](../../../../docs/standard/data/xml/media/dom-class-hierarchy.gif "Dom_class_hierarchy")</span></span>  
<span data-ttu-id="79d2c-105">XML 文档对象模型 (DOM) 层次结构</span><span class="sxs-lookup"><span data-stu-id="79d2c-105">XML Document Object Model (DOM) hierarchy</span></span>  
  
 <span data-ttu-id="79d2c-106">以下类不是继承自**XmlNode**:</span><span class="sxs-lookup"><span data-stu-id="79d2c-106">The following classes do not inherit from the **XmlNode**:</span></span>  
  
-   <span data-ttu-id="79d2c-107">**XmlImplementation**</span><span class="sxs-lookup"><span data-stu-id="79d2c-107">**XmlImplementation**</span></span>  
  
-   <span data-ttu-id="79d2c-108">**XmlNamedNodeMap**</span><span class="sxs-lookup"><span data-stu-id="79d2c-108">**XmlNamedNodeMap**</span></span>  
  
-   <span data-ttu-id="79d2c-109">**XmlNodeList**</span><span class="sxs-lookup"><span data-stu-id="79d2c-109">**XmlNodeList**</span></span>  
  
-   <span data-ttu-id="79d2c-110">**XmlNodeChangedEventArgs**</span><span class="sxs-lookup"><span data-stu-id="79d2c-110">**XmlNodeChangedEventArgs**</span></span>  
  
 <span data-ttu-id="79d2c-111">**XmlImplementation**类用于创建 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="79d2c-111">The **XmlImplementation** class is used to create an XML document.</span></span> <span data-ttu-id="79d2c-112">有关详细信息，请参阅[XML 文档创建](../../../../docs/standard/data/xml/xml-document-creation.md)。</span><span class="sxs-lookup"><span data-stu-id="79d2c-112">For more information, see [XML Document Creation](../../../../docs/standard/data/xml/xml-document-creation.md).</span></span>  
  
 <span data-ttu-id="79d2c-113">**XmlNamedNodeMap**类处理节点的无序的集。</span><span class="sxs-lookup"><span data-stu-id="79d2c-113">The **XmlNamedNodeMap** class handles an unordered set of nodes.</span></span> <span data-ttu-id="79d2c-114">有关详细信息，请参阅[按名称或索引检索未排序节点](../../../../docs/standard/data/xml/unordered-node-retrieval-by-name-or-index.md)。</span><span class="sxs-lookup"><span data-stu-id="79d2c-114">For more information, see [Unordered Node Retrieval by Name or Index](../../../../docs/standard/data/xml/unordered-node-retrieval-by-name-or-index.md).</span></span>  
  
 <span data-ttu-id="79d2c-115">**XmlNodeList**类处理已排序的节点列表。</span><span class="sxs-lookup"><span data-stu-id="79d2c-115">The **XmlNodeList** class handles an ordered list of nodes.</span></span> <span data-ttu-id="79d2c-116">有关详细信息，请参阅[按索引检索已排序节点](../../../../docs/standard/data/xml/ordered-node-retrieval-by-index.md)。</span><span class="sxs-lookup"><span data-stu-id="79d2c-116">For more information, see [Ordered Node Retrieval by Index](../../../../docs/standard/data/xml/ordered-node-retrieval-by-index.md).</span></span>  
  
 <span data-ttu-id="79d2c-117">**XmlNodeChangedEventArgs**类处理上注册的事件处理程序**XmlDocument**。</span><span class="sxs-lookup"><span data-stu-id="79d2c-117">The **XmlNodeChangedEventArgs** class handles event handlers registered on the **XmlDocument**.</span></span> <span data-ttu-id="79d2c-118">有关详细信息，请参阅[使用 XmlNodeChangedEventArgs 的 XML 文档中的事件处理](../../../../docs/standard/data/xml/event-handling-in-an-xml-document-using-the-xmlnodechangedeventargs.md)。</span><span class="sxs-lookup"><span data-stu-id="79d2c-118">For more information, see [Event Handling in an XML Document using the XmlNodeChangedEventArgs](../../../../docs/standard/data/xml/event-handling-in-an-xml-document-using-the-xmlnodechangedeventargs.md).</span></span>  
  
 <span data-ttu-id="79d2c-119">**XmlLinkedNode**类继承自**XmlNode**。</span><span class="sxs-lookup"><span data-stu-id="79d2c-119">The **XmlLinkedNode** class inherits from **XmlNode**.</span></span> <span data-ttu-id="79d2c-120">其目的是重写中的两个方法**XmlNode**: **PreviousSibling**和**NextSibling**方法。</span><span class="sxs-lookup"><span data-stu-id="79d2c-120">Its purpose is to override two methods from **XmlNode**: the **PreviousSibling** and **NextSibling** methods.</span></span> <span data-ttu-id="79d2c-121">然后再继承并使用这些重写的方法**XmlCharacterData**， **XmlDeclaration**， **XmlDocumentType**， **XmlElement**， **XmlEntityReference**，和**XmlProcessingInstruction**，这是上一个和下一个同级的类。</span><span class="sxs-lookup"><span data-stu-id="79d2c-121">These overridden methods are then inherited and used by **XmlCharacterData**, **XmlDeclaration**, **XmlDocumentType**, **XmlElement**, **XmlEntityReference**, and **XmlProcessingInstruction**, which are classes that have previous and next siblings.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79d2c-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="79d2c-122">See Also</span></span>  
 [<span data-ttu-id="79d2c-123">XML 文档对象模型 (DOM)</span><span class="sxs-lookup"><span data-stu-id="79d2c-123">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
