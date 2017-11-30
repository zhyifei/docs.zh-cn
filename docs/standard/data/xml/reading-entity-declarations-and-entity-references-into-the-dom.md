---
title: "将实体声明和实体引用读入 DOM"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 86dba977-5cc4-4567-964f-027ffabc47b2
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 6370db06cbe7ff8d46258b0315059f5c37587fea
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="reading-entity-declarations-and-entity-references-into-the-dom"></a><span data-ttu-id="c778d-102">将实体声明和实体引用读入 DOM</span><span class="sxs-lookup"><span data-stu-id="c778d-102">Reading Entity Declarations and Entity References into the DOM</span></span>
<span data-ttu-id="c778d-103">实体是一个声明，指定了在 XML 中取代内容或标记而使用的名称。</span><span class="sxs-lookup"><span data-stu-id="c778d-103">An entity is a declaration that states a name to be used in the XML in place of content or markup.</span></span> <span data-ttu-id="c778d-104">实体包含两个部分。</span><span class="sxs-lookup"><span data-stu-id="c778d-104">There are two parts to entities.</span></span> <span data-ttu-id="c778d-105">首先，必须使用实体声明将名称绑定到替换内容。</span><span class="sxs-lookup"><span data-stu-id="c778d-105">First, you must tie a name to the replacement content using an entity declaration.</span></span> <span data-ttu-id="c778d-106">实体声明是使用 `<!ENTITY name "value">` 语法在文档类型定义 (DTD) 或 XML 架构中创建的。</span><span class="sxs-lookup"><span data-stu-id="c778d-106">An entity declaration is created by using the `<!ENTITY name "value">` syntax in a document type definition (DTD) or XML schema.</span></span> <span data-ttu-id="c778d-107">其次，在实体声明中定义的名称随后将在 XML 中使用。</span><span class="sxs-lookup"><span data-stu-id="c778d-107">Secondly, the name defined in the entity declaration is subsequently used in the XML.</span></span> <span data-ttu-id="c778d-108">在 XML 中使用时，该名称称为实体引用。</span><span class="sxs-lookup"><span data-stu-id="c778d-108">When used in the XML, it is called an entity reference.</span></span> <span data-ttu-id="c778d-109">例如，下面的实体声明声明一个名为 `publisher` 的实体，该实体与“Microsoft Press”的内容关联。</span><span class="sxs-lookup"><span data-stu-id="c778d-109">For example, the following entity declaration declares an entity of the name `publisher` being associated with the content of "Microsoft Press".</span></span>  
  
```xml  
<!ENTITY publisher "Microsoft Press">  
```  
  
 <span data-ttu-id="c778d-110">下面的示例说明如何在 XML 中将此实体声明作为实体引用使用。</span><span class="sxs-lookup"><span data-stu-id="c778d-110">The following example shows the use of this entity declaration in XML as an entity reference.</span></span>  
  
```xml  
<author>Fred</author>  
<pubinfo>Published by &publisher;</pubinfo>  
```  
  
 <span data-ttu-id="c778d-111">某些分析器在文档加载到内存中时自动扩展实体。</span><span class="sxs-lookup"><span data-stu-id="c778d-111">Some parsers automatically expand entities when a document is loaded into memory.</span></span> <span data-ttu-id="c778d-112">因此，当将 XML 读入内存中时，实体声明将被记住和保存。</span><span class="sxs-lookup"><span data-stu-id="c778d-112">Therefore, when the XML is being read into memory, entity declarations are remembered and saved.</span></span> <span data-ttu-id="c778d-113">当分析器以后遇到 `&;` 字符（用于标识常规实体引用）时，分析器将在实体声明表中查找此名称。</span><span class="sxs-lookup"><span data-stu-id="c778d-113">When the parser subsequently encounters `&;` characters, which identify a general entity reference, the parser looks up that name in an entity declaration table.</span></span> <span data-ttu-id="c778d-114">引用 `&publisher;` 被它所表示的内容取代。</span><span class="sxs-lookup"><span data-stu-id="c778d-114">The reference, `&publisher;` is replaced by the content that it represents.</span></span> <span data-ttu-id="c778d-115">使用以下 XML，</span><span class="sxs-lookup"><span data-stu-id="c778d-115">Using the following XML,</span></span>  
  
```xml  
<author>Fred</author>  
<pubinfo>Published by &publisher;</pubinfo>  
```  
  
 <span data-ttu-id="c778d-116">扩展此实体引用并用 Microsoft Press 内容替换 `&publisher;` 将提供以下扩展的 XML。</span><span class="sxs-lookup"><span data-stu-id="c778d-116">expanding the entity reference and replacing the `&publisher;` with the Microsoft Press content gives the following expanded XML.</span></span>  
  
 <span data-ttu-id="c778d-117">**输出**</span><span class="sxs-lookup"><span data-stu-id="c778d-117">**Output**</span></span>  
  
```xml  
<author>Fred</author>  
<pubinfo>Published by Microsoft Press</pubinfo>  
```  
  
 <span data-ttu-id="c778d-118">有多种实体。</span><span class="sxs-lookup"><span data-stu-id="c778d-118">There are many kinds of entities.</span></span> <span data-ttu-id="c778d-119">下面的关系图显示实体类型和术语的分类。</span><span class="sxs-lookup"><span data-stu-id="c778d-119">The following diagram shows the breakdown of entity types and terminology.</span></span>  
  
 <span data-ttu-id="c778d-120">![实体类型层次结构流程图](../../../../docs/standard/data/xml/media/entity-hierarchy.gif "Entity_hierarchy")</span><span class="sxs-lookup"><span data-stu-id="c778d-120">![flow chart of entity type hierarchy](../../../../docs/standard/data/xml/media/entity-hierarchy.gif "Entity_hierarchy")</span></span>  
  
 <span data-ttu-id="c778d-121">Microsoft.NET Framework 实现的 XML 文档对象模型 (DOM) 的默认值是保留实体引用，并在加载 XML 时不扩展这些实体。</span><span class="sxs-lookup"><span data-stu-id="c778d-121">The default for the Microsoft .NET Framework implementation of the XML Document Object Model (DOM) is to preserve the entities references and not expand the entities when the XML is loaded.</span></span> <span data-ttu-id="c778d-122">这是： 在文档加载到 DOM 中**XmlEntityReference**包含引用变量节点`&publisher;`创建，DTD 中声明与表示实体中的内容的子节点。</span><span class="sxs-lookup"><span data-stu-id="c778d-122">The implication of this is that as a document is loaded in the DOM, an **XmlEntityReference** node containing the reference variable `&publisher;` is created, with child nodes representing the content in the entity declared in the DTD.</span></span>  
  
 <span data-ttu-id="c778d-123">使用`<!ENTITY publisher "Microsoft Press">`实体声明下, 图显示**XmlEntity**和**XmlText**从此声明创建的节点。</span><span class="sxs-lookup"><span data-stu-id="c778d-123">Using the `<!ENTITY publisher "Microsoft Press">` entity declaration, the following diagram shows the **XmlEntity** and **XmlText** nodes created from this declaration.</span></span>  
  
 <span data-ttu-id="c778d-124">![从实体声明创建的节点](../../../../docs/standard/data/xml/media/xml-entitydeclaration-node2.png "xml_entitydeclaration_node2")</span><span class="sxs-lookup"><span data-stu-id="c778d-124">![nodes created from entity declaration](../../../../docs/standard/data/xml/media/xml-entitydeclaration-node2.png "xml_entitydeclaration_node2")</span></span>  
  
 <span data-ttu-id="c778d-125">实体引用在展开与未展开时的差异使在内存中的 DOM 树中生成的节点不同。</span><span class="sxs-lookup"><span data-stu-id="c778d-125">The differences when entity references are expanded and when they are not makes a difference in what nodes are generated in the DOM tree, in memory.</span></span> <span data-ttu-id="c778d-126">主题中讲述的节点之间生成的差异[保留实体引用](../../../../docs/standard/data/xml/entity-references-are-preserved.md)和[实体引用是扩展但不保留](../../../../docs/standard/data/xml/entity-references-are-expanded-and-not-preserved.md)。</span><span class="sxs-lookup"><span data-stu-id="c778d-126">The difference in the nodes that are generated is explained in the topics [Entity References are Preserved](../../../../docs/standard/data/xml/entity-references-are-preserved.md) and [Entity References are Expanded and Not Preserved](../../../../docs/standard/data/xml/entity-references-are-expanded-and-not-preserved.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c778d-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c778d-127">See Also</span></span>  
 [<span data-ttu-id="c778d-128">XML 文档对象模型 (DOM)</span><span class="sxs-lookup"><span data-stu-id="c778d-128">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
