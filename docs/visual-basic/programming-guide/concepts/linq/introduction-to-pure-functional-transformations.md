---
title: "介绍纯函数转换 (Visual Basic 中) |Microsoft 文档"
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
ms.assetid: 82bf3348-c503-4854-a91f-71f9835779ff
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 72d05eada95f5ce08d60c283346e221328c23020
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017


---
# <a name="introduction-to-pure-functional-transformations-visual-basic"></a><span data-ttu-id="e015d-102">介绍纯函数转换 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e015d-102">Introduction to Pure Functional Transformations (Visual Basic)</span></span>
<span data-ttu-id="e015d-103">本节介绍函数转换，包括基本概念和支持的语言构造。</span><span class="sxs-lookup"><span data-stu-id="e015d-103">This section introduces functional transformations, including the underlying concepts and supporting language constructs.</span></span> <span data-ttu-id="e015d-104">本节对面向对象的编程方法与函数转换编程方法进行了对比，并针对如何转换到后者提供了一些建议。</span><span class="sxs-lookup"><span data-stu-id="e015d-104">It contrasts the object-oriented and functional transformation approaches to programming, including advice on how to transition to the latter.</span></span> <span data-ttu-id="e015d-105">尽管可以在很多编程方案中都使用函数转换，但此处使用 XML 转换作为具体示例。</span><span class="sxs-lookup"><span data-stu-id="e015d-105">Although functional transformations can be used in many programming scenarios, XML transformation is used here as a concrete example.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e015d-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="e015d-106">In This Section</span></span>  
  
|<span data-ttu-id="e015d-107">主题</span><span class="sxs-lookup"><span data-stu-id="e015d-107">Topic</span></span>|<span data-ttu-id="e015d-108">描述</span><span class="sxs-lookup"><span data-stu-id="e015d-108">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="e015d-109">概念和术语 （功能转换） (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e015d-109">Concepts and Terminology (Functional Transformation) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/concepts-and-terminology-functional-transformation.md)|<span data-ttu-id="e015d-110">介绍纯函数转换的概念和术语。</span><span class="sxs-lookup"><span data-stu-id="e015d-110">Introduces the concepts and terminology of pure functional transformations.</span></span>|  
|[<span data-ttu-id="e015d-111">函数编程与命令式编程 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e015d-111">Functional Programming vs. Imperative Programming (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/functional-programming-vs-imperative-programming.md)|<span data-ttu-id="e015d-112">将函数编程与更传统的命令性（过程）编程进行对比。</span><span class="sxs-lookup"><span data-stu-id="e015d-112">Compares and contrasts functional programming to more traditional imperative (procedural) programming.</span></span>|  
|[<span data-ttu-id="e015d-113">重构为纯函数 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e015d-113">Refactoring Into Pure Functions (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/refactoring-into-pure-functions.md)|<span data-ttu-id="e015d-114">介绍纯函数，并提供了纯函数和非纯函数的示例。</span><span class="sxs-lookup"><span data-stu-id="e015d-114">Introduces pure functions, and shows examples of and pure and impure functions.</span></span>|  
|[<span data-ttu-id="e015d-115">功能转换 (Visual Basic 中) 的适用性</span><span class="sxs-lookup"><span data-stu-id="e015d-115">Applicability of Functional Transformation (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/applicability-of-functional-transformation.md)|<span data-ttu-id="e015d-116">描述函数转换的典型应用场景。</span><span class="sxs-lookup"><span data-stu-id="e015d-116">Describes typical scenarios for functional transformations.</span></span>|  
|[<span data-ttu-id="e015d-117">XML (Visual Basic 中) 的功能转换</span><span class="sxs-lookup"><span data-stu-id="e015d-117">Functional Transformation of XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/functional-transformation-of-xml.md)|<span data-ttu-id="e015d-118">描述在转换 XML 树的上下文中的函数转换。</span><span class="sxs-lookup"><span data-stu-id="e015d-118">Describes functional transformations in the context of transforming XML trees.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e015d-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e015d-119">See Also</span></span>  
 [<span data-ttu-id="e015d-120">纯功能转换的 XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e015d-120">Pure Functional Transformations of XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/pure-functional-transformations-of-xml.md)
