---
title: "教程： 操作 WordprocessingML 文档 (Visual Basic 中) 中的内容"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f8028ba8-2dd1-4425-930c-8cc23176ebbc
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cd84b8cc9f3c959913b2eac943e7fac16862d4c8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="tutorial-manipulating-content-in-a-wordprocessingml-document-visual-basic"></a><span data-ttu-id="fac59-102">教程： 操作 WordprocessingML 文档 (Visual Basic 中) 中的内容</span><span class="sxs-lookup"><span data-stu-id="fac59-102">Tutorial: Manipulating Content in a WordprocessingML Document (Visual Basic)</span></span>
<span data-ttu-id="fac59-103">本教程演示如何应用函数转换方法和 LINQ to XML 来操作 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="fac59-103">This tutorial shows how to apply the functional transformational approach and LINQ to XML to manipulate XML documents.</span></span> <span data-ttu-id="fac59-104">Visual Basic 示例查询和操作由 Microsoft Word 保存 Office Open XML WordprocessingML 文档中的信息。</span><span class="sxs-lookup"><span data-stu-id="fac59-104">The Visual Basic examples query and manipulate information in Office Open XML WordprocessingML documents that are saved by Microsoft Word.</span></span>  
  
 <span data-ttu-id="fac59-105">有关详细信息，请参阅 [OpenXML 开发人员](http://go.microsoft.com/fwlink/?LinkID=95573)网站。</span><span class="sxs-lookup"><span data-stu-id="fac59-105">For more information, see the [OpenXML Developer](http://go.microsoft.com/fwlink/?LinkID=95573) Web site.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fac59-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="fac59-106">In This Section</span></span>  
  
|<span data-ttu-id="fac59-107">主题</span><span class="sxs-lookup"><span data-stu-id="fac59-107">Topic</span></span>|<span data-ttu-id="fac59-108">描述</span><span class="sxs-lookup"><span data-stu-id="fac59-108">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="fac59-109">形状的 WordprocessingML 文档 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fac59-109">Shape of WordprocessingML Documents (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/shape-of-wordprocessingml-documents.md)|<span data-ttu-id="fac59-110">提供有关 WordprocessingML 文档详细信息的简要说明。</span><span class="sxs-lookup"><span data-stu-id="fac59-110">Provides a quick explanation of details of a WordprocessingML document.</span></span>|  
|[<span data-ttu-id="fac59-111">创建源 Office Open XML 文档 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fac59-111">Creating the Source Office Open XML Document (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md)|<span data-ttu-id="fac59-112">为创建用于本教程中的查询的源文档提供分步说明。</span><span class="sxs-lookup"><span data-stu-id="fac59-112">Provides step-by-step instructions to create the source document for queries in this tutorial.</span></span>|  
|[<span data-ttu-id="fac59-113">查找默认段落样式 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fac59-113">Finding the Default Paragraph Style (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/finding-the-default-paragraph-style.md)|<span data-ttu-id="fac59-114">演示用于查找文档默认样式名称的查询。</span><span class="sxs-lookup"><span data-stu-id="fac59-114">Shows a query to find the name of the default style for a document.</span></span>|  
|[<span data-ttu-id="fac59-115">检索段落及其样式 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fac59-115">Retrieving the Paragraphs and Their Styles (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/retrieving-the-paragraphs-and-their-styles.md)|<span data-ttu-id="fac59-116">演示用于检索文档段落集合的查询。</span><span class="sxs-lookup"><span data-stu-id="fac59-116">Shows a query that retrieves a collection of the paragraphs of a document.</span></span>|  
|[<span data-ttu-id="fac59-117">检索段落 (Visual Basic) 的文本</span><span class="sxs-lookup"><span data-stu-id="fac59-117">Retrieving the Text of the Paragraphs (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/retrieving-the-text-of-the-paragraphs.md)|<span data-ttu-id="fac59-118">补充前一个查询以检索每个段落的文本。</span><span class="sxs-lookup"><span data-stu-id="fac59-118">Augments the previous query to retrieve the text of each paragraph.</span></span>|  
|[<span data-ttu-id="fac59-119">重构使用扩展方法 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fac59-119">Refactoring Using an Extension Method (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/refactoring-using-an-extension-method.md)|<span data-ttu-id="fac59-120">通过使用扩展方法进行重构来简化代码。</span><span class="sxs-lookup"><span data-stu-id="fac59-120">Simplifies the code by refactoring using an extension method.</span></span>|  
|[<span data-ttu-id="fac59-121">使用纯函数重构 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fac59-121">Refactoring Using a Pure Function (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/refactoring-using-a-pure-function.md)|<span data-ttu-id="fac59-122">通过使用纯函数进行重构来进一步简化代码。</span><span class="sxs-lookup"><span data-stu-id="fac59-122">Further simplifies the code by refactoring using a pure function.</span></span>|  
|[<span data-ttu-id="fac59-123">将 XML 投影为不同的形状 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fac59-123">Projecting XML in a Different Shape (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/projecting-xml-in-a-different-shape.md)|<span data-ttu-id="fac59-124">通过将 XML 投影为不同于原始文档的形状来完成 XML 转换。</span><span class="sxs-lookup"><span data-stu-id="fac59-124">Completes an XML transformation by projecting XML in a different shape than the original document.</span></span>|  
|[<span data-ttu-id="fac59-125">在 Word 文档 (Visual Basic 中) 中查找文本</span><span class="sxs-lookup"><span data-stu-id="fac59-125">Finding Text in Word Documents (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/finding-text-in-word-documents.md)|<span data-ttu-id="fac59-126">使用前面的查询在文档中查找指定的文本字符串。</span><span class="sxs-lookup"><span data-stu-id="fac59-126">Uses the previous queries to find a specified text string in a document.</span></span>|  
|[<span data-ttu-id="fac59-127">详细信息的 Office Open XML WordprocessingML 文档 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fac59-127">Details of Office Open XML WordprocessingML Documents (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/details-of-office-open-xml-wordprocessingml-documents.md)|<span data-ttu-id="fac59-128">提供 Office Open XML WordprocessingML 文档的一些详细信息。</span><span class="sxs-lookup"><span data-stu-id="fac59-128">Provides some details of Office Open XML WordprocessingML documents.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fac59-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fac59-129">See Also</span></span>  
 [<span data-ttu-id="fac59-130">纯函数转换的 XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fac59-130">Pure Functional Transformations of XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/pure-functional-transformations-of-xml.md)  
 [<span data-ttu-id="fac59-131">介绍纯函数转换 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fac59-131">Introduction to Pure Functional Transformations (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md)
