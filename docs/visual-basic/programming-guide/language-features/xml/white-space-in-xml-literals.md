---
title: "XML 文本中的空白 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- white space [XML in Visual Basic]
- XML literals [Visual Basic], white space
ms.assetid: dfe3a9ff-d69a-418e-a6b5-476f4ed84219
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d8587abb98fe33ab2c5a0cef6cea76049a00909e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="white-space-in-xml-literals-visual-basic"></a><span data-ttu-id="fd1d7-102">XML 文本中的空白 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fd1d7-102">White Space in XML Literals (Visual Basic)</span></span>
<span data-ttu-id="fd1d7-103">[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]编译器包含仅从 XML 文本的有意义的空白字符，在创建时[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]对象。</span><span class="sxs-lookup"><span data-stu-id="fd1d7-103">The [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler incorporates only the significant white space characters from an XML literal when it creates a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] object.</span></span> <span data-ttu-id="fd1d7-104">它不会合并无意义的空白字符。</span><span class="sxs-lookup"><span data-stu-id="fd1d7-104">The insignificant white space characters are not incorporated.</span></span>  
  
## <a name="significant-and-insignificant-white-space"></a><span data-ttu-id="fd1d7-105">有效空白和无关紧要的空白区域</span><span class="sxs-lookup"><span data-stu-id="fd1d7-105">Significant and Insignificant White Space</span></span>  
 <span data-ttu-id="fd1d7-106">只有三个区域中，XML 文本中的空格字符是有意义：</span><span class="sxs-lookup"><span data-stu-id="fd1d7-106">White space characters in XML literals are significant in only three areas:</span></span>  
  
-   <span data-ttu-id="fd1d7-107">当它们位于属性值。</span><span class="sxs-lookup"><span data-stu-id="fd1d7-107">When they are in an attribute value.</span></span>  
  
-   <span data-ttu-id="fd1d7-108">当它们是元素的文本内容的一部分，并且该文本还包含其他字符。</span><span class="sxs-lookup"><span data-stu-id="fd1d7-108">When they are part of an element's text content and the text also contains other characters.</span></span>  
  
-   <span data-ttu-id="fd1d7-109">当它们位于元素的文本内容的嵌入式表达式。</span><span class="sxs-lookup"><span data-stu-id="fd1d7-109">When they are in an embedded expression for an element's text content.</span></span>  
  
 <span data-ttu-id="fd1d7-110">否则为编译器将视为无意义的空白字符，且不包括然后中[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]文本的对象。</span><span class="sxs-lookup"><span data-stu-id="fd1d7-110">Otherwise, the compiler treats white space characters as insignificant and does not include then in the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] object for the literal.</span></span>  
  
 <span data-ttu-id="fd1d7-111">若要在 XML 文本中包括无关紧要的空白区域，使用嵌入式的表达式包含具有空白区域的字符串文本。</span><span class="sxs-lookup"><span data-stu-id="fd1d7-111">To include insignificant white space in an XML literal, use an embedded expression that contains a string literal with the white space.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fd1d7-112">如果`xml:space`属性出现在 XML 元素文本，[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]编译器包括中的属性<xref:System.Xml.Linq.XElement>对象，但添加此属性不会更改编译器如何处理空白区域。</span><span class="sxs-lookup"><span data-stu-id="fd1d7-112">If the `xml:space` attribute appears in an XML element literal, the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler includes the attribute in the <xref:System.Xml.Linq.XElement> object, but adding this attribute does not change how the compiler treats white space.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="fd1d7-113">示例</span><span class="sxs-lookup"><span data-stu-id="fd1d7-113">Examples</span></span>  
 <span data-ttu-id="fd1d7-114">下面的示例包含两个 XML 元素，外部和内部。</span><span class="sxs-lookup"><span data-stu-id="fd1d7-114">The following example contains two XML elements, outer and inner.</span></span> <span data-ttu-id="fd1d7-115">这两个元素包含文本内容中的空白区域。</span><span class="sxs-lookup"><span data-stu-id="fd1d7-115">Both elements contain white space in their text content.</span></span> <span data-ttu-id="fd1d7-116">中的外部元素的空白区域是无意义，因为它只包含空格和一个 XML 元素。</span><span class="sxs-lookup"><span data-stu-id="fd1d7-116">The white space in the outer element is insignificant because it contains only white space and an XML element.</span></span> <span data-ttu-id="fd1d7-117">中元素的内部的空白区域很重要，因为它包含空格和文本。</span><span class="sxs-lookup"><span data-stu-id="fd1d7-117">The white space in the inner element is significant because it contains white space and text.</span></span>  
  
 [!code-vb[VbXMLSamples#29](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/white-space-in-xml-literals_1.vb)]  
  
 <span data-ttu-id="fd1d7-118">运行时，此代码将显示以下文本。</span><span class="sxs-lookup"><span data-stu-id="fd1d7-118">When run, this code displays the following text.</span></span>  
  
```xml  
<outer>  
  <inner>  
                                          Inner text  
                                      </inner>  
</outer>  
```  
  
## <a name="see-also"></a><span data-ttu-id="fd1d7-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fd1d7-119">See Also</span></span>  
 [<span data-ttu-id="fd1d7-120">在 Visual Basic 中创建 XML</span><span class="sxs-lookup"><span data-stu-id="fd1d7-120">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
