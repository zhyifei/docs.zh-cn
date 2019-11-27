---
title: 如何：在 XML 文本中嵌入表达式
ms.date: 07/20/2015
helpviewer_keywords:
- embedded expressions [Visual Basic]
- XML literals [Visual Basic], embedded expressions
ms.assetid: 75016fad-0141-42de-8564-5051be29487e
ms.openlocfilehash: 2e8dd10b334b0271e3c9de11ed155c9d5d7aae48
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74332932"
---
# <a name="how-to-embed-expressions-in-xml-literals-visual-basic"></a><span data-ttu-id="18c82-102">如何：在 XML 文本中嵌入表达式 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="18c82-102">How to: Embed Expressions in XML Literals (Visual Basic)</span></span>
<span data-ttu-id="18c82-103">可以结合使用 XML 文本和嵌入式表达式来创建 XML 文档、片段或元素，该元素包含在运行时创建的内容。</span><span class="sxs-lookup"><span data-stu-id="18c82-103">You can combine XML literals with embedded expressions to create an XML document, fragment, or element that contains content created at run time.</span></span> <span data-ttu-id="18c82-104">下面的示例演示如何在运行时使用嵌入式表达式填充元素内容、属性和元素名称。</span><span class="sxs-lookup"><span data-stu-id="18c82-104">The following examples demonstrate how to use embedded expressions to populate element content, attributes, and element names at run time.</span></span>  
  
 <span data-ttu-id="18c82-105">嵌入式表达式的语法是 `<%=` `exp` `%>`，这与 ASP.NET 使用的语法相同。</span><span class="sxs-lookup"><span data-stu-id="18c82-105">The syntax for an embedded expression is `<%=` `exp` `%>`, which is the same syntax that ASP.NET uses.</span></span> <span data-ttu-id="18c82-106">有关详细信息，请参阅[XML 中的嵌入式表达式](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="18c82-106">For more information, see [Embedded Expressions in XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span></span>  
  
 <span data-ttu-id="18c82-107">你还可以使用 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] Api 创建 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 对象。</span><span class="sxs-lookup"><span data-stu-id="18c82-107">You can also use the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] APIs to create [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objects.</span></span> <span data-ttu-id="18c82-108">有关详细信息，请参阅 <xref:System.Xml.Linq.XElement>。</span><span class="sxs-lookup"><span data-stu-id="18c82-108">For more information, see <xref:System.Xml.Linq.XElement>.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="18c82-109">过程</span><span class="sxs-lookup"><span data-stu-id="18c82-109">Procedures</span></span>  
  
#### <a name="to-insert-text-as-element-content"></a><span data-ttu-id="18c82-110">插入文本作为元素内容</span><span class="sxs-lookup"><span data-stu-id="18c82-110">To insert text as element content</span></span>  
  
- <span data-ttu-id="18c82-111">下面的示例演示如何在开始和结束名称元素之间插入 `contactName` 变量中包含的文本。</span><span class="sxs-lookup"><span data-stu-id="18c82-111">The following example shows how to insert the text that is contained in the `contactName` variable between the opening and closing name elements.</span></span>  
  
     [!code-vb[VbXMLSamples#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples14.vb#39)]  
  
     <span data-ttu-id="18c82-112">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="18c82-112">This example produces the following output:</span></span>  
  
    ```xml  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-as-an-attribute-value"></a><span data-ttu-id="18c82-113">插入文本作为属性值</span><span class="sxs-lookup"><span data-stu-id="18c82-113">To insert text as an attribute value</span></span>  
  
- <span data-ttu-id="18c82-114">下面的示例演示如何插入 `phoneType` 变量中包含的文本作为 `type` 特性的值。</span><span class="sxs-lookup"><span data-stu-id="18c82-114">The following example shows how to insert the text that is contained in the `phoneType` variable as the value of the `type` attribute.</span></span>  
  
     [!code-vb[VbXMLSamples#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples14.vb#40)]  
  
     <span data-ttu-id="18c82-115">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="18c82-115">This example produces the following output:</span></span>  
  
    ```xml  
    <contact>  
      <phone type="home">206-555-0144</phone>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-for-an-element-name"></a><span data-ttu-id="18c82-116">插入元素名称的文本</span><span class="sxs-lookup"><span data-stu-id="18c82-116">To insert text for an element name</span></span>  
  
- <span data-ttu-id="18c82-117">下面的示例演示如何插入 `elementName` 变量中包含的文本作为元素的名称。</span><span class="sxs-lookup"><span data-stu-id="18c82-117">The following example shows how to insert the text that is contained in the `elementName` variable as the name of an element.</span></span>  
  
     <span data-ttu-id="18c82-118">使用此方法创建元素时，必须使用 \</> 标记将其关闭。</span><span class="sxs-lookup"><span data-stu-id="18c82-118">When creating elements by using this technique, you must close them with the \</> tag.</span></span>  
  
     [!code-vb[VbXMLSamples#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples14.vb#41)]  
  
     <span data-ttu-id="18c82-119">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="18c82-119">This example produces the following output:</span></span>  
  
    ```xml  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="18c82-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="18c82-120">See also</span></span>

- [<span data-ttu-id="18c82-121">如何：创建 XML 文本</span><span class="sxs-lookup"><span data-stu-id="18c82-121">How to: Create XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-create-xml-literals.md)
- [<span data-ttu-id="18c82-122">XML 中的嵌入式表达式</span><span class="sxs-lookup"><span data-stu-id="18c82-122">Embedded Expressions in XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)
- [<span data-ttu-id="18c82-123">在 Visual Basic 中创建 XML</span><span class="sxs-lookup"><span data-stu-id="18c82-123">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="18c82-124">XML</span><span class="sxs-lookup"><span data-stu-id="18c82-124">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
