---
title: "纯函数转换的 XML (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5e19b74a-7773-4b58-b110-953ffd364c55
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 01ad228d91037de1585d1e66292fddb80c785ada
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="pure-functional-transformations-of-xml-visual-basic"></a><span data-ttu-id="c1e40-102">纯函数转换的 XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c1e40-102">Pure Functional Transformations of XML (Visual Basic)</span></span>
<span data-ttu-id="c1e40-103">本节提供 XML 的函数转换教程。</span><span class="sxs-lookup"><span data-stu-id="c1e40-103">This section provides a functional transformation tutorial for XML.</span></span> <span data-ttu-id="c1e40-104">它包括使用函数转换所必须理解的主要概念和语言构造的说明以及使用函数转换来操作 XML 文档的示例。</span><span class="sxs-lookup"><span data-stu-id="c1e40-104">This includes explanations of the main concepts and language constructs that you must understand to use functional transformations, and examples of using functional transformations to manipulate an XML document.</span></span> <span data-ttu-id="c1e40-105">虽然本教程提供 LINQ to XML 代码示例，但所有基础概念也适用于其他 LINQ 技术。</span><span class="sxs-lookup"><span data-stu-id="c1e40-105">Although this tutorial provides LINQ to XML code examples, all of the underlying concepts also apply to other LINQ technologies.</span></span>  
  
 <span data-ttu-id="c1e40-106">[教程： 在 WordprocessingML 文档 (Visual Basic 中) 中使用内容](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md)教程提供的一系列示例，在前一个上每个生成。</span><span class="sxs-lookup"><span data-stu-id="c1e40-106">The [Tutorial: Manipulating Content in a WordprocessingML Document (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md) tutorial provides a series of examples, each building on the previous one.</span></span> <span data-ttu-id="c1e40-107">这些示例演示用于操作 XML 的纯函数转换方法。</span><span class="sxs-lookup"><span data-stu-id="c1e40-107">These examples demonstrate the pure functional transformational approach to manipulating XML.</span></span>  
  
 <span data-ttu-id="c1e40-108">本教程假定 Visual Basic 的知识。</span><span class="sxs-lookup"><span data-stu-id="c1e40-108">This tutorial assumes a working knowledge of Visual Basic.</span></span> <span data-ttu-id="c1e40-109">本教程不提供语言构造的详细语义，但提供到相应语言文档的链接。</span><span class="sxs-lookup"><span data-stu-id="c1e40-109">Detailed semantics of the language constructs are not provided in this tutorial, but links are provided to the language documentation as appropriate.</span></span>  
  
 <span data-ttu-id="c1e40-110">还假定您已了解基本计算机科学概念和 XML（包括 XML 命名空间）的使用知识。</span><span class="sxs-lookup"><span data-stu-id="c1e40-110">A working knowledge of basic computer science concepts and XML, including XML namespaces, is also assumed.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c1e40-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="c1e40-111">In This Section</span></span>  
  
|<span data-ttu-id="c1e40-112">主题</span><span class="sxs-lookup"><span data-stu-id="c1e40-112">Topic</span></span>|<span data-ttu-id="c1e40-113">描述</span><span class="sxs-lookup"><span data-stu-id="c1e40-113">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="c1e40-114">介绍纯函数转换 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c1e40-114">Introduction to Pure Functional Transformations (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md)|<span data-ttu-id="c1e40-115">说明函数转换并定义相关术语。</span><span class="sxs-lookup"><span data-stu-id="c1e40-115">Describes functional transformations and defines the relevant terminology.</span></span>|  
|[<span data-ttu-id="c1e40-116">教程： 延迟执行 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c1e40-116">Tutorial: Deferred Execution (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/tutorial-deferred-execution.md)|<span data-ttu-id="c1e40-117">详细说明迟缓计算和延迟执行。</span><span class="sxs-lookup"><span data-stu-id="c1e40-117">Describes lazy evaluation and deferred execution in detail.</span></span>|  
|[<span data-ttu-id="c1e40-118">教程： 操作 WordprocessingML 文档 (Visual Basic 中) 中的内容</span><span class="sxs-lookup"><span data-stu-id="c1e40-118">Tutorial: Manipulating Content in a WordprocessingML Document (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md)|<span data-ttu-id="c1e40-119">演示函数转换的教程。</span><span class="sxs-lookup"><span data-stu-id="c1e40-119">A tutorial that demonstrates a functional transformation.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c1e40-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c1e40-120">See Also</span></span>  
 [<span data-ttu-id="c1e40-121">查询 XML 树 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c1e40-121">Querying XML Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/querying-xml-trees.md)
