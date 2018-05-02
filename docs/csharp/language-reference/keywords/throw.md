---
title: throw（C# 参考）
ms.date: 03/02/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- throw
- throw_CSharpKeyword
helpviewer_keywords:
- throw statement [C#]
- throw expression [C#]
- throw keyword [C#]
ms.assetid: 5ac4feef-4b1a-4c61-aeb4-61d549e5dd42
caps.latest.revision: 22
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 088a8e70c5aaaae6f833f12cad1052c30fbb6bfa
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="throw-c-reference"></a><span data-ttu-id="a3d41-102">throw（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="a3d41-102">throw (C# Reference)</span></span>
<span data-ttu-id="a3d41-103">发出程序执行期间出现异常的信号。</span><span class="sxs-lookup"><span data-stu-id="a3d41-103">Signals the occurrence of an exception during program execution.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a3d41-104">备注</span><span class="sxs-lookup"><span data-stu-id="a3d41-104">Remarks</span></span>

<span data-ttu-id="a3d41-105">`throw` 的语法为：</span><span class="sxs-lookup"><span data-stu-id="a3d41-105">The syntax of `throw` is:</span></span>

```csharp
throw [e]
```
<span data-ttu-id="a3d41-106">`e` 是一个派生自 <xref:System.Exception?displayProperty=nameWithType> 的类的实例。</span><span class="sxs-lookup"><span data-stu-id="a3d41-106">where `e` is an instance of a class derived from <xref:System.Exception?displayProperty=nameWithType>.</span></span> <span data-ttu-id="a3d41-107">下例使用 `throw` 语句在传递给名为 `GetNumber` 的方法的参数与内部数组的有效索引不对应时引发  <xref:System.IndexOutOfRangeException> 。</span><span class="sxs-lookup"><span data-stu-id="a3d41-107">The following example uses the `throw` statement to throw an <xref:System.IndexOutOfRangeException> if the argument passed to a method named `GetNumber` does not correspond to a valid index of an internal array.</span></span>

[!code-csharp[csrefKeyword#1](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#1)]  

<span data-ttu-id="a3d41-108">然后方法调用方使用 `try-catch` 或 `try-catch-finally` 块来处理引发的异常。</span><span class="sxs-lookup"><span data-stu-id="a3d41-108">Method callers then use a `try-catch` or `try-catch-finally` block to handle the thrown exception.</span></span> <span data-ttu-id="a3d41-109">下例处理由 `GetNumber` 方法引发的异常。</span><span class="sxs-lookup"><span data-stu-id="a3d41-109">The following example handles the exception thrown by the `GetNumber` method.</span></span>

[!code-csharp[csrefKeyword#2](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#2)]  

## <a name="re-throwing-an-exception"></a><span data-ttu-id="a3d41-110">重新引发异常</span><span class="sxs-lookup"><span data-stu-id="a3d41-110">Re-throwing an exception</span></span>

<span data-ttu-id="a3d41-111">`throw` 也可以用于 `catch` 块，以重新引发在 `catch` 块中处理的异常。</span><span class="sxs-lookup"><span data-stu-id="a3d41-111">`throw` can also be used in a `catch` block to re-throw an exception handled in a `catch` block.</span></span>  <span data-ttu-id="a3d41-112">在这种情况下，`throw` 不采用异常操作数。</span><span class="sxs-lookup"><span data-stu-id="a3d41-112">In this case, `throw` does not take an exception operand.</span></span> <span data-ttu-id="a3d41-113">当方法将参数从调用方传递给其他库方法时，这是最有用的，库方法引发的异常必须传递给调用方。</span><span class="sxs-lookup"><span data-stu-id="a3d41-113">It is most useful when a method passes on an argument from a caller to some other library method, and the library method throws an exception that must be passed on to the caller.</span></span> <span data-ttu-id="a3d41-114">例如，以下示例重新引发在尝试检索未初始化字符串的第一个字符时引发的 <xref:System.NullReferenceException>。</span><span class="sxs-lookup"><span data-stu-id="a3d41-114">For example, the following example re-throws an <xref:System.NullReferenceException> that is thrown when attempting to retrieve the first character of an uninitialized string.</span></span> 

[!code-csharp[csrefKeyword#3](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-3.cs#3)]  

> [!IMPORTANT]
> <span data-ttu-id="a3d41-115">还可以使用 `catch` 块中的 `throw e` 语法来实例化传递给调用方的新异常。</span><span class="sxs-lookup"><span data-stu-id="a3d41-115">You can also use the `throw e` syntax in a `catch` block to instantiate a new exception that you pass on to the caller.</span></span> <span data-ttu-id="a3d41-116">在这种情况下，将不会保留可从 <xref:System.Exception.StackTrace> 属性获得的原始异常的堆栈跟踪。</span><span class="sxs-lookup"><span data-stu-id="a3d41-116">In this case, the stack trace of the original exception, which is available from the <xref:System.Exception.StackTrace> property, is not preserved.</span></span>
 
## <a name="the-throw-expression"></a><span data-ttu-id="a3d41-117">`throw` 表达式</span><span class="sxs-lookup"><span data-stu-id="a3d41-117">The `throw` expression</span></span>

<span data-ttu-id="a3d41-118">从 C# 7.0 开始，`throw` 可以用作表达式和语句。</span><span class="sxs-lookup"><span data-stu-id="a3d41-118">Starting with C# 7.0, `throw` can be used as an expression as well as a statement.</span></span> <span data-ttu-id="a3d41-119">这允许在以前不支持的上下文中引发异常。</span><span class="sxs-lookup"><span data-stu-id="a3d41-119">This allows an exception to be thrown in contexts that were previously unsupported.</span></span> <span data-ttu-id="a3d41-120">这些方法包括：</span><span class="sxs-lookup"><span data-stu-id="a3d41-120">These include:</span></span>

- <span data-ttu-id="a3d41-121">[条件运算符](../operators/conditional-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="a3d41-121">[the conditional operator](../operators/conditional-operator.md).</span></span> <span data-ttu-id="a3d41-122">下例使用 `throw` 表达式在向方法传递空字符串数组时引发 <xref:System.ArgumentException>。</span><span class="sxs-lookup"><span data-stu-id="a3d41-122">The following example uses a `throw` expression to throw an <xref:System.ArgumentException> if a method is passed an empty string array.</span></span> <span data-ttu-id="a3d41-123">在 C# 7.0 之前，此逻辑将需要显示在 `if`/`else` 语句中。</span><span class="sxs-lookup"><span data-stu-id="a3d41-123">Before C# 7.0, this logic would need to appear in an `if`/`else` statement.</span></span>

   [!code-csharp[csrefKeyword#4](../../../../samples/snippets/csharp/language-reference/keywords/throw/conditional.cs#1)]  
  
- <span data-ttu-id="a3d41-124">[null 合并运算符](../operators/null-conditional-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="a3d41-124">[the null-coalescing operator](../operators/null-conditional-operator.md).</span></span> <span data-ttu-id="a3d41-125">在以下示例中，如果分配给 `Name` 属性的字符串为 `null`，则将 `throw` 表达式与 null 合并运算符结合使用以引发异常。</span><span class="sxs-lookup"><span data-stu-id="a3d41-125">In the following example, a `throw` expression is used with a null-coalescing operator to throw an exception if the string assigned to a `Name` property is `null`.</span></span>
 
   [!code-csharp[csrefKeyword#5](../../../../samples/snippets/csharp/language-reference/keywords/throw/coalescing.cs#1)]  
 
- <span data-ttu-id="a3d41-126">expression-bodied [lambda](../../lambda-expressions.md) 或方法。</span><span class="sxs-lookup"><span data-stu-id="a3d41-126">an expression-bodied [lambda](../../lambda-expressions.md) or method.</span></span> <span data-ttu-id="a3d41-127">下例说明了 expression-bodied 方法，由于不支持对 <xref:System.DateTime> 值的转换，该方法引发 <xref:System.InvalidCastException>。</span><span class="sxs-lookup"><span data-stu-id="a3d41-127">The following example illustrates an expression-bodied method that throws an <xref:System.InvalidCastException> because a conversion to a <xref:System.DateTime> value is not supported.</span></span>
 
   [!code-csharp[csrefKeyword#6](../../../../samples/snippets/csharp/language-reference/keywords/throw/exp-bodied.cs#1)]  
 
  
## <a name="c-language-specification"></a><span data-ttu-id="a3d41-128">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="a3d41-128">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a3d41-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="a3d41-129">See Also</span></span>  
 [<span data-ttu-id="a3d41-130">C# 参考</span><span class="sxs-lookup"><span data-stu-id="a3d41-130">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="a3d41-131">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="a3d41-131">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="a3d41-132">try-catch</span><span class="sxs-lookup"><span data-stu-id="a3d41-132">try-catch</span></span>](../../../csharp/language-reference/keywords/try-catch.md)  
 [<span data-ttu-id="a3d41-133">C++ 中的 try、catch 和 throw 语句</span><span class="sxs-lookup"><span data-stu-id="a3d41-133">The try, catch, and throw Statements in C++</span></span>](../../../csharp/language-reference/keywords/try-catch.md)  
 [<span data-ttu-id="a3d41-134">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="a3d41-134">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="a3d41-135">异常处理语句</span><span class="sxs-lookup"><span data-stu-id="a3d41-135">Exception Handling Statements</span></span>](../../../csharp/language-reference/keywords/exception-handling-statements.md)  
 [<span data-ttu-id="a3d41-136">如何显式引发异常</span><span class="sxs-lookup"><span data-stu-id="a3d41-136">How to: Explicitly Throw Exceptions</span></span>](../../../standard/exceptions/how-to-explicitly-throw-exceptions.md)
