---
title: XML 文本中的空白 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- white space [XML in Visual Basic]
- XML literals [Visual Basic], white space
ms.assetid: dfe3a9ff-d69a-418e-a6b5-476f4ed84219
ms.openlocfilehash: 60ee90c69aeda38f95107a6043801a4994972079
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649745"
---
# <a name="white-space-in-xml-literals-visual-basic"></a><span data-ttu-id="b65d8-102">XML 文本中的空白 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b65d8-102">White Space in XML Literals (Visual Basic)</span></span>
<span data-ttu-id="b65d8-103">Visual Basic 编译器创建时包含的有意义的空白字符将从 XML 文本[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]对象。</span><span class="sxs-lookup"><span data-stu-id="b65d8-103">The Visual Basic compiler incorporates only the significant white space characters from an XML literal when it creates a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] object.</span></span> <span data-ttu-id="b65d8-104">它不会合并无意义的空白字符。</span><span class="sxs-lookup"><span data-stu-id="b65d8-104">The insignificant white space characters are not incorporated.</span></span>  
  
## <a name="significant-and-insignificant-white-space"></a><span data-ttu-id="b65d8-105">有效空白和无关紧要的空白区域</span><span class="sxs-lookup"><span data-stu-id="b65d8-105">Significant and Insignificant White Space</span></span>  
 <span data-ttu-id="b65d8-106">只有三个区域中，XML 文本中的空格字符是有意义：</span><span class="sxs-lookup"><span data-stu-id="b65d8-106">White space characters in XML literals are significant in only three areas:</span></span>  
  
-   <span data-ttu-id="b65d8-107">当它们位于属性值。</span><span class="sxs-lookup"><span data-stu-id="b65d8-107">When they are in an attribute value.</span></span>  
  
-   <span data-ttu-id="b65d8-108">当它们是元素的文本内容的一部分，并且该文本还包含其他字符。</span><span class="sxs-lookup"><span data-stu-id="b65d8-108">When they are part of an element's text content and the text also contains other characters.</span></span>  
  
-   <span data-ttu-id="b65d8-109">当它们位于元素的文本内容的嵌入式表达式。</span><span class="sxs-lookup"><span data-stu-id="b65d8-109">When they are in an embedded expression for an element's text content.</span></span>  
  
 <span data-ttu-id="b65d8-110">否则为编译器将视为无意义的空白字符，且不包括然后中[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]文本的对象。</span><span class="sxs-lookup"><span data-stu-id="b65d8-110">Otherwise, the compiler treats white space characters as insignificant and does not include then in the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] object for the literal.</span></span>  
  
 <span data-ttu-id="b65d8-111">若要在 XML 文本中包括无关紧要的空白区域，使用嵌入式的表达式包含具有空白区域的字符串文本。</span><span class="sxs-lookup"><span data-stu-id="b65d8-111">To include insignificant white space in an XML literal, use an embedded expression that contains a string literal with the white space.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b65d8-112">如果`xml:space`特性随即显示 XML 元素文本中，Visual Basic 编译器包含中的属性<xref:System.Xml.Linq.XElement>对象，但添加此属性不会更改编译器如何处理空白区域。</span><span class="sxs-lookup"><span data-stu-id="b65d8-112">If the `xml:space` attribute appears in an XML element literal, the Visual Basic compiler includes the attribute in the <xref:System.Xml.Linq.XElement> object, but adding this attribute does not change how the compiler treats white space.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="b65d8-113">示例</span><span class="sxs-lookup"><span data-stu-id="b65d8-113">Examples</span></span>  
 <span data-ttu-id="b65d8-114">下面的示例包含两个 XML 元素，外部和内部。</span><span class="sxs-lookup"><span data-stu-id="b65d8-114">The following example contains two XML elements, outer and inner.</span></span> <span data-ttu-id="b65d8-115">这两个元素包含文本内容中的空白区域。</span><span class="sxs-lookup"><span data-stu-id="b65d8-115">Both elements contain white space in their text content.</span></span> <span data-ttu-id="b65d8-116">中的外部元素的空白区域是无意义，因为它只包含空格和一个 XML 元素。</span><span class="sxs-lookup"><span data-stu-id="b65d8-116">The white space in the outer element is insignificant because it contains only white space and an XML element.</span></span> <span data-ttu-id="b65d8-117">中元素的内部的空白区域很重要，因为它包含空格和文本。</span><span class="sxs-lookup"><span data-stu-id="b65d8-117">The white space in the inner element is significant because it contains white space and text.</span></span>  
  
 [!code-vb[VbXMLSamples#29](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/white-space-in-xml-literals_1.vb)]  
  
 <span data-ttu-id="b65d8-118">运行时，此代码将显示以下文本。</span><span class="sxs-lookup"><span data-stu-id="b65d8-118">When run, this code displays the following text.</span></span>  
  
```xml  
<outer>  
  <inner>  
                                          Inner text  
                                      </inner>  
</outer>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b65d8-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="b65d8-119">See Also</span></span>  
 [<span data-ttu-id="b65d8-120">在 Visual Basic 中创建 XML</span><span class="sxs-lookup"><span data-stu-id="b65d8-120">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
