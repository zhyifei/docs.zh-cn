---
title: 如何：创建 XML 文本 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- XML literals [Visual Basic], creating
ms.assetid: 573a6db5-b14d-4e42-b356-8cc7e2d77745
ms.openlocfilehash: 836ec4390e7675effe57c75c79768272d66925a3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "58836853"
---
# <a name="how-to-create-xml-literals-visual-basic"></a><span data-ttu-id="37754-102">如何：创建 XML 文本 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="37754-102">How to: Create XML Literals (Visual Basic)</span></span>
<span data-ttu-id="37754-103">通过使用 XML 文本，可以直接在代码中创建 XML 文档、 片段或元素。</span><span class="sxs-lookup"><span data-stu-id="37754-103">You can create an XML document, fragment, or element directly in code by using an XML literal.</span></span> <span data-ttu-id="37754-104">本主题中的示例演示如何创建 XML 元素具有三个子元素，以及如何创建 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="37754-104">The examples in this topic demonstrate how to create an XML element that has three child elements, and how to create an XML document.</span></span>  
  
 <span data-ttu-id="37754-105">此外可以使用[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]Api 来创建[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]对象。</span><span class="sxs-lookup"><span data-stu-id="37754-105">You can also use the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] APIs to create [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objects.</span></span> <span data-ttu-id="37754-106">有关详细信息，请参阅 <xref:System.Xml.Linq.XElement>。</span><span class="sxs-lookup"><span data-stu-id="37754-106">For more information, see <xref:System.Xml.Linq.XElement>.</span></span>  
  
### <a name="to-create-an-xml-element"></a><span data-ttu-id="37754-107">若要创建一个 XML 元素</span><span class="sxs-lookup"><span data-stu-id="37754-107">To create an XML element</span></span>  
  
-   <span data-ttu-id="37754-108">使用 XML 文本语法，这是实际的 XML 语法相同创建内嵌的 XML。</span><span class="sxs-lookup"><span data-stu-id="37754-108">Create the XML inline by using the XML literal syntax, which is the same as the actual XML syntax.</span></span>  
  
     [!code-vb[VbXMLSamples#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#5)]  
  
     <span data-ttu-id="37754-109">运行代码。</span><span class="sxs-lookup"><span data-stu-id="37754-109">Run the code.</span></span> <span data-ttu-id="37754-110">此代码的输出为：</span><span class="sxs-lookup"><span data-stu-id="37754-110">The output of this code is:</span></span>  
  
     `<contact>`  
  
     `<name>Patrick Hines</name>`  
  
     `<phone type="home">206-555-0144</phone>`  
  
     `<phone type="work">425-555-0145</phone>`  
  
     `</contact>`  
  
### <a name="to-create-an-xml-document"></a><span data-ttu-id="37754-111">若要创建 XML 文档</span><span class="sxs-lookup"><span data-stu-id="37754-111">To create an XML document</span></span>  
  
-   <span data-ttu-id="37754-112">创建内联 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="37754-112">Create the XML document inline.</span></span> <span data-ttu-id="37754-113">以下代码将创建具有文本语法、 XML 声明、 处理指令、 注释和一个包含另一个元素的元素的 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="37754-113">The following code creates an XML document that has literal syntax, an XML declaration, a processing instruction, a comment, and an element that contains another element.</span></span>  
  
     [!code-vb[VbXMLSamples#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#30)]  
  
     <span data-ttu-id="37754-114">运行代码。</span><span class="sxs-lookup"><span data-stu-id="37754-114">Run the code.</span></span> <span data-ttu-id="37754-115">此代码的输出为：</span><span class="sxs-lookup"><span data-stu-id="37754-115">The output of this code is:</span></span>  
  
     `<?xml-stylesheet type="text/xsl" href="show_book.xsl"?>`  
  
     `<!-- Tests that the application works. -->`  
  
     `<books>`  
  
     `<book/>`  
  
     `</books>`  
  
## <a name="see-also"></a><span data-ttu-id="37754-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="37754-116">See also</span></span>

- [<span data-ttu-id="37754-117">XML</span><span class="sxs-lookup"><span data-stu-id="37754-117">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
- [<span data-ttu-id="37754-118">在 Visual Basic 中创建 XML</span><span class="sxs-lookup"><span data-stu-id="37754-118">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="37754-119">XML 元素文本</span><span class="sxs-lookup"><span data-stu-id="37754-119">XML Element Literal</span></span>](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [<span data-ttu-id="37754-120">XML 文档文本</span><span class="sxs-lookup"><span data-stu-id="37754-120">XML Document Literal</span></span>](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)
