---
title: "在 DOM 中创建新节点"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6c2b9789-b61a-49f9-b33f-db01a945edf2
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ec624a02f98fda4352b5ba8ff43681fba040c676
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="create-new-nodes-in-the-dom"></a><span data-ttu-id="c5d1f-102">在 DOM 中创建新节点</span><span class="sxs-lookup"><span data-stu-id="c5d1f-102">Create New Nodes in the DOM</span></span>
<span data-ttu-id="c5d1f-103"><xref:System.Xml.XmlDocument> 为所有节点类型提供了 create 方法。</span><span class="sxs-lookup"><span data-stu-id="c5d1f-103">The <xref:System.Xml.XmlDocument> has a create method for all of the node types.</span></span> <span data-ttu-id="c5d1f-104">为该方法提供名称（需要时）以及那些具有内容的节点（如文本节点）的内容或其他参数，这样便可创建节点。</span><span class="sxs-lookup"><span data-stu-id="c5d1f-104">Supply the method with a name when required, and content or other parameters for those nodes that have content (for example, a text node), and the node is created.</span></span> <span data-ttu-id="c5d1f-105">下面的方法需要填充名称和几个其他参数以创建相应的节点。</span><span class="sxs-lookup"><span data-stu-id="c5d1f-105">The following methods are ones that need a name and a few other parameters filled to create an appropriate node.</span></span>  
  
-   <xref:System.Xml.XmlDocument.CreateCDataSection%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateComment%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateDocumentFragment%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateDocumentType%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateElement%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateNode%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateProcessingInstruction%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateSignificantWhitespace%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateTextNode%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateWhitespace%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateXmlDeclaration%2A>  
  
 <span data-ttu-id="c5d1f-106">其他节点类型不仅仅只要求向参数提供数据。</span><span class="sxs-lookup"><span data-stu-id="c5d1f-106">Other node types have more requirements than just providing data to parameters.</span></span>  
  
 <span data-ttu-id="c5d1f-107">有关属性的信息，请参阅[DOM 中的元素创建新属性](../../../../docs/standard/data/xml/creating-new-attributes-for-elements-in-the-dom.md)。</span><span class="sxs-lookup"><span data-stu-id="c5d1f-107">For information on attributes, see [Creating New Attributes for Elements in the DOM](../../../../docs/standard/data/xml/creating-new-attributes-for-elements-in-the-dom.md).</span></span> <span data-ttu-id="c5d1f-108">元素和属性名验证的信息，请参阅[XML 元素和属性名验证时创建新节点](../../../../docs/standard/data/xml/xml-element-and-attribute-name-verification-when-creating-new-nodes.md)。</span><span class="sxs-lookup"><span data-stu-id="c5d1f-108">For information on element and attribute name validation, see [XML Element and Attribute Name Verification when Creating New Nodes](../../../../docs/standard/data/xml/xml-element-and-attribute-name-verification-when-creating-new-nodes.md).</span></span> <span data-ttu-id="c5d1f-109">有关如何创建实体引用，请参阅[创建新实体引用](../../../../docs/standard/data/xml/creating-new-entity-references.md)。</span><span class="sxs-lookup"><span data-stu-id="c5d1f-109">For creating entity references, see [Creating New Entity References](../../../../docs/standard/data/xml/creating-new-entity-references.md).</span></span> <span data-ttu-id="c5d1f-110">命名空间如何影响实体引用的扩展的信息，请参阅[对实体引用扩展的新节点包含元素和属性的 Namespace 影响](../../../../docs/standard/data/xml/namespace-affect-on-entity-ref-expansion-for-new-nodes.md)。</span><span class="sxs-lookup"><span data-stu-id="c5d1f-110">For information on how namespaces affect the expansion of entity references, see [Namespace Affect on Entity Reference Expansion for New Nodes Containing Elements and Attributes](../../../../docs/standard/data/xml/namespace-affect-on-entity-ref-expansion-for-new-nodes.md).</span></span>  
  
 <span data-ttu-id="c5d1f-111">创建新节点后，有几个方法可用于将其插入到树中。</span><span class="sxs-lookup"><span data-stu-id="c5d1f-111">Once new nodes are created, there are several methods available to insert them into the tree.</span></span> <span data-ttu-id="c5d1f-112">下表列出了这些方法，并描述了新节点在 XML 文档对象模型 (DOM) 中的位置。</span><span class="sxs-lookup"><span data-stu-id="c5d1f-112">The table lists the methods with a description of where the new node appears in the XML Document Object Model (DOM).</span></span>  
  
|<span data-ttu-id="c5d1f-113">方法</span><span class="sxs-lookup"><span data-stu-id="c5d1f-113">Method</span></span>|<span data-ttu-id="c5d1f-114">节点位置</span><span class="sxs-lookup"><span data-stu-id="c5d1f-114">Node placement</span></span>|  
|------------|--------------------|  
|<xref:System.Xml.XmlNode.InsertBefore%2A>|<span data-ttu-id="c5d1f-115">插入到引用节点之前。</span><span class="sxs-lookup"><span data-stu-id="c5d1f-115">Inserted before the reference node.</span></span> <span data-ttu-id="c5d1f-116">例如，在位置 5 插入新节点：</span><span class="sxs-lookup"><span data-stu-id="c5d1f-116">For example, to insert the new node in position 5:</span></span><br /><br /> `Dim refChild As XmlNode = node.ChildNodes(4) 'The reference is zero-based.node.InsertBefore(newChild, refChild);`<br /><br /> `XmlNode refChild = node.ChildNodes[4]; //The reference is zero-based. node.InsertBefore(newChild, refChild);`<br /><br /> <span data-ttu-id="c5d1f-117">有关更多信息，请参见 <xref:System.Xml.XmlNode.InsertBefore%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="c5d1f-117">For more information, see the <xref:System.Xml.XmlNode.InsertBefore%2A> method.</span></span>|  
|<xref:System.Xml.XmlNode.InsertAfter%2A>|<span data-ttu-id="c5d1f-118">插入到引用节点之后。</span><span class="sxs-lookup"><span data-stu-id="c5d1f-118">Inserted after the reference node.</span></span> <span data-ttu-id="c5d1f-119">例如：</span><span class="sxs-lookup"><span data-stu-id="c5d1f-119">For example:</span></span><br /><br /> `node.InsertAfter(newChild, refChild)`<br /><br /> `node.InsertAfter(newChild, refChild);`<br /><br /> <span data-ttu-id="c5d1f-120">有关更多信息，请参见 <xref:System.Xml.XmlNode.InsertAfter%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="c5d1f-120">For more information, see the <xref:System.Xml.XmlNode.InsertAfter%2A> method.</span></span>|  
|<xref:System.Xml.XmlNode.AppendChild%2A>|<span data-ttu-id="c5d1f-121">将节点添加到给定节点的子节点列表的末尾。</span><span class="sxs-lookup"><span data-stu-id="c5d1f-121">Adds the node to the end of the list of child nodes for the given node.</span></span> <span data-ttu-id="c5d1f-122">如果所添加的节点是 <xref:System.Xml.XmlDocumentFragment>，则会将文档片段的全部内容移至该节点的子列表中。</span><span class="sxs-lookup"><span data-stu-id="c5d1f-122">If the node being added is an <xref:System.Xml.XmlDocumentFragment>, the entire contents of the document fragment are moved into the child list of this node.</span></span> <span data-ttu-id="c5d1f-123">有关更多信息，请参见 <xref:System.Xml.XmlNode.AppendChild%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="c5d1f-123">For more information, see the <xref:System.Xml.XmlNode.AppendChild%2A> method.</span></span>|  
|<xref:System.Xml.XmlNode.PrependChild%2A>|<span data-ttu-id="c5d1f-124">将节点添加到给定节点的子节点列表的开头。</span><span class="sxs-lookup"><span data-stu-id="c5d1f-124">Adds the node to the beginning of the list of child nodes of the given node.</span></span> <span data-ttu-id="c5d1f-125">如果所添加的节点是 <xref:System.Xml.XmlDocumentFragment>，则会将文档片段的全部内容移至该节点的子列表中。</span><span class="sxs-lookup"><span data-stu-id="c5d1f-125">If the node being added is an <xref:System.Xml.XmlDocumentFragment>, the entire contents of the document fragment are moved into the child list of this node.</span></span> <span data-ttu-id="c5d1f-126">有关更多信息，请参见 <xref:System.Xml.XmlNode.PrependChild%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="c5d1f-126">For more information, see the <xref:System.Xml.XmlNode.PrependChild%2A> method.</span></span>|  
|<xref:System.Xml.XmlAttributeCollection.Append%2A>|<span data-ttu-id="c5d1f-127">将 <xref:System.Xml.XmlAttribute> 节点追加到与元素关联的属性集合的末尾。</span><span class="sxs-lookup"><span data-stu-id="c5d1f-127">Appends an <xref:System.Xml.XmlAttribute> node to the end of the attribute collection associated with an element.</span></span> <span data-ttu-id="c5d1f-128">有关更多信息，请参见 <xref:System.Xml.XmlAttributeCollection.Append%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="c5d1f-128">For more information, see the <xref:System.Xml.XmlAttributeCollection.Append%2A> method.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c5d1f-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c5d1f-129">See Also</span></span>  
 [<span data-ttu-id="c5d1f-130">XML 文档对象模型 (DOM)</span><span class="sxs-lookup"><span data-stu-id="c5d1f-130">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
