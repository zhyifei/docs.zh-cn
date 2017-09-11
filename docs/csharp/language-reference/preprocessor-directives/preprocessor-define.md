---
title: "#<a name=\"define-c-reference\"></a>define（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '#define'
dev_langs:
- CSharp
helpviewer_keywords:
- '#define directive [C#]'
ms.assetid: 23638b8f-779c-450e-b600-d55682de7d01
caps.latest.revision: 22
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
ms.openlocfilehash: 8ace15f79480c9aeb0fcb4c7d46c207d4904cef0
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="define-c-reference"></a><span data-ttu-id="9de57-102">#define（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="9de57-102">#define (C# Reference)</span></span>
<span data-ttu-id="9de57-103">使用 `#define` 来定义符号。</span><span class="sxs-lookup"><span data-stu-id="9de57-103">You use `#define` to define a symbol.</span></span> <span data-ttu-id="9de57-104">将符号用作传递给 [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) 指令的表达式时，该表达式的计算结果为 `true`，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="9de57-104">When you use the symbol as the expression that's passed to the [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) directive, the expression will evaluate to `true`, as the following example shows:</span></span>  
  
 <span data-ttu-id="9de57-105">`#`  `define`   `DEBUG`</span><span class="sxs-lookup"><span data-stu-id="9de57-105">`#`  `define`   `DEBUG`</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9de57-106">备注</span><span class="sxs-lookup"><span data-stu-id="9de57-106">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9de57-107">`#define` 指令不能用于声明常量值，这与 C 和 C++ 中的通常做法一样。</span><span class="sxs-lookup"><span data-stu-id="9de57-107">The `#define` directive cannot be used to declare constant values as is typically done in C and C++.</span></span> <span data-ttu-id="9de57-108">C# 中的常量最好定义为类或结构的静态成员。</span><span class="sxs-lookup"><span data-stu-id="9de57-108">Constants in C# are best defined as static members of a class or struct.</span></span> <span data-ttu-id="9de57-109">如果具有多个此类常量，请考虑创建一个单独的“常量”类来容纳它们。</span><span class="sxs-lookup"><span data-stu-id="9de57-109">If you have several such constants, consider creating a separate "Constants" class to hold them.</span></span>  
  
 <span data-ttu-id="9de57-110">符号可用于指定编译的条件。</span><span class="sxs-lookup"><span data-stu-id="9de57-110">Symbols can be used to specify conditions for compilation.</span></span> <span data-ttu-id="9de57-111">可通过 [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) 或 [#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md) 测试符号。</span><span class="sxs-lookup"><span data-stu-id="9de57-111">You can test for the symbol with either [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) or [#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md).</span></span> <span data-ttu-id="9de57-112">还可以使用 `conditional` 属性来执行条件编译。</span><span class="sxs-lookup"><span data-stu-id="9de57-112">You can also use the `conditional` attribute to perform conditional compilation.</span></span>  
  
 <span data-ttu-id="9de57-113">可以定义一个符号，但不能向符号分配值。</span><span class="sxs-lookup"><span data-stu-id="9de57-113">You can define a symbol, but you cannot assign a value to a symbol.</span></span> <span data-ttu-id="9de57-114">文件中必须先出现 `#define` 指令，才能使用并非同时也是预处理器指令的任何指示。</span><span class="sxs-lookup"><span data-stu-id="9de57-114">The `#define` directive must appear in the file before you use any instructions that aren't also preprocessor directives.</span></span>  
  
 <span data-ttu-id="9de57-115">还可以通过 [/define](../../../csharp/language-reference/compiler-options/define-compiler-option.md) 编译器选项来定义符号。</span><span class="sxs-lookup"><span data-stu-id="9de57-115">You can also define a symbol with the [/define](../../../csharp/language-reference/compiler-options/define-compiler-option.md) compiler option.</span></span> <span data-ttu-id="9de57-116">可以通过 [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md) 取消定义符号。</span><span class="sxs-lookup"><span data-stu-id="9de57-116">You can undefine a symbol with [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md).</span></span>  
  
 <span data-ttu-id="9de57-117">使用 `/define` 或 `#define` 定义的符号与具有相同名称的变量不冲突。</span><span class="sxs-lookup"><span data-stu-id="9de57-117">A symbol that you define with `/define` or with `#define` does not conflict with a variable of the same name.</span></span> <span data-ttu-id="9de57-118">也就是说，变量名称不应传递给预处理器指令，且符号仅能由预处理器指令评估。</span><span class="sxs-lookup"><span data-stu-id="9de57-118">That is, a variable name should not be passed to a preprocessor directive and a symbol can only be evaluated by a preprocessor directive.</span></span>  
  
 <span data-ttu-id="9de57-119">使用 `#define` 创建的符号的作用域是在其中定义该符号的文件。</span><span class="sxs-lookup"><span data-stu-id="9de57-119">The scope of a symbol that was created by using `#define` is the file in which the symbol was defined.</span></span>  
  
 <span data-ttu-id="9de57-120">如以下示例所示，必须将 `#define` 指令放在文件顶部。</span><span class="sxs-lookup"><span data-stu-id="9de57-120">As the following example shows, you must put `#define` directives at the top of the file.</span></span>  
  
```csharp  
#define DEBUG  
//#define TRACE  
#undef TRACE  
  
using System;  
  
public class TestDefine  
{  
    static void Main()  
    {  
#if (DEBUG)  
        Console.WriteLine("Debugging is enabled.");  
#endif  
  
#if (TRACE)  
     Console.WriteLine("Tracing is enabled.");  
#endif  
    }  
}  
// Output:  
// Debugging is enabled.  
```  
  
 <span data-ttu-id="9de57-121">有关如何取消对符号进行定义的示例，请参阅 [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md)。</span><span class="sxs-lookup"><span data-stu-id="9de57-121">For an example of how to undefine a symbol, see [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9de57-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9de57-122">See Also</span></span>  
 <span data-ttu-id="9de57-123">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="9de57-123">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="9de57-124">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="9de57-124">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="9de57-125">[C# 预处理器指令](../../../csharp/language-reference/preprocessor-directives/index.md) </span><span class="sxs-lookup"><span data-stu-id="9de57-125">[C# Preprocessor Directives](../../../csharp/language-reference/preprocessor-directives/index.md) </span></span>  
 <span data-ttu-id="9de57-126">[const](../../../csharp/language-reference/keywords/const.md) </span><span class="sxs-lookup"><span data-stu-id="9de57-126">[const](../../../csharp/language-reference/keywords/const.md) </span></span>  
 <span data-ttu-id="9de57-127">[如何：使用跟踪和调试进行条件编译](../../../framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md) </span><span class="sxs-lookup"><span data-stu-id="9de57-127">[How to: Compile Conditionally with Trace and Debug](../../../framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md) </span></span>  
 <span data-ttu-id="9de57-128">[#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md) </span><span class="sxs-lookup"><span data-stu-id="9de57-128">[#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md) </span></span>  
 [<span data-ttu-id="9de57-129">#if</span><span class="sxs-lookup"><span data-stu-id="9de57-129">#if</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md)

