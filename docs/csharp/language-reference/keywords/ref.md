---
title: ref 关键字 - C# 参考
ms.date: 03/19/2020
f1_keywords:
- ref_CSharpKeyword
- ref
helpviewer_keywords:
- parameters [C#], ref
- ref keyword [C#]
ms.openlocfilehash: d54d932ca96f1966ecc05a532a2468b7e16fac46
ms.sourcegitcommit: f87ad41b8e62622da126aa928f7640108c4eff98
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/07/2020
ms.locfileid: "80805848"
---
# <a name="ref-c-reference"></a><span data-ttu-id="a3fda-102">ref（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="a3fda-102">ref (C# Reference)</span></span>

<span data-ttu-id="a3fda-103">`ref` 关键字指示按引用传递的值。</span><span class="sxs-lookup"><span data-stu-id="a3fda-103">The `ref` keyword indicates a value that is passed by reference.</span></span> <span data-ttu-id="a3fda-104">它用在四种不同的上下文中：</span><span class="sxs-lookup"><span data-stu-id="a3fda-104">It is used in four different contexts:</span></span>

- <span data-ttu-id="a3fda-105">在方法签名和方法调用中，按引用将参数传递给方法。</span><span class="sxs-lookup"><span data-stu-id="a3fda-105">In a method signature and in a method call, to pass an argument to a method by reference.</span></span> <span data-ttu-id="a3fda-106">有关详细信息，请参阅[按引用传递参数](#passing-an-argument-by-reference)。</span><span class="sxs-lookup"><span data-stu-id="a3fda-106">For more information, see [Passing an argument by reference](#passing-an-argument-by-reference).</span></span>
- <span data-ttu-id="a3fda-107">在方法签名中，按引用将值返回给调用方。</span><span class="sxs-lookup"><span data-stu-id="a3fda-107">In a method signature, to return a value to the caller by reference.</span></span> <span data-ttu-id="a3fda-108">有关详细信息，请参阅[引用返回值](#reference-return-values)。</span><span class="sxs-lookup"><span data-stu-id="a3fda-108">For more information, see [Reference return values](#reference-return-values).</span></span>
- <span data-ttu-id="a3fda-109">在成员正文中，指示引用返回值是否作为调用方欲修改的引用被存储在本地，或在一般情况下，局部变量按引用访问另一个值。</span><span class="sxs-lookup"><span data-stu-id="a3fda-109">In a member body, to indicate that a reference return value is stored locally as a reference that the caller intends to modify or, in general, a local variable accesses another value by reference.</span></span> <span data-ttu-id="a3fda-110">有关详细信息，请参阅 [Ref 局部变量](#ref-locals)。</span><span class="sxs-lookup"><span data-stu-id="a3fda-110">For more information, see [Ref locals](#ref-locals).</span></span>
- <span data-ttu-id="a3fda-111">在 `struct` 声明中声明 `ref struct` 或 `readonly ref struct`。</span><span class="sxs-lookup"><span data-stu-id="a3fda-111">In a `struct` declaration to declare a `ref struct` or a `readonly ref struct`.</span></span> <span data-ttu-id="a3fda-112">有关详细信息，请参阅 [ref 结构类型](#ref-struct-types)。</span><span class="sxs-lookup"><span data-stu-id="a3fda-112">For more information, see [ref struct types](#ref-struct-types).</span></span>

## <a name="passing-an-argument-by-reference"></a><span data-ttu-id="a3fda-113">按引用传递参数</span><span class="sxs-lookup"><span data-stu-id="a3fda-113">Passing an argument by reference</span></span>

<span data-ttu-id="a3fda-114">在方法的参数列表中使用 `ref` 关键字时，它指示参数按引用传递，而非按值传递。</span><span class="sxs-lookup"><span data-stu-id="a3fda-114">When used in a method's parameter list, the `ref` keyword indicates that an argument is passed by reference, not by value.</span></span> <span data-ttu-id="a3fda-115">`ref` 关键字让形参成为实参的别名，这必须是变量。</span><span class="sxs-lookup"><span data-stu-id="a3fda-115">The `ref` keyword makes the formal parameter an alias for the argument, which must be a variable.</span></span> <span data-ttu-id="a3fda-116">换而言之，对形参执行的任何操作都是对实参执行的。</span><span class="sxs-lookup"><span data-stu-id="a3fda-116">In other words, any operation on the parameter is made on the argument.</span></span> <span data-ttu-id="a3fda-117">例如，如果调用方传递本地变量表达式或数组元素访问表达式，所调用方法会替换 ref 参数引用的对象，然后，当该方法返回时，调用方的本地变量或数组元素将开始引用新对象。</span><span class="sxs-lookup"><span data-stu-id="a3fda-117">For example, if the caller passes a local variable expression or an array element access expression, and the called method replaces the object to which the ref parameter refers, then the caller's local variable or the array element now refers to the new object when the method returns.</span></span>

> [!NOTE]
> <span data-ttu-id="a3fda-118">不要混淆通过引用传递的概念与引用类型的概念。</span><span class="sxs-lookup"><span data-stu-id="a3fda-118">Do not confuse the concept of passing by reference with the concept of reference types.</span></span> <span data-ttu-id="a3fda-119">这两种概念是不同的。</span><span class="sxs-lookup"><span data-stu-id="a3fda-119">The two concepts are not the same.</span></span> <span data-ttu-id="a3fda-120">无论方法参数是值类型还是引用类型，均可由 `ref` 修改。</span><span class="sxs-lookup"><span data-stu-id="a3fda-120">A method parameter can be modified by `ref` regardless of whether it is a value type or a reference type.</span></span> <span data-ttu-id="a3fda-121">当通过引用传递时，不会对值类型装箱。</span><span class="sxs-lookup"><span data-stu-id="a3fda-121">There is no boxing of a value type when it is passed by reference.</span></span>  

<span data-ttu-id="a3fda-122">若要使用 `ref` 参数，方法定义和调用方法均必须显式使用 `ref` 关键字，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="a3fda-122">To use a `ref` parameter, both the method definition and the calling method must explicitly use the `ref` keyword, as shown in the following example.</span></span>  

[!code-csharp-interactive[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#1)]

<span data-ttu-id="a3fda-123">传递到 `ref` 或 `in` 形参的实参必须先经过初始化，然后才能传递。</span><span class="sxs-lookup"><span data-stu-id="a3fda-123">An argument that is passed to a `ref` or `in` parameter must be initialized before it is passed.</span></span> <span data-ttu-id="a3fda-124">这与 [out](out-parameter-modifier.md) 形参不同，在传递之前，不需要显式初始化该形参的实参。</span><span class="sxs-lookup"><span data-stu-id="a3fda-124">This differs from [out](out-parameter-modifier.md) parameters, whose arguments do not have to be explicitly initialized before they are passed.</span></span>

<span data-ttu-id="a3fda-125">类的成员不能具有仅在 `ref`、`in` 或 `out` 方面不同的签名。</span><span class="sxs-lookup"><span data-stu-id="a3fda-125">Members of a class can't have signatures that differ only by `ref`, `in`, or `out`.</span></span> <span data-ttu-id="a3fda-126">如果类型的两个成员之间的唯一区别在于其中一个具有 `ref` 参数，而另一个具有 `out` 或 `in` 参数，则会发生编译器错误。</span><span class="sxs-lookup"><span data-stu-id="a3fda-126">A compiler error occurs if the only difference between two members of a type is that one of them has a `ref` parameter and the other has an `out`, or `in` parameter.</span></span> <span data-ttu-id="a3fda-127">例如，以下代码将不会编译。</span><span class="sxs-lookup"><span data-stu-id="a3fda-127">The following code, for example, doesn't compile.</span></span>  

```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded
    // methods that differ only on ref and out".
    public void SampleMethod(out int i) { }
    public void SampleMethod(ref int i) { }
}
```

<span data-ttu-id="a3fda-128">但是，当一个方法具有 `ref`、`in` 或 `out` 参数，另一个方法具有值参数时，则可以重载方法，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="a3fda-128">However, methods can be overloaded when one method has a `ref`, `in`, or `out` parameter and the other has a value parameter, as shown in the following example.</span></span>
  
[!code-csharp[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#2)]
  
 <span data-ttu-id="a3fda-129">在其他要求签名匹配的情况下（如隐藏或重写），`in`、`ref` 和 `out` 是签名的一部分，相互之间不匹配。</span><span class="sxs-lookup"><span data-stu-id="a3fda-129">In other situations that require signature matching, such as hiding or overriding, `in`, `ref`, and `out` are part of the signature and don't match each other.</span></span>  
  
 <span data-ttu-id="a3fda-130">属性不是变量。</span><span class="sxs-lookup"><span data-stu-id="a3fda-130">Properties are not variables.</span></span> <span data-ttu-id="a3fda-131">它们是方法，不能传递到 `ref` 参数。</span><span class="sxs-lookup"><span data-stu-id="a3fda-131">They are methods, and cannot be passed to `ref` parameters.</span></span>  
  
 <span data-ttu-id="a3fda-132">不能将 `ref`、`in` 和 `out` 关键字用于以下几种方法：</span><span class="sxs-lookup"><span data-stu-id="a3fda-132">You can't use the `ref`, `in`, and `out` keywords for the following kinds of methods:</span></span>  
  
- <span data-ttu-id="a3fda-133">异步方法，通过使用 [async](async.md) 修饰符定义。</span><span class="sxs-lookup"><span data-stu-id="a3fda-133">Async methods, which you define by using the [async](async.md) modifier.</span></span>  
- <span data-ttu-id="a3fda-134">迭代器方法，包括 [yield return](yield.md) 或 `yield break` 语句。</span><span class="sxs-lookup"><span data-stu-id="a3fda-134">Iterator methods, which include a [yield return](yield.md) or `yield break` statement.</span></span>

<span data-ttu-id="a3fda-135">此外，[扩展方法](../../programming-guide/classes-and-structs/extension-methods.md)具有以下限制：</span><span class="sxs-lookup"><span data-stu-id="a3fda-135">In addition, [extension methods](../../programming-guide/classes-and-structs/extension-methods.md) have the following restrictions:</span></span>

- <span data-ttu-id="a3fda-136">不能对扩展方法的第一个参数使用 `out` 关键字。</span><span class="sxs-lookup"><span data-stu-id="a3fda-136">The `out` keyword cannot be used on the first argument of an extension method.</span></span>
- <span data-ttu-id="a3fda-137">当参数不是结构或是不被约束为结构的泛型类型时，不能对扩展方法的第一个参数使用 `ref` 关键字。</span><span class="sxs-lookup"><span data-stu-id="a3fda-137">The `ref` keyword cannot be used on the first argument of an extension method when the argument is not a struct, or a generic type not constrained to be a struct.</span></span>
- <span data-ttu-id="a3fda-138">除非第一个参数是结构，否则不能使用 `in` 关键字。</span><span class="sxs-lookup"><span data-stu-id="a3fda-138">The `in` keyword cannot be used unless the first argument is a struct.</span></span> <span data-ttu-id="a3fda-139">即使约束为结构，也不能对任何泛型类型使用 `in` 关键字。</span><span class="sxs-lookup"><span data-stu-id="a3fda-139">The `in` keyword cannot be used on any generic type, even when constrained to be a struct.</span></span>

## <a name="passing-an-argument-by-reference-an-example"></a><span data-ttu-id="a3fda-140">按引用传递参数：示例</span><span class="sxs-lookup"><span data-stu-id="a3fda-140">Passing an argument by reference: An example</span></span>

<span data-ttu-id="a3fda-141">前面的示例按引用传递值类型。</span><span class="sxs-lookup"><span data-stu-id="a3fda-141">The previous examples pass value types by reference.</span></span> <span data-ttu-id="a3fda-142">还可使用 `ref` 关键字按引用传递引用类型。</span><span class="sxs-lookup"><span data-stu-id="a3fda-142">You can also use the `ref` keyword to pass reference types by reference.</span></span> <span data-ttu-id="a3fda-143">按引用传递引用类型使所调用方能够替换调用方中引用参数引用的对象。</span><span class="sxs-lookup"><span data-stu-id="a3fda-143">Passing a reference type by reference enables the called method to replace the object to which the reference parameter refers in the caller.</span></span> <span data-ttu-id="a3fda-144">对象的存储位置按引用参数的值传递到方法。</span><span class="sxs-lookup"><span data-stu-id="a3fda-144">The storage location of the object is passed to the method as the value of the reference parameter.</span></span> <span data-ttu-id="a3fda-145">如果更改参数存储位置中的值（以指向新对象），你还可以将存储位置更改为调用方所引用的位置。</span><span class="sxs-lookup"><span data-stu-id="a3fda-145">If you change the value in the storage location of the parameter (to point to a new object), you also change the storage location to which the caller refers.</span></span> <span data-ttu-id="a3fda-146">下面的示例将引用类型的实例作为 `ref` 参数传递。</span><span class="sxs-lookup"><span data-stu-id="a3fda-146">The following example passes an instance of a reference type as a `ref` parameter.</span></span>
  
[!code-csharp[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#3)]

<span data-ttu-id="a3fda-147">有关如何通过值和引用传递引用类型的详细信息，请参阅[传递引用类型参数](../../programming-guide/classes-and-structs/passing-reference-type-parameters.md)。</span><span class="sxs-lookup"><span data-stu-id="a3fda-147">For more information about how to pass reference types by value and by reference, see [Passing Reference-Type Parameters](../../programming-guide/classes-and-structs/passing-reference-type-parameters.md).</span></span>
  
## <a name="reference-return-values"></a><span data-ttu-id="a3fda-148">引用返回值</span><span class="sxs-lookup"><span data-stu-id="a3fda-148">Reference return values</span></span>

<span data-ttu-id="a3fda-149">引用返回值（或 ref 返回值）是由方法按引用向调用方返回的值。</span><span class="sxs-lookup"><span data-stu-id="a3fda-149">Reference return values (or ref returns) are values that a method returns by reference to the caller.</span></span> <span data-ttu-id="a3fda-150">即是说，调用方可以修改方法所返回的值，此更改反映在包含方法的对象的状态中。</span><span class="sxs-lookup"><span data-stu-id="a3fda-150">That is, the caller can modify the value returned by a method, and that change is reflected in the state of the object that contains the method.</span></span>

<span data-ttu-id="a3fda-151">使用 `ref` 关键字来定义引用返回值：</span><span class="sxs-lookup"><span data-stu-id="a3fda-151">A reference return value is defined by using the `ref` keyword:</span></span>

- <span data-ttu-id="a3fda-152">在方法签名中。</span><span class="sxs-lookup"><span data-stu-id="a3fda-152">In the method signature.</span></span> <span data-ttu-id="a3fda-153">例如，下列方法签名指示 `GetCurrentPrice` 方法按引用返回了 <xref:System.Decimal> 值。</span><span class="sxs-lookup"><span data-stu-id="a3fda-153">For example, the following method signature indicates that the `GetCurrentPrice` method returns a <xref:System.Decimal> value by reference.</span></span>

```csharp
public ref decimal GetCurrentPrice()
```

- <span data-ttu-id="a3fda-154">在 `return` 标记和方法的 `return` 语句中返回的变量之间。</span><span class="sxs-lookup"><span data-stu-id="a3fda-154">Between the `return` token and the variable returned in a `return` statement in the method.</span></span> <span data-ttu-id="a3fda-155">例如：</span><span class="sxs-lookup"><span data-stu-id="a3fda-155">For example:</span></span>

```csharp
return ref DecimalArray[0];
```

<span data-ttu-id="a3fda-156">为方便调用方修改对象的状态，引用返回值必须存储在被显式定义为 [ref 局部变量](#ref-locals)的变量中。</span><span class="sxs-lookup"><span data-stu-id="a3fda-156">In order for the caller to modify the object's state, the reference return value must be stored to a variable that is explicitly defined as a [ref local](#ref-locals).</span></span>

<span data-ttu-id="a3fda-157">所调用方法还可能会将返回值声明为 `ref readonly` 以按引用返回值，并坚持调用代码无法修改返回的值。</span><span class="sxs-lookup"><span data-stu-id="a3fda-157">The called method may also declare the return value as `ref readonly` to return the value by reference, and enforce that the calling code cannot modify the returned value.</span></span> <span data-ttu-id="a3fda-158">调用方法可以通过将返回的值存储在本地 [ref readonly](#ref-readonly-locals) 变量中来避免复制该值。</span><span class="sxs-lookup"><span data-stu-id="a3fda-158">The calling method can avoid copying the returned valued by storing the value in a local [ref readonly](#ref-readonly-locals) variable.</span></span>

<span data-ttu-id="a3fda-159">有关示例，请参阅 [ref 返回值和 ref 局部变量示例](#a-ref-returns-and-ref-locals-example)。</span><span class="sxs-lookup"><span data-stu-id="a3fda-159">For an example, see [A ref returns and ref locals example](#a-ref-returns-and-ref-locals-example).</span></span>

## <a name="ref-locals"></a><span data-ttu-id="a3fda-160">ref 局部变量</span><span class="sxs-lookup"><span data-stu-id="a3fda-160">Ref locals</span></span>

<span data-ttu-id="a3fda-161">ref 局部变量用于指代使用 `return ref` 返回的值。</span><span class="sxs-lookup"><span data-stu-id="a3fda-161">A ref local variable is used to refer to values returned using `return ref`.</span></span> <span data-ttu-id="a3fda-162">无法将 ref 局部变量初始化为非 ref 返回值。</span><span class="sxs-lookup"><span data-stu-id="a3fda-162">A ref local variable cannot be initialized to a non-ref return value.</span></span> <span data-ttu-id="a3fda-163">也就是说，初始化的右侧必须为引用。</span><span class="sxs-lookup"><span data-stu-id="a3fda-163">In other words, the right-hand side of the initialization must be a reference.</span></span> <span data-ttu-id="a3fda-164">任何对 ref 本地变量值的修改都将反映在对象的状态中，该对象的方法按引用返回值。</span><span class="sxs-lookup"><span data-stu-id="a3fda-164">Any modifications to the value of the ref local are reflected in the state of the object whose method returned the value by reference.</span></span>

<span data-ttu-id="a3fda-165">在变量声明前或在方法（该方法将按引用返回值）调用前使用 `ref` 关键字定义 ref 局部变量。</span><span class="sxs-lookup"><span data-stu-id="a3fda-165">You define a ref local by using the `ref` keyword before the variable declaration, as well as immediately before the call to the method that returns the value by reference.</span></span>

<span data-ttu-id="a3fda-166">例如，下列语句定义名为 `GetEstimatedValue` 的方法返回的 ref 局部变量值：</span><span class="sxs-lookup"><span data-stu-id="a3fda-166">For example, the following statement defines a ref local value that is returned by a method named `GetEstimatedValue`:</span></span>

```csharp
ref decimal estValue = ref Building.GetEstimatedValue();
```

<span data-ttu-id="a3fda-167">可通过相同方式按引用访问值。</span><span class="sxs-lookup"><span data-stu-id="a3fda-167">You can access a value by reference in the same way.</span></span> <span data-ttu-id="a3fda-168">在某些情况下，按引用访问值可避免潜在的高开销复制操作，从而提高性能。</span><span class="sxs-lookup"><span data-stu-id="a3fda-168">In some cases, accessing a value by reference increases performance by avoiding a potentially expensive copy operation.</span></span> <span data-ttu-id="a3fda-169">例如，以下语句显示用户可如何定义一个用于引用值的 ref 局部变量值。</span><span class="sxs-lookup"><span data-stu-id="a3fda-169">For example, the following statement shows how one can define a ref local value that is used to reference a value.</span></span>

```csharp
ref VeryLargeStruct reflocal = ref veryLargeStruct;
```

<span data-ttu-id="a3fda-170">在这两个示例中，必须在两个位置同时使用 `ref` 关键字，否则编译器将生成错误 CS8172：“无法使用值对按引用变量进行初始化”。</span><span class="sxs-lookup"><span data-stu-id="a3fda-170">In both examples the `ref` keyword must be used in both places, or the compiler generates error CS8172, "Cannot initialize a by-reference variable with a value."</span></span>

<span data-ttu-id="a3fda-171">从 C# 7.3 开始，`foreach` 语句的迭代变量可以是 ref local 变量，也可以是 ref readonly local 变量。</span><span class="sxs-lookup"><span data-stu-id="a3fda-171">Beginning with C# 7.3, the iteration variable of the `foreach` statement can be ref local or ref readonly local variable.</span></span> <span data-ttu-id="a3fda-172">有关详细信息，请参阅 [foreach 语句](foreach-in.md)一文。</span><span class="sxs-lookup"><span data-stu-id="a3fda-172">For more information, see the [foreach statement](foreach-in.md) article.</span></span>

<span data-ttu-id="a3fda-173">此外，从 C# 7.3 开始，可以使用 [ref 赋值运算符](../operators/assignment-operator.md#ref-assignment-operator)重新分配 ref local 或 ref readonly local 变量。</span><span class="sxs-lookup"><span data-stu-id="a3fda-173">Also beginning with C# 7.3, you can reassign a ref local or ref readonly local variable with the [ref assignment operator](../operators/assignment-operator.md#ref-assignment-operator).</span></span>

## <a name="ref-readonly-locals"></a><span data-ttu-id="a3fda-174">Ref readonly 局部变量</span><span class="sxs-lookup"><span data-stu-id="a3fda-174">Ref readonly locals</span></span>

<span data-ttu-id="a3fda-175">Ref readonly 局部变量用于指代在其签名中具有 `ref readonly` 并使用 `return ref` 的方法或属性返回的值。</span><span class="sxs-lookup"><span data-stu-id="a3fda-175">A ref readonly local is used to refer to values returned by the method or property that has `ref readonly` in its signature and uses `return ref`.</span></span> <span data-ttu-id="a3fda-176">`ref readonly` 变量将 `ref` 本地变量的属性与 `readonly` 变量结合使用：它是所分配到的存储的别名，且无法修改。</span><span class="sxs-lookup"><span data-stu-id="a3fda-176">A `ref readonly` variable combines the properties of a `ref` local variable with a `readonly` variable: it is an alias to the storage it's assigned to, and it cannot be modified.</span></span>

## <a name="a-ref-returns-and-ref-locals-example"></a><span data-ttu-id="a3fda-177">ref 返回值和 ref 局部变量示例</span><span class="sxs-lookup"><span data-stu-id="a3fda-177">A ref returns and ref locals example</span></span>

<span data-ttu-id="a3fda-178">下列示例定义一个具有两个 <xref:System.String> 字段（`Title` 和 `Author`）的 `Book` 类。</span><span class="sxs-lookup"><span data-stu-id="a3fda-178">The following example defines a `Book` class that has two <xref:System.String> fields, `Title` and `Author`.</span></span> <span data-ttu-id="a3fda-179">还定义包含 `Book` 对象的专用数组的 `BookCollection` 类。</span><span class="sxs-lookup"><span data-stu-id="a3fda-179">It also defines a `BookCollection` class that includes a private array of `Book` objects.</span></span> <span data-ttu-id="a3fda-180">通过调用 `GetBookByTitle` 方法，可按引用返回个别 book 对象。</span><span class="sxs-lookup"><span data-stu-id="a3fda-180">Individual book objects are returned by reference by calling its `GetBookByTitle` method.</span></span>

[!code-csharp[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#4)]

<span data-ttu-id="a3fda-181">调用方将 `GetBookByTitle` 方法所返回的值存储为 ref 局部变量时，调用方对返回值所做的更改将反映在 `BookCollection` 对象中，如下例所示。</span><span class="sxs-lookup"><span data-stu-id="a3fda-181">When the caller stores the value returned by the `GetBookByTitle` method as a ref local, changes that the caller makes to the return value are reflected in the `BookCollection` object, as the following example shows.</span></span>

[!code-csharp[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#5)]

## <a name="ref-struct-types"></a><span data-ttu-id="a3fda-182">Ref 结构类型</span><span class="sxs-lookup"><span data-stu-id="a3fda-182">Ref struct types</span></span>

<span data-ttu-id="a3fda-183">将 `ref` 修饰符添加到 `struct` 声明定义了该类型的实例必须为堆栈分配。</span><span class="sxs-lookup"><span data-stu-id="a3fda-183">Adding the `ref` modifier to a `struct` declaration defines that instances of that type must be stack allocated.</span></span> <span data-ttu-id="a3fda-184">换言之，永远不能在作为另一类的成员的堆上创建这些类型的实例。</span><span class="sxs-lookup"><span data-stu-id="a3fda-184">In other words, instances of these types can never be created on the heap as a member of another class.</span></span> <span data-ttu-id="a3fda-185">此功能的主要动机是 <xref:System.Span%601> 和相关结构。</span><span class="sxs-lookup"><span data-stu-id="a3fda-185">The primary motivation for this feature was <xref:System.Span%601> and related structures.</span></span>

<span data-ttu-id="a3fda-186">保持 `ref struct` 类型作为堆栈分配的变量的目标引入了几条编译器针对所有 `ref struct` 类型强制执行的规则。</span><span class="sxs-lookup"><span data-stu-id="a3fda-186">The goal of keeping a `ref struct` type as a stack-allocated variable introduces several rules that the compiler enforces for all `ref struct` types.</span></span>

- <span data-ttu-id="a3fda-187">不能对 `ref struct` 装箱。</span><span class="sxs-lookup"><span data-stu-id="a3fda-187">You can't box a `ref struct`.</span></span> <span data-ttu-id="a3fda-188">无法向属于 `object`、`dynamic` 或任何接口类型的变量分配 `ref struct` 类型。</span><span class="sxs-lookup"><span data-stu-id="a3fda-188">You cannot assign a `ref struct` type to a variable of type `object`, `dynamic`, or any interface type.</span></span>
- <span data-ttu-id="a3fda-189">`ref struct` 类型不能实现接口。</span><span class="sxs-lookup"><span data-stu-id="a3fda-189">`ref struct` types cannot implement interfaces.</span></span>
- <span data-ttu-id="a3fda-190">不能将 `ref struct` 声明为类或常规结构的字段成员。</span><span class="sxs-lookup"><span data-stu-id="a3fda-190">You can't declare a `ref struct` as a field member of a class or a normal struct.</span></span> <span data-ttu-id="a3fda-191">这包括声明自动实现的属性，后者会创建一个由编译器生成的支持字段。</span><span class="sxs-lookup"><span data-stu-id="a3fda-191">This includes declaring an auto-implemented property, which creates a compiler-generated backing field.</span></span>
- <span data-ttu-id="a3fda-192">不能声明异步方法中属于 `ref struct` 类型的本地变量。</span><span class="sxs-lookup"><span data-stu-id="a3fda-192">You cannot declare local variables that are `ref struct` types in async methods.</span></span> <span data-ttu-id="a3fda-193">不能在返回类似 <xref:System.Threading.Tasks.Task>、<xref:System.Threading.Tasks.Task%601> 或 `Task` 类型的同步方法中声明它们。</span><span class="sxs-lookup"><span data-stu-id="a3fda-193">You can declare them in synchronous methods that return <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601>, or `Task`-like types.</span></span>
- <span data-ttu-id="a3fda-194">无法在迭代器中声明 `ref struct` 本地变量。</span><span class="sxs-lookup"><span data-stu-id="a3fda-194">You cannot declare `ref struct` local variables in iterators.</span></span>
- <span data-ttu-id="a3fda-195">无法捕获 Lambda 表达式或本地函数中的 `ref struct` 变量。</span><span class="sxs-lookup"><span data-stu-id="a3fda-195">You cannot capture `ref struct` variables in lambda expressions or local functions.</span></span>

<span data-ttu-id="a3fda-196">这些限制可确保不会以可提升至托管堆的方式意外地使用 `ref struct`。</span><span class="sxs-lookup"><span data-stu-id="a3fda-196">These restrictions ensure you don't accidentally use a `ref struct` in a manner that could promote it to the managed heap.</span></span>

<span data-ttu-id="a3fda-197">可以组合修饰符以将结构声明为 `readonly ref`。</span><span class="sxs-lookup"><span data-stu-id="a3fda-197">You can combine modifiers to declare a struct as `readonly ref`.</span></span> <span data-ttu-id="a3fda-198">`readonly ref struct` 兼具 `ref struct` 和 `readonly struct` 声明的优点和限制。</span><span class="sxs-lookup"><span data-stu-id="a3fda-198">A `readonly ref struct` combines the benefits and restrictions of `ref struct` and `readonly struct` declarations.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="a3fda-199">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="a3fda-199">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a3fda-200">请参阅</span><span class="sxs-lookup"><span data-stu-id="a3fda-200">See also</span></span>

- [<span data-ttu-id="a3fda-201">编写安全高效的代码</span><span class="sxs-lookup"><span data-stu-id="a3fda-201">Write safe efficient code</span></span>](../../write-safe-efficient-code.md)
- [<span data-ttu-id="a3fda-202">ref 返回结果和局部变量</span><span class="sxs-lookup"><span data-stu-id="a3fda-202">Ref returns and ref locals</span></span>](../../programming-guide/classes-and-structs/ref-returns.md)
- [<span data-ttu-id="a3fda-203">条件 ref 表达式</span><span class="sxs-lookup"><span data-stu-id="a3fda-203">Conditional ref expression</span></span>](../operators/conditional-operator.md#conditional-ref-expression)
- [<span data-ttu-id="a3fda-204">传递参数</span><span class="sxs-lookup"><span data-stu-id="a3fda-204">Passing Parameters</span></span>](../../programming-guide/classes-and-structs/passing-parameters.md)
- [<span data-ttu-id="a3fda-205">方法参数</span><span class="sxs-lookup"><span data-stu-id="a3fda-205">Method Parameters</span></span>](method-parameters.md)
- [<span data-ttu-id="a3fda-206">C# 参考</span><span class="sxs-lookup"><span data-stu-id="a3fda-206">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="a3fda-207">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="a3fda-207">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="a3fda-208">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="a3fda-208">C# Keywords</span></span>](index.md)
