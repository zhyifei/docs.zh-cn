---
title: "如何︰ 创建 XML 文本 (Visual Basic 中) |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- XML literals [Visual Basic], creating
ms.assetid: 573a6db5-b14d-4e42-b356-8cc7e2d77745
caps.latest.revision: 17
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
ms.openlocfilehash: 3a7b5dc692317067290b48222ba056d765a449f3
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-create-xml-literals-visual-basic"></a><span data-ttu-id="631c3-102">如何：创建 XML 文本 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="631c3-102">How to: Create XML Literals (Visual Basic)</span></span>
<span data-ttu-id="631c3-103">通过使用 XML 文本，可以在代码中直接创建 XML 文档、 片段或元素。</span><span class="sxs-lookup"><span data-stu-id="631c3-103">You can create an XML document, fragment, or element directly in code by using an XML literal.</span></span> <span data-ttu-id="631c3-104">本主题中的示例演示如何创建一个 XML 元素，有三个子元素，以及如何创建 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="631c3-104">The examples in this topic demonstrate how to create an XML element that has three child elements, and how to create an XML document.</span></span>  
  
 <span data-ttu-id="631c3-105">您还可以使用[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]Api 来创建[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]对象。</span><span class="sxs-lookup"><span data-stu-id="631c3-105">You can also use the [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] APIs to create [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] objects.</span></span> <span data-ttu-id="631c3-106">有关详细信息，请参阅<xref:System.Xml.Linq.XElement>。</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="631c3-106">For more information, see <xref:System.Xml.Linq.XElement>.</span></span>  
  
### <a name="to-create-an-xml-element"></a><span data-ttu-id="631c3-107">若要创建一个 XML 元素</span><span class="sxs-lookup"><span data-stu-id="631c3-107">To create an XML element</span></span>  
  
-   <span data-ttu-id="631c3-108">通过使用 XML 文本语法，这是实际的 XML 语法相同创建内嵌的 XML。</span><span class="sxs-lookup"><span data-stu-id="631c3-108">Create the XML inline by using the XML literal syntax, which is the same as the actual XML syntax.</span></span>  
  
     <span data-ttu-id="631c3-109">[!code-vb[VbXMLSamples #&5;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-xml-literals_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="631c3-109">[!code-vb[VbXMLSamples#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-xml-literals_1.vb)]</span></span>  
  
     <span data-ttu-id="631c3-110">运行代码。</span><span class="sxs-lookup"><span data-stu-id="631c3-110">Run the code.</span></span> <span data-ttu-id="631c3-111">此代码的输出为︰</span><span class="sxs-lookup"><span data-stu-id="631c3-111">The output of this code is:</span></span>  
  
     `<contact>`  
  
     `<name>Patrick Hines</name>`  
  
     `<phone type="home">206-555-0144</phone>`  
  
     `<phone type="work">425-555-0145</phone>`  
  
     `</contact>`  
  
### <a name="to-create-an-xml-document"></a><span data-ttu-id="631c3-112">若要创建的 XML 文档</span><span class="sxs-lookup"><span data-stu-id="631c3-112">To create an XML document</span></span>  
  
-   <span data-ttu-id="631c3-113">创建 XML 文档内联。</span><span class="sxs-lookup"><span data-stu-id="631c3-113">Create the XML document inline.</span></span> <span data-ttu-id="631c3-114">下面的代码创建具有文本语法、 XML 声明、 处理指令、 注释和一个包含另一个元素的元素的 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="631c3-114">The following code creates an XML document that has literal syntax, an XML declaration, a processing instruction, a comment, and an element that contains another element.</span></span>  
  
     <span data-ttu-id="631c3-115">[!code-vb[VbXMLSamples #&30;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-xml-literals_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="631c3-115">[!code-vb[VbXMLSamples#30](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-xml-literals_2.vb)]</span></span>  
  
     <span data-ttu-id="631c3-116">运行代码。</span><span class="sxs-lookup"><span data-stu-id="631c3-116">Run the code.</span></span> <span data-ttu-id="631c3-117">此代码的输出为︰</span><span class="sxs-lookup"><span data-stu-id="631c3-117">The output of this code is:</span></span>  
  
     `<?xml-stylesheet type="text/xsl" href="show_book.xsl"?>`  
  
     `<!-- Tests that the application works. -->`  
  
     `<books>`  
  
     `<book/>`  
  
     `</books>`  
  
## <a name="see-also"></a><span data-ttu-id="631c3-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="631c3-118">See Also</span></span>  
 <span data-ttu-id="631c3-119">[XML](../../../../visual-basic/programming-guide/language-features/xml/index.md) </span><span class="sxs-lookup"><span data-stu-id="631c3-119">[XML](../../../../visual-basic/programming-guide/language-features/xml/index.md) </span></span>  
<span data-ttu-id="631c3-120"> [在 Visual Basic 中创建 XML](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span><span class="sxs-lookup"><span data-stu-id="631c3-120"> [Creating XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span></span>  
<span data-ttu-id="631c3-121"> [XML 元素文本](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) </span><span class="sxs-lookup"><span data-stu-id="631c3-121"> [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) </span></span>  
<span data-ttu-id="631c3-122"> [XML 文档文本](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)</span><span class="sxs-lookup"><span data-stu-id="631c3-122"> [XML Document Literal](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)</span></span>
