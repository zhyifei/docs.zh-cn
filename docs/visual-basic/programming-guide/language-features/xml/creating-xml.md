---
title: 创建 XML
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], creating
- LINQ to XML [Visual Basic], creating XML
- XML literals [Visual Basic], creating
ms.assetid: 8ae29ec5-e5fb-4137-9df5-60a288df7045
ms.openlocfilehash: 1c720bc2aca4cec3dd10656d924cf2413fc18a2d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351740"
---
# <a name="creating-xml-in-visual-basic"></a><span data-ttu-id="62146-102">在 Visual Basic 中创建 XML</span><span class="sxs-lookup"><span data-stu-id="62146-102">Creating XML in Visual Basic</span></span>
<span data-ttu-id="62146-103">Visual Basic enables you to use *XML literals* directly in your code.</span><span class="sxs-lookup"><span data-stu-id="62146-103">Visual Basic enables you to use *XML literals* directly in your code.</span></span> <span data-ttu-id="62146-104">The XML literal syntax represents [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objects, and it is similar to the XML 1.0 syntax.</span><span class="sxs-lookup"><span data-stu-id="62146-104">The XML literal syntax represents [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objects, and it is similar to the XML 1.0 syntax.</span></span> <span data-ttu-id="62146-105">This makes it easier to create XML elements, documents, and fragments programmatically because your code has the same structure as the final XML.</span><span class="sxs-lookup"><span data-stu-id="62146-105">This makes it easier to create XML elements, documents, and fragments programmatically because your code has the same structure as the final XML.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="62146-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="62146-106">In This Section</span></span>  
  
|<span data-ttu-id="62146-107">术语</span><span class="sxs-lookup"><span data-stu-id="62146-107">Term</span></span>|<span data-ttu-id="62146-108">定义</span><span class="sxs-lookup"><span data-stu-id="62146-108">Definition</span></span>|  
|---|---|  
|[<span data-ttu-id="62146-109">XML 文本概述</span><span class="sxs-lookup"><span data-stu-id="62146-109">XML Literals Overview</span></span>](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md)|<span data-ttu-id="62146-110">Introduction to XML literals and how they relate to [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="62146-110">Introduction to XML literals and how they relate to [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span>|  
|[<span data-ttu-id="62146-111">XML 中的嵌入式表达式</span><span class="sxs-lookup"><span data-stu-id="62146-111">Embedded Expressions in XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)|<span data-ttu-id="62146-112">Describes how to use embedded expressions in XML literals.</span><span class="sxs-lookup"><span data-stu-id="62146-112">Describes how to use embedded expressions in XML literals.</span></span>|  
|[<span data-ttu-id="62146-113">如何：创建 XML 文本</span><span class="sxs-lookup"><span data-stu-id="62146-113">How to: Create XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-create-xml-literals.md)|<span data-ttu-id="62146-114">Describes how to create an XML element in code by using an XML literal.</span><span class="sxs-lookup"><span data-stu-id="62146-114">Describes how to create an XML element in code by using an XML literal.</span></span>|  
|[<span data-ttu-id="62146-115">XML 文本中的空白</span><span class="sxs-lookup"><span data-stu-id="62146-115">White Space in XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/white-space-in-xml-literals.md)|<span data-ttu-id="62146-116">Describes how Visual Basic treats white space in XML literals.</span><span class="sxs-lookup"><span data-stu-id="62146-116">Describes how Visual Basic treats white space in XML literals.</span></span>|  
|[<span data-ttu-id="62146-117">XML 文本和 XML 1.0 规范</span><span class="sxs-lookup"><span data-stu-id="62146-117">XML Literals and the XML 1.0 Specification</span></span>](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md)|<span data-ttu-id="62146-118">Describes how the XML literal syntax in Visual Basic relates to the XML 1.0 specification.</span><span class="sxs-lookup"><span data-stu-id="62146-118">Describes how the XML literal syntax in Visual Basic relates to the XML 1.0 specification.</span></span>|  
|[<span data-ttu-id="62146-119">如何：在 XML 文本中嵌入表达式</span><span class="sxs-lookup"><span data-stu-id="62146-119">How to: Embed Expressions in XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-embed-expressions-in-xml-literals.md)|<span data-ttu-id="62146-120">Describes how to use embedded expressions in XML literals to create content at run time.</span><span class="sxs-lookup"><span data-stu-id="62146-120">Describes how to use embedded expressions in XML literals to create content at run time.</span></span>|  
|[<span data-ttu-id="62146-121">已声明的 XML 元素和特性的名称</span><span class="sxs-lookup"><span data-stu-id="62146-121">Names of Declared XML Elements and Attributes</span></span>](../../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)|<span data-ttu-id="62146-122">Describes guidelines for naming XML elements and attributes.</span><span class="sxs-lookup"><span data-stu-id="62146-122">Describes guidelines for naming XML elements and attributes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="62146-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="62146-123">See also</span></span>

- [<span data-ttu-id="62146-124">XML</span><span class="sxs-lookup"><span data-stu-id="62146-124">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
