---
title: "如何︰ 在 XML 文本 (Visual Basic 中) 中嵌入表达式 |Microsoft 文档"
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
- embedded expressions [Visual Basic]
- XML literals [Visual Basic], embedded expressions
ms.assetid: 75016fad-0141-42de-8564-5051be29487e
caps.latest.revision: 16
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
ms.openlocfilehash: e4f086b06575cb8300bd65d450cda6b9893bb692
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-embed-expressions-in-xml-literals-visual-basic"></a><span data-ttu-id="c59d9-102">如何：在 XML 文本中嵌入表达式 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c59d9-102">How to: Embed Expressions in XML Literals (Visual Basic)</span></span>
<span data-ttu-id="c59d9-103">您可以使用嵌入式表达式来创建 XML 文档、 片段或包含在运行时创建的内容的元素组合 XML 文本。</span><span class="sxs-lookup"><span data-stu-id="c59d9-103">You can combine XML literals with embedded expressions to create an XML document, fragment, or element that contains content created at run time.</span></span> <span data-ttu-id="c59d9-104">下面的示例演示如何使用嵌入式的表达式可以在运行时填充元素内容、 属性和元素名称。</span><span class="sxs-lookup"><span data-stu-id="c59d9-104">The following examples demonstrate how to use embedded expressions to populate element content, attributes, and element names at run time.</span></span>  
  
 <span data-ttu-id="c59d9-105">嵌入式表达式的语法是`<%=` `exp` `%>`，这是相同的语法，[!INCLUDE[vstecasp](../../../../csharp/language-reference/preprocessor-directives/includes/vstecasp_md.md)]使用。</span><span class="sxs-lookup"><span data-stu-id="c59d9-105">The syntax for an embedded expression is `<%=` `exp` `%>`, which is the same syntax that [!INCLUDE[vstecasp](../../../../csharp/language-reference/preprocessor-directives/includes/vstecasp_md.md)] uses.</span></span> <span data-ttu-id="c59d9-106">有关详细信息，请参阅[XML 中的嵌入式表达式](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="c59d9-106">For more information, see [Embedded Expressions in XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span></span>  
  
 <span data-ttu-id="c59d9-107">您还可以使用[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]Api 来创建[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]对象。</span><span class="sxs-lookup"><span data-stu-id="c59d9-107">You can also use the [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] APIs to create [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] objects.</span></span> <span data-ttu-id="c59d9-108">有关详细信息，请参阅<xref:System.Xml.Linq.XElement>。</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="c59d9-108">For more information, see <xref:System.Xml.Linq.XElement>.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="c59d9-109">过程</span><span class="sxs-lookup"><span data-stu-id="c59d9-109">Procedures</span></span>  
  
#### <a name="to-insert-text-as-element-content"></a><span data-ttu-id="c59d9-110">若要作为元素内容中插入文本</span><span class="sxs-lookup"><span data-stu-id="c59d9-110">To insert text as element content</span></span>  
  
-   <span data-ttu-id="c59d9-111">下面的示例演示如何插入中包含的文本`contactName`变量之间打开和关闭名称元素。</span><span class="sxs-lookup"><span data-stu-id="c59d9-111">The following example shows how to insert the text that is contained in the `contactName` variable between the opening and closing name elements.</span></span>  
  
     <span data-ttu-id="c59d9-112">[!code-vb[VbXMLSamples #&39;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="c59d9-112">[!code-vb[VbXMLSamples#39](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_1.vb)]</span></span>  
  
     <span data-ttu-id="c59d9-113">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="c59d9-113">This example produces the following output:</span></span>  
  
    ```  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-as-an-attribute-value"></a><span data-ttu-id="c59d9-114">若要插入文本作为属性值</span><span class="sxs-lookup"><span data-stu-id="c59d9-114">To insert text as an attribute value</span></span>  
  
-   <span data-ttu-id="c59d9-115">下面的示例演示如何插入中包含的文本`phoneType`变量的值作为`type`属性。</span><span class="sxs-lookup"><span data-stu-id="c59d9-115">The following example shows how to insert the text that is contained in the `phoneType` variable as the value of the `type` attribute.</span></span>  
  
     <span data-ttu-id="c59d9-116">[!code-vb[VbXMLSamples #&40;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="c59d9-116">[!code-vb[VbXMLSamples#40](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_2.vb)]</span></span>  
  
     <span data-ttu-id="c59d9-117">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="c59d9-117">This example produces the following output:</span></span>  
  
    ```  
    <contact>  
      <phone type="home">206-555-0144</phone>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-for-an-element-name"></a><span data-ttu-id="c59d9-118">若要插入的元素名的文本</span><span class="sxs-lookup"><span data-stu-id="c59d9-118">To insert text for an element name</span></span>  
  
-   <span data-ttu-id="c59d9-119">下面的示例演示如何插入中包含的文本`elementName`变量作为一个元素的名称。</span><span class="sxs-lookup"><span data-stu-id="c59d9-119">The following example shows how to insert the text that is contained in the `elementName` variable as the name of an element.</span></span>  
  
     <span data-ttu-id="c59d9-120">创建元素时通过使用此技术，您必须将它们与\</&1;> 标记。</span><span class="sxs-lookup"><span data-stu-id="c59d9-120">When creating elements by using this technique, you must close them with the \</> tag.</span></span>  
  
     <span data-ttu-id="c59d9-121">[!code-vb[VbXMLSamples #&41;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="c59d9-121">[!code-vb[VbXMLSamples#41](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_3.vb)]</span></span>  
  
     <span data-ttu-id="c59d9-122">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="c59d9-122">This example produces the following output:</span></span>  
  
    ```  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="c59d9-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c59d9-123">See Also</span></span>  
 <span data-ttu-id="c59d9-124">[如何︰ 创建 XML 文本](../../../../visual-basic/programming-guide/language-features/xml/how-to-create-xml-literals.md) </span><span class="sxs-lookup"><span data-stu-id="c59d9-124">[How to: Create XML Literals](../../../../visual-basic/programming-guide/language-features/xml/how-to-create-xml-literals.md) </span></span>  
<span data-ttu-id="c59d9-125"> [XML 中的嵌入式的表达式](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md) </span><span class="sxs-lookup"><span data-stu-id="c59d9-125"> [Embedded Expressions in XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md) </span></span>  
<span data-ttu-id="c59d9-126"> [在 Visual Basic 中创建 XML](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span><span class="sxs-lookup"><span data-stu-id="c59d9-126"> [Creating XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span></span>  
<span data-ttu-id="c59d9-127"> [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)</span><span class="sxs-lookup"><span data-stu-id="c59d9-127"> [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)</span></span>
