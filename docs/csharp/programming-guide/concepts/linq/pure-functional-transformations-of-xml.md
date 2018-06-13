---
title: XML 的纯功能转换 (C#)
ms.date: 07/20/2015
ms.assetid: 97e8e582-eb3d-4756-bbfb-0899eb688ae4
ms.openlocfilehash: 7bbe5735541432108794959a7889976d4951fffd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33336705"
---
# <a name="pure-functional-transformations-of-xml-c"></a><span data-ttu-id="1dd71-102">XML 的纯功能转换 (C#)</span><span class="sxs-lookup"><span data-stu-id="1dd71-102">Pure Functional Transformations of XML (C#)</span></span>
<span data-ttu-id="1dd71-103">本节提供 XML 的函数转换教程。</span><span class="sxs-lookup"><span data-stu-id="1dd71-103">This section provides a functional transformation tutorial for XML.</span></span> <span data-ttu-id="1dd71-104">它包括使用函数转换所必须理解的主要概念和语言构造的说明以及使用函数转换来操作 XML 文档的示例。</span><span class="sxs-lookup"><span data-stu-id="1dd71-104">This includes explanations of the main concepts and language constructs that you must understand to use functional transformations, and examples of using functional transformations to manipulate an XML document.</span></span> <span data-ttu-id="1dd71-105">虽然本教程提供 LINQ to XML 代码示例，但所有基础概念也适用于其他 LINQ 技术。</span><span class="sxs-lookup"><span data-stu-id="1dd71-105">Although this tutorial provides LINQ to XML code examples, all of the underlying concepts also apply to other LINQ technologies.</span></span>  
  
 <span data-ttu-id="1dd71-106">[教程：操作 WordprocessingML 文档中的内容 (C#)](../../../../csharp/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md) 教程提供一系列示例，每个示例都是在前一个示例的基础上生成的。</span><span class="sxs-lookup"><span data-stu-id="1dd71-106">The [Tutorial: Manipulating Content in a WordprocessingML Document (C#)](../../../../csharp/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md) tutorial provides a series of examples, each building on the previous one.</span></span> <span data-ttu-id="1dd71-107">这些示例演示用于操作 XML 的纯函数转换方法。</span><span class="sxs-lookup"><span data-stu-id="1dd71-107">These examples demonstrate the pure functional transformational approach to manipulating XML.</span></span>  
  
 <span data-ttu-id="1dd71-108">本教程假定你了解 C# 的使用知识。</span><span class="sxs-lookup"><span data-stu-id="1dd71-108">This tutorial assumes a working knowledge of C#.</span></span> <span data-ttu-id="1dd71-109">本教程不提供语言构造的详细语义，但提供到相应语言文档的链接。</span><span class="sxs-lookup"><span data-stu-id="1dd71-109">Detailed semantics of the language constructs are not provided in this tutorial, but links are provided to the language documentation as appropriate.</span></span>  
  
 <span data-ttu-id="1dd71-110">还假定您已了解基本计算机科学概念和 XML（包括 XML 命名空间）的使用知识。</span><span class="sxs-lookup"><span data-stu-id="1dd71-110">A working knowledge of basic computer science concepts and XML, including XML namespaces, is also assumed.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1dd71-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="1dd71-111">In This Section</span></span>  
  
|<span data-ttu-id="1dd71-112">主题</span><span class="sxs-lookup"><span data-stu-id="1dd71-112">Topic</span></span>|<span data-ttu-id="1dd71-113">描述</span><span class="sxs-lookup"><span data-stu-id="1dd71-113">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="1dd71-114">纯函数转换简介 (C#)</span><span class="sxs-lookup"><span data-stu-id="1dd71-114">Introduction to Pure Functional Transformations (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md)|<span data-ttu-id="1dd71-115">说明函数转换并定义相关术语。</span><span class="sxs-lookup"><span data-stu-id="1dd71-115">Describes functional transformations and defines the relevant terminology.</span></span>|  
|[<span data-ttu-id="1dd71-116">教程：将查询链接在一起 (C#)</span><span class="sxs-lookup"><span data-stu-id="1dd71-116">Tutorial: Chaining Queries Together (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/tutorial-chaining-queries-together.md)|<span data-ttu-id="1dd71-117">详细说明迟缓计算和延迟执行。</span><span class="sxs-lookup"><span data-stu-id="1dd71-117">Describes lazy evaluation and deferred execution in detail.</span></span>|  
|[<span data-ttu-id="1dd71-118">教程：操作 WordprocessingML 文档中的内容 (C#)</span><span class="sxs-lookup"><span data-stu-id="1dd71-118">Tutorial: Manipulating Content in a WordprocessingML Document (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md)|<span data-ttu-id="1dd71-119">演示函数转换的教程。</span><span class="sxs-lookup"><span data-stu-id="1dd71-119">A tutorial that demonstrates a functional transformation.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1dd71-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="1dd71-120">See Also</span></span>  
 [<span data-ttu-id="1dd71-121">查询 XML 树 (C#)</span><span class="sxs-lookup"><span data-stu-id="1dd71-121">Querying XML Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/querying-xml-trees.md)
