---
title: XML (Visual Basic 中) 的功能转换
ms.date: 07/20/2015
ms.assetid: fdbe5b91-f457-4b4e-a11b-def4bdd77bab
ms.openlocfilehash: 06803feb0fe23ae4afe2237b64bf920f6e229060
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2018
ms.locfileid: "49371675"
---
# <a name="functional-transformation-of-xml-visual-basic"></a><span data-ttu-id="92bb5-102">XML (Visual Basic 中) 的功能转换</span><span class="sxs-lookup"><span data-stu-id="92bb5-102">Functional Transformation of XML (Visual Basic)</span></span>
<span data-ttu-id="92bb5-103">本主题讨论用于修改 XML 文档的纯函数转换方法，并将该方法与过程方法进行比较。</span><span class="sxs-lookup"><span data-stu-id="92bb5-103">This topic discusses the pure functional transformation approach to modifying XML documents, and contrasts it with a procedural approach.</span></span>  
  
## <a name="modifying-an-xml-document"></a><span data-ttu-id="92bb5-104">修改 XML 文档</span><span class="sxs-lookup"><span data-stu-id="92bb5-104">Modifying an XML Document</span></span>  
 <span data-ttu-id="92bb5-105">对 XML 程序员来说，最常见的任务之一就是将 XML 从一种形状转换为另一种形状。</span><span class="sxs-lookup"><span data-stu-id="92bb5-105">One of the most common tasks for an XML programmer is transforming XML from one shape to another.</span></span> <span data-ttu-id="92bb5-106">XML 文档的形状就是文档的结构，包括下列内容：</span><span class="sxs-lookup"><span data-stu-id="92bb5-106">The shape of an XML document is the structure of the document, which includes the following:</span></span>  
  
-   <span data-ttu-id="92bb5-107">文档所表达的层次结构。</span><span class="sxs-lookup"><span data-stu-id="92bb5-107">The hierarchy expressed by the document.</span></span>  
  
-   <span data-ttu-id="92bb5-108">元素和属性的名称。</span><span class="sxs-lookup"><span data-stu-id="92bb5-108">The element and attribute names.</span></span>  
  
-   <span data-ttu-id="92bb5-109">元素和属性的数据类型。</span><span class="sxs-lookup"><span data-stu-id="92bb5-109">The data types of the elements and attributes.</span></span>  
  
 <span data-ttu-id="92bb5-110">通常，将 XML 从一种形状转换为另一种形状的最有效方法是纯函数转换方法。</span><span class="sxs-lookup"><span data-stu-id="92bb5-110">In general, the most effective approach to transforming XML from one shape to another is that of pure functional transformation.</span></span> <span data-ttu-id="92bb5-111">在这种方法中，程序员的主要任务是创建一个转换，该转换将应用到整个 XML 文档（或应用到一个或多个严格定义的节点）。</span><span class="sxs-lookup"><span data-stu-id="92bb5-111">In this approach, the primary programmer task is to create a transformation which is applied to the entire XML document (or to one or more strictly defined nodes).</span></span> <span data-ttu-id="92bb5-112">可以说，函数转换最容易进行编码（如果程序员熟悉这种方法），生成的代码最容易维护，并且相比其他方法通常更加简洁。</span><span class="sxs-lookup"><span data-stu-id="92bb5-112">Functional transformation is arguably the easiest to code (after a programmer is familiar with the approach), yields the most maintainable code, and is often more compact than alternative approaches.</span></span>  
  
### <a name="xml-functional-transformational-technologies"></a><span data-ttu-id="92bb5-113">XML 函数转换技术</span><span class="sxs-lookup"><span data-stu-id="92bb5-113">XML Functional Transformational Technologies</span></span>  
 <span data-ttu-id="92bb5-114">Microsoft 提供了两种函数转换技术用于 XML 文档：XSLT 和 LINQ to XML。</span><span class="sxs-lookup"><span data-stu-id="92bb5-114">Microsoft offers two functional transformation technologies for use on XML documents: XSLT and LINQ to XML.</span></span> <span data-ttu-id="92bb5-115">在 <xref:System.Xml.Xsl> 托管命名空间和 MSXML 的本机 COM 实现中都支持 XSLT。</span><span class="sxs-lookup"><span data-stu-id="92bb5-115">XSLT is supported in the <xref:System.Xml.Xsl> managed namespace and in the native COM implementation of MSXML.</span></span> <span data-ttu-id="92bb5-116">尽管 XSLT 是操作 XML 文档的可靠技术，但它要求专门领域的专业知识，即 XSLT 语言和支持它的 API。</span><span class="sxs-lookup"><span data-stu-id="92bb5-116">Although XSLT is a robust technology for manipulating XML documents, it requires expertise in a specialized domain, namely the XSLT language and its supporting APIs.</span></span>  
  
 <span data-ttu-id="92bb5-117">LINQ to XML 提供了必要的工具，使用这些工具可以在 C# 或 Visual Basic 代码中以富于表现力而又强有力的方式编写纯函数转换。</span><span class="sxs-lookup"><span data-stu-id="92bb5-117">LINQ to XML provides the tools necessary to code pure functional transformations in an expressive and powerful way, within C# or Visual Basic code.</span></span> <span data-ttu-id="92bb5-118">例如，LINQ to XML 文档中的很多示例都使用纯函数方法。</span><span class="sxs-lookup"><span data-stu-id="92bb5-118">For example, many of the examples in the LINQ to XML documentation use a pure functional approach.</span></span> <span data-ttu-id="92bb5-119">此外，在[教程： 操作 WordprocessingML 文档 (Visual Basic 中) 中的内容](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md)教程中，我们使用 LINQ to XML 使用函数方法中处理 Microsoft Word 文档中的信息。</span><span class="sxs-lookup"><span data-stu-id="92bb5-119">Also, in the [Tutorial: Manipulating Content in a WordprocessingML Document (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md) tutorial, we use LINQ to XML in a functional approach to manipulate information in a Microsoft Word document.</span></span>  
  
 <span data-ttu-id="92bb5-120">有关 LINQ to XML 与其他 Microsoft XML 技术的更全面比较，请参见 [LINQ to XML 和其他 XML 技术](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-vs-other-xml-technologies.md)。</span><span class="sxs-lookup"><span data-stu-id="92bb5-120">For a more complete comparison of LINQ to XML with other Microsoft XML technologies, see [LINQ to XML vs. Other XML Technologies](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-vs-other-xml-technologies.md).</span></span>  
  
 <span data-ttu-id="92bb5-121">如果源文档具有不规则的结构，则推荐使用 XSLT 工具进行以文档为中心的转换。</span><span class="sxs-lookup"><span data-stu-id="92bb5-121">XSLT is the recommended tool for  document-centric transformations when the source document has an irregular structure.</span></span> <span data-ttu-id="92bb5-122">但是 LINQ to XML 也可以执行以文档为中心的转换。</span><span class="sxs-lookup"><span data-stu-id="92bb5-122">However, LINQ to XML can also perform document-centric transforms.</span></span> <span data-ttu-id="92bb5-123">有关详细信息，请参阅[如何： 使用批注转换 linq to XML 树中 XSLT 样式 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-use-annotation-trees-to-transform-linq-to-xml-trees-in-an-xslt-style.md)。</span><span class="sxs-lookup"><span data-stu-id="92bb5-123">For more information, see [How to: Use Annotations to Transform LINQ to XML Trees in an XSLT Style (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-use-annotation-trees-to-transform-linq-to-xml-trees-in-an-xslt-style.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92bb5-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="92bb5-124">See also</span></span>

- [<span data-ttu-id="92bb5-125">纯功能转换 (Visual Basic) 简介</span><span class="sxs-lookup"><span data-stu-id="92bb5-125">Introduction to Pure Functional Transformations (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md)  
- [<span data-ttu-id="92bb5-126">LINQ to XML 与其他 XML 技术</span><span class="sxs-lookup"><span data-stu-id="92bb5-126">LINQ to XML vs. Other XML Technologies</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-vs-other-xml-technologies.md)
