---
title: 如何：创建 XML 文本 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- XML literals [Visual Basic], creating
ms.assetid: 573a6db5-b14d-4e42-b356-8cc7e2d77745
ms.openlocfilehash: e5f8429b3ff02678bf8bf3e9e32bef6eb1a56831
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33652865"
---
# <a name="how-to-create-xml-literals-visual-basic"></a><span data-ttu-id="4420c-102">如何：创建 XML 文本 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4420c-102">How to: Create XML Literals (Visual Basic)</span></span>
<span data-ttu-id="4420c-103">通过使用 XML 文本，可以在代码中直接创建 XML 文档、 片段或元素。</span><span class="sxs-lookup"><span data-stu-id="4420c-103">You can create an XML document, fragment, or element directly in code by using an XML literal.</span></span> <span data-ttu-id="4420c-104">本主题中的示例演示如何创建 XML 元素，具有三个子元素，以及如何创建 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="4420c-104">The examples in this topic demonstrate how to create an XML element that has three child elements, and how to create an XML document.</span></span>  
  
 <span data-ttu-id="4420c-105">你还可以使用[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]Api 来创建[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]对象。</span><span class="sxs-lookup"><span data-stu-id="4420c-105">You can also use the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] APIs to create [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objects.</span></span> <span data-ttu-id="4420c-106">有关详细信息，请参阅<xref:System.Xml.Linq.XElement>。</span><span class="sxs-lookup"><span data-stu-id="4420c-106">For more information, see <xref:System.Xml.Linq.XElement>.</span></span>  
  
### <a name="to-create-an-xml-element"></a><span data-ttu-id="4420c-107">若要创建一个 XML 元素</span><span class="sxs-lookup"><span data-stu-id="4420c-107">To create an XML element</span></span>  
  
-   <span data-ttu-id="4420c-108">通过使用 XML 文本语法，这是实际的 XML 语法相同创建 XML 内联。</span><span class="sxs-lookup"><span data-stu-id="4420c-108">Create the XML inline by using the XML literal syntax, which is the same as the actual XML syntax.</span></span>  
  
     [!code-vb[VbXMLSamples#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-xml-literals_1.vb)]  
  
     <span data-ttu-id="4420c-109">运行代码。</span><span class="sxs-lookup"><span data-stu-id="4420c-109">Run the code.</span></span> <span data-ttu-id="4420c-110">此代码的输出为：</span><span class="sxs-lookup"><span data-stu-id="4420c-110">The output of this code is:</span></span>  
  
     `<contact>`  
  
     `<name>Patrick Hines</name>`  
  
     `<phone type="home">206-555-0144</phone>`  
  
     `<phone type="work">425-555-0145</phone>`  
  
     `</contact>`  
  
### <a name="to-create-an-xml-document"></a><span data-ttu-id="4420c-111">若要创建 XML 文档</span><span class="sxs-lookup"><span data-stu-id="4420c-111">To create an XML document</span></span>  
  
-   <span data-ttu-id="4420c-112">创建 XML 文档内联。</span><span class="sxs-lookup"><span data-stu-id="4420c-112">Create the XML document inline.</span></span> <span data-ttu-id="4420c-113">下面的代码创建具有文本语法、 XML 声明、 处理指令、 注释和一个包含另一个元素的元素的 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="4420c-113">The following code creates an XML document that has literal syntax, an XML declaration, a processing instruction, a comment, and an element that contains another element.</span></span>  
  
     [!code-vb[VbXMLSamples#30](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-xml-literals_2.vb)]  
  
     <span data-ttu-id="4420c-114">运行代码。</span><span class="sxs-lookup"><span data-stu-id="4420c-114">Run the code.</span></span> <span data-ttu-id="4420c-115">此代码的输出为：</span><span class="sxs-lookup"><span data-stu-id="4420c-115">The output of this code is:</span></span>  
  
     `<?xml-stylesheet type="text/xsl" href="show_book.xsl"?>`  
  
     `<!-- Tests that the application works. -->`  
  
     `<books>`  
  
     `<book/>`  
  
     `</books>`  
  
## <a name="see-also"></a><span data-ttu-id="4420c-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="4420c-116">See Also</span></span>  
 [<span data-ttu-id="4420c-117">XML</span><span class="sxs-lookup"><span data-stu-id="4420c-117">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 [<span data-ttu-id="4420c-118">在 Visual Basic 中创建 XML</span><span class="sxs-lookup"><span data-stu-id="4420c-118">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [<span data-ttu-id="4420c-119">XML 元素文本</span><span class="sxs-lookup"><span data-stu-id="4420c-119">XML Element Literal</span></span>](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)  
 [<span data-ttu-id="4420c-120">XML 文档文本</span><span class="sxs-lookup"><span data-stu-id="4420c-120">XML Document Literal</span></span>](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)
