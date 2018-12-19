---
title: '#if 预处理器指令 - C# 参考'
ms.custom: seodec18
ms.date: 06/30/2018
f1_keywords:
- '#if'
helpviewer_keywords:
- '#if directive [C#]'
ms.assetid: 48cabbff-ca82-491f-a56a-eeccd528c7c2
ms.openlocfilehash: df1b26b0e06d4fff81627ec633ce97f9d6ca036f
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2018
ms.locfileid: "53239626"
---
# <a name="if-c-reference"></a><span data-ttu-id="60db9-102">#if（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="60db9-102">#if (C# Reference)</span></span>

<span data-ttu-id="60db9-103">如果 C# 编译器遇到 `#if` 指令，最终是 [#endif](preprocessor-endif.md) 指令，则仅当定义指定的符号时，它才编译这些指令之间的代码。</span><span class="sxs-lookup"><span data-stu-id="60db9-103">When the C# compiler encounters an `#if` directive, followed eventually by an [#endif](preprocessor-endif.md) directive, it compiles the code between the directives only if the specified symbol is defined.</span></span> <span data-ttu-id="60db9-104">与 C 和 C++ 不同，你不能为符号分配数字值。</span><span class="sxs-lookup"><span data-stu-id="60db9-104">Unlike C and C++, you cannot assign a numeric value to a symbol.</span></span> <span data-ttu-id="60db9-105">C# 中的 #if 语句是布尔值，且仅测试是否已定义该符号。</span><span class="sxs-lookup"><span data-stu-id="60db9-105">The #if statement in C# is Boolean and only tests whether the symbol has been defined or not.</span></span> <span data-ttu-id="60db9-106">例如:</span><span class="sxs-lookup"><span data-stu-id="60db9-106">For example:</span></span>

```csharp
#if DEBUG
    Console.WriteLine("Debug version");
#endif
```

<span data-ttu-id="60db9-107">仅可以使用运算符 [==](../operators/equality-comparison-operator.md)（相等）和 [!=](../operators/not-equal-operator.md)（不相等）测试 [true](../keywords/true.md) 或 [false](../keywords/false.md)。</span><span class="sxs-lookup"><span data-stu-id="60db9-107">You can use the operators [==](../operators/equality-comparison-operator.md) (equality) and [!=](../operators/not-equal-operator.md) (inequality) only to test for [true](../keywords/true.md) or [false](../keywords/false.md).</span></span> <span data-ttu-id="60db9-108">True 表示定义该符号。</span><span class="sxs-lookup"><span data-stu-id="60db9-108">True means the symbol is defined.</span></span> <span data-ttu-id="60db9-109">语句 `#if DEBUG` 具有与 `#if (DEBUG == true)` 相同的含义。</span><span class="sxs-lookup"><span data-stu-id="60db9-109">The statement `#if DEBUG` has the same meaning as `#if (DEBUG == true)`.</span></span> <span data-ttu-id="60db9-110">可以使用运算符 [&&](../operators/conditional-and-operator.md) (and)、[&#124;&#124;](../operators/conditional-or-operator.md) (or) 和 [!](../operators/logical-negation-operator.md)</span><span class="sxs-lookup"><span data-stu-id="60db9-110">You can use the operators [&&](../operators/conditional-and-operator.md) (and), [&#124;&#124;](../operators/conditional-or-operator.md) (or), and [!](../operators/logical-negation-operator.md)</span></span> <span data-ttu-id="60db9-111">(not) 评估是否已经定义了多个符号。</span><span class="sxs-lookup"><span data-stu-id="60db9-111">(not) to evaluate whether multiple symbols have been defined.</span></span> <span data-ttu-id="60db9-112">还可以用括号对符号和运算符进行分组。</span><span class="sxs-lookup"><span data-stu-id="60db9-112">You can also group symbols and operators with parentheses.</span></span>

## <a name="remarks"></a><span data-ttu-id="60db9-113">备注</span><span class="sxs-lookup"><span data-stu-id="60db9-113">Remarks</span></span>

<span data-ttu-id="60db9-114">`#if` 以及 [#else](preprocessor-else.md)、[#elif](preprocessor-elif.md)、[#endif](preprocessor-endif.md)、[#define](preprocessor-define.md) 和 [#undef](preprocessor-undef.md) 指令，允许基于是否存在一个或多个符号包括或排除代码。</span><span class="sxs-lookup"><span data-stu-id="60db9-114">`#if`, along with the [#else](preprocessor-else.md), [#elif](preprocessor-elif.md), [#endif](preprocessor-endif.md), [#define](preprocessor-define.md), and [#undef](preprocessor-undef.md) directives, lets you include or exclude code based on the existence of one or more symbols.</span></span> <span data-ttu-id="60db9-115">这在编译调试版本的代码或编译特定配置的代码时会很有用。</span><span class="sxs-lookup"><span data-stu-id="60db9-115">This can be useful when compiling code for a debug build or when compiling for a specific configuration.</span></span>

<span data-ttu-id="60db9-116">以 `#if` 指令开头的条件指令必须以 `#endif` 指令显式终止。</span><span class="sxs-lookup"><span data-stu-id="60db9-116">A conditional directive beginning with a `#if` directive must explicitly be terminated with a `#endif` directive.</span></span>

<span data-ttu-id="60db9-117">`#define` 允许你定义一个符号。</span><span class="sxs-lookup"><span data-stu-id="60db9-117">`#define` lets you define a symbol.</span></span> <span data-ttu-id="60db9-118">然后通过将该符号用作传递给 `#if` 指令的表达式，该表达式的计算结果为 `true`。</span><span class="sxs-lookup"><span data-stu-id="60db9-118">By then using the symbol as the expression passed to the `#if` directive, the expression evaluates to `true`.</span></span>

<span data-ttu-id="60db9-119">还可以通过 [-define](../compiler-options/define-compiler-option.md) 编译器选项来定义符号。</span><span class="sxs-lookup"><span data-stu-id="60db9-119">You can also define a symbol with the [-define](../compiler-options/define-compiler-option.md) compiler option.</span></span> <span data-ttu-id="60db9-120">可以通过 [#undef](preprocessor-undef.md) 取消定义符号。</span><span class="sxs-lookup"><span data-stu-id="60db9-120">You can undefine a symbol with [#undef](preprocessor-undef.md).</span></span>

<span data-ttu-id="60db9-121">使用 `-define` 或 `#define` 定义的符号与具有相同名称的变量不冲突。</span><span class="sxs-lookup"><span data-stu-id="60db9-121">A symbol that you define with `-define` or with `#define` doesn't conflict with a variable of the same name.</span></span> <span data-ttu-id="60db9-122">也就是说，变量名称不应传递给预处理器指令，且符号仅能由预处理器指令评估。</span><span class="sxs-lookup"><span data-stu-id="60db9-122">That is, a variable name should not be passed to a preprocessor directive, and a symbol can only be evaluated by a preprocessor directive.</span></span>

<span data-ttu-id="60db9-123">使用 `#define` 创建的符号的作用域是在其中定义它的文件。</span><span class="sxs-lookup"><span data-stu-id="60db9-123">The scope of a symbol created with `#define` is the file in which it was defined.</span></span>

<span data-ttu-id="60db9-124">此外，生成系统还会感知表示不同[目标框架](../../../standard/frameworks.md)的预定义预处理器符号。</span><span class="sxs-lookup"><span data-stu-id="60db9-124">The build system is also aware of predefined preprocessor symbols representing different [target frameworks](../../../standard/frameworks.md).</span></span> <span data-ttu-id="60db9-125">在创建可以面向多个.NET 实现或版本的应用程序时，这些符号会很有用。</span><span class="sxs-lookup"><span data-stu-id="60db9-125">They're useful when creating applications that can target more than one .NET implementation or version.</span></span>

[!INCLUDE [Preprocessor symbols](~/includes/preprocessor-symbols.md)]

<span data-ttu-id="60db9-126">其他预定义符号包括 DEBUG 和 TRACE 常量。</span><span class="sxs-lookup"><span data-stu-id="60db9-126">Other predefined symbols include the DEBUG and TRACE constants.</span></span> <span data-ttu-id="60db9-127">你可以使用 `#define` 替代项目的值集。</span><span class="sxs-lookup"><span data-stu-id="60db9-127">You can override the values set for the project using `#define`.</span></span> <span data-ttu-id="60db9-128">例如，会根据生成配置属性（“调试”或者“发布”模式）自动设置 DEBUG 符号。</span><span class="sxs-lookup"><span data-stu-id="60db9-128">The DEBUG symbol, for example, is automatically set depending on your build configuration properties ("Debug" or "Release" mode).</span></span>

## <a name="examples"></a><span data-ttu-id="60db9-129">示例</span><span class="sxs-lookup"><span data-stu-id="60db9-129">Examples</span></span>

<span data-ttu-id="60db9-130">下例显示如何在文件上定义 MYTEST 符号，然后测试 MYTEST 和 DEBUG 符号的值。</span><span class="sxs-lookup"><span data-stu-id="60db9-130">The following example shows you how to define a MYTEST symbol on a file and then test the values of the MYTEST and DEBUG symbols.</span></span> <span data-ttu-id="60db9-131">此示例的输出取决于是在“调试”还是“发布”配置模式下生成项目。</span><span class="sxs-lookup"><span data-stu-id="60db9-131">The output of this example depends on whether you built the project on Debug or Release configuration mode.</span></span>

```csharp
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

<span data-ttu-id="60db9-132">下例显示如何针对不同的目标框架进行测试，以便在可能时使用较新的 API：</span><span class="sxs-lookup"><span data-stu-id="60db9-132">The following example shows you how to test for different target frameworks so you can use newer APIs when possible:</span></span>

```csharp
public class MyClass
{
    static void Main()
    {
#if NET40
        WebClient _client = new WebClient();
#else
        HttpClient _client = new HttpClient();
#endif
    }
    //...
}
```

## <a name="see-also"></a><span data-ttu-id="60db9-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="60db9-133">See also</span></span>

- [<span data-ttu-id="60db9-134">C# 参考</span><span class="sxs-lookup"><span data-stu-id="60db9-134">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="60db9-135">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="60db9-135">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="60db9-136">C# 预处理器指令</span><span class="sxs-lookup"><span data-stu-id="60db9-136">C# Preprocessor Directives</span></span>](index.md)  
- <span data-ttu-id="60db9-137">[如何：使用跟踪和调试执行有条件编译](../../../framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md)。</span><span class="sxs-lookup"><span data-stu-id="60db9-137">[How to: Compile Conditionally with Trace and Debug](../../../framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md).</span></span>
