---
title: "XML 文本 (Visual Basic 中) 中的空白区域 |Microsoft 文档"
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
- white space [XML in Visual Basic]
- XML literals [Visual Basic], white space
ms.assetid: dfe3a9ff-d69a-418e-a6b5-476f4ed84219
caps.latest.revision: 14
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
ms.openlocfilehash: 4fc3d30a9c71cbd732597c5e3f32bd01eb489a80
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="white-space-in-xml-literals-visual-basic"></a><span data-ttu-id="e0f9b-102">XML 文本中的空白 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e0f9b-102">White Space in XML Literals (Visual Basic)</span></span>
<span data-ttu-id="e0f9b-103">[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]编译器在其创建时包含有意义的空白字符将从 XML 文本[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]对象。</span><span class="sxs-lookup"><span data-stu-id="e0f9b-103">The [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler incorporates only the significant white space characters from an XML literal when it creates a [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] object.</span></span> <span data-ttu-id="e0f9b-104">它不会合并无意义的空白字符。</span><span class="sxs-lookup"><span data-stu-id="e0f9b-104">The insignificant white space characters are not incorporated.</span></span>  
  
## <a name="significant-and-insignificant-white-space"></a><span data-ttu-id="e0f9b-105">有效空白和无关紧要的空白区域</span><span class="sxs-lookup"><span data-stu-id="e0f9b-105">Significant and Insignificant White Space</span></span>  
 <span data-ttu-id="e0f9b-106">XML 文本中的空白字符只有三个区域中有意义︰</span><span class="sxs-lookup"><span data-stu-id="e0f9b-106">White space characters in XML literals are significant in only three areas:</span></span>  
  
-   <span data-ttu-id="e0f9b-107">当它们都在某一属性值。</span><span class="sxs-lookup"><span data-stu-id="e0f9b-107">When they are in an attribute value.</span></span>  
  
-   <span data-ttu-id="e0f9b-108">当它们都属于某个元素的文本内容，并且文本还包含其他字符。</span><span class="sxs-lookup"><span data-stu-id="e0f9b-108">When they are part of an element's text content and the text also contains other characters.</span></span>  
  
-   <span data-ttu-id="e0f9b-109">在嵌入式表达式中的元素的文本内容。</span><span class="sxs-lookup"><span data-stu-id="e0f9b-109">When they are in an embedded expression for an element's text content.</span></span>  
  
 <span data-ttu-id="e0f9b-110">否则为编译器将视为无意义的空白字符，不会将它们包含在[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]文本对象。</span><span class="sxs-lookup"><span data-stu-id="e0f9b-110">Otherwise, the compiler treats white space characters as insignificant and does not include then in the [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] object for the literal.</span></span>  
  
 <span data-ttu-id="e0f9b-111">若要在 XML 文本中包括无关紧要的空白区域，使用嵌入式的表达式，其中包含具有空白区域的字符串文本。</span><span class="sxs-lookup"><span data-stu-id="e0f9b-111">To include insignificant white space in an XML literal, use an embedded expression that contains a string literal with the white space.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e0f9b-112">如果`xml:space`特性出现在 XML 元素文本，[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]编译器该特性包含在<xref:System.Xml.Linq.XElement>对象，但添加此属性不会更改编译器如何处理空白区域。</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="e0f9b-112">If the `xml:space` attribute appears in an XML element literal, the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler includes the attribute in the <xref:System.Xml.Linq.XElement> object, but adding this attribute does not change how the compiler treats white space.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="e0f9b-113">示例</span><span class="sxs-lookup"><span data-stu-id="e0f9b-113">Examples</span></span>  
 <span data-ttu-id="e0f9b-114">下面的示例包含两个 XML 元素，但是外部和内部。</span><span class="sxs-lookup"><span data-stu-id="e0f9b-114">The following example contains two XML elements, outer and inner.</span></span> <span data-ttu-id="e0f9b-115">这两个元素包含文本内容中的空白区域。</span><span class="sxs-lookup"><span data-stu-id="e0f9b-115">Both elements contain white space in their text content.</span></span> <span data-ttu-id="e0f9b-116">外部元素中的空白区域是无意义，因为它仅包含空白区域和一个 XML 元素。</span><span class="sxs-lookup"><span data-stu-id="e0f9b-116">The white space in the outer element is insignificant because it contains only white space and an XML element.</span></span> <span data-ttu-id="e0f9b-117">内部元素中的空白区域很重要，因为它包含的空白区域和文本。</span><span class="sxs-lookup"><span data-stu-id="e0f9b-117">The white space in the inner element is significant because it contains white space and text.</span></span>  
  
 <span data-ttu-id="e0f9b-118">[!code-vb[VbXMLSamples #&29;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/white-space-in-xml-literals_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="e0f9b-118">[!code-vb[VbXMLSamples#29](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/white-space-in-xml-literals_1.vb)]</span></span>  
  
 <span data-ttu-id="e0f9b-119">当运行时，此代码将显示以下文本。</span><span class="sxs-lookup"><span data-stu-id="e0f9b-119">When run, this code displays the following text.</span></span>  
  
```  
<outer>  
  <inner>  
                                          Inner text  
                                      </inner>  
</outer>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e0f9b-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e0f9b-120">See Also</span></span>  
 [<span data-ttu-id="e0f9b-121">在 Visual Basic 中创建 XML</span><span class="sxs-lookup"><span data-stu-id="e0f9b-121">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
