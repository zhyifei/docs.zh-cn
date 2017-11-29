---
title: "Visual Basic 限制"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- limits
- limitations [Visual Basic]
- limitations
- limits, Visual Basic code
- Visual Basic code, limitations
ms.assetid: cf1646b7-5d24-48c6-9616-bda8a4849d91
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 97a2e162b9f1a673fbe805a5d2ef1421cd423a4f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="visual-basic-limitations"></a><span data-ttu-id="e75dc-102">Visual Basic 限制</span><span class="sxs-lookup"><span data-stu-id="e75dc-102">Visual Basic Limitations</span></span>
<span data-ttu-id="e75dc-103">早期版本的[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]强制在代码中，如变量名的长度的边界中模块和模块大小允许的变量数目。</span><span class="sxs-lookup"><span data-stu-id="e75dc-103">Earlier versions of [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] enforced boundaries in code, such as the length of variable names, the number of variables allowed in modules, and module size.</span></span> <span data-ttu-id="e75dc-104">在 Visual Basic.NET 中，这些限制都放宽了，为你提供更大的自由度中编写和排列你的代码。</span><span class="sxs-lookup"><span data-stu-id="e75dc-104">In Visual Basic .NET, these restrictions have been relaxed, giving you greater freedom in writing and arranging your code.</span></span>  
  
 <span data-ttu-id="e75dc-105">物理限制都依赖更上运行时内存比在编译时的注意事项。</span><span class="sxs-lookup"><span data-stu-id="e75dc-105">Physical limits are dependent more on run-time memory than on compile-time considerations.</span></span> <span data-ttu-id="e75dc-106">如果你使用较为审慎编程方法，并将大型应用程序中划分为多个类和模块，则很少会遇到内部[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]限制。</span><span class="sxs-lookup"><span data-stu-id="e75dc-106">If you use prudent programming practices, and divide large applications into multiple classes and modules, then there is very little chance of encountering an internal [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] limitation.</span></span>  
  
 <span data-ttu-id="e75dc-107">以下是在极端情况下可能会遇到一些限制：</span><span class="sxs-lookup"><span data-stu-id="e75dc-107">The following are some limitations that you might encounter in extreme cases:</span></span>  
  
-   <span data-ttu-id="e75dc-108">**名称长度。**</span><span class="sxs-lookup"><span data-stu-id="e75dc-108">**Name Length.**</span></span> <span data-ttu-id="e75dc-109">没有最大为每个声明的编程元素的名称的字符数。</span><span class="sxs-lookup"><span data-stu-id="e75dc-109">There is a maximum number of characters for the name of every declared programming element.</span></span> <span data-ttu-id="e75dc-110">如果元素名称进行限定，此最大值适用于整个限定字符串。</span><span class="sxs-lookup"><span data-stu-id="e75dc-110">This maximum applies to an entire qualification string if the element name is qualified.</span></span> <span data-ttu-id="e75dc-111">请参阅[声明的元素名称](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)。</span><span class="sxs-lookup"><span data-stu-id="e75dc-111">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
-   <span data-ttu-id="e75dc-112">**行长度。**</span><span class="sxs-lookup"><span data-stu-id="e75dc-112">**Line Length.**</span></span> <span data-ttu-id="e75dc-113">没有最多 65535 中的字符代码的源代码在物理行。</span><span class="sxs-lookup"><span data-stu-id="e75dc-113">There is a maximum of 65535 characters in a physical line of source code.</span></span> <span data-ttu-id="e75dc-114">如果使用行继续符，则可以能采用逻辑源代码行。</span><span class="sxs-lookup"><span data-stu-id="e75dc-114">The logical source code line can be longer if you use line continuation characters.</span></span> <span data-ttu-id="e75dc-115">请参阅[如何： 拆分和合并代码中的语句](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)。</span><span class="sxs-lookup"><span data-stu-id="e75dc-115">See [How to: Break and Combine Statements in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).</span></span>  
  
-   <span data-ttu-id="e75dc-116">**数组维度。**</span><span class="sxs-lookup"><span data-stu-id="e75dc-116">**Array Dimensions.**</span></span> <span data-ttu-id="e75dc-117">没有可以声明数组的维度的最大数量。</span><span class="sxs-lookup"><span data-stu-id="e75dc-117">There is a maximum number of dimensions you can declare for an array.</span></span> <span data-ttu-id="e75dc-118">这就限制了多少可用于指定数组元素的索引。</span><span class="sxs-lookup"><span data-stu-id="e75dc-118">This limits how many indexes you can use to specify an array element.</span></span> <span data-ttu-id="e75dc-119">请参阅[数组在 Visual Basic 中的维度](../../../visual-basic/programming-guide/language-features/arrays/array-dimensions.md)。</span><span class="sxs-lookup"><span data-stu-id="e75dc-119">See [Array Dimensions in Visual Basic](../../../visual-basic/programming-guide/language-features/arrays/array-dimensions.md).</span></span>  
  
-   <span data-ttu-id="e75dc-120">**字符串长度。**</span><span class="sxs-lookup"><span data-stu-id="e75dc-120">**String Length.**</span></span> <span data-ttu-id="e75dc-121">没有最大可以存储在单个字符串中的 Unicode 字符数。</span><span class="sxs-lookup"><span data-stu-id="e75dc-121">There is a maximum number of Unicode characters you can store in a single string.</span></span> <span data-ttu-id="e75dc-122">请参阅[字符串数据类型](../../../visual-basic/language-reference/data-types/string-data-type.md)。</span><span class="sxs-lookup"><span data-stu-id="e75dc-122">See [String Data Type](../../../visual-basic/language-reference/data-types/string-data-type.md).</span></span>  
  
-   <span data-ttu-id="e75dc-123">**环境字符串长度。**</span><span class="sxs-lookup"><span data-stu-id="e75dc-123">**Environment String Length.**</span></span> <span data-ttu-id="e75dc-124">没有为 32768 个字符作为命令行参数使用任何环境字符串的最大值。</span><span class="sxs-lookup"><span data-stu-id="e75dc-124">There is a maximum of 32768 characters for any environment string used as a command-line argument.</span></span> <span data-ttu-id="e75dc-125">这是在所有平台上的限制。</span><span class="sxs-lookup"><span data-stu-id="e75dc-125">This is a limitation on all platforms.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e75dc-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e75dc-126">See Also</span></span>  
 [<span data-ttu-id="e75dc-127">程序结构和代码约定</span><span class="sxs-lookup"><span data-stu-id="e75dc-127">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)  
 [<span data-ttu-id="e75dc-128">Visual Basic 命名约定</span><span class="sxs-lookup"><span data-stu-id="e75dc-128">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
