---
title: 强制转换和转换
description: 了解F#编程语言如何提供各种基元类型之间算术转换的转换运算符。
ms.date: 02/20/2020
ms.openlocfilehash: 5f9727d14a7ae070e0f0f71fa0a0abe04f662071
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543581"
---
# <a name="casting-and-conversions-f"></a><span data-ttu-id="76b94-103">强制转换和转换 (F#)</span><span class="sxs-lookup"><span data-stu-id="76b94-103">Casting and Conversions (F#)</span></span>

<span data-ttu-id="76b94-104">本主题介绍中F#对类型转换的支持。</span><span class="sxs-lookup"><span data-stu-id="76b94-104">This topic describes support for type conversions in F#.</span></span>

## <a name="arithmetic-types"></a><span data-ttu-id="76b94-105">算术类型</span><span class="sxs-lookup"><span data-stu-id="76b94-105">Arithmetic Types</span></span>

<span data-ttu-id="76b94-106">F#提供各种基元类型（如整型和浮点类型之间）的算术转换的转换运算符。</span><span class="sxs-lookup"><span data-stu-id="76b94-106">F# provides conversion operators for arithmetic conversions between various primitive types, such as between integer and floating point types.</span></span> <span data-ttu-id="76b94-107">整数和字符转换运算符具有 checked 和 unchecked 形式;浮点运算符和 `enum` 转换运算符不能。</span><span class="sxs-lookup"><span data-stu-id="76b94-107">The integral and char conversion operators have checked and unchecked forms; the floating point operators and the `enum` conversion operator do not.</span></span> <span data-ttu-id="76b94-108">未检查的窗体是在 `Microsoft.FSharp.Core.Operators` 中定义的，并且在 `Microsoft.FSharp.Core.Operators.Checked`中定义了选中的窗体。</span><span class="sxs-lookup"><span data-stu-id="76b94-108">The unchecked forms are defined in `Microsoft.FSharp.Core.Operators` and the checked forms are defined in `Microsoft.FSharp.Core.Operators.Checked`.</span></span> <span data-ttu-id="76b94-109">如果生成的值超出了目标类型的限制，则选中的窗体将检查溢出并生成运行时异常。</span><span class="sxs-lookup"><span data-stu-id="76b94-109">The checked forms check for overflow and generate a runtime exception if the resulting value exceeds the limits of the target type.</span></span>

<span data-ttu-id="76b94-110">其中每个运算符都具有与目标类型名称相同的名称。</span><span class="sxs-lookup"><span data-stu-id="76b94-110">Each of these operators has the same name as the name of the destination type.</span></span> <span data-ttu-id="76b94-111">例如，在以下代码中，在其中显式批注了类型，`byte` 以两种不同的含义显示。</span><span class="sxs-lookup"><span data-stu-id="76b94-111">For example, in the following code, in which the types are explicitly annotated, `byte` appears with two different meanings.</span></span> <span data-ttu-id="76b94-112">第一次出现类型，第二个是转换运算符。</span><span class="sxs-lookup"><span data-stu-id="76b94-112">The first occurrence is the type and the second is the conversion operator.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4401.fs)]

<span data-ttu-id="76b94-113">下表显示了在中定义的F#转换运算符。</span><span class="sxs-lookup"><span data-stu-id="76b94-113">The following table shows conversion operators defined in F#.</span></span>

|<span data-ttu-id="76b94-114">运算符</span><span class="sxs-lookup"><span data-stu-id="76b94-114">Operator</span></span>|<span data-ttu-id="76b94-115">说明</span><span class="sxs-lookup"><span data-stu-id="76b94-115">Description</span></span>|
|--------|-----------|
|`byte`|<span data-ttu-id="76b94-116">转换为字节，即8位无符号类型。</span><span class="sxs-lookup"><span data-stu-id="76b94-116">Convert to byte, an 8-bit unsigned type.</span></span>|
|`sbyte`|<span data-ttu-id="76b94-117">转换为有符号字节。</span><span class="sxs-lookup"><span data-stu-id="76b94-117">Convert to signed byte.</span></span>|
|`int16`|<span data-ttu-id="76b94-118">转换为16位带符号整数。</span><span class="sxs-lookup"><span data-stu-id="76b94-118">Convert to a 16-bit signed integer.</span></span>|
|`uint16`|<span data-ttu-id="76b94-119">转换为16位无符号整数。</span><span class="sxs-lookup"><span data-stu-id="76b94-119">Convert to a 16-bit unsigned integer.</span></span>|
|`int32, int`|<span data-ttu-id="76b94-120">转换为32位有符号整数。</span><span class="sxs-lookup"><span data-stu-id="76b94-120">Convert to a 32-bit signed integer.</span></span>|
|`uint32`|<span data-ttu-id="76b94-121">转换为32位无符号整数。</span><span class="sxs-lookup"><span data-stu-id="76b94-121">Convert to a 32-bit unsigned integer.</span></span>|
|`int64`|<span data-ttu-id="76b94-122">转换为64位有符号整数。</span><span class="sxs-lookup"><span data-stu-id="76b94-122">Convert to a 64-bit signed integer.</span></span>|
|`uint64`|<span data-ttu-id="76b94-123">转换为64位无符号整数。</span><span class="sxs-lookup"><span data-stu-id="76b94-123">Convert to a 64-bit unsigned integer.</span></span>|
|`nativeint`|<span data-ttu-id="76b94-124">转换为本机整数。</span><span class="sxs-lookup"><span data-stu-id="76b94-124">Convert to a native integer.</span></span>|
|`unativeint`|<span data-ttu-id="76b94-125">转换为无符号本机整数。</span><span class="sxs-lookup"><span data-stu-id="76b94-125">Convert to an unsigned native integer.</span></span>|
|`float, double`|<span data-ttu-id="76b94-126">转换为64位双精度 IEEE 浮点数。</span><span class="sxs-lookup"><span data-stu-id="76b94-126">Convert to a 64-bit double-precision IEEE floating point number.</span></span>|
|`float32, single`|<span data-ttu-id="76b94-127">转换为32位单精度 IEEE 浮点数。</span><span class="sxs-lookup"><span data-stu-id="76b94-127">Convert to a 32-bit single-precision IEEE floating point number.</span></span>|
|`decimal`|<span data-ttu-id="76b94-128">转换为 `System.Decimal`。</span><span class="sxs-lookup"><span data-stu-id="76b94-128">Convert to `System.Decimal`.</span></span>|
|`char`|<span data-ttu-id="76b94-129">转换为 `System.Char`，这是一个 Unicode 字符。</span><span class="sxs-lookup"><span data-stu-id="76b94-129">Convert to `System.Char`, a Unicode character.</span></span>|
|`enum`|<span data-ttu-id="76b94-130">转换为枚举类型。</span><span class="sxs-lookup"><span data-stu-id="76b94-130">Convert to an enumerated type.</span></span>|

<span data-ttu-id="76b94-131">除了内置的基元类型外，还可以将这些运算符用于通过适当的签名实现 `op_Explicit` 或 `op_Implicit` 方法的类型。</span><span class="sxs-lookup"><span data-stu-id="76b94-131">In addition to built-in primitive types, you can use these operators with types that implement `op_Explicit` or `op_Implicit` methods with appropriate signatures.</span></span> <span data-ttu-id="76b94-132">例如，`int` 转换运算符适用于任何提供静态方法的类型，该 `op_Explicit` 方法采用类型作为参数并返回 `int`。</span><span class="sxs-lookup"><span data-stu-id="76b94-132">For example, the `int` conversion operator works with any type that provides a static method `op_Explicit` that takes the type as a parameter and returns `int`.</span></span> <span data-ttu-id="76b94-133">作为一般规则，不能通过返回类型重载方法，可以对 `op_Explicit` 和 `op_Implicit`执行此操作。</span><span class="sxs-lookup"><span data-stu-id="76b94-133">As a special exception to the general rule that methods cannot be overloaded by return type, you can do this for `op_Explicit` and `op_Implicit`.</span></span>

## <a name="enumerated-types"></a><span data-ttu-id="76b94-134">枚举类型</span><span class="sxs-lookup"><span data-stu-id="76b94-134">Enumerated Types</span></span>

<span data-ttu-id="76b94-135">`enum` 运算符是一个泛型运算符，它采用一个类型参数来表示要转换为的 `enum` 的类型。</span><span class="sxs-lookup"><span data-stu-id="76b94-135">The `enum` operator is a generic operator that takes one type parameter that represents the type of the `enum` to convert to.</span></span> <span data-ttu-id="76b94-136">当它转换为枚举类型时，类型推理将尝试确定要转换为的 `enum` 的类型。</span><span class="sxs-lookup"><span data-stu-id="76b94-136">When it converts to an enumerated type, type inference attempts to determine the type of the `enum` that you want to convert to.</span></span> <span data-ttu-id="76b94-137">在下面的示例中，变量 `col1` 未显式批注，但其类型是从后面的相等测试推断出来的。</span><span class="sxs-lookup"><span data-stu-id="76b94-137">In the following example, the variable `col1` is not explicitly annotated, but its type is inferred from the later equality test.</span></span> <span data-ttu-id="76b94-138">因此，编译器可以推断出你要转换为 `Color` 枚举。</span><span class="sxs-lookup"><span data-stu-id="76b94-138">Therefore, the compiler can deduce that you are converting to a `Color` enumeration.</span></span> <span data-ttu-id="76b94-139">另外，还可以提供类型注释，如以下示例中的 `col2`。</span><span class="sxs-lookup"><span data-stu-id="76b94-139">Alternatively, you can supply a type annotation, as with `col2` in the following example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4402.fs)]

<span data-ttu-id="76b94-140">你还可以将目标枚举类型显式指定为类型参数，如以下代码所示：</span><span class="sxs-lookup"><span data-stu-id="76b94-140">You can also specify the target enumeration type explicitly as a type parameter, as in the following code:</span></span>

```fsharp
let col3 = enum<Color> 3
```

<span data-ttu-id="76b94-141">请注意，仅当枚举的基础类型与正在转换的类型兼容时，才会转换枚举。</span><span class="sxs-lookup"><span data-stu-id="76b94-141">Note that the enumeration casts work only if the underlying type of the enumeration is compatible with the type being converted.</span></span> <span data-ttu-id="76b94-142">在下面的代码中，由于 `int32` 和 `uint32`不匹配，转换无法编译。</span><span class="sxs-lookup"><span data-stu-id="76b94-142">In the following code, the conversion fails to compile because of the mismatch between `int32` and `uint32`.</span></span>

```fsharp
// Error: types are incompatible
let col4 : Color = enum 2u
```

<span data-ttu-id="76b94-143">有关详细信息，请参阅[枚举](enumerations.md)。</span><span class="sxs-lookup"><span data-stu-id="76b94-143">For more information, see [Enumerations](enumerations.md).</span></span>

## <a name="casting-object-types"></a><span data-ttu-id="76b94-144">强制转换对象类型</span><span class="sxs-lookup"><span data-stu-id="76b94-144">Casting Object Types</span></span>

<span data-ttu-id="76b94-145">对象层次结构中的类型之间的转换是面向对象编程的基础。</span><span class="sxs-lookup"><span data-stu-id="76b94-145">Conversion between types in an object hierarchy is fundamental to object-oriented programming.</span></span> <span data-ttu-id="76b94-146">有两种基本类型的转换：强制转换（向上转换）和强制转换（downcasting）。</span><span class="sxs-lookup"><span data-stu-id="76b94-146">There are two basic types of conversions: casting up (upcasting) and casting down (downcasting).</span></span> <span data-ttu-id="76b94-147">向上转换层次结构意味着将派生对象引用强制转换为基对象引用。</span><span class="sxs-lookup"><span data-stu-id="76b94-147">Casting up a hierarchy means casting from a derived object reference to a base object reference.</span></span> <span data-ttu-id="76b94-148">只要基类位于派生类的继承层次结构中，此类强制转换就可以正常工作。</span><span class="sxs-lookup"><span data-stu-id="76b94-148">Such a cast is guaranteed to work as long as the base class is in the inheritance hierarchy of the derived class.</span></span> <span data-ttu-id="76b94-149">将层次结构向下强制转换为派生对象引用后，仅当对象实际上是正确目标（派生）类型或派生自目标类型的类型的实例时，才会成功。</span><span class="sxs-lookup"><span data-stu-id="76b94-149">Casting down a hierarchy, from a base object reference to a derived object reference, succeeds only if the object actually is an instance of the correct destination (derived) type or a type derived from the destination type.</span></span>

<span data-ttu-id="76b94-150">F#为这些类型的转换提供运算符。</span><span class="sxs-lookup"><span data-stu-id="76b94-150">F# provides operators for these types of conversions.</span></span> <span data-ttu-id="76b94-151">`:>` 运算符在层次结构中向上转换，`:?>` 运算符沿层次结构向下转换。</span><span class="sxs-lookup"><span data-stu-id="76b94-151">The `:>` operator casts up the hierarchy, and the `:?>` operator casts down the hierarchy.</span></span>

### <a name="upcasting"></a><span data-ttu-id="76b94-152">向上转换</span><span class="sxs-lookup"><span data-stu-id="76b94-152">Upcasting</span></span>

<span data-ttu-id="76b94-153">在许多面向对象的语言中，向上转换是隐式的;在F#中，规则略有不同。</span><span class="sxs-lookup"><span data-stu-id="76b94-153">In many object-oriented languages, upcasting is implicit; in F#, the rules are slightly different.</span></span> <span data-ttu-id="76b94-154">将参数传递给对象类型上的方法时，会自动应用向上转换。</span><span class="sxs-lookup"><span data-stu-id="76b94-154">Upcasting is applied automatically when you pass arguments to methods on an object type.</span></span> <span data-ttu-id="76b94-155">但是，对于模块中的 let 绑定函数，向上转换不是自动的，除非将参数类型声明为可变类型。</span><span class="sxs-lookup"><span data-stu-id="76b94-155">However, for let-bound functions in a module, upcasting is not automatic, unless the parameter type is declared as a flexible type.</span></span> <span data-ttu-id="76b94-156">有关详细信息，请参阅[可变类型](flexible-Types.md)。</span><span class="sxs-lookup"><span data-stu-id="76b94-156">For more information, see [Flexible Types](flexible-Types.md).</span></span>

<span data-ttu-id="76b94-157">`:>` 运算符执行静态强制转换，这意味着在编译时确定强制转换是否成功。</span><span class="sxs-lookup"><span data-stu-id="76b94-157">The `:>` operator performs a static cast, which means that the success of the cast is determined at compile time.</span></span> <span data-ttu-id="76b94-158">如果使用 `:>` 的强制转换编译成功，则它是有效的强制转换，并且在运行时不会出现故障。</span><span class="sxs-lookup"><span data-stu-id="76b94-158">If a cast that uses `:>` compiles successfully, it is a valid cast and has no chance of failure at run time.</span></span>

<span data-ttu-id="76b94-159">你还可以使用 `upcast` 运算符来执行此类转换。</span><span class="sxs-lookup"><span data-stu-id="76b94-159">You can also use the `upcast` operator to perform such a conversion.</span></span> <span data-ttu-id="76b94-160">以下表达式指定了层次结构中的转换：</span><span class="sxs-lookup"><span data-stu-id="76b94-160">The following expression specifies a conversion up the hierarchy:</span></span>

```fsharp
upcast expression
```

<span data-ttu-id="76b94-161">当使用向上转换运算符时，编译器将尝试推断从上下文转换为的类型。</span><span class="sxs-lookup"><span data-stu-id="76b94-161">When you use the upcast operator, the compiler attempts to infer the type you are converting to from the context.</span></span> <span data-ttu-id="76b94-162">如果编译器无法确定目标类型，则编译器将报告错误。</span><span class="sxs-lookup"><span data-stu-id="76b94-162">If the compiler is unable to determine the target type, the compiler reports an error.</span></span> <span data-ttu-id="76b94-163">可能需要类型批注。</span><span class="sxs-lookup"><span data-stu-id="76b94-163">A type annotation may be required.</span></span>

### <a name="downcasting"></a><span data-ttu-id="76b94-164">Downcasting</span><span class="sxs-lookup"><span data-stu-id="76b94-164">Downcasting</span></span>

<span data-ttu-id="76b94-165">`:?>` 运算符执行动态强制转换，这意味着在运行时确定强制转换是否成功。</span><span class="sxs-lookup"><span data-stu-id="76b94-165">The `:?>` operator performs a dynamic cast, which means that the success of the cast is determined at run time.</span></span> <span data-ttu-id="76b94-166">在编译时不检查使用 `:?>` 运算符的强制转换;但在运行时，尝试强制转换为指定的类型。</span><span class="sxs-lookup"><span data-stu-id="76b94-166">A cast that uses the `:?>` operator is not checked at compile time; but at run time, an attempt is made to cast to the specified type.</span></span> <span data-ttu-id="76b94-167">如果对象与目标类型兼容，则强制转换成功。</span><span class="sxs-lookup"><span data-stu-id="76b94-167">If the object is compatible with the target type, the cast succeeds.</span></span> <span data-ttu-id="76b94-168">如果对象与目标类型不兼容，则运行时将引发 `InvalidCastException`。</span><span class="sxs-lookup"><span data-stu-id="76b94-168">If the object is not compatible with the target type, the runtime raises an `InvalidCastException`.</span></span>

<span data-ttu-id="76b94-169">你还可以使用 `downcast` 运算符来执行动态类型转换。</span><span class="sxs-lookup"><span data-stu-id="76b94-169">You can also use the `downcast` operator to perform a dynamic type conversion.</span></span> <span data-ttu-id="76b94-170">以下表达式指定向下转换到从程序上下文推断出的类型的层次结构：</span><span class="sxs-lookup"><span data-stu-id="76b94-170">The following expression specifies a conversion down the hierarchy to a type that is inferred from program context:</span></span>

```fsharp
downcast expression
```

<span data-ttu-id="76b94-171">与 `upcast` 运算符一样，如果编译器无法从上下文推断特定目标类型，则会报告错误。</span><span class="sxs-lookup"><span data-stu-id="76b94-171">As for the `upcast` operator, if the compiler cannot infer a specific target type from the context, it reports an error.</span></span> <span data-ttu-id="76b94-172">可能需要类型批注。</span><span class="sxs-lookup"><span data-stu-id="76b94-172">A type annotation may be required.</span></span>

<span data-ttu-id="76b94-173">下面的代码演示了如何使用 `:>` 和 `:?>` 运算符。</span><span class="sxs-lookup"><span data-stu-id="76b94-173">The following code illustrates the use of the `:>` and `:?>` operators.</span></span> <span data-ttu-id="76b94-174">此代码说明，当你知道转换将成功时，`:?>` 运算符最适用，因为如果转换失败，则会引发 `InvalidCastException`。</span><span class="sxs-lookup"><span data-stu-id="76b94-174">The code illustrates that the `:?>` operator is best used when you know that conversion will succeed, because it throws `InvalidCastException` if the conversion fails.</span></span> <span data-ttu-id="76b94-175">如果您不知道转换将会成功，则使用 `match` 表达式的类型测试更好，因为这样可以避免生成异常的开销。</span><span class="sxs-lookup"><span data-stu-id="76b94-175">If you do not know that a conversion will succeed, a type test that uses a `match` expression is better because it avoids the overhead of generating an exception.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4403.fs)]

<span data-ttu-id="76b94-176">由于泛型运算符 `downcast` 和 `upcast` 依赖于类型推理来确定参数和返回类型，因此，在上面的代码中，可以替换</span><span class="sxs-lookup"><span data-stu-id="76b94-176">Because generic operators `downcast` and `upcast` rely on type inference to determine the argument and return type, in the above code, you can replace</span></span>

```fsharp
let base1 = d1 :> Base1
```

<span data-ttu-id="76b94-177">替换为</span><span class="sxs-lookup"><span data-stu-id="76b94-177">with</span></span>

```fsharp
let base1: Base1 = upcast d1
```

<span data-ttu-id="76b94-178">请注意，类型批注是必需的，因为 `upcast` 本身无法确定基类。</span><span class="sxs-lookup"><span data-stu-id="76b94-178">Note that a type annotation is required, since `upcast` by itself could not determine the base class.</span></span>

## <a name="see-also"></a><span data-ttu-id="76b94-179">另请参阅</span><span class="sxs-lookup"><span data-stu-id="76b94-179">See also</span></span>

- [<span data-ttu-id="76b94-180">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="76b94-180">F# Language Reference</span></span>](index.md)
