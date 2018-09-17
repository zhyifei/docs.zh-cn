---
title: 纯功能转换简介 (C#)
ms.date: 07/20/2015
ms.assetid: 8495c9d9-2d02-4aa0-8a10-9e8794b985fe
ms.openlocfilehash: f04189c5ae6fc8f6c827f983357ab0126b2c086d
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2018
ms.locfileid: "45675621"
---
# <a name="introduction-to-pure-functional-transformations-c"></a><span data-ttu-id="bd652-102">纯功能转换简介 (C#)</span><span class="sxs-lookup"><span data-stu-id="bd652-102">Introduction to Pure Functional Transformations (C#)</span></span>
<span data-ttu-id="bd652-103">本节介绍函数转换，包括基本概念和支持的语言构造。</span><span class="sxs-lookup"><span data-stu-id="bd652-103">This section introduces functional transformations, including the underlying concepts and supporting language constructs.</span></span> <span data-ttu-id="bd652-104">本节对面向对象的编程方法与函数转换编程方法进行了对比，并针对如何转换到后者提供了一些建议。</span><span class="sxs-lookup"><span data-stu-id="bd652-104">It contrasts the object-oriented and functional transformation approaches to programming, including advice on how to transition to the latter.</span></span> <span data-ttu-id="bd652-105">尽管可以在很多编程方案中都使用函数转换，但此处使用 XML 转换作为具体示例。</span><span class="sxs-lookup"><span data-stu-id="bd652-105">Although functional transformations can be used in many programming scenarios, XML transformation is used here as a concrete example.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bd652-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="bd652-106">In This Section</span></span>  
  
|<span data-ttu-id="bd652-107">主题</span><span class="sxs-lookup"><span data-stu-id="bd652-107">Topic</span></span>|<span data-ttu-id="bd652-108">描述</span><span class="sxs-lookup"><span data-stu-id="bd652-108">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="bd652-109">概念和术语（功能转换）(C#)</span><span class="sxs-lookup"><span data-stu-id="bd652-109">Concepts and Terminology (Functional Transformation) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/concepts-and-terminology-functional-transformation.md)|<span data-ttu-id="bd652-110">介绍纯函数转换的概念和术语。</span><span class="sxs-lookup"><span data-stu-id="bd652-110">Introduces the concepts and terminology of pure functional transformations.</span></span>|  
|[<span data-ttu-id="bd652-111">函数编程与命令式编程 (C#)</span><span class="sxs-lookup"><span data-stu-id="bd652-111">Functional Programming vs. Imperative Programming (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/functional-programming-vs-imperative-programming.md)|<span data-ttu-id="bd652-112">将函数编程与更传统的命令性（过程）编程进行对比。</span><span class="sxs-lookup"><span data-stu-id="bd652-112">Compares and contrasts functional programming to more traditional imperative (procedural) programming.</span></span>|  
|[<span data-ttu-id="bd652-113">重构为纯函数 (C#)</span><span class="sxs-lookup"><span data-stu-id="bd652-113">Refactoring Into Pure Functions (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/refactoring-into-pure-functions.md)|<span data-ttu-id="bd652-114">介绍纯函数，并提供了纯函数和非纯函数的示例。</span><span class="sxs-lookup"><span data-stu-id="bd652-114">Introduces pure functions, and shows examples of and pure and impure functions.</span></span>|  
|[<span data-ttu-id="bd652-115">功能转换的适用性 (C#)</span><span class="sxs-lookup"><span data-stu-id="bd652-115">Applicability of Functional Transformation (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/applicability-of-functional-transformation.md)|<span data-ttu-id="bd652-116">描述函数转换的典型应用场景。</span><span class="sxs-lookup"><span data-stu-id="bd652-116">Describes typical scenarios for functional transformations.</span></span>|  
|[<span data-ttu-id="bd652-117">XML 的功能转换 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bd652-117">Functional Transformation of XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/functional-transformation-of-xml.md)|<span data-ttu-id="bd652-118">描述在转换 XML 树的上下文中的函数转换。</span><span class="sxs-lookup"><span data-stu-id="bd652-118">Describes functional transformations in the context of transforming XML trees.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bd652-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="bd652-119">See Also</span></span>

- [<span data-ttu-id="bd652-120">XML 的纯功能转换 (C#)</span><span class="sxs-lookup"><span data-stu-id="bd652-120">Pure Functional Transformations of XML (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/pure-functional-transformations-of-xml.md)
