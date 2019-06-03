---
title: throw - C# 参考
ms.custom: seodec18
ms.date: 03/02/2015
f1_keywords:
- throw
- throw_CSharpKeyword
helpviewer_keywords:
- throw statement [C#]
- throw expression [C#]
- throw keyword [C#]
ms.assetid: 5ac4feef-4b1a-4c61-aeb4-61d549e5dd42
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c4536a5caa789712227bfd637d65cfc4c22adf80
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/31/2019
ms.locfileid: "66422688"
---
# <a name="throw-c-reference"></a><span data-ttu-id="a3135-102">throw（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="a3135-102">throw (C# Reference)</span></span>

<span data-ttu-id="a3135-103">发出程序执行期间出现异常的信号。</span><span class="sxs-lookup"><span data-stu-id="a3135-103">Signals the occurrence of an exception during program execution.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a3135-104">备注</span><span class="sxs-lookup"><span data-stu-id="a3135-104">Remarks</span></span>

<span data-ttu-id="a3135-105">`throw` 的语法为：</span><span class="sxs-lookup"><span data-stu-id="a3135-105">The syntax of `throw` is:</span></span>

```csharp
throw [e]
```

<span data-ttu-id="a3135-106">`e` 是一个派生自 <xref:System.Exception?displayProperty=nameWithType> 的类的实例。</span><span class="sxs-lookup"><span data-stu-id="a3135-106">where `e` is an instance of a class derived from <xref:System.Exception?displayProperty=nameWithType>.</span></span> <span data-ttu-id="a3135-107">下例使用 `throw` 语句在传递给名为 `GetNumber` 的方法的参数与内部数组的有效索引不对应时引发  <xref:System.IndexOutOfRangeException> 。</span><span class="sxs-lookup"><span data-stu-id="a3135-107">The following example uses the `throw` statement to throw an <xref:System.IndexOutOfRangeException> if the argument passed to a method named `GetNumber` does not correspond to a valid index of an internal array.</span></span>

[!code-csharp[csrefKeyword#1](~/samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#1)]  

<span data-ttu-id="a3135-108">然后方法调用方使用 `try-catch` 或 `try-catch-finally` 块来处理引发的异常。</span><span class="sxs-lookup"><span data-stu-id="a3135-108">Method callers then use a `try-catch` or `try-catch-finally` block to handle the thrown exception.</span></span> <span data-ttu-id="a3135-109">下例处理由 `GetNumber` 方法引发的异常。</span><span class="sxs-lookup"><span data-stu-id="a3135-109">The following example handles the exception thrown by the `GetNumber` method.</span></span>

[!code-csharp[csrefKeyword#2](~/samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#2)]  

## <a name="re-throwing-an-exception"></a><span data-ttu-id="a3135-110">重新引发异常</span><span class="sxs-lookup"><span data-stu-id="a3135-110">Re-throwing an exception</span></span>

<span data-ttu-id="a3135-111">`throw` 也可以用于 `catch` 块，以重新引发在 `catch` 块中处理的异常。</span><span class="sxs-lookup"><span data-stu-id="a3135-111">`throw` can also be used in a `catch` block to re-throw an exception handled in a `catch` block.</span></span>  <span data-ttu-id="a3135-112">在这种情况下，`throw` 不采用异常操作数。</span><span class="sxs-lookup"><span data-stu-id="a3135-112">In this case, `throw` does not take an exception operand.</span></span> <span data-ttu-id="a3135-113">当方法将参数从调用方传递给其他库方法时，这是最有用的，库方法引发的异常必须传递给调用方。</span><span class="sxs-lookup"><span data-stu-id="a3135-113">It is most useful when a method passes on an argument from a caller to some other library method, and the library method throws an exception that must be passed on to the caller.</span></span> <span data-ttu-id="a3135-114">例如，以下示例重新引发在尝试检索未初始化字符串的第一个字符时引发的 <xref:System.NullReferenceException>。</span><span class="sxs-lookup"><span data-stu-id="a3135-114">For example, the following example re-throws an <xref:System.NullReferenceException> that is thrown when attempting to retrieve the first character of an uninitialized string.</span></span>

[!code-csharp[csrefKeyword#3](~/samples/snippets/csharp/language-reference/keywords/throw/throw-3.cs#3)]  

> [!IMPORTANT]
> <span data-ttu-id="a3135-115">还可以使用 `catch` 块中的 `throw e` 语法来实例化传递给调用方的新异常。</span><span class="sxs-lookup"><span data-stu-id="a3135-115">You can also use the `throw e` syntax in a `catch` block to instantiate a new exception that you pass on to the caller.</span></span> <span data-ttu-id="a3135-116">在这种情况下，将不会保留可从 <xref:System.Exception.StackTrace> 属性获得的原始异常的堆栈跟踪。</span><span class="sxs-lookup"><span data-stu-id="a3135-116">In this case, the stack trace of the original exception, which is available from the <xref:System.Exception.StackTrace> property, is not preserved.</span></span>

## <a name="the-throw-expression"></a><span data-ttu-id="a3135-117">`throw` 表达式</span><span class="sxs-lookup"><span data-stu-id="a3135-117">The `throw` expression</span></span>

<span data-ttu-id="a3135-118">从 C# 7.0 开始，`throw` 可以用作表达式和语句。</span><span class="sxs-lookup"><span data-stu-id="a3135-118">Starting with C# 7.0, `throw` can be used as an expression as well as a statement.</span></span> <span data-ttu-id="a3135-119">这允许在以前不支持的上下文中引发异常。</span><span class="sxs-lookup"><span data-stu-id="a3135-119">This allows an exception to be thrown in contexts that were previously unsupported.</span></span> <span data-ttu-id="a3135-120">这些方法包括：</span><span class="sxs-lookup"><span data-stu-id="a3135-120">These include:</span></span>

- <span data-ttu-id="a3135-121">[条件运算符](../operators/conditional-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="a3135-121">[the conditional operator](../operators/conditional-operator.md).</span></span> <span data-ttu-id="a3135-122">下例使用 `throw` 表达式在向方法传递空字符串数组时引发 <xref:System.ArgumentException>。</span><span class="sxs-lookup"><span data-stu-id="a3135-122">The following example uses a `throw` expression to throw an <xref:System.ArgumentException> if a method is passed an empty string array.</span></span> <span data-ttu-id="a3135-123">在 C# 7.0 之前，此逻辑将需要显示在 `if`/`else` 语句中。</span><span class="sxs-lookup"><span data-stu-id="a3135-123">Before C# 7.0, this logic would need to appear in an `if`/`else` statement.</span></span>

   [!code-csharp[csrefKeyword#4](~/samples/snippets/csharp/language-reference/keywords/throw/conditional.cs#1)]  
  
- <span data-ttu-id="a3135-124">[null 合并运算符](../operators/null-coalescing-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="a3135-124">[the null-coalescing operator](../operators/null-coalescing-operator.md).</span></span> <span data-ttu-id="a3135-125">在以下示例中，如果分配给 `Name` 属性的字符串为 `null`，则将 `throw` 表达式与 null 合并运算符结合使用以引发异常。</span><span class="sxs-lookup"><span data-stu-id="a3135-125">In the following example, a `throw` expression is used with a null-coalescing operator to throw an exception if the string assigned to a `Name` property is `null`.</span></span>

   [!code-csharp[csrefKeyword#5](~/samples/snippets/csharp/language-reference/keywords/throw/coalescing.cs#1)]  

- <span data-ttu-id="a3135-126">expression-bodied [lambda](../../programming-guide/statements-expressions-operators/lambda-expressions.md) 或方法。</span><span class="sxs-lookup"><span data-stu-id="a3135-126">an expression-bodied [lambda](../../programming-guide/statements-expressions-operators/lambda-expressions.md) or method.</span></span> <span data-ttu-id="a3135-127">下例说明了 expression-bodied 方法，由于不支持对 <xref:System.DateTime> 值的转换，该方法引发 <xref:System.InvalidCastException>。</span><span class="sxs-lookup"><span data-stu-id="a3135-127">The following example illustrates an expression-bodied method that throws an <xref:System.InvalidCastException> because a conversion to a <xref:System.DateTime> value is not supported.</span></span>

   [!code-csharp[csrefKeyword#6](~/samples/snippets/csharp/language-reference/keywords/throw/exp-bodied.cs#1)]  

## <a name="c-language-specification"></a><span data-ttu-id="a3135-128">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="a3135-128">C# language specification</span></span>  

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a3135-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="a3135-129">See also</span></span>

- [<span data-ttu-id="a3135-130">C# 参考</span><span class="sxs-lookup"><span data-stu-id="a3135-130">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="a3135-131">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="a3135-131">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="a3135-132">try-catch</span><span class="sxs-lookup"><span data-stu-id="a3135-132">try-catch</span></span>](try-catch.md)
- [<span data-ttu-id="a3135-133">C++ 中的 try、catch 和 throw 语句</span><span class="sxs-lookup"><span data-stu-id="a3135-133">The try, catch, and throw Statements in C++</span></span>](try-catch.md)
- [<span data-ttu-id="a3135-134">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="a3135-134">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="a3135-135">如何：显式抛出异常</span><span class="sxs-lookup"><span data-stu-id="a3135-135">How to: Explicitly Throw Exceptions</span></span>](../../../standard/exceptions/how-to-explicitly-throw-exceptions.md)
