---
title: '#if 预处理器指令 - C# 参考'
ms.custom: seodec18
ms.date: 10/27/2019
f1_keywords:
- '#if'
helpviewer_keywords:
- '#if directive [C#]'
ms.assetid: 48cabbff-ca82-491f-a56a-eeccd528c7c2
ms.openlocfilehash: 561a628c60888a8d4f3c50c8413784e1ed210599
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2019
ms.locfileid: "73035996"
---
# <a name="if-c-reference"></a><span data-ttu-id="b4d13-102">#if（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="b4d13-102">#if (C# Reference)</span></span>

<span data-ttu-id="b4d13-103">如果 C# 编译器遇到 `#if` 指令，最终是 [#endif](preprocessor-endif.md) 指令，则仅当定义指定的符号时，它才编译这些指令之间的代码。</span><span class="sxs-lookup"><span data-stu-id="b4d13-103">When the C# compiler encounters an `#if` directive, followed eventually by an [#endif](preprocessor-endif.md) directive, it compiles the code between the directives only if the specified symbol is defined.</span></span> <span data-ttu-id="b4d13-104">与 C 和 C++ 不同，你不能为符号分配数字值。</span><span class="sxs-lookup"><span data-stu-id="b4d13-104">Unlike C and C++, you cannot assign a numeric value to a symbol.</span></span> <span data-ttu-id="b4d13-105">C# 中的 #if 语句是布尔值，且仅测试是否已定义该符号。</span><span class="sxs-lookup"><span data-stu-id="b4d13-105">The #if statement in C# is Boolean and only tests whether the symbol has been defined or not.</span></span> <span data-ttu-id="b4d13-106">例如:</span><span class="sxs-lookup"><span data-stu-id="b4d13-106">For example:</span></span>

```csharp
#if DEBUG
    Console.WriteLine("Debug version");
#endif
```

<span data-ttu-id="b4d13-107">仅可以使用运算符 [==](../operators/equality-operators.md#equality-operator-)（相等）和 [!=](../operators/equality-operators.md#inequality-operator-)（不相等）测试 [true](../keywords/true-literal.md) 或 [false](../keywords/false-literal.md)。</span><span class="sxs-lookup"><span data-stu-id="b4d13-107">You can use the operators [==](../operators/equality-operators.md#equality-operator-) (equality) and [!=](../operators/equality-operators.md#inequality-operator-) (inequality) only to test for [true](../keywords/true-literal.md) or [false](../keywords/false-literal.md).</span></span> <span data-ttu-id="b4d13-108">True 表示定义该符号。</span><span class="sxs-lookup"><span data-stu-id="b4d13-108">True means the symbol is defined.</span></span> <span data-ttu-id="b4d13-109">语句 `#if DEBUG` 具有与 `#if (DEBUG == true)` 相同的含义。</span><span class="sxs-lookup"><span data-stu-id="b4d13-109">The statement `#if DEBUG` has the same meaning as `#if (DEBUG == true)`.</span></span> <span data-ttu-id="b4d13-110">可以使用运算符 [&&](../operators/boolean-logical-operators.md#conditional-logical-and-operator-) (and)、[&#124;&#124;](../operators/boolean-logical-operators.md#conditional-logical-or-operator-) (or) 和 [!](../operators/boolean-logical-operators.md#logical-negation-operator-)</span><span class="sxs-lookup"><span data-stu-id="b4d13-110">You can use the operators [&&](../operators/boolean-logical-operators.md#conditional-logical-and-operator-) (and), [&#124;&#124;](../operators/boolean-logical-operators.md#conditional-logical-or-operator-) (or), and [!](../operators/boolean-logical-operators.md#logical-negation-operator-)</span></span> <span data-ttu-id="b4d13-111">(not) 评估是否已经定义了多个符号。</span><span class="sxs-lookup"><span data-stu-id="b4d13-111">(not) to evaluate whether multiple symbols have been defined.</span></span> <span data-ttu-id="b4d13-112">还可以用括号对符号和运算符进行分组。</span><span class="sxs-lookup"><span data-stu-id="b4d13-112">You can also group symbols and operators with parentheses.</span></span>

## <a name="remarks"></a><span data-ttu-id="b4d13-113">备注</span><span class="sxs-lookup"><span data-stu-id="b4d13-113">Remarks</span></span>

<span data-ttu-id="b4d13-114">`#if` 以及 [#else](preprocessor-else.md)、[#elif](preprocessor-elif.md)、[#endif](preprocessor-endif.md)、[#define](preprocessor-define.md) 和 [#undef](preprocessor-undef.md) 指令，允许基于是否存在一个或多个符号包括或排除代码。</span><span class="sxs-lookup"><span data-stu-id="b4d13-114">`#if`, along with the [#else](preprocessor-else.md), [#elif](preprocessor-elif.md), [#endif](preprocessor-endif.md), [#define](preprocessor-define.md), and [#undef](preprocessor-undef.md) directives, lets you include or exclude code based on the existence of one or more symbols.</span></span> <span data-ttu-id="b4d13-115">这在编译调试版本的代码或编译特定配置的代码时会很有用。</span><span class="sxs-lookup"><span data-stu-id="b4d13-115">This can be useful when compiling code for a debug build or when compiling for a specific configuration.</span></span>

<span data-ttu-id="b4d13-116">以 `#if` 指令开头的条件指令必须以 `#endif` 指令显式终止。</span><span class="sxs-lookup"><span data-stu-id="b4d13-116">A conditional directive beginning with a `#if` directive must explicitly be terminated with a `#endif` directive.</span></span>

<span data-ttu-id="b4d13-117">`#define` 允许你定义一个符号。</span><span class="sxs-lookup"><span data-stu-id="b4d13-117">`#define` lets you define a symbol.</span></span> <span data-ttu-id="b4d13-118">然后通过将该符号用作传递给 `#if` 指令的表达式，该表达式的计算结果为 `true`。</span><span class="sxs-lookup"><span data-stu-id="b4d13-118">By then using the symbol as the expression passed to the `#if` directive, the expression evaluates to `true`.</span></span>

<span data-ttu-id="b4d13-119">还可以通过 [-define](../compiler-options/define-compiler-option.md) 编译器选项来定义符号。</span><span class="sxs-lookup"><span data-stu-id="b4d13-119">You can also define a symbol with the [-define](../compiler-options/define-compiler-option.md) compiler option.</span></span> <span data-ttu-id="b4d13-120">可以通过 [#undef](preprocessor-undef.md) 取消定义符号。</span><span class="sxs-lookup"><span data-stu-id="b4d13-120">You can undefine a symbol with [#undef](preprocessor-undef.md).</span></span>

<span data-ttu-id="b4d13-121">使用 `-define` 或 `#define` 定义的符号与具有相同名称的变量不冲突。</span><span class="sxs-lookup"><span data-stu-id="b4d13-121">A symbol that you define with `-define` or with `#define` doesn't conflict with a variable of the same name.</span></span> <span data-ttu-id="b4d13-122">也就是说，变量名称不应传递给预处理器指令，且符号仅能由预处理器指令评估。</span><span class="sxs-lookup"><span data-stu-id="b4d13-122">That is, a variable name should not be passed to a preprocessor directive, and a symbol can only be evaluated by a preprocessor directive.</span></span>

<span data-ttu-id="b4d13-123">使用 `#define` 创建的符号的作用域是在其中定义它的文件。</span><span class="sxs-lookup"><span data-stu-id="b4d13-123">The scope of a symbol created with `#define` is the file in which it was defined.</span></span>

<span data-ttu-id="b4d13-124">此外，生成系统还会感知表示 SDK 样式项目中不同[目标框架](../../../standard/frameworks.md)的预定义预处理器符号。</span><span class="sxs-lookup"><span data-stu-id="b4d13-124">The build system is also aware of predefined preprocessor symbols representing different [target frameworks](../../../standard/frameworks.md) in SDK-style projects.</span></span> <span data-ttu-id="b4d13-125">在创建可以面向多个.NET 实现或版本的应用程序时，这些符号会很有用。</span><span class="sxs-lookup"><span data-stu-id="b4d13-125">They're useful when creating applications that can target more than one .NET implementation or version.</span></span>

[!INCLUDE [Preprocessor symbols](~/includes/preprocessor-symbols.md)]

> [!NOTE]
> <span data-ttu-id="b4d13-126">对于传统的 .NET Framework 项目，必须通过项目的属性页面在 Visual Studio 中为不同目标框架手动配置条件编译符号。</span><span class="sxs-lookup"><span data-stu-id="b4d13-126">For traditional .NET Framework projects, you have to manually configure the conditional compilation symbols for the different target frameworks in Visual Studio via the project's properties pages.</span></span>

<span data-ttu-id="b4d13-127">其他预定义符号包括 DEBUG 和 TRACE 常量。</span><span class="sxs-lookup"><span data-stu-id="b4d13-127">Other predefined symbols include the DEBUG and TRACE constants.</span></span> <span data-ttu-id="b4d13-128">你可以使用 `#define` 替代项目的值集。</span><span class="sxs-lookup"><span data-stu-id="b4d13-128">You can override the values set for the project using `#define`.</span></span> <span data-ttu-id="b4d13-129">例如，会根据生成配置属性（“调试”或者“发布”模式）自动设置 DEBUG 符号。</span><span class="sxs-lookup"><span data-stu-id="b4d13-129">The DEBUG symbol, for example, is automatically set depending on your build configuration properties ("Debug" or "Release" mode).</span></span>

## <a name="examples"></a><span data-ttu-id="b4d13-130">示例</span><span class="sxs-lookup"><span data-stu-id="b4d13-130">Examples</span></span>

<span data-ttu-id="b4d13-131">下例显示如何在文件上定义 MYTEST 符号，然后测试 MYTEST 和 DEBUG 符号的值。</span><span class="sxs-lookup"><span data-stu-id="b4d13-131">The following example shows you how to define a MYTEST symbol on a file and then test the values of the MYTEST and DEBUG symbols.</span></span> <span data-ttu-id="b4d13-132">此示例的输出取决于是在“调试”还是“发布”配置模式下生成项目。</span><span class="sxs-lookup"><span data-stu-id="b4d13-132">The output of this example depends on whether you built the project on Debug or Release configuration mode.</span></span>

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

<span data-ttu-id="b4d13-133">下例显示如何针对不同的目标框架进行测试，以便在可能时使用较新的 API：</span><span class="sxs-lookup"><span data-stu-id="b4d13-133">The following example shows you how to test for different target frameworks so you can use newer APIs when possible:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="b4d13-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="b4d13-134">See also</span></span>

- [<span data-ttu-id="b4d13-135">C# 参考</span><span class="sxs-lookup"><span data-stu-id="b4d13-135">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="b4d13-136">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="b4d13-136">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="b4d13-137">C# 预处理器指令</span><span class="sxs-lookup"><span data-stu-id="b4d13-137">C# Preprocessor Directives</span></span>](index.md)
- [<span data-ttu-id="b4d13-138">如何：使用跟踪和调试执行有条件编译</span><span class="sxs-lookup"><span data-stu-id="b4d13-138">How to: Compile Conditionally with Trace and Debug</span></span>](../../../framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md)
