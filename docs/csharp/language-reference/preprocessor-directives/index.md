---
title: "C# 预处理器指令"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- cs.preprocessor
dev_langs:
- CSharp
helpviewer_keywords:
- preprocessor directives [C#]
- keywords [C#], preprocessor directives
ms.assetid: f2406090-b244-4f7e-ab72-3698fefed724
caps.latest.revision: 13
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 91bb2daefbc677fad8a3dd93b37aac996234d48c
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="c-preprocessor-directives"></a><span data-ttu-id="f66c1-102">C# 预处理器指令</span><span class="sxs-lookup"><span data-stu-id="f66c1-102">C# Preprocessor Directives</span></span>
<span data-ttu-id="f66c1-103">本节包含以下 C# 预处理器指令的相关信息。</span><span class="sxs-lookup"><span data-stu-id="f66c1-103">This section contains information about the following C# preprocessor directives.</span></span>  
  
 [<span data-ttu-id="f66c1-104">#if</span><span class="sxs-lookup"><span data-stu-id="f66c1-104">#if</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md)  
  
 [<span data-ttu-id="f66c1-105">#else</span><span class="sxs-lookup"><span data-stu-id="f66c1-105">#else</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-else.md)  
  
 [<span data-ttu-id="f66c1-106">#elif</span><span class="sxs-lookup"><span data-stu-id="f66c1-106">#elif</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md)  
  
 [<span data-ttu-id="f66c1-107">#endif</span><span class="sxs-lookup"><span data-stu-id="f66c1-107">#endif</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md)  
  
 [<span data-ttu-id="f66c1-108">#define</span><span class="sxs-lookup"><span data-stu-id="f66c1-108">#define</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md)  
  
 [<span data-ttu-id="f66c1-109">#undef</span><span class="sxs-lookup"><span data-stu-id="f66c1-109">#undef</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md)  
  
 [<span data-ttu-id="f66c1-110">#warning</span><span class="sxs-lookup"><span data-stu-id="f66c1-110">#warning</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-warning.md)  
  
 [<span data-ttu-id="f66c1-111">#error</span><span class="sxs-lookup"><span data-stu-id="f66c1-111">#error</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-error.md)  
  
 [<span data-ttu-id="f66c1-112">#line</span><span class="sxs-lookup"><span data-stu-id="f66c1-112">#line</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-line.md)  
  
 [<span data-ttu-id="f66c1-113">#region</span><span class="sxs-lookup"><span data-stu-id="f66c1-113">#region</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-region.md)  
  
 [<span data-ttu-id="f66c1-114">#endregion</span><span class="sxs-lookup"><span data-stu-id="f66c1-114">#endregion</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-endregion.md)  
  
 [<span data-ttu-id="f66c1-115">#pragma</span><span class="sxs-lookup"><span data-stu-id="f66c1-115">#pragma</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma.md)  
  
 [<span data-ttu-id="f66c1-116">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="f66c1-116">#pragma warning</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md)  
  
 [<span data-ttu-id="f66c1-117">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="f66c1-117">#pragma checksum</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-checksum.md)  
  
 <span data-ttu-id="f66c1-118">请参阅各个主题了解更多信息和示例。</span><span class="sxs-lookup"><span data-stu-id="f66c1-118">See the individual topics for more information and examples.</span></span>  
  
 <span data-ttu-id="f66c1-119">尽管编译器没有单独的预处理器，但本节中所述的指令如同经过了预处理器的处理。</span><span class="sxs-lookup"><span data-stu-id="f66c1-119">Although the compiler does not have a separate preprocessor, the directives described in this section are processed as if there were one.</span></span> <span data-ttu-id="f66c1-120">这些指令用于帮助条件编译。</span><span class="sxs-lookup"><span data-stu-id="f66c1-120">They are used to help in conditional compilation.</span></span> <span data-ttu-id="f66c1-121">不同于 C 和 C++ 指令，不能使用这些指令来创建宏。</span><span class="sxs-lookup"><span data-stu-id="f66c1-121">Unlike C and C++ directives, you cannot use these directives to create macros.</span></span>  
  
 <span data-ttu-id="f66c1-122">预处理器指令必须是一行中唯一的说明。</span><span class="sxs-lookup"><span data-stu-id="f66c1-122">A preprocessor directive must be the only instruction on a line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f66c1-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f66c1-123">See Also</span></span>  
 <span data-ttu-id="f66c1-124">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="f66c1-124">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 [<span data-ttu-id="f66c1-125">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="f66c1-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)

