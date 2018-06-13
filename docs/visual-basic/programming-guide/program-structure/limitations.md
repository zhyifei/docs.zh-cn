---
title: Visual Basic 限制
ms.date: 07/20/2015
helpviewer_keywords:
- limits
- limitations [Visual Basic]
- limitations
- limits, Visual Basic code
- Visual Basic code, limitations
ms.assetid: cf1646b7-5d24-48c6-9616-bda8a4849d91
ms.openlocfilehash: 57378c3aa18a5cc108c10e8654e55803f3cf9052
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649924"
---
# <a name="visual-basic-limitations"></a><span data-ttu-id="00da4-102">Visual Basic 限制</span><span class="sxs-lookup"><span data-stu-id="00da4-102">Visual Basic Limitations</span></span>
<span data-ttu-id="00da4-103">早期版本的 Visual Basic 强制执行在代码中，如的变量名，在模块和模块大小允许的变量数的长度的边界。</span><span class="sxs-lookup"><span data-stu-id="00da4-103">Earlier versions of Visual Basic enforced boundaries in code, such as the length of variable names, the number of variables allowed in modules, and module size.</span></span> <span data-ttu-id="00da4-104">在 Visual Basic.NET 中，这些限制都放宽了，为你提供更大的自由度中编写和排列你的代码。</span><span class="sxs-lookup"><span data-stu-id="00da4-104">In Visual Basic .NET, these restrictions have been relaxed, giving you greater freedom in writing and arranging your code.</span></span>  
  
 <span data-ttu-id="00da4-105">物理限制都依赖更上运行时内存比在编译时的注意事项。</span><span class="sxs-lookup"><span data-stu-id="00da4-105">Physical limits are dependent more on run-time memory than on compile-time considerations.</span></span> <span data-ttu-id="00da4-106">如果你使用较为审慎编程方法，并将大型应用程序中划分为多个类和模块，则遇到了内部的 Visual Basic 限制的可能性很小。</span><span class="sxs-lookup"><span data-stu-id="00da4-106">If you use prudent programming practices, and divide large applications into multiple classes and modules, then there is very little chance of encountering an internal Visual Basic limitation.</span></span>  
  
 <span data-ttu-id="00da4-107">以下是在极端情况下可能会遇到一些限制：</span><span class="sxs-lookup"><span data-stu-id="00da4-107">The following are some limitations that you might encounter in extreme cases:</span></span>  
  
-   <span data-ttu-id="00da4-108">**名称长度。**</span><span class="sxs-lookup"><span data-stu-id="00da4-108">**Name Length.**</span></span> <span data-ttu-id="00da4-109">没有最大为每个声明的编程元素的名称的字符数。</span><span class="sxs-lookup"><span data-stu-id="00da4-109">There is a maximum number of characters for the name of every declared programming element.</span></span> <span data-ttu-id="00da4-110">如果元素名称进行限定，此最大值适用于整个限定字符串。</span><span class="sxs-lookup"><span data-stu-id="00da4-110">This maximum applies to an entire qualification string if the element name is qualified.</span></span> <span data-ttu-id="00da4-111">请参阅[声明的元素名称](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)。</span><span class="sxs-lookup"><span data-stu-id="00da4-111">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
-   <span data-ttu-id="00da4-112">**行长度。**</span><span class="sxs-lookup"><span data-stu-id="00da4-112">**Line Length.**</span></span> <span data-ttu-id="00da4-113">没有最多 65535 中的字符代码的源代码在物理行。</span><span class="sxs-lookup"><span data-stu-id="00da4-113">There is a maximum of 65535 characters in a physical line of source code.</span></span> <span data-ttu-id="00da4-114">如果使用行继续符，则可以能采用逻辑源代码行。</span><span class="sxs-lookup"><span data-stu-id="00da4-114">The logical source code line can be longer if you use line continuation characters.</span></span> <span data-ttu-id="00da4-115">请参阅[如何： 拆分和合并代码中的语句](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)。</span><span class="sxs-lookup"><span data-stu-id="00da4-115">See [How to: Break and Combine Statements in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).</span></span>  
  
-   <span data-ttu-id="00da4-116">**数组维度。**</span><span class="sxs-lookup"><span data-stu-id="00da4-116">**Array Dimensions.**</span></span> <span data-ttu-id="00da4-117">没有可以声明数组的维度的最大数量。</span><span class="sxs-lookup"><span data-stu-id="00da4-117">There is a maximum number of dimensions you can declare for an array.</span></span> <span data-ttu-id="00da4-118">这就限制了多少可用于指定数组元素的索引。</span><span class="sxs-lookup"><span data-stu-id="00da4-118">This limits how many indexes you can use to specify an array element.</span></span> <span data-ttu-id="00da4-119">请参阅[数组在 Visual Basic 中的维度](../../../visual-basic/programming-guide/language-features/arrays/array-dimensions.md)。</span><span class="sxs-lookup"><span data-stu-id="00da4-119">See [Array Dimensions in Visual Basic](../../../visual-basic/programming-guide/language-features/arrays/array-dimensions.md).</span></span>  
  
-   <span data-ttu-id="00da4-120">**字符串长度。**</span><span class="sxs-lookup"><span data-stu-id="00da4-120">**String Length.**</span></span> <span data-ttu-id="00da4-121">没有最大可以存储在单个字符串中的 Unicode 字符数。</span><span class="sxs-lookup"><span data-stu-id="00da4-121">There is a maximum number of Unicode characters you can store in a single string.</span></span> <span data-ttu-id="00da4-122">请参阅[字符串数据类型](../../../visual-basic/language-reference/data-types/string-data-type.md)。</span><span class="sxs-lookup"><span data-stu-id="00da4-122">See [String Data Type](../../../visual-basic/language-reference/data-types/string-data-type.md).</span></span>  
  
-   <span data-ttu-id="00da4-123">**环境字符串长度。**</span><span class="sxs-lookup"><span data-stu-id="00da4-123">**Environment String Length.**</span></span> <span data-ttu-id="00da4-124">没有为 32768 个字符作为命令行参数使用任何环境字符串的最大值。</span><span class="sxs-lookup"><span data-stu-id="00da4-124">There is a maximum of 32768 characters for any environment string used as a command-line argument.</span></span> <span data-ttu-id="00da4-125">这是在所有平台上的限制。</span><span class="sxs-lookup"><span data-stu-id="00da4-125">This is a limitation on all platforms.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00da4-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="00da4-126">See Also</span></span>  
 [<span data-ttu-id="00da4-127">程序结构和代码约定</span><span class="sxs-lookup"><span data-stu-id="00da4-127">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)  
 [<span data-ttu-id="00da4-128">Visual Basic 命名约定</span><span class="sxs-lookup"><span data-stu-id="00da4-128">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
