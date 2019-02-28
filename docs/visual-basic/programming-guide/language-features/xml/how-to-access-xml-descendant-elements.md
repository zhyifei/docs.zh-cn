---
title: 如何：访问 XML 子代元素 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- XML descendent axis property [Visual Basic]
- XML axis [Visual Basic], descendent
- descendent axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: aabfa258-4112-4e7e-bab9-403f96072ef7
ms.openlocfilehash: 1edbbc052bbf319d91f1f944451312e7d67594ca
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "56973855"
---
# <a name="how-to-access-xml-descendant-elements-visual-basic"></a><span data-ttu-id="b6169-102">如何：访问 XML 子代元素 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b6169-102">How to: Access XML Descendant Elements (Visual Basic)</span></span>
<span data-ttu-id="b6169-103">此示例演示如何使用子代轴属性来访问具有指定的名称并且包含 XML 元素下的所有 XML 元素。</span><span class="sxs-lookup"><span data-stu-id="b6169-103">This example shows how to use a descendant axis property to access all XML elements that have a specified name and that are contained under an XML element.</span></span> <span data-ttu-id="b6169-104">具体而言，它使用`Value`属性设置为集合中获取第一个元素的值`name`子代轴属性返回。</span><span class="sxs-lookup"><span data-stu-id="b6169-104">In particular, it uses the `Value` property to get the value of the first element in the collection that the `name` descendant axis property returns.</span></span> <span data-ttu-id="b6169-105">`name`子代轴属性获取名为的所有元素`name`中包含的`contacts`对象。</span><span class="sxs-lookup"><span data-stu-id="b6169-105">The `name` descendant axis property gets all elements named `name` that are contained in the `contacts` object.</span></span> <span data-ttu-id="b6169-106">此示例还使用`phone`子代轴属性来访问名为的所有后代`phone`中包含的`contacts`对象。</span><span class="sxs-lookup"><span data-stu-id="b6169-106">This example also uses the `phone` descendant axis property to access all descendants named `phone` that are contained in the `contacts` object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b6169-107">示例</span><span class="sxs-lookup"><span data-stu-id="b6169-107">Example</span></span>  
 [!code-vb[VbXMLSamples#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b6169-108">编译代码</span><span class="sxs-lookup"><span data-stu-id="b6169-108">Compiling the Code</span></span>  
 <span data-ttu-id="b6169-109">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="b6169-109">This example requires:</span></span>  
  
-   <span data-ttu-id="b6169-110">对 <xref:System.Xml.Linq> 命名空间的引用。</span><span class="sxs-lookup"><span data-stu-id="b6169-110">A reference to the <xref:System.Xml.Linq> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6169-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="b6169-111">See also</span></span>
- <xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=nameWithType>
- [<span data-ttu-id="b6169-112">XML 子代轴属性</span><span class="sxs-lookup"><span data-stu-id="b6169-112">XML Descendant Axis Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-descendant-axis-property.md)
- [<span data-ttu-id="b6169-113">XML 值属性</span><span class="sxs-lookup"><span data-stu-id="b6169-113">XML Value Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)
- [<span data-ttu-id="b6169-114">在 Visual Basic 中访问 XML</span><span class="sxs-lookup"><span data-stu-id="b6169-114">Accessing XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
- [<span data-ttu-id="b6169-115">XML</span><span class="sxs-lookup"><span data-stu-id="b6169-115">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
