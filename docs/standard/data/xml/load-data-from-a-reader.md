---
title: "从读取器中加载数据"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7e74918c-bc72-4977-a49b-e1520a6d8f60
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b899ae870fe92b31d7f4fcd088531f63694bd233
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="load-data-from-a-reader"></a><span data-ttu-id="d06bd-102">从读取器中加载数据</span><span class="sxs-lookup"><span data-stu-id="d06bd-102">Load Data from a Reader</span></span>
<span data-ttu-id="d06bd-103">如果使用 <xref:System.Xml.XmlDocument.Load%2A> 方法和 <xref:System.Xml.XmlReader> 的参数加载 XML 文档，与从其他格式加载数据的行为相比，发生的行为有所不同。</span><span class="sxs-lookup"><span data-stu-id="d06bd-103">If an XML document is loaded using the <xref:System.Xml.XmlDocument.Load%2A> method and a parameter of an <xref:System.Xml.XmlReader>, there are differences in the behavior that occurs when compared to the behavior of loading data from the other formats.</span></span> <span data-ttu-id="d06bd-104">如果读取器处于初始状态，<xref:System.Xml.XmlDocument.Load%2A> 将使用读取器中的全部内容，并通过读取器中的所有数据生成 XML 文档对象模型 (DOM)。</span><span class="sxs-lookup"><span data-stu-id="d06bd-104">If the reader is in its initial state, <xref:System.Xml.XmlDocument.Load%2A> consumes the entire contents from the reader and builds the XML Document Object Model (DOM) from all the data in the reader.</span></span>  
  
 <span data-ttu-id="d06bd-105">如果读取器已位于文档中某个位置的节点上，并且将读取器传递给 <xref:System.Xml.XmlDocument.Load%2A> 方法，<xref:System.Xml.XmlDocument.Load%2A> 会尝试将当前节点及其所有同级节点（直到关闭当前深度的结束标记）读入内存。</span><span class="sxs-lookup"><span data-stu-id="d06bd-105">If the reader is already positioned on a node somewhere in the document, and the reader is then passed to the <xref:System.Xml.XmlDocument.Load%2A> method, <xref:System.Xml.XmlDocument.Load%2A> attempts to read the current node and all of its siblings, up to the end tag that closes the current depth into memory.</span></span> <span data-ttu-id="d06bd-106">尝试的 <xref:System.Xml.XmlDocument.Load%2A> 是否成功取决于在尝试加载时读取器所处的节点，因为 <xref:System.Xml.XmlDocument.Load%2A> 会验证读取器中的 XML 的格式是否正确。</span><span class="sxs-lookup"><span data-stu-id="d06bd-106">The success of the attempted <xref:System.Xml.XmlDocument.Load%2A> depends on the node that the reader is on when the load is attempted, as <xref:System.Xml.XmlDocument.Load%2A> verifies that the XML from the reader is well-formed.</span></span> <span data-ttu-id="d06bd-107">如果 XML 的格式不正确，<xref:System.Xml.XmlDocument.Load%2A> 将引发异常。</span><span class="sxs-lookup"><span data-stu-id="d06bd-107">If the XML is not well-formed, the <xref:System.Xml.XmlDocument.Load%2A> throws an exception.</span></span> <span data-ttu-id="d06bd-108">例如，以下节点集包含两个根级别的元素，XML 的格式不正确，<xref:System.Xml.XmlDocument.Load%2A> 将引发异常。</span><span class="sxs-lookup"><span data-stu-id="d06bd-108">For example, the following set of nodes contain two root-level elements, the XML is not well-formed, and <xref:System.Xml.XmlDocument.Load%2A> throws an exception.</span></span>  
  
-   <span data-ttu-id="d06bd-109">依次为 Comment 节点、Element 节点、Element 节点、EndElement 节点。</span><span class="sxs-lookup"><span data-stu-id="d06bd-109">Comment node, followed by an Element node, followed by an Element node, followed by an EndElement node.</span></span>  
  
 <span data-ttu-id="d06bd-110">下面的节点集创建不完整的 DOM，原因是没有根级别元素。</span><span class="sxs-lookup"><span data-stu-id="d06bd-110">The following set of nodes creates an incomplete DOM, because there is no root-level element.</span></span>  
  
-   <span data-ttu-id="d06bd-111">Comment 节点，后跟 ProcessingInstruction 节点，后跟 Comment 节点，后跟 EndElement 节点。</span><span class="sxs-lookup"><span data-stu-id="d06bd-111">Comment node followed by a ProcessingInstruction node followed by a Comment node followed by an EndElement node.</span></span>  
  
 <span data-ttu-id="d06bd-112">这不引发异常，并且加载数据。</span><span class="sxs-lookup"><span data-stu-id="d06bd-112">This does not throw an exception, and the data is loaded.</span></span> <span data-ttu-id="d06bd-113">可以向这些节点的顶部添加根元素并创建保存时不会发生错误的格式正确的 XML。</span><span class="sxs-lookup"><span data-stu-id="d06bd-113">You can add a root element to the top of these nodes and create well-formed XML that can be saved without error.</span></span>  
  
 <span data-ttu-id="d06bd-114">如果读取器定位于对于文档的根级别来说无效的叶节点（如空白或属性节点），则读取器继续读取，直到定位在可用于根的节点上。</span><span class="sxs-lookup"><span data-stu-id="d06bd-114">If the reader is positioned on a leaf node that is invalid for the root level of a document (for example, a white space or attribute node), the reader continues to read until it is positioned on a node that can be used for the root.</span></span> <span data-ttu-id="d06bd-115">文档在此时开始加载。</span><span class="sxs-lookup"><span data-stu-id="d06bd-115">The document begins loading at this point.</span></span>  
  
 <span data-ttu-id="d06bd-116">默认情况下，<xref:System.Xml.XmlDocument.Load%2A> 不会使用文档类型定义 (DTD) 或架构验证来验证 XML 是否有效。</span><span class="sxs-lookup"><span data-stu-id="d06bd-116">By default, <xref:System.Xml.XmlDocument.Load%2A> does not verify whether the XML is valid using document type definition (DTD) or schema validation.</span></span> <span data-ttu-id="d06bd-117">只验证 XML 的格式是否正确。</span><span class="sxs-lookup"><span data-stu-id="d06bd-117">It only verifies whether the XML is well-formed.</span></span> <span data-ttu-id="d06bd-118">要进行验证，需要使用 <xref:System.Xml.XmlReader> 类创建一个 <xref:System.Xml.XmlReaderSettings>。</span><span class="sxs-lookup"><span data-stu-id="d06bd-118">In order for validation to occur, you need to create an <xref:System.Xml.XmlReader> using the <xref:System.Xml.XmlReaderSettings> class.</span></span> <span data-ttu-id="d06bd-119"><xref:System.Xml.XmlReader> 类可以使用 DTD 或架构定义语言 (XSD) 架构强制进行验证。</span><span class="sxs-lookup"><span data-stu-id="d06bd-119">The <xref:System.Xml.XmlReader> class can enforce validation using a DTD or Schema definition language (XSD) schema.</span></span> <span data-ttu-id="d06bd-120"><xref:System.Xml.ValidationType> 类的 <xref:System.Xml.XmlReaderSettings> 属性确定 <xref:System.Xml.XmlReader> 实例是否强制进行验证。</span><span class="sxs-lookup"><span data-stu-id="d06bd-120">The <xref:System.Xml.ValidationType> property on the <xref:System.Xml.XmlReaderSettings> class determines whether the <xref:System.Xml.XmlReader> instance enforces validation.</span></span> <span data-ttu-id="d06bd-121">有关验证 XML 数据的详细信息，请参阅 <xref:System.Xml.XmlReader> 引用页的“备注”部分。</span><span class="sxs-lookup"><span data-stu-id="d06bd-121">For more information about validating XML data, see the Remarks section of the <xref:System.Xml.XmlReader> reference page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d06bd-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d06bd-122">See Also</span></span>  
 [<span data-ttu-id="d06bd-123">XML 文档对象模型 (DOM)</span><span class="sxs-lookup"><span data-stu-id="d06bd-123">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
