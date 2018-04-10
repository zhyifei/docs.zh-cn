---
title: 强制转换和转换 (F#)
description: '了解如何 F # 编程语言提供转换运算符的各种基元类型之间的算术转换。'
keywords: visual f#, f#, 函数编程
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: db30db67-da21-4206-bf0c-9211bd3cb22f
ms.openlocfilehash: df8352b0dd8651f1480515311454a218ea79b971
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2018
---
# <a name="casting-and-conversions-f"></a><span data-ttu-id="40ee9-104">强制转换和转换 (F#)</span><span class="sxs-lookup"><span data-stu-id="40ee9-104">Casting and Conversions (F#)</span></span>

<span data-ttu-id="40ee9-105">本主题介绍对 F # 中的类型转换的支持。</span><span class="sxs-lookup"><span data-stu-id="40ee9-105">This topic describes support for type conversions in F#.</span></span>

## <a name="arithmetic-types"></a><span data-ttu-id="40ee9-106">算术类型</span><span class="sxs-lookup"><span data-stu-id="40ee9-106">Arithmetic Types</span></span>
<span data-ttu-id="40ee9-107">F # 提供了转换运算符算术之间的转换各种基元类型，如整数和浮点类型之间。</span><span class="sxs-lookup"><span data-stu-id="40ee9-107">F# provides conversion operators for arithmetic conversions between various primitive types, such as between integer and floating point types.</span></span> <span data-ttu-id="40ee9-108">整型和 char 转换运算符已选中和取消选中窗体;浮点运算符和`enum`转换运算符不这样做。</span><span class="sxs-lookup"><span data-stu-id="40ee9-108">The integral and char conversion operators have checked and unchecked forms; the floating point operators and the `enum` conversion operator do not.</span></span> <span data-ttu-id="40ee9-109">未选中的表单定义中`Microsoft.FSharp.Core.Operators`和检查的形式定义在`Microsoft.FSharp.Core.Operators.Checked`。</span><span class="sxs-lookup"><span data-stu-id="40ee9-109">The unchecked forms are defined in `Microsoft.FSharp.Core.Operators` and the checked forms are defined in `Microsoft.FSharp.Core.Operators.Checked`.</span></span> <span data-ttu-id="40ee9-110">选中窗体溢出检查，并生成运行时异常，如果生成的值超出目标类型的限制。</span><span class="sxs-lookup"><span data-stu-id="40ee9-110">The checked forms check for overflow and generate a runtime exception if the resulting value exceeds the limits of the target type.</span></span>

<span data-ttu-id="40ee9-111">每个这些运算符具有相同名称作为目标类型的名称。</span><span class="sxs-lookup"><span data-stu-id="40ee9-111">Each of these operators has the same name as the name of the destination type.</span></span> <span data-ttu-id="40ee9-112">例如，在下面的代码，在其中的类型已显式批注，`byte`随即出现，两个不同的含义。</span><span class="sxs-lookup"><span data-stu-id="40ee9-112">For example, in the following code, in which the types are explicitly annotated, `byte` appears with two different meanings.</span></span> <span data-ttu-id="40ee9-113">第一个匹配项的类型，第二个是转换运算符。</span><span class="sxs-lookup"><span data-stu-id="40ee9-113">The first occurrence is the type and the second is the conversion operator.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4401.fs)]

<span data-ttu-id="40ee9-114">下表显示 F # 中定义的转换运算符。</span><span class="sxs-lookup"><span data-stu-id="40ee9-114">The following table shows conversion operators defined in F#.</span></span>

|<span data-ttu-id="40ee9-115">运算符</span><span class="sxs-lookup"><span data-stu-id="40ee9-115">Operator</span></span>|<span data-ttu-id="40ee9-116">描述</span><span class="sxs-lookup"><span data-stu-id="40ee9-116">Description</span></span>|
|--------|-----------|
|`byte`|<span data-ttu-id="40ee9-117">将转换为字节，8 位无符号类型。</span><span class="sxs-lookup"><span data-stu-id="40ee9-117">Convert to byte, an 8-bit unsigned type.</span></span>|
|`sbyte`|<span data-ttu-id="40ee9-118">将转换为有符号字节。</span><span class="sxs-lookup"><span data-stu-id="40ee9-118">Convert to signed byte.</span></span>|
|`int16`|<span data-ttu-id="40ee9-119">将转换为 16 位有符号整数。</span><span class="sxs-lookup"><span data-stu-id="40ee9-119">Convert to a 16-bit signed integer.</span></span>|
|`uint16`|<span data-ttu-id="40ee9-120">将转换为 16 位无符号整数。</span><span class="sxs-lookup"><span data-stu-id="40ee9-120">Convert to a 16-bit unsigned integer.</span></span>|
|`int32, int`|<span data-ttu-id="40ee9-121">将转换为 32 位有符号整数。</span><span class="sxs-lookup"><span data-stu-id="40ee9-121">Convert to a 32-bit signed integer.</span></span>|
|`uint32`|<span data-ttu-id="40ee9-122">将转换为 32 位无符号整数。</span><span class="sxs-lookup"><span data-stu-id="40ee9-122">Convert to a 32-bit unsigned integer.</span></span>|
|`int64`|<span data-ttu-id="40ee9-123">将转换为 64 位有符号整数。</span><span class="sxs-lookup"><span data-stu-id="40ee9-123">Convert to a 64-bit signed integer.</span></span>|
|`uint64`|<span data-ttu-id="40ee9-124">将转换为 64 位无符号整数。</span><span class="sxs-lookup"><span data-stu-id="40ee9-124">Convert to a 64-bit unsigned integer.</span></span>|
|`nativeint`|<span data-ttu-id="40ee9-125">将转换为本机的整数。</span><span class="sxs-lookup"><span data-stu-id="40ee9-125">Convert to a native integer.</span></span>|
|`unativeint`|<span data-ttu-id="40ee9-126">将转换为本机的无符号整数。</span><span class="sxs-lookup"><span data-stu-id="40ee9-126">Convert to an unsigned native integer.</span></span>|
|`float, double`|<span data-ttu-id="40ee9-127">将转换为 64 位双精度 IEEE 浮点数。</span><span class="sxs-lookup"><span data-stu-id="40ee9-127">Convert to a 64-bit double-precision IEEE floating point number.</span></span>|
|`float32, single`|<span data-ttu-id="40ee9-128">将转换为 32 位单精度 IEEE 浮点数。</span><span class="sxs-lookup"><span data-stu-id="40ee9-128">Convert to a 32-bit single-precision IEEE floating point number.</span></span>|
|`decimal`|<span data-ttu-id="40ee9-129">将转换为`System.Decimal`。</span><span class="sxs-lookup"><span data-stu-id="40ee9-129">Convert to `System.Decimal`.</span></span>|
|`char`|<span data-ttu-id="40ee9-130">将转换为`System.Char`，Unicode 字符。</span><span class="sxs-lookup"><span data-stu-id="40ee9-130">Convert to `System.Char`, a Unicode character.</span></span>|
|`enum`|<span data-ttu-id="40ee9-131">将转换为枚举类型。</span><span class="sxs-lookup"><span data-stu-id="40ee9-131">Convert to an enumerated type.</span></span>|
<span data-ttu-id="40ee9-132">除了内置的基元类型，你可以与实现的类型使用这些运算符`op_Explicit`或`op_Implicit`具有适当的签名方法。</span><span class="sxs-lookup"><span data-stu-id="40ee9-132">In addition to built-in primitive types, you can use these operators with types that implement `op_Explicit` or `op_Implicit` methods with appropriate signatures.</span></span> <span data-ttu-id="40ee9-133">例如，`int`转换运算符适用于提供一个静态方法的任何类型`op_Explicit`，采用类型作为参数并返回`int`。</span><span class="sxs-lookup"><span data-stu-id="40ee9-133">For example, the `int` conversion operator works with any type that provides a static method `op_Explicit` that takes the type as a parameter and returns `int`.</span></span> <span data-ttu-id="40ee9-134">作为一般规则，无法由返回类型重载这些方法的特例，你可以这样做`op_Explicit`和`op_Implicit`。</span><span class="sxs-lookup"><span data-stu-id="40ee9-134">As a special exception to the general rule that methods cannot be overloaded by return type, you can do this for `op_Explicit` and `op_Implicit`.</span></span>

## <a name="enumerated-types"></a><span data-ttu-id="40ee9-135">枚举的类型</span><span class="sxs-lookup"><span data-stu-id="40ee9-135">Enumerated Types</span></span>
<span data-ttu-id="40ee9-136">`enum`运算符是采用一个表示的类型的类型参数的泛型运算符`enum`将转换为。</span><span class="sxs-lookup"><span data-stu-id="40ee9-136">The `enum` operator is a generic operator that takes one type parameter that represents the type of the `enum` to convert to.</span></span> <span data-ttu-id="40ee9-137">当它将转换为枚举类型时，键入推理会尝试确定的一种`enum`你想要将转换为。</span><span class="sxs-lookup"><span data-stu-id="40ee9-137">When it converts to an enumerated type, type inference attempts to determine the type of the `enum` that you want to convert to.</span></span> <span data-ttu-id="40ee9-138">在下面的示例中，变量`col1`未显示批注，但其类型推断从更高版本的相等性测试。</span><span class="sxs-lookup"><span data-stu-id="40ee9-138">In the following example, the variable `col1` is not explicitly annotated, but its type is inferred from the later equality test.</span></span> <span data-ttu-id="40ee9-139">因此，编译器可以推断出你要转换为`Color`枚举。</span><span class="sxs-lookup"><span data-stu-id="40ee9-139">Therefore, the compiler can deduce that you are converting to a `Color` enumeration.</span></span> <span data-ttu-id="40ee9-140">或者，你可以提供一个类型批注，与`col2`在下面的示例。</span><span class="sxs-lookup"><span data-stu-id="40ee9-140">Alternatively, you can supply a type annotation, as with `col2` in the following example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4402.fs)]
    
<span data-ttu-id="40ee9-141">你可以显式指定的目标枚举类型，作为类型参数，如以下代码所示：</span><span class="sxs-lookup"><span data-stu-id="40ee9-141">You can also specify the target enumeration type explicitly as a type parameter, as in the following code:</span></span>

```fsharp
let col3 = enum<Color> 3
```

<span data-ttu-id="40ee9-142">请注意在枚举转换工作，仅当在枚举的基础类型为与要转换的类型兼容。</span><span class="sxs-lookup"><span data-stu-id="40ee9-142">Note that the enumeration casts work only if the underlying type of the enumeration is compatible with the type being converted.</span></span> <span data-ttu-id="40ee9-143">在下面的代码中，则转换失败由于之间不匹配编译`int32`和`uint32`。</span><span class="sxs-lookup"><span data-stu-id="40ee9-143">In the following code, the conversion fails to compile because of the mismatch between `int32` and `uint32`.</span></span>

```fsharp
// Error: types are incompatible
let col4 : Color = enum 2u
```

<span data-ttu-id="40ee9-144">有关详细信息，请参阅[枚举](enumerations.md)。</span><span class="sxs-lookup"><span data-stu-id="40ee9-144">For more information, see [Enumerations](enumerations.md).</span></span>

## <a name="casting-object-types"></a><span data-ttu-id="40ee9-145">强制转换对象类型</span><span class="sxs-lookup"><span data-stu-id="40ee9-145">Casting Object Types</span></span>
<span data-ttu-id="40ee9-146">对象层次结构中的类型之间的转换是面向对象的编程的基础。</span><span class="sxs-lookup"><span data-stu-id="40ee9-146">Conversion between types in an object hierarchy is fundamental to object-oriented programming.</span></span> <span data-ttu-id="40ee9-147">有两种基本类型的转换： 向上 （向上转换） 强制转换和向下转换）。</span><span class="sxs-lookup"><span data-stu-id="40ee9-147">There are two basic types of conversions: casting up (upcasting) and casting down (downcasting).</span></span> <span data-ttu-id="40ee9-148">沿层次结构向上的强制转换意味着强制转换为基对象引用是派生的对象引用。</span><span class="sxs-lookup"><span data-stu-id="40ee9-148">Casting up a hierarchy means casting from a derived object reference to a base object reference.</span></span> <span data-ttu-id="40ee9-149">此类强制转换可保证只要的基类派生的类的继承层次结构中正常工作。</span><span class="sxs-lookup"><span data-stu-id="40ee9-149">Such a cast is guaranteed to work as long as the base class is in the inheritance hierarchy of the derived class.</span></span> <span data-ttu-id="40ee9-150">在层次结构，为派生的对象引用，是基对象引用强制转换时才会成功对象实际上是正确的目标 （派生） 类型或从目标类型派生的类型的实例。</span><span class="sxs-lookup"><span data-stu-id="40ee9-150">Casting down a hierarchy, from a base object reference to a derived object reference, succeeds only if the object actually is an instance of the correct destination (derived) type or a type derived from the destination type.</span></span>

<span data-ttu-id="40ee9-151">F # 提供了为这些类型的转换的运算符。</span><span class="sxs-lookup"><span data-stu-id="40ee9-151">F# provides operators for these types of conversions.</span></span> <span data-ttu-id="40ee9-152">`:>`层次结构向上转换运算符与`:?>`运算符将沿层次结构强制转换。</span><span class="sxs-lookup"><span data-stu-id="40ee9-152">The `:>` operator casts up the hierarchy, and the `:?>` operator casts down the hierarchy.</span></span>

### <a name="upcasting"></a><span data-ttu-id="40ee9-153">向上转换</span><span class="sxs-lookup"><span data-stu-id="40ee9-153">Upcasting</span></span>
<span data-ttu-id="40ee9-154">在许多面向对象语言中，向上转换是隐式;F # 中的规则是略有不同。</span><span class="sxs-lookup"><span data-stu-id="40ee9-154">In many object-oriented languages, upcasting is implicit; in F#, the rules are slightly different.</span></span> <span data-ttu-id="40ee9-155">在传递给方法上的对象类型自变量时，将自动应用向上转换。</span><span class="sxs-lookup"><span data-stu-id="40ee9-155">Upcasting is applied automatically when you pass arguments to methods on an object type.</span></span> <span data-ttu-id="40ee9-156">但是，对于模块中的 let 绑定函数，向上转换不是自动进行的除非参数类型声明为灵活类型。</span><span class="sxs-lookup"><span data-stu-id="40ee9-156">However, for let-bound functions in a module, upcasting is not automatic, unless the parameter type is declared as a flexible type.</span></span> <span data-ttu-id="40ee9-157">有关详细信息，请参阅[可变类型](flexible-Types.md)。</span><span class="sxs-lookup"><span data-stu-id="40ee9-157">For more information, see [Flexible Types](flexible-Types.md).</span></span>

<span data-ttu-id="40ee9-158">`:>`运算符执行静态强制转换，这意味着在编译时确定转换是否成功。</span><span class="sxs-lookup"><span data-stu-id="40ee9-158">The `:>` operator performs a static cast, which means that the success of the cast is determined at compile time.</span></span> <span data-ttu-id="40ee9-159">如果使用强制转换`:>`编译成功，它是有效的强制转换并在运行时具有不可能将失败。</span><span class="sxs-lookup"><span data-stu-id="40ee9-159">If a cast that uses `:>` compiles successfully, it is a valid cast and has no chance of failure at run time.</span></span>

<span data-ttu-id="40ee9-160">你还可以使用`upcast`运算符来执行这种转换。</span><span class="sxs-lookup"><span data-stu-id="40ee9-160">You can also use the `upcast` operator to perform such a conversion.</span></span> <span data-ttu-id="40ee9-161">以下表达式指定层次结构向上转换：</span><span class="sxs-lookup"><span data-stu-id="40ee9-161">The following expression specifies a conversion up the hierarchy:</span></span>

```fsharp
upcast expression
```

<span data-ttu-id="40ee9-162">当使用向上转换运算符时，编译器将尝试推断要从上下文转换为的类型。</span><span class="sxs-lookup"><span data-stu-id="40ee9-162">When you use the upcast operator, the compiler attempts to infer the type you are converting to from the context.</span></span> <span data-ttu-id="40ee9-163">如果编译器无法确定目标类型，编译器将报告错误。</span><span class="sxs-lookup"><span data-stu-id="40ee9-163">If the compiler is unable to determine the target type, the compiler reports an error.</span></span>

### <a name="downcasting"></a><span data-ttu-id="40ee9-164">向下转换</span><span class="sxs-lookup"><span data-stu-id="40ee9-164">Downcasting</span></span>
<span data-ttu-id="40ee9-165">`:?>`运算符执行动态强制转换，这意味着在运行时确定转换是否成功。</span><span class="sxs-lookup"><span data-stu-id="40ee9-165">The `:?>` operator performs a dynamic cast, which means that the success of the cast is determined at run time.</span></span> <span data-ttu-id="40ee9-166">使用强制转换`:?>`运算符不检查在编译时; 但在运行时，尝试强制转换为指定的类型。</span><span class="sxs-lookup"><span data-stu-id="40ee9-166">A cast that uses the `:?>` operator is not checked at compile time; but at run time, an attempt is made to cast to the specified type.</span></span> <span data-ttu-id="40ee9-167">如果对象是与目标类型兼容，该强制转换会成功。</span><span class="sxs-lookup"><span data-stu-id="40ee9-167">If the object is compatible with the target type, the cast succeeds.</span></span> <span data-ttu-id="40ee9-168">如果对象不是与目标类型兼容的则运行时将引发`InvalidCastException`。</span><span class="sxs-lookup"><span data-stu-id="40ee9-168">If the object is not compatible with the target type, the runtime raises an `InvalidCastException`.</span></span>

<span data-ttu-id="40ee9-169">你还可以使用`downcast`运算符执行的动态类型转换。</span><span class="sxs-lookup"><span data-stu-id="40ee9-169">You can also use the `downcast` operator to perform a dynamic type conversion.</span></span> <span data-ttu-id="40ee9-170">以下表达式指定沿层次结构到从程序上下文中推断出类型的转换：</span><span class="sxs-lookup"><span data-stu-id="40ee9-170">The following expression specifies a conversion down the hierarchy to a type that is inferred from program context:</span></span>

```fsharp
downcast expression
```

<span data-ttu-id="40ee9-171">同样适用于`upcast`运算符，如果编译器无法推断特定的目标类型从上下文，则将报告错误。</span><span class="sxs-lookup"><span data-stu-id="40ee9-171">As for the `upcast` operator, if the compiler cannot infer a specific target type from the context, it reports an error.</span></span>

<span data-ttu-id="40ee9-172">下面的代码演示如何使用`:>`和`:?>`运算符。</span><span class="sxs-lookup"><span data-stu-id="40ee9-172">The following code illustrates the use of the `:>` and `:?>` operators.</span></span> <span data-ttu-id="40ee9-173">该代码演示`:?>`当你知道，转换将失败，因为它将引发时，最好使用运算符`InvalidCastException`如果转换失败。</span><span class="sxs-lookup"><span data-stu-id="40ee9-173">The code illustrates that the `:?>` operator is best used when you know that conversion will succeed, because it throws `InvalidCastException` if the conversion fails.</span></span> <span data-ttu-id="40ee9-174">如果你不知道，转换将失败，使用的类型测试`match`表达式是更好，因为它避免生成异常的开销。</span><span class="sxs-lookup"><span data-stu-id="40ee9-174">If you do not know that a conversion will succeed, a type test that uses a `match` expression is better because it avoids the overhead of generating an exception.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4403.fs)]

<span data-ttu-id="40ee9-175">因为泛型运算符`downcast`和`upcast`依赖类型推断来确定自变量和返回类型，在上述代码中，你可以替换</span><span class="sxs-lookup"><span data-stu-id="40ee9-175">Because generic operators `downcast` and `upcast` rely on type inference to determine the argument and return type, in the above code, you can replace</span></span>

```fsharp
let base1 = d1 :> Base1
```

<span data-ttu-id="40ee9-176">替换为</span><span class="sxs-lookup"><span data-stu-id="40ee9-176">with</span></span>

```fsharp
let base1 = upcast d1
```

<span data-ttu-id="40ee9-177">在前面的代码中，自变量类型和返回类型是`Derived1`和`Base1`分别。</span><span class="sxs-lookup"><span data-stu-id="40ee9-177">In the previous code, the argument type and return types are `Derived1` and `Base1`, respectively.</span></span>

<span data-ttu-id="40ee9-178">有关类型测试的详细信息，请参阅[匹配表达式](match-Expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="40ee9-178">For more information about type tests, see [Match Expressions](match-Expressions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="40ee9-179">另请参阅</span><span class="sxs-lookup"><span data-stu-id="40ee9-179">See Also</span></span>
[<span data-ttu-id="40ee9-180">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="40ee9-180">F# Language Reference</span></span>](index.md)
