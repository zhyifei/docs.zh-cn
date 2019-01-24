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
ms.openlocfilehash: 0f356b52304110299ed0af9bbccd5d03893f31a9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54596353"
---
# <a name="visual-basic-limitations"></a><span data-ttu-id="08db7-102">Visual Basic 限制</span><span class="sxs-lookup"><span data-stu-id="08db7-102">Visual Basic Limitations</span></span>
<span data-ttu-id="08db7-103">早期版本的 Visual Basic 强制执行在代码中，如变量的名称，在模块和模块大小允许的变量数的长度的边界。</span><span class="sxs-lookup"><span data-stu-id="08db7-103">Earlier versions of Visual Basic enforced boundaries in code, such as the length of variable names, the number of variables allowed in modules, and module size.</span></span> <span data-ttu-id="08db7-104">在 Visual Basic.NET 中，这些限制已放宽，为您提供编写和安排你的代码以更大的自由度。</span><span class="sxs-lookup"><span data-stu-id="08db7-104">In Visual Basic .NET, these restrictions have been relaxed, giving you greater freedom in writing and arranging your code.</span></span>  
  
 <span data-ttu-id="08db7-105">都依赖在编译时的注意事项的更多运行时内存比物理限制。</span><span class="sxs-lookup"><span data-stu-id="08db7-105">Physical limits are dependent more on run-time memory than on compile-time considerations.</span></span> <span data-ttu-id="08db7-106">如果使用比较明智的做法的编程方法，并将大型应用程序划分为多个类和模块，则遇到了内部 Visual Basic 限制的可能性很小。</span><span class="sxs-lookup"><span data-stu-id="08db7-106">If you use prudent programming practices, and divide large applications into multiple classes and modules, then there is very little chance of encountering an internal Visual Basic limitation.</span></span>  
  
 <span data-ttu-id="08db7-107">以下是在极端情况下可能会遇到一些限制：</span><span class="sxs-lookup"><span data-stu-id="08db7-107">The following are some limitations that you might encounter in extreme cases:</span></span>  
  
-   <span data-ttu-id="08db7-108">**名称的长度。**</span><span class="sxs-lookup"><span data-stu-id="08db7-108">**Name Length.**</span></span> <span data-ttu-id="08db7-109">没有最大为每个声明的编程元素的名称的字符数。</span><span class="sxs-lookup"><span data-stu-id="08db7-109">There is a maximum number of characters for the name of every declared programming element.</span></span> <span data-ttu-id="08db7-110">如果元素名称进行限定，此最大值适用于整个限定字符串。</span><span class="sxs-lookup"><span data-stu-id="08db7-110">This maximum applies to an entire qualification string if the element name is qualified.</span></span> <span data-ttu-id="08db7-111">请参阅 [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)。</span><span class="sxs-lookup"><span data-stu-id="08db7-111">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
-   <span data-ttu-id="08db7-112">**行长度。**</span><span class="sxs-lookup"><span data-stu-id="08db7-112">**Line Length.**</span></span> <span data-ttu-id="08db7-113">没有源代码的物理行中的 65535 个字符的最大值。</span><span class="sxs-lookup"><span data-stu-id="08db7-113">There is a maximum of 65535 characters in a physical line of source code.</span></span> <span data-ttu-id="08db7-114">逻辑源的代码行可以是使用行继续符的情况下更长。</span><span class="sxs-lookup"><span data-stu-id="08db7-114">The logical source code line can be longer if you use line continuation characters.</span></span> <span data-ttu-id="08db7-115">请参阅[如何：拆分和合并代码中的语句](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)。</span><span class="sxs-lookup"><span data-stu-id="08db7-115">See [How to: Break and Combine Statements in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).</span></span>  
  
-   <span data-ttu-id="08db7-116">**数组维数。**</span><span class="sxs-lookup"><span data-stu-id="08db7-116">**Array Dimensions.**</span></span> <span data-ttu-id="08db7-117">没有可以声明为数组的维度的最大数目。</span><span class="sxs-lookup"><span data-stu-id="08db7-117">There is a maximum number of dimensions you can declare for an array.</span></span> <span data-ttu-id="08db7-118">这就限制了多少个索引可用于指定的数组元素。</span><span class="sxs-lookup"><span data-stu-id="08db7-118">This limits how many indexes you can use to specify an array element.</span></span> <span data-ttu-id="08db7-119">请参阅[数组中 Visual Basic 的维度](../../../visual-basic/programming-guide/language-features/arrays/array-dimensions.md)。</span><span class="sxs-lookup"><span data-stu-id="08db7-119">See [Array Dimensions in Visual Basic](../../../visual-basic/programming-guide/language-features/arrays/array-dimensions.md).</span></span>  
  
-   <span data-ttu-id="08db7-120">**字符串长度。**</span><span class="sxs-lookup"><span data-stu-id="08db7-120">**String Length.**</span></span> <span data-ttu-id="08db7-121">没有可以在单个字符串中存储的 Unicode 字符的最大数目。</span><span class="sxs-lookup"><span data-stu-id="08db7-121">There is a maximum number of Unicode characters you can store in a single string.</span></span> <span data-ttu-id="08db7-122">请参阅[字符串数据类型](../../../visual-basic/language-reference/data-types/string-data-type.md)。</span><span class="sxs-lookup"><span data-stu-id="08db7-122">See [String Data Type](../../../visual-basic/language-reference/data-types/string-data-type.md).</span></span>  
  
-   <span data-ttu-id="08db7-123">**环境字符串长度。**</span><span class="sxs-lookup"><span data-stu-id="08db7-123">**Environment String Length.**</span></span> <span data-ttu-id="08db7-124">没有 32768 个字符作为命令行参数使用任何环境字符串的最大值。</span><span class="sxs-lookup"><span data-stu-id="08db7-124">There is a maximum of 32768 characters for any environment string used as a command-line argument.</span></span> <span data-ttu-id="08db7-125">这是在所有平台上的限制。</span><span class="sxs-lookup"><span data-stu-id="08db7-125">This is a limitation on all platforms.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08db7-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="08db7-126">See also</span></span>
- [<span data-ttu-id="08db7-127">程序结构和代码约定</span><span class="sxs-lookup"><span data-stu-id="08db7-127">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [<span data-ttu-id="08db7-128">Visual Basic 命名约定</span><span class="sxs-lookup"><span data-stu-id="08db7-128">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
