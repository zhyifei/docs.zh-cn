---
title: XML 文本中的空白
ms.date: 07/20/2015
helpviewer_keywords:
- white space [XML in Visual Basic]
- XML literals [Visual Basic], white space
ms.assetid: dfe3a9ff-d69a-418e-a6b5-476f4ed84219
ms.openlocfilehash: 56ededeb12d07e979bc86b03924e1ae0f0432822
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74335999"
---
# <a name="white-space-in-xml-literals-visual-basic"></a><span data-ttu-id="27fea-102">XML 文本中的空白 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="27fea-102">White Space in XML Literals (Visual Basic)</span></span>
<span data-ttu-id="27fea-103">在创建 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 对象时，Visual Basic 编译器仅合并 XML 文本中的有效空白字符。</span><span class="sxs-lookup"><span data-stu-id="27fea-103">The Visual Basic compiler incorporates only the significant white space characters from an XML literal when it creates a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] object.</span></span> <span data-ttu-id="27fea-104">不包含无意义的空白字符。</span><span class="sxs-lookup"><span data-stu-id="27fea-104">The insignificant white space characters are not incorporated.</span></span>  
  
## <a name="significant-and-insignificant-white-space"></a><span data-ttu-id="27fea-105">重要且无意义的空白</span><span class="sxs-lookup"><span data-stu-id="27fea-105">Significant and Insignificant White Space</span></span>  
 <span data-ttu-id="27fea-106">XML 文本中的空格字符仅在三个区域中很重要：</span><span class="sxs-lookup"><span data-stu-id="27fea-106">White space characters in XML literals are significant in only three areas:</span></span>  
  
- <span data-ttu-id="27fea-107">在属性值中。</span><span class="sxs-lookup"><span data-stu-id="27fea-107">When they are in an attribute value.</span></span>  
  
- <span data-ttu-id="27fea-108">当它们是元素的文本内容的一部分并且文本还包含其他字符时。</span><span class="sxs-lookup"><span data-stu-id="27fea-108">When they are part of an element's text content and the text also contains other characters.</span></span>  
  
- <span data-ttu-id="27fea-109">当它们位于元素的文本内容的嵌入式表达式中时。</span><span class="sxs-lookup"><span data-stu-id="27fea-109">When they are in an embedded expression for an element's text content.</span></span>  
  
 <span data-ttu-id="27fea-110">否则，编译器会将空白字符视为不重要的，并且不会在文本的 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 对象中包含。</span><span class="sxs-lookup"><span data-stu-id="27fea-110">Otherwise, the compiler treats white space characters as insignificant and does not include then in the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] object for the literal.</span></span>  
  
 <span data-ttu-id="27fea-111">若要在 XML 文本中包含无意义的空白，请使用包含带有空格的字符串文字的嵌入式表达式。</span><span class="sxs-lookup"><span data-stu-id="27fea-111">To include insignificant white space in an XML literal, use an embedded expression that contains a string literal with the white space.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="27fea-112">如果 `xml:space` 特性显示在 XML 元素文本中，则 Visual Basic 编译器在 <xref:System.Xml.Linq.XElement> 对象中包含特性，但添加此特性不会更改编译器处理空白的方式。</span><span class="sxs-lookup"><span data-stu-id="27fea-112">If the `xml:space` attribute appears in an XML element literal, the Visual Basic compiler includes the attribute in the <xref:System.Xml.Linq.XElement> object, but adding this attribute does not change how the compiler treats white space.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="27fea-113">示例</span><span class="sxs-lookup"><span data-stu-id="27fea-113">Examples</span></span>  
 <span data-ttu-id="27fea-114">下面的示例包含两个 XML 元素：外部和内部。</span><span class="sxs-lookup"><span data-stu-id="27fea-114">The following example contains two XML elements, outer and inner.</span></span> <span data-ttu-id="27fea-115">这两个元素在其文本内容中都包含空格。</span><span class="sxs-lookup"><span data-stu-id="27fea-115">Both elements contain white space in their text content.</span></span> <span data-ttu-id="27fea-116">外部元素中的空白是无意义的，因为它仅包含空格和 XML 元素。</span><span class="sxs-lookup"><span data-stu-id="27fea-116">The white space in the outer element is insignificant because it contains only white space and an XML element.</span></span> <span data-ttu-id="27fea-117">内部元素中的空格非常重要，因为它包含空格和文本。</span><span class="sxs-lookup"><span data-stu-id="27fea-117">The white space in the inner element is significant because it contains white space and text.</span></span>  
  
 [!code-vb[VbXMLSamples#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#29)]  
  
 <span data-ttu-id="27fea-118">运行时，此代码显示以下文本。</span><span class="sxs-lookup"><span data-stu-id="27fea-118">When run, this code displays the following text.</span></span>  
  
```xml  
<outer>  
  <inner>  
                                          Inner text  
                                      </inner>  
</outer>  
```  
  
## <a name="see-also"></a><span data-ttu-id="27fea-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="27fea-119">See also</span></span>

- [<span data-ttu-id="27fea-120">在 Visual Basic 中创建 XML</span><span class="sxs-lookup"><span data-stu-id="27fea-120">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
