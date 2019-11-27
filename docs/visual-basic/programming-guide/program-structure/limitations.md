---
title: 限制
ms.date: 07/20/2015
helpviewer_keywords:
- limits
- limitations [Visual Basic]
- limitations
- limits, Visual Basic code
- Visual Basic code, limitations
ms.assetid: cf1646b7-5d24-48c6-9616-bda8a4849d91
ms.openlocfilehash: f7e19977a011565bb4b1536af5cab195f8a01017
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347368"
---
# <a name="visual-basic-limitations"></a><span data-ttu-id="8adfd-102">Visual Basic 限制</span><span class="sxs-lookup"><span data-stu-id="8adfd-102">Visual Basic Limitations</span></span>
<span data-ttu-id="8adfd-103">的早期版本 Visual Basic 在代码中强制实施边界，如变量名称长度、模块中允许的变量数和模块大小。</span><span class="sxs-lookup"><span data-stu-id="8adfd-103">Earlier versions of Visual Basic enforced boundaries in code, such as the length of variable names, the number of variables allowed in modules, and module size.</span></span> <span data-ttu-id="8adfd-104">在 Visual Basic .NET 中，这些限制已被宽松，使你可以更自由地编写和排列代码。</span><span class="sxs-lookup"><span data-stu-id="8adfd-104">In Visual Basic .NET, these restrictions have been relaxed, giving you greater freedom in writing and arranging your code.</span></span>  
  
 <span data-ttu-id="8adfd-105">物理限制在运行时内存上依赖于编译时注意事项。</span><span class="sxs-lookup"><span data-stu-id="8adfd-105">Physical limits are dependent more on run-time memory than on compile-time considerations.</span></span> <span data-ttu-id="8adfd-106">如果使用明智的编程做法，并将大型应用程序划分为多个类和模块，则可能会遇到内部 Visual Basic 限制。</span><span class="sxs-lookup"><span data-stu-id="8adfd-106">If you use prudent programming practices, and divide large applications into multiple classes and modules, then there is very little chance of encountering an internal Visual Basic limitation.</span></span>  
  
 <span data-ttu-id="8adfd-107">下面是在极端情况下可能遇到的一些限制：</span><span class="sxs-lookup"><span data-stu-id="8adfd-107">The following are some limitations that you might encounter in extreme cases:</span></span>  
  
- <span data-ttu-id="8adfd-108">**名称长度。**</span><span class="sxs-lookup"><span data-stu-id="8adfd-108">**Name Length.**</span></span> <span data-ttu-id="8adfd-109">每个声明的编程元素的名称中的字符数最多为个。</span><span class="sxs-lookup"><span data-stu-id="8adfd-109">There is a maximum number of characters for the name of every declared programming element.</span></span> <span data-ttu-id="8adfd-110">如果元素名称是限定的，则此最大值适用于整个限定字符串。</span><span class="sxs-lookup"><span data-stu-id="8adfd-110">This maximum applies to an entire qualification string if the element name is qualified.</span></span> <span data-ttu-id="8adfd-111">请参阅 [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)。</span><span class="sxs-lookup"><span data-stu-id="8adfd-111">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
- <span data-ttu-id="8adfd-112">**行长度。**</span><span class="sxs-lookup"><span data-stu-id="8adfd-112">**Line Length.**</span></span> <span data-ttu-id="8adfd-113">源代码的物理行中最多包含65535个字符。</span><span class="sxs-lookup"><span data-stu-id="8adfd-113">There is a maximum of 65535 characters in a physical line of source code.</span></span> <span data-ttu-id="8adfd-114">如果使用行继续符，则逻辑源代码行可能会更长。</span><span class="sxs-lookup"><span data-stu-id="8adfd-114">The logical source code line can be longer if you use line continuation characters.</span></span> <span data-ttu-id="8adfd-115">请参阅[如何：在代码中中断和组合语句](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)。</span><span class="sxs-lookup"><span data-stu-id="8adfd-115">See [How to: Break and Combine Statements in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).</span></span>  
  
- <span data-ttu-id="8adfd-116">**数组维度。**</span><span class="sxs-lookup"><span data-stu-id="8adfd-116">**Array Dimensions.**</span></span> <span data-ttu-id="8adfd-117">可以为数组声明的维数有最大值。</span><span class="sxs-lookup"><span data-stu-id="8adfd-117">There is a maximum number of dimensions you can declare for an array.</span></span> <span data-ttu-id="8adfd-118">这限制了可用于指定数组元素的索引数。</span><span class="sxs-lookup"><span data-stu-id="8adfd-118">This limits how many indexes you can use to specify an array element.</span></span> <span data-ttu-id="8adfd-119">请参阅[Visual Basic 中的数组维度](../../../visual-basic/programming-guide/language-features/arrays/array-dimensions.md)。</span><span class="sxs-lookup"><span data-stu-id="8adfd-119">See [Array Dimensions in Visual Basic](../../../visual-basic/programming-guide/language-features/arrays/array-dimensions.md).</span></span>  
  
- <span data-ttu-id="8adfd-120">**字符串长度。**</span><span class="sxs-lookup"><span data-stu-id="8adfd-120">**String Length.**</span></span> <span data-ttu-id="8adfd-121">在单个字符串中，可以存储的 Unicode 字符数最多为个。</span><span class="sxs-lookup"><span data-stu-id="8adfd-121">There is a maximum number of Unicode characters you can store in a single string.</span></span> <span data-ttu-id="8adfd-122">请参阅[String 数据类型](../../../visual-basic/language-reference/data-types/string-data-type.md)。</span><span class="sxs-lookup"><span data-stu-id="8adfd-122">See [String Data Type](../../../visual-basic/language-reference/data-types/string-data-type.md).</span></span>  
  
- <span data-ttu-id="8adfd-123">**环境字符串长度。**</span><span class="sxs-lookup"><span data-stu-id="8adfd-123">**Environment String Length.**</span></span> <span data-ttu-id="8adfd-124">对于用作命令行参数的任何环境字符串，最多可包含32768个字符。</span><span class="sxs-lookup"><span data-stu-id="8adfd-124">There is a maximum of 32768 characters for any environment string used as a command-line argument.</span></span> <span data-ttu-id="8adfd-125">这是对所有平台的限制。</span><span class="sxs-lookup"><span data-stu-id="8adfd-125">This is a limitation on all platforms.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8adfd-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8adfd-126">See also</span></span>

- [<span data-ttu-id="8adfd-127">程序结构和代码约定</span><span class="sxs-lookup"><span data-stu-id="8adfd-127">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [<span data-ttu-id="8adfd-128">Visual Basic 命名约定</span><span class="sxs-lookup"><span data-stu-id="8adfd-128">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
