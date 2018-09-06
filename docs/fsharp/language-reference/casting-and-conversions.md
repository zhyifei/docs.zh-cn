---
title: 强制转换和转换 (F#)
description: '了解如何 F # 编程语言提供转换运算符的各种基元类型之间的算术转换。'
ms.date: 05/16/2016
ms.openlocfilehash: aca1a2523130ee485a7e7c9a6a45a410904cb246
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2018
ms.locfileid: "43784538"
---
# <a name="casting-and-conversions-f"></a><span data-ttu-id="ebf1e-103">强制转换和转换 (F#)</span><span class="sxs-lookup"><span data-stu-id="ebf1e-103">Casting and Conversions (F#)</span></span>

<span data-ttu-id="ebf1e-104">本主题介绍对 F # 中的类型转换的支持。</span><span class="sxs-lookup"><span data-stu-id="ebf1e-104">This topic describes support for type conversions in F#.</span></span>

## <a name="arithmetic-types"></a><span data-ttu-id="ebf1e-105">算术类型</span><span class="sxs-lookup"><span data-stu-id="ebf1e-105">Arithmetic Types</span></span>

<span data-ttu-id="ebf1e-106">F # 提供转换运算符各种基元类型之间的算术转换如整数和浮点类型之间。</span><span class="sxs-lookup"><span data-stu-id="ebf1e-106">F# provides conversion operators for arithmetic conversions between various primitive types, such as between integer and floating point types.</span></span> <span data-ttu-id="ebf1e-107">整型和 char 转换运算符具有选中和取消选中窗体;浮点运算符和`enum`转换运算符不这样做。</span><span class="sxs-lookup"><span data-stu-id="ebf1e-107">The integral and char conversion operators have checked and unchecked forms; the floating point operators and the `enum` conversion operator do not.</span></span> <span data-ttu-id="ebf1e-108">取消选中窗体中定义`Microsoft.FSharp.Core.Operators`并选中窗体中定义`Microsoft.FSharp.Core.Operators.Checked`。</span><span class="sxs-lookup"><span data-stu-id="ebf1e-108">The unchecked forms are defined in `Microsoft.FSharp.Core.Operators` and the checked forms are defined in `Microsoft.FSharp.Core.Operators.Checked`.</span></span> <span data-ttu-id="ebf1e-109">选中窗体溢出检查，并生成运行时异常，如果生成的值超出了目标类型的限制。</span><span class="sxs-lookup"><span data-stu-id="ebf1e-109">The checked forms check for overflow and generate a runtime exception if the resulting value exceeds the limits of the target type.</span></span>

<span data-ttu-id="ebf1e-110">每个运算符具有名称与目标类型的名称相同。</span><span class="sxs-lookup"><span data-stu-id="ebf1e-110">Each of these operators has the same name as the name of the destination type.</span></span> <span data-ttu-id="ebf1e-111">例如，在下面的代码，在其中的类型已显式批注，`byte`显示有两个不同的含义。</span><span class="sxs-lookup"><span data-stu-id="ebf1e-111">For example, in the following code, in which the types are explicitly annotated, `byte` appears with two different meanings.</span></span> <span data-ttu-id="ebf1e-112">第一个匹配项是类型，第二个是转换运算符。</span><span class="sxs-lookup"><span data-stu-id="ebf1e-112">The first occurrence is the type and the second is the conversion operator.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4401.fs)]

<span data-ttu-id="ebf1e-113">下表显示了 F # 中定义的转换运算符。</span><span class="sxs-lookup"><span data-stu-id="ebf1e-113">The following table shows conversion operators defined in F#.</span></span>

|<span data-ttu-id="ebf1e-114">运算符</span><span class="sxs-lookup"><span data-stu-id="ebf1e-114">Operator</span></span>|<span data-ttu-id="ebf1e-115">描述</span><span class="sxs-lookup"><span data-stu-id="ebf1e-115">Description</span></span>|
|--------|-----------|
|`byte`|<span data-ttu-id="ebf1e-116">将转换为字节，8 位无符号类型。</span><span class="sxs-lookup"><span data-stu-id="ebf1e-116">Convert to byte, an 8-bit unsigned type.</span></span>|
|`sbyte`|<span data-ttu-id="ebf1e-117">将转换为有符号字节。</span><span class="sxs-lookup"><span data-stu-id="ebf1e-117">Convert to signed byte.</span></span>|
|`int16`|<span data-ttu-id="ebf1e-118">将转换为 16 位有符号整数。</span><span class="sxs-lookup"><span data-stu-id="ebf1e-118">Convert to a 16-bit signed integer.</span></span>|
|`uint16`|<span data-ttu-id="ebf1e-119">将转换为 16 位无符号整数。</span><span class="sxs-lookup"><span data-stu-id="ebf1e-119">Convert to a 16-bit unsigned integer.</span></span>|
|`int32, int`|<span data-ttu-id="ebf1e-120">将转换为 32 位有符号整数。</span><span class="sxs-lookup"><span data-stu-id="ebf1e-120">Convert to a 32-bit signed integer.</span></span>|
|`uint32`|<span data-ttu-id="ebf1e-121">将转换为 32 位无符号整数。</span><span class="sxs-lookup"><span data-stu-id="ebf1e-121">Convert to a 32-bit unsigned integer.</span></span>|
|`int64`|<span data-ttu-id="ebf1e-122">将转换为 64 位有符号整数。</span><span class="sxs-lookup"><span data-stu-id="ebf1e-122">Convert to a 64-bit signed integer.</span></span>|
|`uint64`|<span data-ttu-id="ebf1e-123">将转换为 64 位无符号整数。</span><span class="sxs-lookup"><span data-stu-id="ebf1e-123">Convert to a 64-bit unsigned integer.</span></span>|
|`nativeint`|<span data-ttu-id="ebf1e-124">将转换为本机整数。</span><span class="sxs-lookup"><span data-stu-id="ebf1e-124">Convert to a native integer.</span></span>|
|`unativeint`|<span data-ttu-id="ebf1e-125">将转换为无符号本机整数。</span><span class="sxs-lookup"><span data-stu-id="ebf1e-125">Convert to an unsigned native integer.</span></span>|
|`float, double`|<span data-ttu-id="ebf1e-126">将转换为 64 位双精度 IEEE 浮点数。</span><span class="sxs-lookup"><span data-stu-id="ebf1e-126">Convert to a 64-bit double-precision IEEE floating point number.</span></span>|
|`float32, single`|<span data-ttu-id="ebf1e-127">将转换为 32 位单精度 IEEE 浮点数。</span><span class="sxs-lookup"><span data-stu-id="ebf1e-127">Convert to a 32-bit single-precision IEEE floating point number.</span></span>|
|`decimal`|<span data-ttu-id="ebf1e-128">将转换为`System.Decimal`。</span><span class="sxs-lookup"><span data-stu-id="ebf1e-128">Convert to `System.Decimal`.</span></span>|
|`char`|<span data-ttu-id="ebf1e-129">将转换为`System.Char`，Unicode 字符。</span><span class="sxs-lookup"><span data-stu-id="ebf1e-129">Convert to `System.Char`, a Unicode character.</span></span>|
|`enum`|<span data-ttu-id="ebf1e-130">将转换为枚举类型。</span><span class="sxs-lookup"><span data-stu-id="ebf1e-130">Convert to an enumerated type.</span></span>|
<span data-ttu-id="ebf1e-131">除了内置基元类型，可以实现的类型与使用这些运算符`op_Explicit`或`op_Implicit`的带有适当签名方法。</span><span class="sxs-lookup"><span data-stu-id="ebf1e-131">In addition to built-in primitive types, you can use these operators with types that implement `op_Explicit` or `op_Implicit` methods with appropriate signatures.</span></span> <span data-ttu-id="ebf1e-132">例如，`int`转换运算符适用于任何类型，它提供一种静态方法`op_Explicit`用于采用类型作为参数并返回`int`。</span><span class="sxs-lookup"><span data-stu-id="ebf1e-132">For example, the `int` conversion operator works with any type that provides a static method `op_Explicit` that takes the type as a parameter and returns `int`.</span></span> <span data-ttu-id="ebf1e-133">作为一般规则无法由返回类型重载方法一个特殊的例外，你可以这样做`op_Explicit`和`op_Implicit`。</span><span class="sxs-lookup"><span data-stu-id="ebf1e-133">As a special exception to the general rule that methods cannot be overloaded by return type, you can do this for `op_Explicit` and `op_Implicit`.</span></span>

## <a name="enumerated-types"></a><span data-ttu-id="ebf1e-134">枚举的类型</span><span class="sxs-lookup"><span data-stu-id="ebf1e-134">Enumerated Types</span></span>

<span data-ttu-id="ebf1e-135">`enum`运算符是采用一个表示的类型的类型参数的泛型运算符`enum`将转换为。</span><span class="sxs-lookup"><span data-stu-id="ebf1e-135">The `enum` operator is a generic operator that takes one type parameter that represents the type of the `enum` to convert to.</span></span> <span data-ttu-id="ebf1e-136">将转换为枚举类型，类型推理会尝试确定的类型`enum`想要将转换为。</span><span class="sxs-lookup"><span data-stu-id="ebf1e-136">When it converts to an enumerated type, type inference attempts to determine the type of the `enum` that you want to convert to.</span></span> <span data-ttu-id="ebf1e-137">在下面的示例中，变量`col1`未显式批注，但其类型推断从更高版本的相等性测试。</span><span class="sxs-lookup"><span data-stu-id="ebf1e-137">In the following example, the variable `col1` is not explicitly annotated, but its type is inferred from the later equality test.</span></span> <span data-ttu-id="ebf1e-138">因此，编译器可以推断出要转换为`Color`枚举。</span><span class="sxs-lookup"><span data-stu-id="ebf1e-138">Therefore, the compiler can deduce that you are converting to a `Color` enumeration.</span></span> <span data-ttu-id="ebf1e-139">或者，你可以提供一个类型批注，如同`col2`在下面的示例。</span><span class="sxs-lookup"><span data-stu-id="ebf1e-139">Alternatively, you can supply a type annotation, as with `col2` in the following example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4402.fs)]

<span data-ttu-id="ebf1e-140">您可以显式指定目标枚举类型，作为类型参数，如以下代码所示：</span><span class="sxs-lookup"><span data-stu-id="ebf1e-140">You can also specify the target enumeration type explicitly as a type parameter, as in the following code:</span></span>

```fsharp
let col3 = enum<Color> 3
```

<span data-ttu-id="ebf1e-141">请注意枚举转换工作，仅当枚举的基础类型是与要转换的类型兼容。</span><span class="sxs-lookup"><span data-stu-id="ebf1e-141">Note that the enumeration casts work only if the underlying type of the enumeration is compatible with the type being converted.</span></span> <span data-ttu-id="ebf1e-142">在下面的代码，则转换失败由于之间不匹配编译`int32`和`uint32`。</span><span class="sxs-lookup"><span data-stu-id="ebf1e-142">In the following code, the conversion fails to compile because of the mismatch between `int32` and `uint32`.</span></span>

```fsharp
// Error: types are incompatible
let col4 : Color = enum 2u
```

<span data-ttu-id="ebf1e-143">有关详细信息，请参阅[枚举](enumerations.md)。</span><span class="sxs-lookup"><span data-stu-id="ebf1e-143">For more information, see [Enumerations](enumerations.md).</span></span>

## <a name="casting-object-types"></a><span data-ttu-id="ebf1e-144">强制转换对象类型</span><span class="sxs-lookup"><span data-stu-id="ebf1e-144">Casting Object Types</span></span>

<span data-ttu-id="ebf1e-145">类型的对象层次结构之间的转换是面向对象的编程的基础。</span><span class="sxs-lookup"><span data-stu-id="ebf1e-145">Conversion between types in an object hierarchy is fundamental to object-oriented programming.</span></span> <span data-ttu-id="ebf1e-146">有两种基本类型的转换： 向上转换） 和向下转换）。</span><span class="sxs-lookup"><span data-stu-id="ebf1e-146">There are two basic types of conversions: casting up (upcasting) and casting down (downcasting).</span></span> <span data-ttu-id="ebf1e-147">强制转换的层次结构表示强制转换为基对象引用是派生的对象引用。</span><span class="sxs-lookup"><span data-stu-id="ebf1e-147">Casting up a hierarchy means casting from a derived object reference to a base object reference.</span></span> <span data-ttu-id="ebf1e-148">此类强制转换是能保证有效，前提是在派生类的继承层次结构中的类的基类。</span><span class="sxs-lookup"><span data-stu-id="ebf1e-148">Such a cast is guaranteed to work as long as the base class is in the inheritance hierarchy of the derived class.</span></span> <span data-ttu-id="ebf1e-149">按层次结构，从基对象引用为派生的对象引用，强制转换成功，仅当该对象实际上是正确的目标 （派生） 类型或派生自目标类型的类型的实例。</span><span class="sxs-lookup"><span data-stu-id="ebf1e-149">Casting down a hierarchy, from a base object reference to a derived object reference, succeeds only if the object actually is an instance of the correct destination (derived) type or a type derived from the destination type.</span></span>

<span data-ttu-id="ebf1e-150">F # 提供的这些类型的转换运算符。</span><span class="sxs-lookup"><span data-stu-id="ebf1e-150">F# provides operators for these types of conversions.</span></span> <span data-ttu-id="ebf1e-151">`:>`层次结构，向上转换运算符和`:?>`沿层次结构将转换运算符。</span><span class="sxs-lookup"><span data-stu-id="ebf1e-151">The `:>` operator casts up the hierarchy, and the `:?>` operator casts down the hierarchy.</span></span>

### <a name="upcasting"></a><span data-ttu-id="ebf1e-152">向上转换</span><span class="sxs-lookup"><span data-stu-id="ebf1e-152">Upcasting</span></span>

<span data-ttu-id="ebf1e-153">在许多面向对象语言中，向上转换是隐式;在 F # 中，规则略有不同。</span><span class="sxs-lookup"><span data-stu-id="ebf1e-153">In many object-oriented languages, upcasting is implicit; in F#, the rules are slightly different.</span></span> <span data-ttu-id="ebf1e-154">当你将参数传递到方法的对象类型上时，将自动应用向上转换。</span><span class="sxs-lookup"><span data-stu-id="ebf1e-154">Upcasting is applied automatically when you pass arguments to methods on an object type.</span></span> <span data-ttu-id="ebf1e-155">但是，对于在模块中的 let 绑定函数，向上转换不是自动的除非参数类型被声明为灵活的类型。</span><span class="sxs-lookup"><span data-stu-id="ebf1e-155">However, for let-bound functions in a module, upcasting is not automatic, unless the parameter type is declared as a flexible type.</span></span> <span data-ttu-id="ebf1e-156">有关详细信息，请参阅[可变类型](flexible-Types.md)。</span><span class="sxs-lookup"><span data-stu-id="ebf1e-156">For more information, see [Flexible Types](flexible-Types.md).</span></span>

<span data-ttu-id="ebf1e-157">`:>`运算符执行静态强制转换，这意味着在编译时确定转换是否成功。</span><span class="sxs-lookup"><span data-stu-id="ebf1e-157">The `:>` operator performs a static cast, which means that the success of the cast is determined at compile time.</span></span> <span data-ttu-id="ebf1e-158">如果使用的强制转换`:>`编译成功，它是有效的转换，在运行时有无故障的可能性。</span><span class="sxs-lookup"><span data-stu-id="ebf1e-158">If a cast that uses `:>` compiles successfully, it is a valid cast and has no chance of failure at run time.</span></span>

<span data-ttu-id="ebf1e-159">此外可以使用`upcast`运算符来执行此类转换。</span><span class="sxs-lookup"><span data-stu-id="ebf1e-159">You can also use the `upcast` operator to perform such a conversion.</span></span> <span data-ttu-id="ebf1e-160">以下表达式指定层次结构向上转换：</span><span class="sxs-lookup"><span data-stu-id="ebf1e-160">The following expression specifies a conversion up the hierarchy:</span></span>

```fsharp
upcast expression
```

<span data-ttu-id="ebf1e-161">当使用向上转换运算符时，编译器将尝试推断上下文中将转换为的类型。</span><span class="sxs-lookup"><span data-stu-id="ebf1e-161">When you use the upcast operator, the compiler attempts to infer the type you are converting to from the context.</span></span> <span data-ttu-id="ebf1e-162">如果编译器无法确定目标类型，编译器会报告错误。</span><span class="sxs-lookup"><span data-stu-id="ebf1e-162">If the compiler is unable to determine the target type, the compiler reports an error.</span></span>

### <a name="downcasting"></a><span data-ttu-id="ebf1e-163">向下转换</span><span class="sxs-lookup"><span data-stu-id="ebf1e-163">Downcasting</span></span>

<span data-ttu-id="ebf1e-164">`:?>`运算符执行动态强制转换，这意味着在运行时确定转换是否成功。</span><span class="sxs-lookup"><span data-stu-id="ebf1e-164">The `:?>` operator performs a dynamic cast, which means that the success of the cast is determined at run time.</span></span> <span data-ttu-id="ebf1e-165">使用强制转换`:?>`运算符不检查在编译时; 但在运行时，尝试将强制转换为指定的类型。</span><span class="sxs-lookup"><span data-stu-id="ebf1e-165">A cast that uses the `:?>` operator is not checked at compile time; but at run time, an attempt is made to cast to the specified type.</span></span> <span data-ttu-id="ebf1e-166">如果对象是与目标类型兼容，强制转换会成功。</span><span class="sxs-lookup"><span data-stu-id="ebf1e-166">If the object is compatible with the target type, the cast succeeds.</span></span> <span data-ttu-id="ebf1e-167">如果对象不是与目标类型兼容的运行时将引发`InvalidCastException`。</span><span class="sxs-lookup"><span data-stu-id="ebf1e-167">If the object is not compatible with the target type, the runtime raises an `InvalidCastException`.</span></span>

<span data-ttu-id="ebf1e-168">此外可以使用`downcast`运算符来执行动态类型转换。</span><span class="sxs-lookup"><span data-stu-id="ebf1e-168">You can also use the `downcast` operator to perform a dynamic type conversion.</span></span> <span data-ttu-id="ebf1e-169">以下表达式指定沿层次结构从程序上下文中推断出的类型的转换：</span><span class="sxs-lookup"><span data-stu-id="ebf1e-169">The following expression specifies a conversion down the hierarchy to a type that is inferred from program context:</span></span>

```fsharp
downcast expression
```

<span data-ttu-id="ebf1e-170">同样适用于`upcast`运算符，如果编译器无法推断特定的目标类型从上下文，它将报告错误。</span><span class="sxs-lookup"><span data-stu-id="ebf1e-170">As for the `upcast` operator, if the compiler cannot infer a specific target type from the context, it reports an error.</span></span>

<span data-ttu-id="ebf1e-171">下面的代码演示如何使用`:>`和`:?>`运算符。</span><span class="sxs-lookup"><span data-stu-id="ebf1e-171">The following code illustrates the use of the `:>` and `:?>` operators.</span></span> <span data-ttu-id="ebf1e-172">该代码演示`:?>`您知道，转换将失败，因为它会引发，最好使用运算符`InvalidCastException`如果转换失败。</span><span class="sxs-lookup"><span data-stu-id="ebf1e-172">The code illustrates that the `:?>` operator is best used when you know that conversion will succeed, because it throws `InvalidCastException` if the conversion fails.</span></span> <span data-ttu-id="ebf1e-173">如果不知道，转换会成功，使用的类型测试`match`表达式是更好的因为它可以避免生成异常的开销。</span><span class="sxs-lookup"><span data-stu-id="ebf1e-173">If you do not know that a conversion will succeed, a type test that uses a `match` expression is better because it avoids the overhead of generating an exception.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4403.fs)]

<span data-ttu-id="ebf1e-174">因为泛型运算符`downcast`和`upcast`依赖类型推断来确定自变量和返回类型，在上面的代码，您可以替换</span><span class="sxs-lookup"><span data-stu-id="ebf1e-174">Because generic operators `downcast` and `upcast` rely on type inference to determine the argument and return type, in the above code, you can replace</span></span>

```fsharp
let base1 = d1 :> Base1
```

<span data-ttu-id="ebf1e-175">替换为</span><span class="sxs-lookup"><span data-stu-id="ebf1e-175">with</span></span>

```fsharp
let base1 = upcast d1
```

<span data-ttu-id="ebf1e-176">在上面的代码中的参数类型和返回类型是`Derived1`和`Base1`分别。</span><span class="sxs-lookup"><span data-stu-id="ebf1e-176">In the previous code, the argument type and return types are `Derived1` and `Base1`, respectively.</span></span>

<span data-ttu-id="ebf1e-177">类型测试的详细信息，请参阅[匹配表达式](match-Expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="ebf1e-177">For more information about type tests, see [Match Expressions](match-Expressions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ebf1e-178">请参阅</span><span class="sxs-lookup"><span data-stu-id="ebf1e-178">See also</span></span>

- [<span data-ttu-id="ebf1e-179">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="ebf1e-179">F# Language Reference</span></span>](index.md)
