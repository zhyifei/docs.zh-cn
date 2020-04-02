---
title: 结构类型 - C# 参考
ms.date: 03/26/2020
f1_keywords:
- struct_CSharpKeyword
helpviewer_keywords:
- struct keyword [C#]
- struct type [C#]
- structure type [C#]
ms.assetid: ff3dd9b7-dc93-4720-8855-ef5558f65c7c
ms.openlocfilehash: 6a2c97b93a8f6d1d62bd8a96865a4fe6587f55d3
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2020
ms.locfileid: "80345130"
---
# <a name="structure-types-c-reference"></a><span data-ttu-id="e583b-102">结构类型（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="e583b-102">Structure types (C# reference)</span></span>

<span data-ttu-id="e583b-103">结构类型（“structure type”或“struct type”）是一种可封装数据和相关功能的[值类型](value-types.md)。</span><span class="sxs-lookup"><span data-stu-id="e583b-103">A *structure type* (or *struct type*) is a [value type](value-types.md) that can encapsulate data and related functionality.</span></span> <span data-ttu-id="e583b-104">使用 `struct` 关键字定义结构类型：</span><span class="sxs-lookup"><span data-stu-id="e583b-104">You use the `struct` keyword to define a structure type:</span></span>

[!code-csharp[struct example](snippets/StructType.cs#StructExample)]

<span data-ttu-id="e583b-105">结构类型具有值语义。</span><span class="sxs-lookup"><span data-stu-id="e583b-105">Structure types have *value semantics*.</span></span> <span data-ttu-id="e583b-106">也就是说，结构类型的变量包含类型的实例。</span><span class="sxs-lookup"><span data-stu-id="e583b-106">That is, a variable of a structure type contains an instance of the type.</span></span> <span data-ttu-id="e583b-107">默认情况下，在分配中，通过将参数传递给方法并返回方法结果来复制变量值。</span><span class="sxs-lookup"><span data-stu-id="e583b-107">By default, variable values are copied on assignment, passing an argument to a method, and returning a method result.</span></span> <span data-ttu-id="e583b-108">对于结构类型变量，将复制该类型的实例。</span><span class="sxs-lookup"><span data-stu-id="e583b-108">In the case of a structure-type variable, an instance of the type is copied.</span></span> <span data-ttu-id="e583b-109">有关更多信息，请参阅[值类型](value-types.md)。</span><span class="sxs-lookup"><span data-stu-id="e583b-109">For more information, see [Value types](value-types.md).</span></span>

<span data-ttu-id="e583b-110">通常，可以使用结构类型来设计以数据为中心的较小类型，这些类型只有很少的行为或没有行为。</span><span class="sxs-lookup"><span data-stu-id="e583b-110">Typically, you use structure types to design small data-centric types that provide little or no behavior.</span></span> <span data-ttu-id="e583b-111">例如，.NET 使用结构类型来表示数字（[整数](integral-numeric-types.md)和[实数](floating-point-numeric-types.md)）、[布尔值](bool.md)、[Unicode 字符](char.md)以及[时间实例](xref:System.DateTime)。</span><span class="sxs-lookup"><span data-stu-id="e583b-111">For example, .NET uses structure types to represent a number (both [integer](integral-numeric-types.md) and [real](floating-point-numeric-types.md)), a [Boolean value](bool.md), a [Unicode character](char.md), a [time instance](xref:System.DateTime).</span></span> <span data-ttu-id="e583b-112">如果侧重于类型的行为，请考虑定义一个[类](../keywords/class.md)。</span><span class="sxs-lookup"><span data-stu-id="e583b-112">If you're focused on the behavior of a type, consider defining a [class](../keywords/class.md).</span></span> <span data-ttu-id="e583b-113">类类型具有引用语义。</span><span class="sxs-lookup"><span data-stu-id="e583b-113">Class types have *reference semantics*.</span></span> <span data-ttu-id="e583b-114">也就是说，类类型的变量包含的是对类型的实例的引用，而不是实例本身。</span><span class="sxs-lookup"><span data-stu-id="e583b-114">That is, a variable of a class type contains a reference to an instance of the type, not the instance itself.</span></span>

<span data-ttu-id="e583b-115">由于结构类型具有值语义，因此建议定义不可变的结构类型。</span><span class="sxs-lookup"><span data-stu-id="e583b-115">Because structure types have value semantics, we recommend you to define *immutable* structure types.</span></span>

## <a name="readonly-struct"></a><span data-ttu-id="e583b-116">`readonly` 结构</span><span class="sxs-lookup"><span data-stu-id="e583b-116">`readonly` struct</span></span>

<span data-ttu-id="e583b-117">从 C# 7.2 开始，可以使用 `readonly` 修饰符来声明结构类型不可变：</span><span class="sxs-lookup"><span data-stu-id="e583b-117">Beginning with C# 7.2, you use the `readonly` modifier to declare that a structure type is immutable:</span></span>

[!code-csharp[readonly struct](snippets/StructType.cs#ReadonlyStruct)]

<span data-ttu-id="e583b-118">`readonly` 结构的所有数据成员都必须是只读的，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e583b-118">All data members of a `readonly` struct must be read-only as follows:</span></span>

- <span data-ttu-id="e583b-119">任何字段声明都必须具有 [`readonly` 修饰符](../keywords/readonly.md)</span><span class="sxs-lookup"><span data-stu-id="e583b-119">Any field declaration must have the [`readonly` modifier](../keywords/readonly.md)</span></span>
- <span data-ttu-id="e583b-120">任何属性（包括自动实现的属性）都必须是只读的</span><span class="sxs-lookup"><span data-stu-id="e583b-120">Any property, including auto-implemented ones, must be read-only</span></span>

<span data-ttu-id="e583b-121">这样可以保证 `readonly` 结构的成员不会修改该结构的状态。</span><span class="sxs-lookup"><span data-stu-id="e583b-121">That guarantees that no member of a `readonly` struct modifies the state of the struct.</span></span>

> [!NOTE]
> <span data-ttu-id="e583b-122">在 `readonly` 结构中，可变引用类型的数据成员仍可改变其自身的状态。</span><span class="sxs-lookup"><span data-stu-id="e583b-122">In a `readonly` struct, a data member of a mutable reference type still can mutate its own state.</span></span> <span data-ttu-id="e583b-123">例如，不能替换 <xref:System.Collections.Generic.List%601> 实例，但可以向其中添加新元素。</span><span class="sxs-lookup"><span data-stu-id="e583b-123">For example, you cannot replace a <xref:System.Collections.Generic.List%601> instance, but you can add new elements to it.</span></span>

## <a name="limitations-with-the-design-of-a-structure-type"></a><span data-ttu-id="e583b-124">结构类型的设计限制</span><span class="sxs-lookup"><span data-stu-id="e583b-124">Limitations with the design of a structure type</span></span>

<span data-ttu-id="e583b-125">设计结构类型时，具有与[类](../keywords/class.md)类型相同的功能，但有以下例外：</span><span class="sxs-lookup"><span data-stu-id="e583b-125">When you design a structure type, you have the same capabilities as with a [class](../keywords/class.md) type, with the following exceptions:</span></span>

- <span data-ttu-id="e583b-126">不能声明无参数构造函数。</span><span class="sxs-lookup"><span data-stu-id="e583b-126">You cannot declare a parameterless constructor.</span></span> <span data-ttu-id="e583b-127">每个结构类型都已经提供了一个隐式无参数构造函数，该构造函数生成类型的[默认值](default-values.md)。</span><span class="sxs-lookup"><span data-stu-id="e583b-127">Every structure type already provides an implicit parameterless constructor that produces the [default value](default-values.md) of the type.</span></span>

- <span data-ttu-id="e583b-128">不能在声明实例字段或属性时对它们进行初始化。</span><span class="sxs-lookup"><span data-stu-id="e583b-128">You cannot initialize an instance field or property at its declaration.</span></span> <span data-ttu-id="e583b-129">但是，可以在其声明中初始化[静态](../keywords/static.md)或[常量](../keywords/const.md)字段或静态属性。</span><span class="sxs-lookup"><span data-stu-id="e583b-129">However, you can initialize a [static](../keywords/static.md) or [const](../keywords/const.md) field or a static property at its declaration.</span></span>

- <span data-ttu-id="e583b-130">结构类型的构造函数必须初始化该类型的所有实例字段。</span><span class="sxs-lookup"><span data-stu-id="e583b-130">A constructor of a structure type must initialize all instance fields of the type.</span></span>

- <span data-ttu-id="e583b-131">结构类型不能从其他类或结构类型继承，也不能作为类的基础类型。</span><span class="sxs-lookup"><span data-stu-id="e583b-131">A structure type cannot inherit from other class or structure type and it cannot be the base of a class.</span></span> <span data-ttu-id="e583b-132">但是，结构类型可以实现[接口](../keywords/interface.md)。</span><span class="sxs-lookup"><span data-stu-id="e583b-132">However, a structure type can implement [interfaces](../keywords/interface.md).</span></span>

- <span data-ttu-id="e583b-133">不能在结构类型中声明[终结器](../../programming-guide/classes-and-structs/destructors.md)。</span><span class="sxs-lookup"><span data-stu-id="e583b-133">You cannot declare a [finalizer](../../programming-guide/classes-and-structs/destructors.md) within a structure type.</span></span>

## <a name="instantiation-of-a-structure-type"></a><span data-ttu-id="e583b-134">结构类型的实例化</span><span class="sxs-lookup"><span data-stu-id="e583b-134">Instantiation of a structure type</span></span>

<span data-ttu-id="e583b-135">在 C# 中，必须先初始化已声明的变量，然后才能使用该变量。</span><span class="sxs-lookup"><span data-stu-id="e583b-135">In C#, you must initialize a declared variable before it can be used.</span></span> <span data-ttu-id="e583b-136">由于结构类型变量不能为 `null`（除非它是[可为空的值类型](nullable-value-types.md)的变量），必须实例化相应类型的实例。</span><span class="sxs-lookup"><span data-stu-id="e583b-136">Because a structure-type variable cannot be `null` (unless it's a variable of a [nullable value type](nullable-value-types.md)), you must instantiate an instance of the corresponding type.</span></span> <span data-ttu-id="e583b-137">有多种方法可实现此目的。</span><span class="sxs-lookup"><span data-stu-id="e583b-137">There are several ways to do that.</span></span>

<span data-ttu-id="e583b-138">通常，可使用 [`new`](../operators/new-operator.md) 运算符调用适当的构造函数来实例化结构类型。</span><span class="sxs-lookup"><span data-stu-id="e583b-138">Typically, you instantiate a structure type by calling an appropriate constructor with the [`new`](../operators/new-operator.md) operator.</span></span> <span data-ttu-id="e583b-139">每个结构类型都至少有一个构造函数。</span><span class="sxs-lookup"><span data-stu-id="e583b-139">Every structure type has at least one constructor.</span></span> <span data-ttu-id="e583b-140">这是一个隐式无参数构造函数，用于生成类型的[默认值](default-values.md)。</span><span class="sxs-lookup"><span data-stu-id="e583b-140">That's an implicit parameterless constructor, which produces the [default value](default-values.md) of the type.</span></span> <span data-ttu-id="e583b-141">还可以使用[默认值表达式](../operators/default.md)来生成类型的默认值。</span><span class="sxs-lookup"><span data-stu-id="e583b-141">You can also use a [default value expression](../operators/default.md) to produce the default value of a type.</span></span>

<span data-ttu-id="e583b-142">如果结构类型的所有实例字段都是可访问的，则还可以在不使用 `new` 运算符的情况下对其进行实例化。</span><span class="sxs-lookup"><span data-stu-id="e583b-142">If all instance fields of a structure type are accessible, you can also instantiate it without the `new` operator.</span></span> <span data-ttu-id="e583b-143">在这种情况下，在首次使用实例之前必须初始化所有实例字段。</span><span class="sxs-lookup"><span data-stu-id="e583b-143">In that case you must initialize all instance fields before the first use of the instance.</span></span> <span data-ttu-id="e583b-144">下面的示例演示如何执行此操作：</span><span class="sxs-lookup"><span data-stu-id="e583b-144">The following example shows how to do that:</span></span>

[!code-csharp[without new](snippets/StructType.cs#WithoutNew)]

<span data-ttu-id="e583b-145">在处理[内置值类型](value-types.md#built-in-value-types)的情况下，请使用相应的文本来指定类型的值。</span><span class="sxs-lookup"><span data-stu-id="e583b-145">In the case of the [built-in value types](value-types.md#built-in-value-types), use the corresponding literals to specify a value of the type.</span></span>

## <a name="passing-structure-type-variables-by-reference"></a><span data-ttu-id="e583b-146">按引用传递结构类型变量</span><span class="sxs-lookup"><span data-stu-id="e583b-146">Passing structure-type variables by reference</span></span>

<span data-ttu-id="e583b-147">将结构类型变量作为参数传递给方法或从方法返回结构类型值时，将复制结构类型的整个实例。</span><span class="sxs-lookup"><span data-stu-id="e583b-147">When you pass a structure-type variable to a method as an argument or return a structure-type value from a method, the whole instance of a structure type is copied.</span></span> <span data-ttu-id="e583b-148">这可能会影响高性能方案中涉及大型结构类型的代码的性能。</span><span class="sxs-lookup"><span data-stu-id="e583b-148">That can affect the performance of your code in high-performance scenarios that involve large structure types.</span></span> <span data-ttu-id="e583b-149">通过按引用传递结构类型变量，可以避免值复制操作。</span><span class="sxs-lookup"><span data-stu-id="e583b-149">You can avoid value copying by passing a structure-type variable by reference.</span></span> <span data-ttu-id="e583b-150">使用 [`ref`](../keywords/ref.md#passing-an-argument-by-reference)、[`out`](../keywords/out-parameter-modifier.md) 或 [`in`](../keywords/in-parameter-modifier.md) 方法参数修饰符，指示必须按引用传递参数。</span><span class="sxs-lookup"><span data-stu-id="e583b-150">Use the [`ref`](../keywords/ref.md#passing-an-argument-by-reference), [`out`](../keywords/out-parameter-modifier.md), or [`in`](../keywords/in-parameter-modifier.md) method parameter modifiers to indicate that an argument must be passed by reference.</span></span> <span data-ttu-id="e583b-151">使用 [ref 返回值](../../programming-guide/classes-and-structs/ref-returns.md)按引用返回方法结果。</span><span class="sxs-lookup"><span data-stu-id="e583b-151">Use [ref returns](../../programming-guide/classes-and-structs/ref-returns.md) to return a method result by reference.</span></span> <span data-ttu-id="e583b-152">有关详细信息，请参阅[编写安全有效的 C# 代码](../../write-safe-efficient-code.md)。</span><span class="sxs-lookup"><span data-stu-id="e583b-152">For more information, see [Write safe and efficient C# code](../../write-safe-efficient-code.md).</span></span>

## <a name="conversions"></a><span data-ttu-id="e583b-153">转换</span><span class="sxs-lookup"><span data-stu-id="e583b-153">Conversions</span></span>

<span data-ttu-id="e583b-154">对于任何结构类型，都存在与 <xref:System.ValueType?displayProperty=nameWithType> 和 <xref:System.Object?displayProperty=nameWithType> 类型之间的[装箱和取消装箱](../../programming-guide/types/boxing-and-unboxing.md)相互转换。</span><span class="sxs-lookup"><span data-stu-id="e583b-154">For any structure type, there exist [boxing and unboxing](../../programming-guide/types/boxing-and-unboxing.md) conversions to and from the <xref:System.ValueType?displayProperty=nameWithType> and <xref:System.Object?displayProperty=nameWithType> types.</span></span> <span data-ttu-id="e583b-155">还存在结构类型和它所实现的任何接口之间的装箱和取消装箱转换。</span><span class="sxs-lookup"><span data-stu-id="e583b-155">There exist also boxing and unboxing conversions between a structure type and any interface that it implements.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="e583b-156">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="e583b-156">C# language specification</span></span>

<span data-ttu-id="e583b-157">有关详细信息，请参阅 [C# 语言规范](~/_csharplang/spec/introduction.md)中的[结构](~/_csharplang/spec/structs.md)部分。</span><span class="sxs-lookup"><span data-stu-id="e583b-157">For more information, see the [Structs](~/_csharplang/spec/structs.md) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="e583b-158">有关 `readonly` 结构的详细信息，请参阅[功能建议说明](~/_csharplang/proposals/csharp-7.2/readonly-ref.md#readonly-structs)。</span><span class="sxs-lookup"><span data-stu-id="e583b-158">For more information about `readonly` structs, see the [feature proposal note](~/_csharplang/proposals/csharp-7.2/readonly-ref.md#readonly-structs).</span></span>

## <a name="see-also"></a><span data-ttu-id="e583b-159">请参阅</span><span class="sxs-lookup"><span data-stu-id="e583b-159">See also</span></span>

- [<span data-ttu-id="e583b-160">C# 参考</span><span class="sxs-lookup"><span data-stu-id="e583b-160">C# reference</span></span>](../index.md)
- [<span data-ttu-id="e583b-161">设计指南 - 在类和结构之间选择</span><span class="sxs-lookup"><span data-stu-id="e583b-161">Design guidelines - Choosing between class and struct</span></span>](../../../standard/design-guidelines/choosing-between-class-and-struct.md)
- [<span data-ttu-id="e583b-162">设计指南 - 结构设计</span><span class="sxs-lookup"><span data-stu-id="e583b-162">Design guidelines - Struct design</span></span>](../../../standard/design-guidelines/struct.md)
- [<span data-ttu-id="e583b-163">类和结构</span><span class="sxs-lookup"><span data-stu-id="e583b-163">Classes and structs</span></span>](../../programming-guide/classes-and-structs/index.md)
