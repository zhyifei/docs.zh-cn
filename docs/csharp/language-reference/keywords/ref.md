---
title: ref 关键字（C# 参考）
ms.date: 03/06/2018
f1_keywords:
- ref_CSharpKeyword
- ref
helpviewer_keywords:
- parameters [C#], ref
- ref keyword [C#]
ms.openlocfilehash: e0b82de125246e95d8dce2a7afc20119a8a1fe4f
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/16/2018
ms.locfileid: "45591745"
---
# <a name="ref-c-reference"></a><span data-ttu-id="fb707-102">ref（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="fb707-102">ref (C# Reference)</span></span>

<span data-ttu-id="fb707-103">`ref` 关键字指示按引用传递的值。</span><span class="sxs-lookup"><span data-stu-id="fb707-103">The `ref` keyword indicates a value that is passed by reference.</span></span> <span data-ttu-id="fb707-104">它用在四种不同的上下文中：</span><span class="sxs-lookup"><span data-stu-id="fb707-104">It is used in four different contexts:</span></span>

- <span data-ttu-id="fb707-105">在方法签名和方法调用中，按引用将参数传递给方法。</span><span class="sxs-lookup"><span data-stu-id="fb707-105">In a method signature and in a method call, to pass an argument to a method by reference.</span></span> <span data-ttu-id="fb707-106">有关详细信息，请参阅[引用传递参数](#passing-an-argument-by-reference)。</span><span class="sxs-lookup"><span data-stu-id="fb707-106">See [Passing an argument by reference](#passing-an-argument-by-reference) for more information.</span></span>
- <span data-ttu-id="fb707-107">在方法签名中，按引用将值返回给调用方。</span><span class="sxs-lookup"><span data-stu-id="fb707-107">In a method signature, to return a value to the caller by reference.</span></span> <span data-ttu-id="fb707-108">有关详细信息，请参阅[引用返回值](#reference-return-values)。</span><span class="sxs-lookup"><span data-stu-id="fb707-108">See [Reference return values](#reference-return-values) for more information.</span></span>
- <span data-ttu-id="fb707-109">在成员正文中，指示引用返回值是否作为调用方欲修改的引用被存储在本地，或在一般情况下，局部变量按引用访问另一个值。</span><span class="sxs-lookup"><span data-stu-id="fb707-109">In a member body, to indicate that a reference return value is stored locally as a reference that the caller intends to modify or, in general, a local variable accesses another value by reference.</span></span> <span data-ttu-id="fb707-110">有关详细信息，请参阅 [ref 局部变量](#ref-locals)。</span><span class="sxs-lookup"><span data-stu-id="fb707-110">See [Ref locals](#ref-locals) for more information.</span></span>
- <span data-ttu-id="fb707-111">在 `struct` 声明中声明 `ref struct` 或 `ref readonly struct`。</span><span class="sxs-lookup"><span data-stu-id="fb707-111">In a `struct` declaration to declare a `ref struct` or a `ref readonly struct`.</span></span> <span data-ttu-id="fb707-112">有关更多信息，请参见[具有值类型的引用语义](../../reference-semantics-with-value-types.md)。</span><span class="sxs-lookup"><span data-stu-id="fb707-112">For more information, see [Reference semantics with value types](../../reference-semantics-with-value-types.md).</span></span>

## <a name="passing-an-argument-by-reference"></a><span data-ttu-id="fb707-113">按引用传递参数</span><span class="sxs-lookup"><span data-stu-id="fb707-113">Passing an argument by reference</span></span>

<span data-ttu-id="fb707-114">在方法的参数列表中使用 `ref` 关键字时，它指示参数按引用传递，而非按值传递。</span><span class="sxs-lookup"><span data-stu-id="fb707-114">When used in a method's parameter list, the `ref` keyword indicates that an argument is passed by reference, not by value.</span></span> <span data-ttu-id="fb707-115">按引用传递的效果是，对所调用方法中参数进行的任何更改都反映在调用方法中。</span><span class="sxs-lookup"><span data-stu-id="fb707-115">The effect of passing by reference is that any change to the argument in the called method is reflected in the calling method.</span></span> <span data-ttu-id="fb707-116">例如，如果调用方传递本地变量表达式或数组元素访问表达式，所调用方法会替换 ref 参数引用的对象，然后，当该方法返回时，调用方的本地变量或数组元素将开始引用新对象。</span><span class="sxs-lookup"><span data-stu-id="fb707-116">For example, if the caller passes a local variable expression or an array element access expression, and the called method replaces the object to which the ref parameter refers, then the caller’s local variable or the array element now refers to the new object when the method returns.</span></span>

> [!NOTE]
> <span data-ttu-id="fb707-117">不要混淆通过引用传递的概念与引用类型的概念。</span><span class="sxs-lookup"><span data-stu-id="fb707-117">Do not confuse the concept of passing by reference with the concept of reference types.</span></span> <span data-ttu-id="fb707-118">这两种概念是不同的。</span><span class="sxs-lookup"><span data-stu-id="fb707-118">The two concepts are not the same.</span></span> <span data-ttu-id="fb707-119">无论方法参数是值类型还是引用类型，均可由 `ref` 修改。</span><span class="sxs-lookup"><span data-stu-id="fb707-119">A method parameter can be modified by `ref` regardless of whether it is a value type or a reference type.</span></span> <span data-ttu-id="fb707-120">当通过引用传递时，不会对值类型装箱。</span><span class="sxs-lookup"><span data-stu-id="fb707-120">There is no boxing of a value type when it is passed by reference.</span></span>  

<span data-ttu-id="fb707-121">若要使用 `ref` 参数，方法定义和调用方法均必须显式使用 `ref` 关键字，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="fb707-121">To use a `ref` parameter, both the method definition and the calling method must explicitly use the `ref` keyword, as shown in the following example.</span></span>  

[!code-csharp-interactive[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#1)]

<span data-ttu-id="fb707-122">传递到 `ref` 或 `in` 形参的实参必须先经过初始化，然后才能传递。</span><span class="sxs-lookup"><span data-stu-id="fb707-122">An argument that is passed to a `ref` or `in` parameter must be initialized before it is passed.</span></span> <span data-ttu-id="fb707-123">这与 [out](out-parameter-modifier.md) 形参不同，在传递之前，不需要显式初始化该形参的实参。</span><span class="sxs-lookup"><span data-stu-id="fb707-123">This differs from [out](out-parameter-modifier.md) parameters, whose arguments do not have to be explicitly initialized before they are passed.</span></span>

<span data-ttu-id="fb707-124">类的成员不能具有仅在 `ref`、`in` 或 `out` 方面不同的签名。</span><span class="sxs-lookup"><span data-stu-id="fb707-124">Members of a class can't have signatures that differ only by `ref`, `in`, or `out`.</span></span> <span data-ttu-id="fb707-125">如果类型的两个成员之间的唯一区别在于其中一个具有 `ref` 参数，而另一个具有 `out` 或 `in` 参数，则会发生编译器错误。</span><span class="sxs-lookup"><span data-stu-id="fb707-125">A compiler error occurs if the only difference between two members of a type is that one of them has a `ref` parameter and the other has an `out`, or `in` parameter.</span></span> <span data-ttu-id="fb707-126">例如，以下代码将不会编译。</span><span class="sxs-lookup"><span data-stu-id="fb707-126">The following code, for example, doesn't compile.</span></span>  

```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded 
    // methods that differ only on ref and out".
    public void SampleMethod(out int i) { }
    public void SampleMethod(ref int i) { }
}
```

<span data-ttu-id="fb707-127">但是，当一个方法具有 `ref`、`in` 或 `out` 参数，另一个方法具有值参数时，则可以重载方法，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="fb707-127">However, methods can be overloaded when one method has a `ref`, `in`, or `out` parameter and the other has a value parameter, as shown in the following example.</span></span>
  
[!code-csharp[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#2)]
  
 <span data-ttu-id="fb707-128">在其他要求签名匹配的情况下（如隐藏或重写），`in`、`ref` 和 `out` 是签名的一部分，相互之间不匹配。</span><span class="sxs-lookup"><span data-stu-id="fb707-128">In other situations that require signature matching, such as hiding or overriding, `in`, `ref`, and `out` are part of the signature and don't match each other.</span></span>  
  
 <span data-ttu-id="fb707-129">属性不是变量。</span><span class="sxs-lookup"><span data-stu-id="fb707-129">Properties are not variables.</span></span> <span data-ttu-id="fb707-130">它们是方法，不能传递到 `ref` 参数。</span><span class="sxs-lookup"><span data-stu-id="fb707-130">They are methods, and cannot be passed to `ref` parameters.</span></span>  
  
 <span data-ttu-id="fb707-131">不能将 `ref`、`in` 和 `out` 关键字用于以下几种方法：</span><span class="sxs-lookup"><span data-stu-id="fb707-131">You can't use the `ref`, `in`, and `out` keywords for the following kinds of methods:</span></span>  
  
- <span data-ttu-id="fb707-132">异步方法，通过使用 [async](async.md) 修饰符定义。</span><span class="sxs-lookup"><span data-stu-id="fb707-132">Async methods, which you define by using the [async](async.md) modifier.</span></span>  
- <span data-ttu-id="fb707-133">迭代器方法，包括 [yield return](yield.md) 或 `yield break` 语句。</span><span class="sxs-lookup"><span data-stu-id="fb707-133">Iterator methods, which include a [yield return](yield.md) or `yield break` statement.</span></span>  

## <a name="passing-an-argument-by-reference-an-example"></a><span data-ttu-id="fb707-134">按引用传递参数：示例</span><span class="sxs-lookup"><span data-stu-id="fb707-134">Passing an argument by reference: An example</span></span>

<span data-ttu-id="fb707-135">前面的示例按引用传递值类型。</span><span class="sxs-lookup"><span data-stu-id="fb707-135">The previous examples pass value types by reference.</span></span> <span data-ttu-id="fb707-136">还可使用 `ref` 关键字按引用传递引用类型。</span><span class="sxs-lookup"><span data-stu-id="fb707-136">You can also use the `ref` keyword to pass reference types by reference.</span></span> <span data-ttu-id="fb707-137">按引用传递引用类型使所调用方能够替换调用方中引用参数引用的对象。</span><span class="sxs-lookup"><span data-stu-id="fb707-137">Passing a reference type by reference enables the called method to replace the object to which the reference parameter refers in the caller.</span></span> <span data-ttu-id="fb707-138">对象的存储位置按引用参数的值传递到方法。</span><span class="sxs-lookup"><span data-stu-id="fb707-138">The storage location of the object is passed to the method as the value of the reference parameter.</span></span> <span data-ttu-id="fb707-139">如果更改参数存储位置中的值（以指向新对象），你还可以将存储位置更改为调用方所引用的位置。</span><span class="sxs-lookup"><span data-stu-id="fb707-139">If you change the value in the storage location of the parameter (to point to a new object), you also change the storage location to which the caller refers.</span></span> <span data-ttu-id="fb707-140">下面的示例将引用类型的实例作为 `ref` 参数传递。</span><span class="sxs-lookup"><span data-stu-id="fb707-140">The following example passes an instance of a reference type as a `ref` parameter.</span></span>
  
[!code-csharp[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#3)]

<span data-ttu-id="fb707-141">有关如何通过值和引用传递引用类型的详细信息，请参阅[传递引用类型参数](../../programming-guide/classes-and-structs/passing-reference-type-parameters.md)。</span><span class="sxs-lookup"><span data-stu-id="fb707-141">For more information about how to pass reference types by value and by reference, see [Passing Reference-Type Parameters](../../programming-guide/classes-and-structs/passing-reference-type-parameters.md).</span></span>
  
## <a name="reference-return-values"></a><span data-ttu-id="fb707-142">引用返回值</span><span class="sxs-lookup"><span data-stu-id="fb707-142">Reference return values</span></span>

<span data-ttu-id="fb707-143">引用返回值（或 ref 返回值）是由方法按引用向调用方返回的值。</span><span class="sxs-lookup"><span data-stu-id="fb707-143">Reference return values (or ref returns) are values that a method returns by reference to the caller.</span></span> <span data-ttu-id="fb707-144">即是说，调用方可以修改方法所返回的值，此更改反映在包含方法的对象的状态中。</span><span class="sxs-lookup"><span data-stu-id="fb707-144">That is, the caller can modify the value returned by a method, and that change is reflected in the state of the object that contains the method.</span></span>

<span data-ttu-id="fb707-145">使用 `ref` 关键字来定义引用返回值：</span><span class="sxs-lookup"><span data-stu-id="fb707-145">A reference return value is defined by using the `ref` keyword:</span></span>

- <span data-ttu-id="fb707-146">在方法签名中。</span><span class="sxs-lookup"><span data-stu-id="fb707-146">In the method signature.</span></span> <span data-ttu-id="fb707-147">例如，下列方法签名指示 `GetCurrentPrice` 方法按引用返回了 <xref:System.Decimal> 值。</span><span class="sxs-lookup"><span data-stu-id="fb707-147">For example, the following method signature indicates that the `GetCurrentPrice` method returns a <xref:System.Decimal> value by reference.</span></span>

```csharp
public ref decimal GetCurrentPrice()
```

- <span data-ttu-id="fb707-148">在 `return` 标记和方法的 `return` 语句中返回的变量之间。</span><span class="sxs-lookup"><span data-stu-id="fb707-148">Between the `return` token and the variable returned in a `return` statement in the method.</span></span> <span data-ttu-id="fb707-149">例如:</span><span class="sxs-lookup"><span data-stu-id="fb707-149">For example:</span></span>

```csharp
return ref DecimalArray[0];
```

<span data-ttu-id="fb707-150">为方便调用方修改对象的状态，引用返回值必须存储在被显式定义为 [ref 局部变量](#ref-locals)的变量中。</span><span class="sxs-lookup"><span data-stu-id="fb707-150">In order for the caller to modify the object's state, the reference return value must be stored to a variable that is explicitly defined as a [ref local](#ref-locals).</span></span>

<span data-ttu-id="fb707-151">有关示例，请参阅 [ref 返回值和 ref 局部变量示例](#a-ref-returns-and-ref-locals-example)</span><span class="sxs-lookup"><span data-stu-id="fb707-151">For an example, see [A ref returns and ref locals example](#a-ref-returns-and-ref-locals-example)</span></span>

## <a name="ref-locals"></a><span data-ttu-id="fb707-152">ref 局部变量</span><span class="sxs-lookup"><span data-stu-id="fb707-152">Ref locals</span></span>

<span data-ttu-id="fb707-153">ref 局部变量用于指代使用 `return ref` 返回的值。</span><span class="sxs-lookup"><span data-stu-id="fb707-153">A ref local variable is used to refer to values returned using `return ref`.</span></span> <span data-ttu-id="fb707-154">无法将 ref 局部变量初始化为非 ref 返回值。</span><span class="sxs-lookup"><span data-stu-id="fb707-154">A ref local variable cannot be initialized to a non-ref return value.</span></span> <span data-ttu-id="fb707-155">也就是说，初始化的右侧必须为引用。</span><span class="sxs-lookup"><span data-stu-id="fb707-155">In other words, the right hand side of the initialization must be a reference.</span></span> <span data-ttu-id="fb707-156">任何对 ref 本地变量值的修改都将反映在对象的状态中，该对象的方法按引用返回值。</span><span class="sxs-lookup"><span data-stu-id="fb707-156">Any modifications to the value of the ref local are reflected in the state of the object whose method returned the value by reference.</span></span>

<span data-ttu-id="fb707-157">在变量声明前或在方法（该方法将按引用返回值）调用前使用 `ref` 关键字定义 ref 局部变量。</span><span class="sxs-lookup"><span data-stu-id="fb707-157">You define a ref local by using the `ref` keyword before the variable declaration, as well as immediately before the call to the method that returns the value by reference.</span></span>

<span data-ttu-id="fb707-158">例如，下列语句定义名为 `GetEstimatedValue` 的方法返回的 ref 局部变量值：</span><span class="sxs-lookup"><span data-stu-id="fb707-158">For example, the following statement defines a ref local value that is returned by a method named `GetEstimatedValue`:</span></span>

```csharp
ref decimal estValue = ref Building.GetEstimatedValue();
```

<span data-ttu-id="fb707-159">可通过相同方式按引用访问值。</span><span class="sxs-lookup"><span data-stu-id="fb707-159">You can access a value by reference in the same way.</span></span> <span data-ttu-id="fb707-160">在某些情况下，按引用访问值可避免潜在的高开销复制操作，从而提高性能。</span><span class="sxs-lookup"><span data-stu-id="fb707-160">In some cases, accessing a value by reference increases performance by avoiding a potentially expensive copy operation.</span></span> <span data-ttu-id="fb707-161">例如，以下语句显示用户可如何定义一个用于引用值的 ref 局部变量值。</span><span class="sxs-lookup"><span data-stu-id="fb707-161">For example, the following statement shows how one can define a ref local value that is used to reference a value.</span></span>

```csharp
ref VeryLargeStruct reflocal = ref veryLargeStruct;
```

<span data-ttu-id="fb707-162">请注意，在这两个示例中，必须在两个位置同时使用 `ref` 关键字，否则编译器将生成错误 CS8172：“无法使用值对按引用变量进行初始化”。</span><span class="sxs-lookup"><span data-stu-id="fb707-162">Note that in both examples the `ref` keyword must be used in both places, or the compiler generates error CS8172, "Cannot initialize a by-reference variable with a value."</span></span>

## <a name="a-ref-returns-and-ref-locals-example"></a><span data-ttu-id="fb707-163">ref 返回值和 ref 局部变量示例</span><span class="sxs-lookup"><span data-stu-id="fb707-163">A ref returns and ref locals example</span></span>

<span data-ttu-id="fb707-164">下列示例定义一个具有两个 <xref:System.String> 字段（`Title` 和 `Author`）的 `Book` 类。</span><span class="sxs-lookup"><span data-stu-id="fb707-164">The following example defines a `Book` class that has two <xref:System.String> fields, `Title` and `Author`.</span></span> <span data-ttu-id="fb707-165">还定义包含 `Book` 对象的专用数组的 `BookCollection` 类。</span><span class="sxs-lookup"><span data-stu-id="fb707-165">It also defines a `BookCollection` class that includes a private array of `Book` objects.</span></span> <span data-ttu-id="fb707-166">通过调用 `GetBookByTitle` 方法，可按引用返回个别 book 对象。</span><span class="sxs-lookup"><span data-stu-id="fb707-166">Individual book objects are returned by reference by calling its `GetBookByTitle` method.</span></span>

[!code-csharp[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#4)]

<span data-ttu-id="fb707-167">调用方将 `GetBookByTitle` 方法所返回的值存储为 ref 局部变量时，调用方对返回值所做的更改将反映在 `BookCollection` 对象中，如下例所示。</span><span class="sxs-lookup"><span data-stu-id="fb707-167">When the caller stores the value returned by the `GetBookByTitle` method as a ref local, changes that the caller makes to the return value are reflected in the `BookCollection` object, as the following example shows.</span></span>

[!code-csharp[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#5)]

## <a name="c-language-specification"></a><span data-ttu-id="fb707-168">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="fb707-168">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="fb707-169">请参阅</span><span class="sxs-lookup"><span data-stu-id="fb707-169">See also</span></span>

- [<span data-ttu-id="fb707-170">引用语义结合值类型</span><span class="sxs-lookup"><span data-stu-id="fb707-170">Reference semantics with value types</span></span>](../../reference-semantics-with-value-types.md)  
- [<span data-ttu-id="fb707-171">传递参数</span><span class="sxs-lookup"><span data-stu-id="fb707-171">Passing Parameters</span></span>](../../programming-guide/classes-and-structs/passing-parameters.md)  
- [<span data-ttu-id="fb707-172">方法参数</span><span class="sxs-lookup"><span data-stu-id="fb707-172">Method Parameters</span></span>](method-parameters.md)  
- [<span data-ttu-id="fb707-173">C# 参考</span><span class="sxs-lookup"><span data-stu-id="fb707-173">C# Reference</span></span>](../index.md)  
- [<span data-ttu-id="fb707-174">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="fb707-174">C# Programming Guide</span></span>](../../programming-guide/index.md)  
- [<span data-ttu-id="fb707-175">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="fb707-175">C# Keywords</span></span>](index.md)