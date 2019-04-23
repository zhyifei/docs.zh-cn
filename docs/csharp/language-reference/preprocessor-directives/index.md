---
title: C# 预处理器指令
ms.date: 07/20/2015
f1_keywords:
- cs.preprocessor
helpviewer_keywords:
- preprocessor directives [C#]
- keywords [C#], preprocessor directives
ms.assetid: f2406090-b244-4f7e-ab72-3698fefed724
ms.openlocfilehash: 54067777ed2e92eea263b17cce0d4cdf13ed731d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61689315"
---
# <a name="c-preprocessor-directives"></a><span data-ttu-id="8ca57-102">C# 预处理器指令</span><span class="sxs-lookup"><span data-stu-id="8ca57-102">C# preprocessor directives</span></span>
<span data-ttu-id="8ca57-103">本节介绍了以下 C# 预处理器指令：</span><span class="sxs-lookup"><span data-stu-id="8ca57-103">This section contains information about the following C# preprocessor directives:</span></span>

- [<span data-ttu-id="8ca57-104">#if</span><span class="sxs-lookup"><span data-stu-id="8ca57-104">#if</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md)
- [<span data-ttu-id="8ca57-105">#else</span><span class="sxs-lookup"><span data-stu-id="8ca57-105">#else</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-else.md)
- [<span data-ttu-id="8ca57-106">#elif</span><span class="sxs-lookup"><span data-stu-id="8ca57-106">#elif</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md)
- [<span data-ttu-id="8ca57-107">#endif</span><span class="sxs-lookup"><span data-stu-id="8ca57-107">#endif</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md)
- [<span data-ttu-id="8ca57-108">#define</span><span class="sxs-lookup"><span data-stu-id="8ca57-108">#define</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md)
- [<span data-ttu-id="8ca57-109">#undef</span><span class="sxs-lookup"><span data-stu-id="8ca57-109">#undef</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md)
- [<span data-ttu-id="8ca57-110">#warning</span><span class="sxs-lookup"><span data-stu-id="8ca57-110">#warning</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-warning.md)
- [<span data-ttu-id="8ca57-111">#error</span><span class="sxs-lookup"><span data-stu-id="8ca57-111">#error</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-error.md)
- [<span data-ttu-id="8ca57-112">#line</span><span class="sxs-lookup"><span data-stu-id="8ca57-112">#line</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-line.md)
- [<span data-ttu-id="8ca57-113">#region</span><span class="sxs-lookup"><span data-stu-id="8ca57-113">#region</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-region.md)
- [<span data-ttu-id="8ca57-114">#endregion</span><span class="sxs-lookup"><span data-stu-id="8ca57-114">#endregion</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-endregion.md)
- [<span data-ttu-id="8ca57-115">#pragma</span><span class="sxs-lookup"><span data-stu-id="8ca57-115">#pragma</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma.md)
- [<span data-ttu-id="8ca57-116">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="8ca57-116">#pragma warning</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md)
- [<span data-ttu-id="8ca57-117">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="8ca57-117">#pragma checksum</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-checksum.md)

<span data-ttu-id="8ca57-118">请参阅各个主题了解更多信息和示例。</span><span class="sxs-lookup"><span data-stu-id="8ca57-118">See the individual topics for more information and examples.</span></span>

<span data-ttu-id="8ca57-119">尽管编译器没有单独的预处理器，但本节中所述指令的处理方式与有预处理器时一样。</span><span class="sxs-lookup"><span data-stu-id="8ca57-119">Although the compiler doesn't have a separate preprocessor, the directives described in this section are processed as if there were one.</span></span> <span data-ttu-id="8ca57-120">这些指令用于帮助条件编译。</span><span class="sxs-lookup"><span data-stu-id="8ca57-120">They are used to help in conditional compilation.</span></span> <span data-ttu-id="8ca57-121">不同于 C 和 C++ 指令，不能使用这些指令来创建宏。</span><span class="sxs-lookup"><span data-stu-id="8ca57-121">Unlike C and C++ directives, you cannot use these directives to create macros.</span></span>

<span data-ttu-id="8ca57-122">预处理器指令必须是一行中唯一的说明。</span><span class="sxs-lookup"><span data-stu-id="8ca57-122">A preprocessor directive must be the only instruction on a line.</span></span>

## <a name="see-also"></a><span data-ttu-id="8ca57-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="8ca57-123">See also</span></span>

- [<span data-ttu-id="8ca57-124">C# 参考</span><span class="sxs-lookup"><span data-stu-id="8ca57-124">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="8ca57-125">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="8ca57-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
