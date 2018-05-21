---
title: using 语句（C# 参考）
ms.date: 07/20/2015
helpviewer_keywords:
- using statement [C#]
ms.assetid: afc355e6-f0b9-4240-94dd-0d93f17d9fc3
ms.openlocfilehash: fa27039e8444090c8a516b92ba5ab62c7f93c51a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="using-statement-c-reference"></a><span data-ttu-id="0294d-102">using 语句（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="0294d-102">using Statement (C# Reference)</span></span>
<span data-ttu-id="0294d-103">提供可确保正确使用 <xref:System.IDisposable> 对象的方便语法。</span><span class="sxs-lookup"><span data-stu-id="0294d-103">Provides a convenient syntax that ensures the correct use of <xref:System.IDisposable> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0294d-104">示例</span><span class="sxs-lookup"><span data-stu-id="0294d-104">Example</span></span>  
 <span data-ttu-id="0294d-105">下面的示例演示如何使用 using 语句。</span><span class="sxs-lookup"><span data-stu-id="0294d-105">The following example shows how to use the using statement.</span></span>  
  
 [!code-csharp[csrefKeywordsNamespace#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_1.cs)]  
  
## <a name="remarks"></a><span data-ttu-id="0294d-106">备注</span><span class="sxs-lookup"><span data-stu-id="0294d-106">Remarks</span></span>  
 <span data-ttu-id="0294d-107"><xref:System.IO.File> 和 <xref:System.Drawing.Font> 是访问非托管资源（本例中为文件句柄和设备上下文）的托管类型的示例。</span><span class="sxs-lookup"><span data-stu-id="0294d-107"><xref:System.IO.File> and <xref:System.Drawing.Font> are examples of managed types that access unmanaged resources (in this case file handles and device contexts).</span></span> <span data-ttu-id="0294d-108">有许多其他类别的非托管资源和封装这些资源的类库类型。</span><span class="sxs-lookup"><span data-stu-id="0294d-108">There are many other kinds of unmanaged resources and class library types that encapsulate them.</span></span> <span data-ttu-id="0294d-109">所有此类类型都必须实现 <xref:System.IDisposable> 接口。</span><span class="sxs-lookup"><span data-stu-id="0294d-109">All such types must implement the <xref:System.IDisposable> interface.</span></span>  
  
<span data-ttu-id="0294d-110">`IDisposable` 对象的生存期限于单个方法时，应在 `using` 语句中声明并实例化它。</span><span class="sxs-lookup"><span data-stu-id="0294d-110">When the lifetime of an `IDisposable` object is limited to a single method, you should declare and instantiate it in a `using` statement.</span></span> <span data-ttu-id="0294d-111">`using` 语句按照正确的方式调用对象上的 <xref:System.IDisposable.Dispose%2A> 方法，并（在按照前面所示方式使用它时）会导致在调用 <xref:System.IDisposable.Dispose%2A> 时对象自身处于范围之外。</span><span class="sxs-lookup"><span data-stu-id="0294d-111">The `using` statement calls the <xref:System.IDisposable.Dispose%2A> method on the object in the correct way, and (when you use it as shown earlier) it also causes the object itself to go out of scope as soon as <xref:System.IDisposable.Dispose%2A> is called.</span></span> <span data-ttu-id="0294d-112">在 `using` 块中，对象是只读的并且无法进行修改或重新分配。</span><span class="sxs-lookup"><span data-stu-id="0294d-112">Within the `using` block, the object is read-only and cannot be modified or reassigned.</span></span>  
  
 <span data-ttu-id="0294d-113">`using` 语句确保调用 <xref:System.IDisposable.Dispose%2A>，即使在调用对象上的方法时出现异常也是如此。</span><span class="sxs-lookup"><span data-stu-id="0294d-113">The `using` statement ensures that <xref:System.IDisposable.Dispose%2A> is called even if an exception occurs while you are calling methods on the object.</span></span> <span data-ttu-id="0294d-114">通过将对象放入 try 块中，然后调用 finally 块中的 <xref:System.IDisposable.Dispose%2A>，可以实现相同的结果；实际上，这就是编译器转换 `using` 语句的方式。</span><span class="sxs-lookup"><span data-stu-id="0294d-114">You can achieve the same result by putting the object inside a try block and then calling <xref:System.IDisposable.Dispose%2A> in a finally block; in fact, this is how the `using` statement is translated by the compiler.</span></span> <span data-ttu-id="0294d-115">前面的代码示例在编译时将扩展到以下代码（请注意，使用额外的大括号为对象创建有限范围）：</span><span class="sxs-lookup"><span data-stu-id="0294d-115">The code example earlier expands to the following code at compile time (note the extra curly braces to create the limited scope for the object):</span></span>  
  
 [!code-csharp[csrefKeywordsNamespace#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_2.cs)]  
  
 <span data-ttu-id="0294d-116">可在 `using` 语句中声明一个类型的多个实例，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="0294d-116">Multiple instances of a type can be declared in a `using` statement, as shown in the following example.</span></span>  
  
 [!code-csharp[csrefKeywordsNamespace#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_3.cs)]  
  
 <span data-ttu-id="0294d-117">可以实例化资源对象，然后将变量传递到 `using` 语句，但这不是最佳做法。</span><span class="sxs-lookup"><span data-stu-id="0294d-117">You can instantiate the resource object and then pass the variable to the `using` statement, but this is not a best practice.</span></span> <span data-ttu-id="0294d-118">在这种情况下，该对象将在控制权离开 `using` 块之后保持在范围内，即使它可能将不再具有对其非托管资源的访问权限。</span><span class="sxs-lookup"><span data-stu-id="0294d-118">In this case, the object remains in scope after control leaves the `using` block even though it will probably no longer have access to its unmanaged resources.</span></span> <span data-ttu-id="0294d-119">换句话说，再也无法完全初始化该对象。</span><span class="sxs-lookup"><span data-stu-id="0294d-119">In other words, it will no longer be fully initialized.</span></span> <span data-ttu-id="0294d-120">如果尝试在 `using` 块外部使用该对象，则可能导致引发异常。</span><span class="sxs-lookup"><span data-stu-id="0294d-120">If you try to use the object outside the `using` block, you risk causing an exception to be thrown.</span></span> <span data-ttu-id="0294d-121">因此，通常最好在 `using` 语句中实例化该对象并将其范围限制在 `using` 块中。</span><span class="sxs-lookup"><span data-stu-id="0294d-121">For this reason, it is generally better to instantiate the object in the `using` statement and limit its scope to the `using` block.</span></span>  
  
 [!code-csharp[csrefKeywordsNamespace#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_4.cs)]  
  
<span data-ttu-id="0294d-122">有关释放 `IDisposable` 对象的详细信息，请参阅[使用实现 IDisposable 的对象](../../../standard/garbage-collection/using-objects.md)。</span><span class="sxs-lookup"><span data-stu-id="0294d-122">For more information on disposing of `IDisposable` objects, see [Using objects that implement IDisposable](../../../standard/garbage-collection/using-objects.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="0294d-123">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="0294d-123">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0294d-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="0294d-124">See Also</span></span>  
 [<span data-ttu-id="0294d-125">C# 参考</span><span class="sxs-lookup"><span data-stu-id="0294d-125">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="0294d-126">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="0294d-126">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="0294d-127">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="0294d-127">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="0294d-128">using 指令</span><span class="sxs-lookup"><span data-stu-id="0294d-128">using Directive</span></span>](../../../csharp/language-reference/keywords/using-directive.md)  
 [<span data-ttu-id="0294d-129">垃圾回收</span><span class="sxs-lookup"><span data-stu-id="0294d-129">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)  
 [<span data-ttu-id="0294d-130">使用实现 IDisposable 的对象</span><span class="sxs-lookup"><span data-stu-id="0294d-130">Using objects that implement IDisposable</span></span>](../../../standard/garbage-collection/using-objects.md)  
 [<span data-ttu-id="0294d-131">IDisposable 接口</span><span class="sxs-lookup"><span data-stu-id="0294d-131">IDisposable interface</span></span>](xref:System.IDisposable)
