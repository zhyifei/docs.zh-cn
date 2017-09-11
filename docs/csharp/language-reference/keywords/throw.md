---
title: "throw（C# 参考）"
ms.date: 2015-03-02
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- throw
- throw_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- throw statement [C#]
- throw expression [C#]
- throw keyword [C#]
ms.assetid: 5ac4feef-4b1a-4c61-aeb4-61d549e5dd42
caps.latest.revision: 22
author: rpetrusha
ms.author: ronpet
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
ms.openlocfilehash: 955f6d87614e0b452ace162e79e34aec9decad54
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="throw-c-reference"></a><span data-ttu-id="2a4c0-102">throw（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="2a4c0-102">throw (C# Reference)</span></span>
<span data-ttu-id="2a4c0-103">发出程序执行期间出现异常的信号。</span><span class="sxs-lookup"><span data-stu-id="2a4c0-103">Signals the occurrence of an exception during program execution.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2a4c0-104">备注</span><span class="sxs-lookup"><span data-stu-id="2a4c0-104">Remarks</span></span>

<span data-ttu-id="2a4c0-105">`throw` 的语法为：</span><span class="sxs-lookup"><span data-stu-id="2a4c0-105">The syntax of `throw` is:</span></span>

```csharp
throw [e]
```
<span data-ttu-id="2a4c0-106">`e` 是一个派生自 <xref:System.Exception?displayProperty=fullName> 的类的实例。</span><span class="sxs-lookup"><span data-stu-id="2a4c0-106">where `e` is an instance of a class derived from <xref:System.Exception?displayProperty=fullName>.</span></span> <span data-ttu-id="2a4c0-107">下例使用 `throw` 语句在传递给名为 `GetNumber` 的方法的参数与内部数组的有效索引不对应时引发 @System.IndexOutOfRangeException。</span><span class="sxs-lookup"><span data-stu-id="2a4c0-107">The following example uses the `throw` statement to throw an @System.IndexOutOfRangeException if the argument passed to a method named `GetNumber` does not correspond to a valid index of an internal array.</span></span>

<span data-ttu-id="2a4c0-108">[!code-cs[csrefKeyword#1](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="2a4c0-108">[!code-cs[csrefKeyword#1](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#1)]</span></span>  

<span data-ttu-id="2a4c0-109">然后方法调用方使用 `try-catch` 或 `try-catch-finally` 块来处理引发的异常。</span><span class="sxs-lookup"><span data-stu-id="2a4c0-109">Method callers then use a `try-catch` or `try-catch-finally` block to handle the thrown exception.</span></span> <span data-ttu-id="2a4c0-110">下例处理由 `GetNumber` 方法引发的异常。</span><span class="sxs-lookup"><span data-stu-id="2a4c0-110">The following example handles the exception thrown by the `GetNumber` method.</span></span>

<span data-ttu-id="2a4c0-111">[!code-cs[csrefKeyword#2](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#2)]</span><span class="sxs-lookup"><span data-stu-id="2a4c0-111">[!code-cs[csrefKeyword#2](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#2)]</span></span>  

## <a name="re-throwing-an-exception"></a><span data-ttu-id="2a4c0-112">重新引发异常</span><span class="sxs-lookup"><span data-stu-id="2a4c0-112">Re-throwing an exception</span></span>

<span data-ttu-id="2a4c0-113">`throw` 也可以用于 `catch` 块，以重新引发在 `catch` 块中处理的异常。</span><span class="sxs-lookup"><span data-stu-id="2a4c0-113">`throw` can also be used in a `catch` block to re-throw an exception handled in a `catch` block.</span></span>  <span data-ttu-id="2a4c0-114">在这种情况下，`throw` 不采用异常操作数。</span><span class="sxs-lookup"><span data-stu-id="2a4c0-114">In this case, `throw` does not take an exception operand.</span></span> <span data-ttu-id="2a4c0-115">当方法将参数从调用方传递给其他库方法时，这是最有用的，库方法引发的异常必须传递给调用方。</span><span class="sxs-lookup"><span data-stu-id="2a4c0-115">It is most useful when a method passes on an argument from a caller to some other library method, and the library method throws an exception that must be passed on to the caller.</span></span> <span data-ttu-id="2a4c0-116">例如，以下示例重新引发在尝试检索未初始化字符串的第一个字符时引发的 @System.NullReferenceException。</span><span class="sxs-lookup"><span data-stu-id="2a4c0-116">For example, the following example re-throws an @System.NullReferenceException that is thrown when attempting to retrieve the first character of an uninitialized string.</span></span> 

<span data-ttu-id="2a4c0-117">[!code-cs[csrefKeyword#3](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-3.cs#3)]</span><span class="sxs-lookup"><span data-stu-id="2a4c0-117">[!code-cs[csrefKeyword#3](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-3.cs#3)]</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="2a4c0-118">还可以使用 `catch` 块中的 `throw e` 语法来实例化传递给调用方的新异常。</span><span class="sxs-lookup"><span data-stu-id="2a4c0-118">You can also use the `throw e` syntax in a `catch` block to instantiate a new exception that you pass on to the caller.</span></span> <span data-ttu-id="2a4c0-119">在这种情况下，将不会保留可从 @System.Exception.Stacktrace 属性获得的原始异常的堆栈跟踪。</span><span class="sxs-lookup"><span data-stu-id="2a4c0-119">In this case, the stack trace of the original exception, which is available from the @System.Exception.Stacktrace property, is not preserved.</span></span>
 
## <a name="the-throw-expression"></a><span data-ttu-id="2a4c0-120">`throw` 表达式</span><span class="sxs-lookup"><span data-stu-id="2a4c0-120">The `throw` expression</span></span>

<span data-ttu-id="2a4c0-121">从 C# 7 开始，`throw` 可以用作表达式和语句。</span><span class="sxs-lookup"><span data-stu-id="2a4c0-121">Starting with C# 7, `throw` can be used as an expression as well as a statement.</span></span> <span data-ttu-id="2a4c0-122">这允许在以前不支持的上下文中引发异常。</span><span class="sxs-lookup"><span data-stu-id="2a4c0-122">This allows an exception to be thrown in contexts that were previously unsupported.</span></span> <span data-ttu-id="2a4c0-123">这些方法包括：</span><span class="sxs-lookup"><span data-stu-id="2a4c0-123">These include:</span></span>

- <span data-ttu-id="2a4c0-124">[条件运算符](../operators/conditional-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="2a4c0-124">[the conditional operator](../operators/conditional-operator.md).</span></span> <span data-ttu-id="2a4c0-125">下例使用 `throw` 表达式在向方法传递空字符串数组时引发 @System.ArgumentException。</span><span class="sxs-lookup"><span data-stu-id="2a4c0-125">The following example uses a `throw` expression to throw an @System.ArgumentException if a method is passed an empty string array.</span></span> <span data-ttu-id="2a4c0-126">在 C# 7 之前，此逻辑将需要显示在 `if`/`else` 语句中。</span><span class="sxs-lookup"><span data-stu-id="2a4c0-126">Before C# 7, this logic would need to appear in an `if`/`else` statement.</span></span>

   <span data-ttu-id="2a4c0-127">[!code-cs[csrefKeyword#4](../../../../samples/snippets/csharp/language-reference/keywords/throw/conditional.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="2a4c0-127">[!code-cs[csrefKeyword#4](../../../../samples/snippets/csharp/language-reference/keywords/throw/conditional.cs#1)]</span></span>  
  
- <span data-ttu-id="2a4c0-128">[null 合并运算符](../operators/null-conditional-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="2a4c0-128">[the null-coalescing operator](../operators/null-conditional-operator.md).</span></span> <span data-ttu-id="2a4c0-129">在以下示例中，如果分配给 `Name` 属性的字符串为 `null`，则将 `throw` 表达式与 null 合并运算符结合使用以引发异常。</span><span class="sxs-lookup"><span data-stu-id="2a4c0-129">In the following example, a `throw` expression is used with a null-coalescing operator to throw an exception if the string assigned to a `Name` property is `null`.</span></span>
 
   <span data-ttu-id="2a4c0-130">[!code-cs[csrefKeyword#5](../../../../samples/snippets/csharp/language-reference/keywords/throw/coalescing.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="2a4c0-130">[!code-cs[csrefKeyword#5](../../../../samples/snippets/csharp/language-reference/keywords/throw/coalescing.cs#1)]</span></span>  
 
- <span data-ttu-id="2a4c0-131">expression-bodied [lambda](../../lambda-expressions.md) 或方法。</span><span class="sxs-lookup"><span data-stu-id="2a4c0-131">an expression-bodied [lambda](../../lambda-expressions.md) or method.</span></span> <span data-ttu-id="2a4c0-132">下例说明了 expression-bodied 方法，由于不支持对 @System.DateTime 值的转换，该方法引发 @System.InvalidCastException。</span><span class="sxs-lookup"><span data-stu-id="2a4c0-132">The following example illustrates an expression-bodied method that throws an @System.InvalidCastException because a conversion to a @System.DateTime value is not supported.</span></span>
 
   <span data-ttu-id="2a4c0-133">[!code-cs[csrefKeyword#6](../../../../samples/snippets/csharp/language-reference/keywords/throw/exp-bodied.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="2a4c0-133">[!code-cs[csrefKeyword#6](../../../../samples/snippets/csharp/language-reference/keywords/throw/exp-bodied.cs#1)]</span></span>  
 
  
## <a name="c-language-specification"></a><span data-ttu-id="2a4c0-134">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="2a4c0-134">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2a4c0-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="2a4c0-135">See Also</span></span>  
 <span data-ttu-id="2a4c0-136">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="2a4c0-136">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="2a4c0-137">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="2a4c0-137">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="2a4c0-138">[try-catch](../../../csharp/language-reference/keywords/try-catch.md) </span><span class="sxs-lookup"><span data-stu-id="2a4c0-138">[try-catch](../../../csharp/language-reference/keywords/try-catch.md) </span></span>  
 <span data-ttu-id="2a4c0-139">[C++ 中的 try、catch 和 throw 语句](../../../csharp/language-reference/keywords/try-catch.md) </span><span class="sxs-lookup"><span data-stu-id="2a4c0-139">[The try, catch, and throw Statements in C++](../../../csharp/language-reference/keywords/try-catch.md) </span></span>  
 <span data-ttu-id="2a4c0-140">[C# 关键字](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="2a4c0-140">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="2a4c0-141">[异常处理语句](../../../csharp/language-reference/keywords/exception-handling-statements.md) </span><span class="sxs-lookup"><span data-stu-id="2a4c0-141">[Exception Handling Statements](../../../csharp/language-reference/keywords/exception-handling-statements.md) </span></span>  
 [<span data-ttu-id="2a4c0-142">如何显式引发异常</span><span class="sxs-lookup"><span data-stu-id="2a4c0-142">How to: Explicitly Throw Exceptions</span></span>](https://msdn.microsoft.com/library/xhcbs8fz)

