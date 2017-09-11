---
title: "Visual Basic 限制 |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- limits
- limitations, Visual Basic
- limitations
- limits, Visual Basic code
- Visual Basic code, limitations
ms.assetid: cf1646b7-5d24-48c6-9616-bda8a4849d91
caps.latest.revision: 14
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
ms.openlocfilehash: a3bd551ade2f0c55cd943cfbd353b09dfede4063
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="visual-basic-limitations"></a><span data-ttu-id="f2d69-102">Visual Basic 限制</span><span class="sxs-lookup"><span data-stu-id="f2d69-102">Visual Basic Limitations</span></span>
<span data-ttu-id="f2d69-103">早期版本的[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]强制在代码中，如变量名的长度的边界中的模块和模块的大小允许的变量的数目。</span><span class="sxs-lookup"><span data-stu-id="f2d69-103">Earlier versions of [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] enforced boundaries in code, such as the length of variable names, the number of variables allowed in modules, and module size.</span></span> <span data-ttu-id="f2d69-104">在[!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)]，已放宽这些限制，使您可以编写和安排您的代码以更大的自由度。</span><span class="sxs-lookup"><span data-stu-id="f2d69-104">In [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)], these restrictions have been relaxed, giving you greater freedom in writing and arranging your code.</span></span>  
  
 <span data-ttu-id="f2d69-105">所依赖的编译时的注意事项的更多地运行时内存比物理限制。</span><span class="sxs-lookup"><span data-stu-id="f2d69-105">Physical limits are dependent more on run-time memory than on compile-time considerations.</span></span> <span data-ttu-id="f2d69-106">如果你使用比较明智的做法的编程方法，并将大型应用程序划分为多个类和模块，则没有遇到内部的可能性很小[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]限制。</span><span class="sxs-lookup"><span data-stu-id="f2d69-106">If you use prudent programming practices, and divide large applications into multiple classes and modules, then there is very little chance of encountering an internal [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] limitation.</span></span>  
  
 <span data-ttu-id="f2d69-107">以下是在极端情况下可能会遇到一些限制︰</span><span class="sxs-lookup"><span data-stu-id="f2d69-107">The following are some limitations that you might encounter in extreme cases:</span></span>  
  
-   <span data-ttu-id="f2d69-108">**名称长度。**</span><span class="sxs-lookup"><span data-stu-id="f2d69-108">**Name Length.**</span></span> <span data-ttu-id="f2d69-109">没有最大为每个已声明的编程元素的名称的字符数。</span><span class="sxs-lookup"><span data-stu-id="f2d69-109">There is a maximum number of characters for the name of every declared programming element.</span></span> <span data-ttu-id="f2d69-110">如果元素名称进行限定，此最大值适用于整个限定字符串。</span><span class="sxs-lookup"><span data-stu-id="f2d69-110">This maximum applies to an entire qualification string if the element name is qualified.</span></span> <span data-ttu-id="f2d69-111">请参阅[声明的元素名称](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)。</span><span class="sxs-lookup"><span data-stu-id="f2d69-111">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
-   <span data-ttu-id="f2d69-112">**行长度。**</span><span class="sxs-lookup"><span data-stu-id="f2d69-112">**Line Length.**</span></span> <span data-ttu-id="f2d69-113">则最多 65535 中的字符代码的源代码在物理行。</span><span class="sxs-lookup"><span data-stu-id="f2d69-113">There is a maximum of 65535 characters in a physical line of source code.</span></span> <span data-ttu-id="f2d69-114">可以使用行继续符的情况下更长的逻辑的源代码行。</span><span class="sxs-lookup"><span data-stu-id="f2d69-114">The logical source code line can be longer if you use line continuation characters.</span></span> <span data-ttu-id="f2d69-115">请参阅[如何︰ 拆分和合并代码中的语句](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)。</span><span class="sxs-lookup"><span data-stu-id="f2d69-115">See [How to: Break and Combine Statements in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).</span></span>  
  
-   <span data-ttu-id="f2d69-116">**数组维度。**</span><span class="sxs-lookup"><span data-stu-id="f2d69-116">**Array Dimensions.**</span></span> <span data-ttu-id="f2d69-117">有可以声明为数组的维数的最大数目。</span><span class="sxs-lookup"><span data-stu-id="f2d69-117">There is a maximum number of dimensions you can declare for an array.</span></span> <span data-ttu-id="f2d69-118">这就限制了多少个索引可用于指定数组元素。</span><span class="sxs-lookup"><span data-stu-id="f2d69-118">This limits how many indexes you can use to specify an array element.</span></span> <span data-ttu-id="f2d69-119">请参阅[数组在 Visual Basic 中的维度](../../../visual-basic/programming-guide/language-features/arrays/array-dimensions.md)。</span><span class="sxs-lookup"><span data-stu-id="f2d69-119">See [Array Dimensions in Visual Basic](../../../visual-basic/programming-guide/language-features/arrays/array-dimensions.md).</span></span>  
  
-   <span data-ttu-id="f2d69-120">**字符串长度。**</span><span class="sxs-lookup"><span data-stu-id="f2d69-120">**String Length.**</span></span> <span data-ttu-id="f2d69-121">有可以存储在单个字符串中的 Unicode 字符的最大数目。</span><span class="sxs-lookup"><span data-stu-id="f2d69-121">There is a maximum number of Unicode characters you can store in a single string.</span></span> <span data-ttu-id="f2d69-122">请参阅[字符串数据类型](../../../visual-basic/language-reference/data-types/string-data-type.md)。</span><span class="sxs-lookup"><span data-stu-id="f2d69-122">See [String Data Type](../../../visual-basic/language-reference/data-types/string-data-type.md).</span></span>  
  
-   <span data-ttu-id="f2d69-123">**环境字符串的长度。**</span><span class="sxs-lookup"><span data-stu-id="f2d69-123">**Environment String Length.**</span></span> <span data-ttu-id="f2d69-124">没有为 32768 个字符作为命令行参数使用任何环境字符串的最大值。</span><span class="sxs-lookup"><span data-stu-id="f2d69-124">There is a maximum of 32768 characters for any environment string used as a command-line argument.</span></span> <span data-ttu-id="f2d69-125">这是在所有平台上的限制。</span><span class="sxs-lookup"><span data-stu-id="f2d69-125">This is a limitation on all platforms.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2d69-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f2d69-126">See Also</span></span>  
 <span data-ttu-id="f2d69-127">[程序结构和代码约定](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md) </span><span class="sxs-lookup"><span data-stu-id="f2d69-127">[Program Structure and Code Conventions](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md) </span></span>  
<span data-ttu-id="f2d69-128"> [Visual Basic 命名约定](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)</span><span class="sxs-lookup"><span data-stu-id="f2d69-128"> [Visual Basic Naming Conventions](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)</span></span>
