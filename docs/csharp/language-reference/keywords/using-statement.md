---
title: using 语句 - C# 参考
ms.date: 04/07/2020
helpviewer_keywords:
- using statement [C#]
ms.assetid: afc355e6-f0b9-4240-94dd-0d93f17d9fc3
ms.openlocfilehash: 3c479faeeb66865b8c368edba881429a7cb956ec
ms.sourcegitcommit: 5988e9a29cedb8757320817deda3c08c6f44a6aa
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2020
ms.locfileid: "82199672"
---
# <a name="using-statement-c-reference"></a><span data-ttu-id="c6524-102">using 语句（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="c6524-102">using statement (C# Reference)</span></span>

<span data-ttu-id="c6524-103">提供可确保正确使用 <xref:System.IDisposable> 对象的方便语法。</span><span class="sxs-lookup"><span data-stu-id="c6524-103">Provides a convenient syntax that ensures the correct use of <xref:System.IDisposable> objects.</span></span> <span data-ttu-id="c6524-104">从 C#8.0 开始，`using` 语句可确保正确使用 <xref:System.IAsyncDisposable> 对象。</span><span class="sxs-lookup"><span data-stu-id="c6524-104">Beginning in C# 8.0, the `using` statement ensures the correct use of <xref:System.IAsyncDisposable> objects.</span></span>

## <a name="example"></a><span data-ttu-id="c6524-105">示例</span><span class="sxs-lookup"><span data-stu-id="c6524-105">Example</span></span>

<span data-ttu-id="c6524-106">下面的示例演示如何使用 `using` 语句。</span><span class="sxs-lookup"><span data-stu-id="c6524-106">The following example shows how to use the `using` statement.</span></span>

:::code language="csharp" source="snippets/usings.cs" id="SnippetFirstExample":::

<span data-ttu-id="c6524-107">从 C# 8.0 开始，可以对不需要使用大括号的 `using` 语句使用以下替代语法：</span><span class="sxs-lookup"><span data-stu-id="c6524-107">Beginning with C# 8.0, you can use the following alternative syntax for the `using` statement that doesn't require braces:</span></span>

:::code language="csharp" source="snippets/usings.cs" id="SnippetModernUsing":::

## <a name="remarks"></a><span data-ttu-id="c6524-108">备注</span><span class="sxs-lookup"><span data-stu-id="c6524-108">Remarks</span></span>

<span data-ttu-id="c6524-109"><xref:System.IO.File> 和 <xref:System.Drawing.Font> 是访问非托管资源（本例中为文件句柄和设备上下文）的托管类型的示例。</span><span class="sxs-lookup"><span data-stu-id="c6524-109"><xref:System.IO.File> and <xref:System.Drawing.Font> are examples of managed types that access unmanaged resources (in this case file handles and device contexts).</span></span> <span data-ttu-id="c6524-110">有许多其他类别的非托管资源和封装这些资源的类库类型。</span><span class="sxs-lookup"><span data-stu-id="c6524-110">There are many other kinds of unmanaged resources and class library types that encapsulate them.</span></span> <span data-ttu-id="c6524-111">所有此类类型都必须实现 <xref:System.IDisposable> 接口或 <xref:System.IAsyncDisposable> 接口。</span><span class="sxs-lookup"><span data-stu-id="c6524-111">All such types must implement the <xref:System.IDisposable> interface, or the <xref:System.IAsyncDisposable> interface.</span></span>

<span data-ttu-id="c6524-112">`IDisposable` 对象的生存期限于单个方法时，应在 `using` 语句中声明并实例化它。</span><span class="sxs-lookup"><span data-stu-id="c6524-112">When the lifetime of an `IDisposable` object is limited to a single method, you should declare and instantiate it in the `using` statement.</span></span> <span data-ttu-id="c6524-113">`using` 语句按照正确的方式调用对象上的 <xref:System.IDisposable.Dispose%2A> 方法，并（在按照前面所示方式使用它时）会导致在调用 <xref:System.IDisposable.Dispose%2A> 时对象自身处于范围之外。</span><span class="sxs-lookup"><span data-stu-id="c6524-113">The `using` statement calls the <xref:System.IDisposable.Dispose%2A> method on the object in the correct way, and (when you use it as shown earlier) it also causes the object itself to go out of scope as soon as <xref:System.IDisposable.Dispose%2A> is called.</span></span> <span data-ttu-id="c6524-114">在 `using` 块中，对象是只读的并且无法进行修改或重新分配。</span><span class="sxs-lookup"><span data-stu-id="c6524-114">Within the `using` block, the object is read-only and can't be modified or reassigned.</span></span> <span data-ttu-id="c6524-115">如果对象实现 `IAsyncDisposable` 而不是 `IDisposable`，`using` 语句将调用 <xref:System.IAsyncDisposable.DisposeAsync%2A> 和 `awaits` 返回的 <xref:System.Threading.Tasks.Task>。</span><span class="sxs-lookup"><span data-stu-id="c6524-115">If the object implements `IAsyncDisposable` instead of `IDisposable`, the `using` statement calls the <xref:System.IAsyncDisposable.DisposeAsync%2A> and `awaits` the returned <xref:System.Threading.Tasks.Task>.</span></span>

<span data-ttu-id="c6524-116">`using` 语句可确保调用 <xref:System.IDisposable.Dispose%2A> 或 <xref:System.IAsyncDisposable.DisposeAsync%2A>，即使 `using` 块中发生异常也是如此。</span><span class="sxs-lookup"><span data-stu-id="c6524-116">The `using` statement ensures that <xref:System.IDisposable.Dispose%2A> (or <xref:System.IAsyncDisposable.DisposeAsync%2A>) is called even if an exception occurs within the `using` block.</span></span> <span data-ttu-id="c6524-117">通过将对象放入 `try` 块中，然后调用 `finally` 块中的 <xref:System.IDisposable.Dispose%2A>（或 <xref:System.IAsyncDisposable.DisposeAsync%2A>），可以实现相同的结果；实际上，这就是编译器转换 `using` 语句的方式。</span><span class="sxs-lookup"><span data-stu-id="c6524-117">You can achieve the same result by putting the object inside a `try` block and then calling <xref:System.IDisposable.Dispose%2A> (or <xref:System.IAsyncDisposable.DisposeAsync%2A>) in a `finally` block; in fact, this is how the `using` statement is translated by the compiler.</span></span> <span data-ttu-id="c6524-118">前面的代码示例在编译时将扩展到以下代码（请注意，使用额外的大括号为对象创建有限范围）：</span><span class="sxs-lookup"><span data-stu-id="c6524-118">The code example earlier expands to the following code at compile time (note the extra curly braces to create the limited scope for the object):</span></span>

:::code language="csharp" source="snippets/usings.cs" id="SnippetTryFinallyExample":::

<span data-ttu-id="c6524-119">较新的 `using` 语句语法转换为类似的代码。</span><span class="sxs-lookup"><span data-stu-id="c6524-119">The newer `using` statement syntax translates to similar code.</span></span> <span data-ttu-id="c6524-120">`try` 块在声明变量的位置打开。</span><span class="sxs-lookup"><span data-stu-id="c6524-120">The `try` block opens where the variable is declared.</span></span> <span data-ttu-id="c6524-121">`finally` 块添加在封闭块的末尾，通常是在方法的末尾。</span><span class="sxs-lookup"><span data-stu-id="c6524-121">The `finally` block is added at the close of the enclosing block, typically at the end of a method.</span></span>

<span data-ttu-id="c6524-122">有关 `try`-`finally` 语句的详细信息，请参阅 [try-finally](try-finally.md) 一文。</span><span class="sxs-lookup"><span data-stu-id="c6524-122">For more information about the `try`-`finally` statement, see the [try-finally](try-finally.md) article.</span></span>

<span data-ttu-id="c6524-123">可在单个 `using` 语句中声明一个类型的多个实例，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="c6524-123">Multiple instances of a type can be declared in a single `using` statement, as shown in the following example.</span></span> <span data-ttu-id="c6524-124">注意，在单个语句中声明多个变量时，不能使用隐式类型的变量 (`var`)：</span><span class="sxs-lookup"><span data-stu-id="c6524-124">Notice that you can't use implicitly typed variables (`var`) when you declare multiple variables in a single statement:</span></span>

:::code language="csharp" source="snippets/usings.cs" id="SnippetDeclareMultipleVariables":::

<span data-ttu-id="c6524-125">可以使用与 C# 8 一起引入的新语法，合并同一类型的多个声明，如下面的示例中所示：</span><span class="sxs-lookup"><span data-stu-id="c6524-125">You can combine multiple declarations of the same type using the new syntax introduced with C# 8 as well, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/usings.cs" id="SnippetModernMultipleVariables":::

<span data-ttu-id="c6524-126">可以实例化资源对象，然后将变量传递到 `using` 语句，但这不是最佳做法。</span><span class="sxs-lookup"><span data-stu-id="c6524-126">You can instantiate the resource object and then pass the variable to the `using` statement, but this isn't a best practice.</span></span> <span data-ttu-id="c6524-127">在这种情况下，控件退出 `using` 块以后，对象保留在作用域中，但是可能没有访问其未托管资源的权限。</span><span class="sxs-lookup"><span data-stu-id="c6524-127">In this case, after control leaves the `using` block, the object remains in scope but probably has no access to its unmanaged resources.</span></span> <span data-ttu-id="c6524-128">换而言之，它不再是完全初始化的。</span><span class="sxs-lookup"><span data-stu-id="c6524-128">In other words, it's not fully initialized anymore.</span></span> <span data-ttu-id="c6524-129">如果尝试在 `using` 块外部使用该对象，则可能导致引发异常。</span><span class="sxs-lookup"><span data-stu-id="c6524-129">If you try to use the object outside the `using` block, you risk causing an exception to be thrown.</span></span> <span data-ttu-id="c6524-130">因此，最好在 `using` 语句中实例化该对象并将其范围限制在 `using` 块中。</span><span class="sxs-lookup"><span data-stu-id="c6524-130">For this reason, it's better to instantiate the object in the `using` statement and limit its scope to the `using` block.</span></span>

:::code language="csharp" source="snippets/usings.cs" id="SnippetDeclareBeforeUsing":::

<span data-ttu-id="c6524-131">有关释放 `IDisposable` 对象的详细信息，请参阅[使用实现 IDisposable 的对象](../../../standard/garbage-collection/using-objects.md)。</span><span class="sxs-lookup"><span data-stu-id="c6524-131">For more information about disposing of `IDisposable` objects, see [Using objects that implement IDisposable](../../../standard/garbage-collection/using-objects.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="c6524-132">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="c6524-132">C# language specification</span></span>

<span data-ttu-id="c6524-133">有关详细信息，请参阅 [C# 语言规范](/dotnet/csharp/language-reference/language-specification/introduction)中的 [using 语句](~/_csharplang/spec/statements.md#the-using-statement)。</span><span class="sxs-lookup"><span data-stu-id="c6524-133">For more information, see [The using statement](~/_csharplang/spec/statements.md#the-using-statement) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="c6524-134">该语言规范是 C# 语法和用法的权威资料。</span><span class="sxs-lookup"><span data-stu-id="c6524-134">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="c6524-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="c6524-135">See also</span></span>

- [<span data-ttu-id="c6524-136">C# 参考</span><span class="sxs-lookup"><span data-stu-id="c6524-136">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="c6524-137">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="c6524-137">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="c6524-138">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="c6524-138">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="c6524-139">using 指令</span><span class="sxs-lookup"><span data-stu-id="c6524-139">using Directive</span></span>](using-directive.md)
- [<span data-ttu-id="c6524-140">垃圾回收</span><span class="sxs-lookup"><span data-stu-id="c6524-140">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
- [<span data-ttu-id="c6524-141">使用实现 IDisposable 的对象</span><span class="sxs-lookup"><span data-stu-id="c6524-141">Using objects that implement IDisposable</span></span>](../../../standard/garbage-collection/using-objects.md)
- [<span data-ttu-id="c6524-142">IDisposable 接口</span><span class="sxs-lookup"><span data-stu-id="c6524-142">IDisposable interface</span></span>](xref:System.IDisposable)
- [<span data-ttu-id="c6524-143">C# 8.0 中的 using 语句</span><span class="sxs-lookup"><span data-stu-id="c6524-143">using statement in C# 8.0</span></span>](~/_csharplang/proposals/csharp-8.0/using.md)
