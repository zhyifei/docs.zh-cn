---
title: 如何：访问 XML 子元素 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- XML axis [Visual Basic], child
- child axis property [Visual Basic]
- XML child axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: 6689eb36-c471-469f-a82d-099ab8197b25
ms.openlocfilehash: 874c7490e451d64bf50e25934ea43a9b928ddab9
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "56980550"
---
# <a name="how-to-access-xml-child-elements-visual-basic"></a><span data-ttu-id="84b0c-102">如何：访问 XML 子元素 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="84b0c-102">How to: Access XML Child Elements (Visual Basic)</span></span>
<span data-ttu-id="84b0c-103">此示例演示如何使用子轴属性来访问某个 XML 元素中具有指定的名称的所有 XML 子元素。</span><span class="sxs-lookup"><span data-stu-id="84b0c-103">This example shows how to use a child axis property to access all XML child elements that have a specified name in an XML element.</span></span> <span data-ttu-id="84b0c-104">具体而言，它使用<xref:System.Xml.Linq.XElement.Value%2A>属性设置为集合中获取第一个元素的值`name`子轴属性返回。</span><span class="sxs-lookup"><span data-stu-id="84b0c-104">In particular, it uses the <xref:System.Xml.Linq.XElement.Value%2A> property to get the value of the first element in the collection that the `name` child axis property returns.</span></span> <span data-ttu-id="84b0c-105">`name`子轴属性获取名为的所有子元素`phone`中`contact`对象。</span><span class="sxs-lookup"><span data-stu-id="84b0c-105">The `name` child axis property gets all child elements named `phone` in the `contact` object.</span></span> <span data-ttu-id="84b0c-106">此示例还使用`phone`子轴属性来访问名为的所有子元素`phone`中包含的`contact`对象。</span><span class="sxs-lookup"><span data-stu-id="84b0c-106">This example also uses the `phone` child axis property to access all child elements named `phone` that are contained in the `contact` object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="84b0c-107">示例</span><span class="sxs-lookup"><span data-stu-id="84b0c-107">Example</span></span>  
 [!code-vb[VbXMLSamples#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples4.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="84b0c-108">编译代码</span><span class="sxs-lookup"><span data-stu-id="84b0c-108">Compiling the Code</span></span>  
 <span data-ttu-id="84b0c-109">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="84b0c-109">This example requires:</span></span>  
  
-   <span data-ttu-id="84b0c-110">对 <xref:System.Xml.Linq> 命名空间的引用。</span><span class="sxs-lookup"><span data-stu-id="84b0c-110">A reference to the <xref:System.Xml.Linq> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84b0c-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="84b0c-111">See also</span></span>
- <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType>
- [<span data-ttu-id="84b0c-112">XML 子轴属性</span><span class="sxs-lookup"><span data-stu-id="84b0c-112">XML Child Axis Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)
- [<span data-ttu-id="84b0c-113">XML 值属性</span><span class="sxs-lookup"><span data-stu-id="84b0c-113">XML Value Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)
- [<span data-ttu-id="84b0c-114">在 Visual Basic 中访问 XML</span><span class="sxs-lookup"><span data-stu-id="84b0c-114">Accessing XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
- [<span data-ttu-id="84b0c-115">XML</span><span class="sxs-lookup"><span data-stu-id="84b0c-115">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
