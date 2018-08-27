---
title: 如何：在 XML 文本中嵌入表达式 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- embedded expressions [Visual Basic]
- XML literals [Visual Basic], embedded expressions
ms.assetid: 75016fad-0141-42de-8564-5051be29487e
ms.openlocfilehash: 41dc6ef8d2ec2ffd6cd1cf793911f2e09f1a1e77
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2018
ms.locfileid: "42929511"
---
# <a name="how-to-embed-expressions-in-xml-literals-visual-basic"></a><span data-ttu-id="121d8-102">如何：在 XML 文本中嵌入表达式 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="121d8-102">How to: Embed Expressions in XML Literals (Visual Basic)</span></span>
<span data-ttu-id="121d8-103">您可以将 XML 文本与嵌入的表达式来创建 XML 文档、 片段或包含在运行时创建的内容的元素。</span><span class="sxs-lookup"><span data-stu-id="121d8-103">You can combine XML literals with embedded expressions to create an XML document, fragment, or element that contains content created at run time.</span></span> <span data-ttu-id="121d8-104">以下示例演示如何使用嵌入式的表达式在运行时填充元素内容、 属性和元素名称。</span><span class="sxs-lookup"><span data-stu-id="121d8-104">The following examples demonstrate how to use embedded expressions to populate element content, attributes, and element names at run time.</span></span>  
  
 <span data-ttu-id="121d8-105">嵌入式表达式的语法是`<%=` `exp` `%>`，这是相同的语法的[!INCLUDE[vstecasp](~/includes/vstecasp-md.md)]使用。</span><span class="sxs-lookup"><span data-stu-id="121d8-105">The syntax for an embedded expression is `<%=` `exp` `%>`, which is the same syntax that [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] uses.</span></span> <span data-ttu-id="121d8-106">有关详细信息，请参阅[XML 中的嵌入式表达式](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="121d8-106">For more information, see [Embedded Expressions in XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span></span>  
  
 <span data-ttu-id="121d8-107">此外可以使用[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]Api 来创建[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]对象。</span><span class="sxs-lookup"><span data-stu-id="121d8-107">You can also use the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] APIs to create [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objects.</span></span> <span data-ttu-id="121d8-108">有关详细信息，请参阅<xref:System.Xml.Linq.XElement>。</span><span class="sxs-lookup"><span data-stu-id="121d8-108">For more information, see <xref:System.Xml.Linq.XElement>.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="121d8-109">过程</span><span class="sxs-lookup"><span data-stu-id="121d8-109">Procedures</span></span>  
  
#### <a name="to-insert-text-as-element-content"></a><span data-ttu-id="121d8-110">若要作为元素内容中插入文本</span><span class="sxs-lookup"><span data-stu-id="121d8-110">To insert text as element content</span></span>  
  
-   <span data-ttu-id="121d8-111">下面的示例演示如何插入文本中包含的`contactName`变量之间的开始和结束的名称元素。</span><span class="sxs-lookup"><span data-stu-id="121d8-111">The following example shows how to insert the text that is contained in the `contactName` variable between the opening and closing name elements.</span></span>  
  
     [!code-vb[VbXMLSamples#39](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_1.vb)]  
  
     <span data-ttu-id="121d8-112">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="121d8-112">This example produces the following output:</span></span>  
  
    ```xml  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-as-an-attribute-value"></a><span data-ttu-id="121d8-113">作为属性值中插入文本</span><span class="sxs-lookup"><span data-stu-id="121d8-113">To insert text as an attribute value</span></span>  
  
-   <span data-ttu-id="121d8-114">下面的示例演示如何插入中包含的文本`phoneType`变量的值作为`type`属性。</span><span class="sxs-lookup"><span data-stu-id="121d8-114">The following example shows how to insert the text that is contained in the `phoneType` variable as the value of the `type` attribute.</span></span>  
  
     [!code-vb[VbXMLSamples#40](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_2.vb)]  
  
     <span data-ttu-id="121d8-115">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="121d8-115">This example produces the following output:</span></span>  
  
    ```xml  
    <contact>  
      <phone type="home">206-555-0144</phone>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-for-an-element-name"></a><span data-ttu-id="121d8-116">若要插入的元素名称的文本</span><span class="sxs-lookup"><span data-stu-id="121d8-116">To insert text for an element name</span></span>  
  
-   <span data-ttu-id="121d8-117">下面的示例演示如何插入文本中包含的`elementName`变量作为元素的名称。</span><span class="sxs-lookup"><span data-stu-id="121d8-117">The following example shows how to insert the text that is contained in the `elementName` variable as the name of an element.</span></span>  
  
     <span data-ttu-id="121d8-118">创建元素时使用此技术，必须将它们与\</ > 标记。</span><span class="sxs-lookup"><span data-stu-id="121d8-118">When creating elements by using this technique, you must close them with the \</> tag.</span></span>  
  
     [!code-vb[VbXMLSamples#41](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_3.vb)]  
  
     <span data-ttu-id="121d8-119">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="121d8-119">This example produces the following output:</span></span>  
  
    ```xml  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="121d8-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="121d8-120">See Also</span></span>  
 [<span data-ttu-id="121d8-121">如何：创建 XML 文本</span><span class="sxs-lookup"><span data-stu-id="121d8-121">How to: Create XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-create-xml-literals.md)  
 [<span data-ttu-id="121d8-122">XML 中的嵌入式表达式</span><span class="sxs-lookup"><span data-stu-id="121d8-122">Embedded Expressions in XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)  
 [<span data-ttu-id="121d8-123">在 Visual Basic 中创建 XML</span><span class="sxs-lookup"><span data-stu-id="121d8-123">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [<span data-ttu-id="121d8-124">XML</span><span class="sxs-lookup"><span data-stu-id="121d8-124">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
