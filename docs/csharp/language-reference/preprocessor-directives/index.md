---
title: C# 预处理器指令
ms.date: 07/20/2015
f1_keywords:
- cs.preprocessor
helpviewer_keywords:
- preprocessor directives [C#]
- keywords [C#], preprocessor directives
ms.assetid: f2406090-b244-4f7e-ab72-3698fefed724
ms.openlocfilehash: f63ba3e0bd89a88ad04b14c2f359a8cde65e8f12
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/19/2019
ms.locfileid: "69608597"
---
# <a name="c-preprocessor-directives"></a><span data-ttu-id="b9c84-102">C# 预处理器指令</span><span class="sxs-lookup"><span data-stu-id="b9c84-102">C# preprocessor directives</span></span>
<span data-ttu-id="b9c84-103">本节介绍了以下 C# 预处理器指令：</span><span class="sxs-lookup"><span data-stu-id="b9c84-103">This section contains information about the following C# preprocessor directives:</span></span>

- [<span data-ttu-id="b9c84-104">#if</span><span class="sxs-lookup"><span data-stu-id="b9c84-104">#if</span></span>](./preprocessor-if.md)
- [<span data-ttu-id="b9c84-105">#else</span><span class="sxs-lookup"><span data-stu-id="b9c84-105">#else</span></span>](./preprocessor-else.md)
- [<span data-ttu-id="b9c84-106">#elif</span><span class="sxs-lookup"><span data-stu-id="b9c84-106">#elif</span></span>](./preprocessor-elif.md)
- [<span data-ttu-id="b9c84-107">#endif</span><span class="sxs-lookup"><span data-stu-id="b9c84-107">#endif</span></span>](./preprocessor-endif.md)
- [<span data-ttu-id="b9c84-108">#define</span><span class="sxs-lookup"><span data-stu-id="b9c84-108">#define</span></span>](./preprocessor-define.md)
- [<span data-ttu-id="b9c84-109">#undef</span><span class="sxs-lookup"><span data-stu-id="b9c84-109">#undef</span></span>](./preprocessor-undef.md)
- [<span data-ttu-id="b9c84-110">#warning</span><span class="sxs-lookup"><span data-stu-id="b9c84-110">#warning</span></span>](./preprocessor-warning.md)
- [<span data-ttu-id="b9c84-111">#error</span><span class="sxs-lookup"><span data-stu-id="b9c84-111">#error</span></span>](./preprocessor-error.md)
- [<span data-ttu-id="b9c84-112">#line</span><span class="sxs-lookup"><span data-stu-id="b9c84-112">#line</span></span>](./preprocessor-line.md)
- [<span data-ttu-id="b9c84-113">#region</span><span class="sxs-lookup"><span data-stu-id="b9c84-113">#region</span></span>](./preprocessor-region.md)
- [<span data-ttu-id="b9c84-114">#endregion</span><span class="sxs-lookup"><span data-stu-id="b9c84-114">#endregion</span></span>](./preprocessor-endregion.md)
- [<span data-ttu-id="b9c84-115">#pragma</span><span class="sxs-lookup"><span data-stu-id="b9c84-115">#pragma</span></span>](./preprocessor-pragma.md)
- [<span data-ttu-id="b9c84-116">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="b9c84-116">#pragma warning</span></span>](./preprocessor-pragma-warning.md)
- [<span data-ttu-id="b9c84-117">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="b9c84-117">#pragma checksum</span></span>](./preprocessor-pragma-checksum.md)

<span data-ttu-id="b9c84-118">请参阅各个主题了解更多信息和示例。</span><span class="sxs-lookup"><span data-stu-id="b9c84-118">See the individual topics for more information and examples.</span></span>

<span data-ttu-id="b9c84-119">尽管编译器没有单独的预处理器，但本节中所述指令的处理方式与有预处理器时一样。</span><span class="sxs-lookup"><span data-stu-id="b9c84-119">Although the compiler doesn't have a separate preprocessor, the directives described in this section are processed as if there were one.</span></span> <span data-ttu-id="b9c84-120">这些指令用于帮助条件编译。</span><span class="sxs-lookup"><span data-stu-id="b9c84-120">They are used to help in conditional compilation.</span></span> <span data-ttu-id="b9c84-121">不同于 C 和 C++ 指令，不能使用这些指令来创建宏。</span><span class="sxs-lookup"><span data-stu-id="b9c84-121">Unlike C and C++ directives, you cannot use these directives to create macros.</span></span>

<span data-ttu-id="b9c84-122">预处理器指令必须是一行中唯一的说明。</span><span class="sxs-lookup"><span data-stu-id="b9c84-122">A preprocessor directive must be the only instruction on a line.</span></span>

## <a name="see-also"></a><span data-ttu-id="b9c84-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="b9c84-123">See also</span></span>

- [<span data-ttu-id="b9c84-124">C# 参考</span><span class="sxs-lookup"><span data-stu-id="b9c84-124">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="b9c84-125">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="b9c84-125">C# Programming Guide</span></span>](../../programming-guide/index.md)
