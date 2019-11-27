---
title: 如何：访问 XML 后代元素
ms.date: 07/20/2015
helpviewer_keywords:
- XML descendent axis property [Visual Basic]
- XML axis [Visual Basic], descendent
- descendent axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: aabfa258-4112-4e7e-bab9-403f96072ef7
ms.openlocfilehash: 63a094c3c2b20736f0ef6589c76d53b7cc96b29a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74332316"
---
# <a name="how-to-access-xml-descendant-elements-visual-basic"></a><span data-ttu-id="576e2-102">如何：访问 XML 后代元素 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="576e2-102">How to: Access XML Descendant Elements (Visual Basic)</span></span>
<span data-ttu-id="576e2-103">此示例演示如何使用子代轴属性访问具有指定名称并包含在 XML 元素下的所有 XML 元素。</span><span class="sxs-lookup"><span data-stu-id="576e2-103">This example shows how to use a descendant axis property to access all XML elements that have a specified name and that are contained under an XML element.</span></span> <span data-ttu-id="576e2-104">具体而言，它使用 `Value` 属性获取集合中 `name` 子代轴属性返回的第一个元素的值。</span><span class="sxs-lookup"><span data-stu-id="576e2-104">In particular, it uses the `Value` property to get the value of the first element in the collection that the `name` descendant axis property returns.</span></span> <span data-ttu-id="576e2-105">`name` 子代轴属性可获取 `contacts` 对象中包含的所有名为 `name` 的元素。</span><span class="sxs-lookup"><span data-stu-id="576e2-105">The `name` descendant axis property gets all elements named `name` that are contained in the `contacts` object.</span></span> <span data-ttu-id="576e2-106">此示例还使用 `phone` 子代轴属性来访问 `contacts` 对象中包含的所有名为 `phone` 的后代。</span><span class="sxs-lookup"><span data-stu-id="576e2-106">This example also uses the `phone` descendant axis property to access all descendants named `phone` that are contained in the `contacts` object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="576e2-107">示例</span><span class="sxs-lookup"><span data-stu-id="576e2-107">Example</span></span>  
 [!code-vb[VbXMLSamples#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="576e2-108">编译代码</span><span class="sxs-lookup"><span data-stu-id="576e2-108">Compiling the Code</span></span>  
 <span data-ttu-id="576e2-109">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="576e2-109">This example requires:</span></span>  
  
- <span data-ttu-id="576e2-110">对 <xref:System.Xml.Linq> 命名空间的引用。</span><span class="sxs-lookup"><span data-stu-id="576e2-110">A reference to the <xref:System.Xml.Linq> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="576e2-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="576e2-111">See also</span></span>

- <xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=nameWithType>
- [<span data-ttu-id="576e2-112">XML 子代轴属性</span><span class="sxs-lookup"><span data-stu-id="576e2-112">XML Descendant Axis Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-descendant-axis-property.md)
- [<span data-ttu-id="576e2-113">XML 值属性</span><span class="sxs-lookup"><span data-stu-id="576e2-113">XML Value Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)
- [<span data-ttu-id="576e2-114">在 Visual Basic 中访问 XML</span><span class="sxs-lookup"><span data-stu-id="576e2-114">Accessing XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
- [<span data-ttu-id="576e2-115">XML</span><span class="sxs-lookup"><span data-stu-id="576e2-115">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
