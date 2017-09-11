---
title: "在 Visual Basic 中创建 XML |Microsoft 文档"
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
- XML [Visual Basic], creating
- LINQ to XML [Visual Basic], creating XML
- XML literals [Visual Basic], creating
ms.assetid: 8ae29ec5-e5fb-4137-9df5-60a288df7045
caps.latest.revision: 24
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
ms.openlocfilehash: ec45ab4dc7d4c9282d444c00b0b262b3d8dd4da1
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="creating-xml-in-visual-basic"></a><span data-ttu-id="7e03d-102">在 Visual Basic 中创建 XML</span><span class="sxs-lookup"><span data-stu-id="7e03d-102">Creating XML in Visual Basic</span></span>
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="7e03d-103">使您能够使用*XML 文本*直接在代码中。</span><span class="sxs-lookup"><span data-stu-id="7e03d-103"> enables you to use *XML literals* directly in your code.</span></span> <span data-ttu-id="7e03d-104">XML 文本语法表示[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]对象，也是如此类似于 XML 1.0 语法。</span><span class="sxs-lookup"><span data-stu-id="7e03d-104">The XML literal syntax represents [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] objects, and it is similar to the XML 1.0 syntax.</span></span> <span data-ttu-id="7e03d-105">这使得更轻松地以编程方式创建 XML 元素、 文档和片段，因为您的代码具有相同的结构与最终的 XML。</span><span class="sxs-lookup"><span data-stu-id="7e03d-105">This makes it easier to create XML elements, documents, and fragments programmatically because your code has the same structure as the final XML.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7e03d-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="7e03d-106">In This Section</span></span>  
  
|<span data-ttu-id="7e03d-107">术语</span><span class="sxs-lookup"><span data-stu-id="7e03d-107">Term</span></span>|<span data-ttu-id="7e03d-108">定义</span><span class="sxs-lookup"><span data-stu-id="7e03d-108">Definition</span></span>|  
|---|---|  
|[<span data-ttu-id="7e03d-109">XML 文本概述</span><span class="sxs-lookup"><span data-stu-id="7e03d-109">XML Literals Overview</span></span>](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md)|<span data-ttu-id="7e03d-110">XML 文本和它们如何相关简介[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]。</span><span class="sxs-lookup"><span data-stu-id="7e03d-110">Introduction to XML literals and how they relate to [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].</span></span>|  
|[<span data-ttu-id="7e03d-111">XML 中的嵌入式表达式</span><span class="sxs-lookup"><span data-stu-id="7e03d-111">Embedded Expressions in XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)|<span data-ttu-id="7e03d-112">描述如何使用 XML 文本中嵌入的表达式。</span><span class="sxs-lookup"><span data-stu-id="7e03d-112">Describes how to use embedded expressions in XML literals.</span></span>|  
|[<span data-ttu-id="7e03d-113">如何：创建 XML 文本</span><span class="sxs-lookup"><span data-stu-id="7e03d-113">How to: Create XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-create-xml-literals.md)|<span data-ttu-id="7e03d-114">描述如何通过使用 XML 文本在代码中创建一个 XML 元素。</span><span class="sxs-lookup"><span data-stu-id="7e03d-114">Describes how to create an XML element in code by using an XML literal.</span></span>|  
|[<span data-ttu-id="7e03d-115">XML 文本中的空白</span><span class="sxs-lookup"><span data-stu-id="7e03d-115">White Space in XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/white-space-in-xml-literals.md)|<span data-ttu-id="7e03d-116">描述如何[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]空白对待 XML 文本中。</span><span class="sxs-lookup"><span data-stu-id="7e03d-116">Describes how [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] treats white space in XML literals.</span></span>|  
|[<span data-ttu-id="7e03d-117">XML 文本和 XML 1.0 规范</span><span class="sxs-lookup"><span data-stu-id="7e03d-117">XML Literals and the XML 1.0 Specification</span></span>](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md)|<span data-ttu-id="7e03d-118">描述如何在 XML 文本语法[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]与 XML 1.0 规范。</span><span class="sxs-lookup"><span data-stu-id="7e03d-118">Describes how the XML literal syntax in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] relates to the XML 1.0 specification.</span></span>|  
|[<span data-ttu-id="7e03d-119">如何：在 XML 文本中嵌入表达式</span><span class="sxs-lookup"><span data-stu-id="7e03d-119">How to: Embed Expressions in XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-embed-expressions-in-xml-literals.md)|<span data-ttu-id="7e03d-120">描述如何使用 XML 文本中嵌入的表达式在运行时创建的内容。</span><span class="sxs-lookup"><span data-stu-id="7e03d-120">Describes how to use embedded expressions in XML literals to create content at run time.</span></span>|  
|[<span data-ttu-id="7e03d-121">已声明的 XML 元素和特性的名称</span><span class="sxs-lookup"><span data-stu-id="7e03d-121">Names of Declared XML Elements and Attributes</span></span>](../../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)|<span data-ttu-id="7e03d-122">描述 XML 元素和属性命名的准则。</span><span class="sxs-lookup"><span data-stu-id="7e03d-122">Describes guidelines for naming XML elements and attributes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7e03d-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7e03d-123">See Also</span></span>  
 [<span data-ttu-id="7e03d-124">XML</span><span class="sxs-lookup"><span data-stu-id="7e03d-124">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
