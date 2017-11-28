---
title: "#<a name=\"if-c-reference\"></a>if（C# 参考）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: '#if'
helpviewer_keywords: '#if directive [C#]'
ms.assetid: 48cabbff-ca82-491f-a56a-eeccd528c7c2
caps.latest.revision: "17"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: e4e3b79f64f5190d48d7248726ecdf031ad685e6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="if-c-reference"></a><span data-ttu-id="bc03a-102">#if（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="bc03a-102">#if (C# Reference)</span></span>
<span data-ttu-id="bc03a-103">如果 C# 编译器遇到 `#if` 指令，最终是 [#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md) 指令，仅当定义指定的符号时，它才编译这些指令之间的代码。</span><span class="sxs-lookup"><span data-stu-id="bc03a-103">When the C# compiler encounters an `#if` directive, followed eventually by an [#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md) directive, it will compile the code between the directives only if the specified symbol is defined.</span></span>  <span data-ttu-id="bc03a-104">与 C 和 C++ 不同的是，不能将数字的值分配给一个符号；C# 中的 #if 语句是一个布尔值，并仅测试是否定义该符号。</span><span class="sxs-lookup"><span data-stu-id="bc03a-104">Unlike C and C++, you cannot assign a numeric value to a symbol; the #if statement in C# is Boolean and only tests whether the symbol has been defined or not.</span></span> <span data-ttu-id="bc03a-105">例如，</span><span class="sxs-lookup"><span data-stu-id="bc03a-105">For example,</span></span>  
  
```csharp
#define DEBUG  
// ...  
#if DEBUG  
    Console.WriteLine("Debug version");  
#endif  
```  
  
 <span data-ttu-id="bc03a-106">仅可以使用运算符 [==](../../../csharp/language-reference/operators/equality-comparison-operator.md)（相等）、[!=](../../../csharp/language-reference/operators/not-equal-operator.md)（不相等）测试 [true](../../../csharp/language-reference/keywords/true.md) 或 [false](../../../csharp/language-reference/keywords/false.md)。</span><span class="sxs-lookup"><span data-stu-id="bc03a-106">You can use the operators [==](../../../csharp/language-reference/operators/equality-comparison-operator.md) (equality), [!=](../../../csharp/language-reference/operators/not-equal-operator.md) (inequality) only to test for [true](../../../csharp/language-reference/keywords/true.md) or [false](../../../csharp/language-reference/keywords/false.md) .</span></span> <span data-ttu-id="bc03a-107">True 表示定义该符号。</span><span class="sxs-lookup"><span data-stu-id="bc03a-107">True means the symbol is defined.</span></span> <span data-ttu-id="bc03a-108">语句 `#if DEBUG` 具有与 `#if (DEBUG == true)` 相同的含义。</span><span class="sxs-lookup"><span data-stu-id="bc03a-108">The statement `#if DEBUG` has the same meaning as `#if (DEBUG == true)`.</span></span> <span data-ttu-id="bc03a-109">可以使用运算符 [&&](../../../csharp/language-reference/operators/conditional-and-operator.md) (and)、[&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md) (or) 和 [!](../../../csharp/language-reference/operators/logical-negation-operator.md)</span><span class="sxs-lookup"><span data-stu-id="bc03a-109">You can use the operators [&&](../../../csharp/language-reference/operators/conditional-and-operator.md) (and), [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md) (or), and [!](../../../csharp/language-reference/operators/logical-negation-operator.md)</span></span> <span data-ttu-id="bc03a-110">(not) 评估是否已经定义了多个符号。</span><span class="sxs-lookup"><span data-stu-id="bc03a-110">(not) to evaluate whether multiple symbols have been defined.</span></span> <span data-ttu-id="bc03a-111">还可以用括号对符号和运算符进行分组。</span><span class="sxs-lookup"><span data-stu-id="bc03a-111">You can also group symbols and operators with parentheses.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bc03a-112">备注</span><span class="sxs-lookup"><span data-stu-id="bc03a-112">Remarks</span></span>  
 <span data-ttu-id="bc03a-113">`#if` 以及 [#else](../../../csharp/language-reference/preprocessor-directives/preprocessor-else.md)、[#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md)、[#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md)、[#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md) 和 [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md) 指令，允许基于是否存在一个或多个符号包括或排除代码。</span><span class="sxs-lookup"><span data-stu-id="bc03a-113">`#if`, along with the [#else](../../../csharp/language-reference/preprocessor-directives/preprocessor-else.md), [#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md), [#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md), [#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md), and [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md) directives, lets you include or exclude code based on the existence of one or more symbols.</span></span> <span data-ttu-id="bc03a-114">这在编译调试版本的代码或编译特定配置的代码时会很有用。</span><span class="sxs-lookup"><span data-stu-id="bc03a-114">This can be useful when compiling code for a debug build or when compiling for a specific configuration.</span></span>  
  
 <span data-ttu-id="bc03a-115">以 `#if` 指令开头的条件指令必须以 `#endif` 指令显式终止。</span><span class="sxs-lookup"><span data-stu-id="bc03a-115">A conditional directive beginning with a `#if` directive must explicitly be terminated with a `#endif` directive.</span></span>  
  
 <span data-ttu-id="bc03a-116">`#define` 允许你定义一个符号，这样一来，通过将该符号用作传递给 `#if` 指令的表达式，该表达式的计算结果为 `true`。</span><span class="sxs-lookup"><span data-stu-id="bc03a-116">`#define` lets you define a symbol, such that, by using the symbol as the expression passed to the `#if` directive, the expression will evaluate to `true`.</span></span>  
  
 <span data-ttu-id="bc03a-117">还可以通过 [/define](../../../csharp/language-reference/compiler-options/define-compiler-option.md) 编译器选项来定义符号。</span><span class="sxs-lookup"><span data-stu-id="bc03a-117">You can also define a symbol with the [/define](../../../csharp/language-reference/compiler-options/define-compiler-option.md) compiler option.</span></span> <span data-ttu-id="bc03a-118">可以通过 [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md) 取消定义符号。</span><span class="sxs-lookup"><span data-stu-id="bc03a-118">You can undefine a symbol with [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md).</span></span>  
  
 <span data-ttu-id="bc03a-119">使用 `/define` 或 `#define` 定义的符号与具有相同名称的变量不冲突。</span><span class="sxs-lookup"><span data-stu-id="bc03a-119">A symbol that you define with `/define` or with `#define` does not conflict with a variable of the same name.</span></span> <span data-ttu-id="bc03a-120">也就是说，变量名称不应传递给预处理器指令，且符号仅能由预处理器指令评估。</span><span class="sxs-lookup"><span data-stu-id="bc03a-120">That is, a variable name should not be passed to a preprocessor directive and a symbol can only be evaluated by a preprocessor directive.</span></span>  
  
 <span data-ttu-id="bc03a-121">使用 `#define` 创建的符号的作用域是在其中定义它的文件。</span><span class="sxs-lookup"><span data-stu-id="bc03a-121">The scope of a symbol created with `#define` is the file in which it was defined.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bc03a-122">示例</span><span class="sxs-lookup"><span data-stu-id="bc03a-122">Example</span></span>  
  
```csharp
// preprocessor_if.cs  
#define DEBUG
#define MYTEST  
using System;  
public class MyClass   
{  
    static void Main()   
    {  
#if (DEBUG && !MYTEST)  
        Console.WriteLine("DEBUG is defined");  
#elif (!DEBUG && MYTEST)  
        Console.WriteLine("MYTEST is defined");  
#elif (DEBUG && MYTEST)  
        Console.WriteLine("DEBUG and MYTEST are defined");  
#else  
        Console.WriteLine("DEBUG and MYTEST are not defined");  
#endif  
    }  
}  
```  
  
 <span data-ttu-id="bc03a-123">**DEBUG 和 MYTEST 已定义**</span><span class="sxs-lookup"><span data-stu-id="bc03a-123">**DEBUG and MYTEST are defined**</span></span>  
## <a name="see-also"></a><span data-ttu-id="bc03a-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bc03a-124">See Also</span></span>  
 [<span data-ttu-id="bc03a-125">C# 参考</span><span class="sxs-lookup"><span data-stu-id="bc03a-125">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="bc03a-126">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="bc03a-126">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="bc03a-127">C# 预处理器指令</span><span class="sxs-lookup"><span data-stu-id="bc03a-127">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)
