---
title: "如何：访问 XML 后代元素 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XML descendent axis property [Visual Basic]
- XML axis [Visual Basic], descendent
- descendent axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: aabfa258-4112-4e7e-bab9-403f96072ef7
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7b3b6c8ac96bd18a379804b83f3ab3e48a5b0c89
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-access-xml-descendant-elements-visual-basic"></a><span data-ttu-id="fc1cb-102">如何：访问 XML 后代元素 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fc1cb-102">How to: Access XML Descendant Elements (Visual Basic)</span></span>
<span data-ttu-id="fc1cb-103">此示例演示如何使用子代轴属性来访问具有指定的名称且包含的 XML 元素下的所有 XML 元素。</span><span class="sxs-lookup"><span data-stu-id="fc1cb-103">This example shows how to use a descendant axis property to access all XML elements that have a specified name and that are contained under an XML element.</span></span> <span data-ttu-id="fc1cb-104">具体而言，它使用`Value`属性集合中获取的第一个元素的值`name`子代轴属性返回。</span><span class="sxs-lookup"><span data-stu-id="fc1cb-104">In particular, it uses the `Value` property to get the value of the first element in the collection that the `name` descendant axis property returns.</span></span> <span data-ttu-id="fc1cb-105">`name`子代轴属性可获取名为的所有元素`name`中包含`contacts`对象。</span><span class="sxs-lookup"><span data-stu-id="fc1cb-105">The `name` descendant axis property gets all elements named `name` that are contained in the `contacts` object.</span></span> <span data-ttu-id="fc1cb-106">此示例还使用`phone`子代轴属性来访问名为的所有后代`phone`中包含`contacts`对象。</span><span class="sxs-lookup"><span data-stu-id="fc1cb-106">This example also uses the `phone` descendant axis property to access all descendants named `phone` that are contained in the `contacts` object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fc1cb-107">示例</span><span class="sxs-lookup"><span data-stu-id="fc1cb-107">Example</span></span>  
 [!code-vb[VbXMLSamples#31](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-access-xml-descendant-elements_1.vb)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="fc1cb-108">编译代码</span><span class="sxs-lookup"><span data-stu-id="fc1cb-108">Compiling the Code</span></span>  
 <span data-ttu-id="fc1cb-109">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="fc1cb-109">This example requires:</span></span>  
  
-   <span data-ttu-id="fc1cb-110">对 <xref:System.Xml.Linq> 命名空间的引用。</span><span class="sxs-lookup"><span data-stu-id="fc1cb-110">A reference to the <xref:System.Xml.Linq> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc1cb-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fc1cb-111">See Also</span></span>  
 <xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="fc1cb-112">XML 子代轴属性</span><span class="sxs-lookup"><span data-stu-id="fc1cb-112">XML Descendant Axis Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-descendant-axis-property.md)  
 [<span data-ttu-id="fc1cb-113">XML 值属性</span><span class="sxs-lookup"><span data-stu-id="fc1cb-113">XML Value Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)  
 [<span data-ttu-id="fc1cb-114">在 Visual Basic 中访问 XML</span><span class="sxs-lookup"><span data-stu-id="fc1cb-114">Accessing XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)  
 [<span data-ttu-id="fc1cb-115">XML</span><span class="sxs-lookup"><span data-stu-id="fc1cb-115">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
