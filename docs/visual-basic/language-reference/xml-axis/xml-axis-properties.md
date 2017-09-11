---
title: "XML 轴属性 (Visual Basic 中) |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- XML axis properties [Visual Basic]
- Visual Basic code, XML
- XML axis [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: 7e400e20-5d1e-4d22-a65c-9df79d5c1621
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 4dd15670eed316552f2f02e4536122a6a110542d
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="xml-axis-properties-visual-basic"></a><span data-ttu-id="f0a1d-102">XML 轴属性 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f0a1d-102">XML Axis Properties (Visual Basic)</span></span>
<span data-ttu-id="f0a1d-103">本部分中的主题的文档中的 XML 轴属性的语法[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]。</span><span class="sxs-lookup"><span data-stu-id="f0a1d-103">The topics in this section document the syntax of XML axis properties in [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span> <span data-ttu-id="f0a1d-104">XML 轴属性使其可以轻松地在您的代码中直接访问 XML。</span><span class="sxs-lookup"><span data-stu-id="f0a1d-104">The XML axis properties make it easy to access XML directly in your code.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f0a1d-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="f0a1d-105">In This Section</span></span>  
  
|<span data-ttu-id="f0a1d-106">主题</span><span class="sxs-lookup"><span data-stu-id="f0a1d-106">Topic</span></span>|<span data-ttu-id="f0a1d-107">描述</span><span class="sxs-lookup"><span data-stu-id="f0a1d-107">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="f0a1d-108">XML 特性轴属性</span><span class="sxs-lookup"><span data-stu-id="f0a1d-108">XML Attribute Axis Property</span></span>](../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)|<span data-ttu-id="f0a1d-109">描述如何访问的特性<xref:System.Xml.Linq.XElement>对象。</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="f0a1d-109">Describes how to access the attributes of an <xref:System.Xml.Linq.XElement> object.</span></span>|  
|[<span data-ttu-id="f0a1d-110">XML 子轴属性</span><span class="sxs-lookup"><span data-stu-id="f0a1d-110">XML Child Axis Property</span></span>](../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)|<span data-ttu-id="f0a1d-111">介绍如何访问的子级<xref:System.Xml.Linq.XElement>对象。</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="f0a1d-111">Describes how to access the children of an <xref:System.Xml.Linq.XElement> object.</span></span>|  
|[<span data-ttu-id="f0a1d-112">XML 子代轴属性</span><span class="sxs-lookup"><span data-stu-id="f0a1d-112">XML Descendant Axis Property</span></span>](../../../visual-basic/language-reference/xml-axis/xml-descendant-axis-property.md)|<span data-ttu-id="f0a1d-113">介绍如何访问的后代<xref:System.Xml.Linq.XElement>对象。</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="f0a1d-113">Describes how to access the descendants of an <xref:System.Xml.Linq.XElement> object.</span></span>|  
|[<span data-ttu-id="f0a1d-114">扩展索引器属性</span><span class="sxs-lookup"><span data-stu-id="f0a1d-114">Extension Indexer Property</span></span>](../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md)|<span data-ttu-id="f0a1d-115">描述如何访问集合中的各个元素<xref:System.Xml.Linq.XElement>或<xref:System.Xml.Linq.XAttribute>对象。</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="f0a1d-115">Describes how to access individual elements in a collection of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute> objects.</span></span>|  
|[<span data-ttu-id="f0a1d-116">XML 值属性</span><span class="sxs-lookup"><span data-stu-id="f0a1d-116">XML Value Property</span></span>](../../../visual-basic/language-reference/xml-axis/xml-value-property.md)|<span data-ttu-id="f0a1d-117">介绍如何访问的集合的第一个元素的值<xref:System.Xml.Linq.XElement>或<xref:System.Xml.Linq.XAttribute>对象。</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="f0a1d-117">Describes how to access the value of the first element of a collection of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute> objects.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f0a1d-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f0a1d-118">See Also</span></span>  
 [<span data-ttu-id="f0a1d-119">XML</span><span class="sxs-lookup"><span data-stu-id="f0a1d-119">XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/index.md)
