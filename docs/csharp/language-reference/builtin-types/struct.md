---
title: 结构类型 - C# 参考
ms.date: 02/24/2020
f1_keywords:
- struct_CSharpKeyword
helpviewer_keywords:
- struct keyword [C#]
- struct type [C#]
- structure type [C#]
ms.assetid: ff3dd9b7-dc93-4720-8855-ef5558f65c7c
ms.openlocfilehash: b85d0df086f3ca65ed995594dd374286e1c3ba5c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "78847724"
---
# <a name="structure-types-c-reference"></a><span data-ttu-id="b98a8-102">结构类型（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="b98a8-102">Structure types (C# reference)</span></span>

<span data-ttu-id="b98a8-103">结构类型（“structure type”或“struct type”）是一种可封装数据和相关功能的值类型   [](value-types.md)。</span><span class="sxs-lookup"><span data-stu-id="b98a8-103">A *structure type* (or *struct type*) is a [value type](value-types.md) that can encapsulate data and related functionality.</span></span> <span data-ttu-id="b98a8-104">使用 `struct` 关键字定义结构类型：</span><span class="sxs-lookup"><span data-stu-id="b98a8-104">You use the `struct` keyword to define a structure type:</span></span>

[!code-csharp[struct example](snippets/StructType.cs#StructExample)]

<span data-ttu-id="b98a8-105">结构类型具有值语义  。</span><span class="sxs-lookup"><span data-stu-id="b98a8-105">Structure types have *value semantics*.</span></span> <span data-ttu-id="b98a8-106">也就是说，结构类型的变量包含类型的实例。</span><span class="sxs-lookup"><span data-stu-id="b98a8-106">That is, a variable of a structure type contains an instance of the type.</span></span> <span data-ttu-id="b98a8-107">默认情况下，在分配中，通过将参数传递给方法并返回方法结果来复制变量值。</span><span class="sxs-lookup"><span data-stu-id="b98a8-107">By default, variable values are copied on assignment, passing an argument to a method, and returning a method result.</span></span> <span data-ttu-id="b98a8-108">对于结构类型变量，将复制该类型的实例。</span><span class="sxs-lookup"><span data-stu-id="b98a8-108">In the case of a structure-type variable, an instance of the type is copied.</span></span> <span data-ttu-id="b98a8-109">有关更多信息，请参阅[值类型](value-types.md)。</span><span class="sxs-lookup"><span data-stu-id="b98a8-109">For more information, see [Value types](value-types.md).</span></span>

<span data-ttu-id="b98a8-110">通常，可以使用结构类型来设计以数据为中心的较小类型，这些类型只有很少的行为或没有行为。</span><span class="sxs-lookup"><span data-stu-id="b98a8-110">Typically, you use structure types to design small data-centric types that provide little or no behavior.</span></span> <span data-ttu-id="b98a8-111">例如，.NET 使用结构类型来表示数字（[整数](integral-numeric-types.md)和[实数](floating-point-numeric-types.md)）、[布尔值](bool.md)、[Unicode 字符](char.md)以及[时间实例](xref:System.DateTime)。</span><span class="sxs-lookup"><span data-stu-id="b98a8-111">For example, .NET uses structure types to represent a number (both [integer](integral-numeric-types.md) and [real](floating-point-numeric-types.md)), a [Boolean value](bool.md), a [Unicode character](char.md), a [time instance](xref:System.DateTime).</span></span> <span data-ttu-id="b98a8-112">如果侧重于类型的行为，请考虑定义一个[类](../keywords/class.md)。</span><span class="sxs-lookup"><span data-stu-id="b98a8-112">If you're focused on the behavior of a type, consider defining a [class](../keywords/class.md).</span></span> <span data-ttu-id="b98a8-113">类类型具有引用语义  。</span><span class="sxs-lookup"><span data-stu-id="b98a8-113">Class types have *reference semantics*.</span></span> <span data-ttu-id="b98a8-114">也就是说，类类型的变量包含的是对类型的实例的引用，而不是实例本身。</span><span class="sxs-lookup"><span data-stu-id="b98a8-114">That is, a variable of a class type contains a reference to an instance of the type, not the instance itself.</span></span>

## <a name="limitations-with-the-design-of-a-structure-type"></a><span data-ttu-id="b98a8-115">结构类型的设计限制</span><span class="sxs-lookup"><span data-stu-id="b98a8-115">Limitations with the design of a structure type</span></span>

<span data-ttu-id="b98a8-116">设计结构类型时，具有与[类](../keywords/class.md)类型相同的功能，但有以下例外：</span><span class="sxs-lookup"><span data-stu-id="b98a8-116">When you design a structure type, you have the same capabilities as with a [class](../keywords/class.md) type, with the following exceptions:</span></span>

- <span data-ttu-id="b98a8-117">不能声明无参数构造函数。</span><span class="sxs-lookup"><span data-stu-id="b98a8-117">You cannot declare a parameterless constructor.</span></span> <span data-ttu-id="b98a8-118">每个结构类型都已经提供了一个隐式无参数构造函数，该构造函数生成类型的[默认值](default-values.md)。</span><span class="sxs-lookup"><span data-stu-id="b98a8-118">Every structure type already provides an implicit parameterless constructor that produces the [default value](default-values.md) of the type.</span></span>

- <span data-ttu-id="b98a8-119">不能在声明实例字段或属性时对它们进行初始化。</span><span class="sxs-lookup"><span data-stu-id="b98a8-119">You cannot initialize an instance field or property at its declaration.</span></span> <span data-ttu-id="b98a8-120">但是，可以在其声明中初始化[静态](../keywords/static.md)或[常量](../keywords/const.md)字段或静态属性。</span><span class="sxs-lookup"><span data-stu-id="b98a8-120">However, you can initialize a [static](../keywords/static.md) or [const](../keywords/const.md) field or a static property at its declaration.</span></span>

- <span data-ttu-id="b98a8-121">结构类型的构造函数必须初始化该类型的所有实例字段。</span><span class="sxs-lookup"><span data-stu-id="b98a8-121">A constructor of a structure type must initialize all instance fields of the type.</span></span>

- <span data-ttu-id="b98a8-122">结构类型不能从其他类或结构类型继承，也不能作为类的基础类型。</span><span class="sxs-lookup"><span data-stu-id="b98a8-122">A structure type cannot inherit from other class or structure type and it cannot be the base of a class.</span></span> <span data-ttu-id="b98a8-123">但是，结构类型可以实现[接口](../keywords/interface.md)。</span><span class="sxs-lookup"><span data-stu-id="b98a8-123">However, a structure type can implement [interfaces](../keywords/interface.md).</span></span>

- <span data-ttu-id="b98a8-124">不能在结构类型中声明[终结器](../../programming-guide/classes-and-structs/destructors.md)。</span><span class="sxs-lookup"><span data-stu-id="b98a8-124">You cannot declare a [finalizer](../../programming-guide/classes-and-structs/destructors.md) within a structure type.</span></span>

## <a name="instantiation-of-a-structure-type"></a><span data-ttu-id="b98a8-125">结构类型的实例化</span><span class="sxs-lookup"><span data-stu-id="b98a8-125">Instantiation of a structure type</span></span>

<span data-ttu-id="b98a8-126">在 C# 中，必须先初始化已声明的变量，然后才能使用该变量。</span><span class="sxs-lookup"><span data-stu-id="b98a8-126">In C#, you must initialize a declared variable before it can be used.</span></span> <span data-ttu-id="b98a8-127">由于结构类型变量不能为 `null`（除非它是[可为空的值类型](nullable-value-types.md)的变量），必须实例化相应类型的实例。</span><span class="sxs-lookup"><span data-stu-id="b98a8-127">Because a structure-type variable cannot be `null` (unless it's a variable of a [nullable value type](nullable-value-types.md)), you must instantiate an instance of the corresponding type.</span></span> <span data-ttu-id="b98a8-128">有多种方法可实现此目的。</span><span class="sxs-lookup"><span data-stu-id="b98a8-128">There are several ways to do that.</span></span>

<span data-ttu-id="b98a8-129">通常，可使用 [`new`](../operators/new-operator.md) 运算符调用适当的构造函数来实例化结构类型。</span><span class="sxs-lookup"><span data-stu-id="b98a8-129">Typically, you instantiate a structure type by calling an appropriate constructor with the [`new`](../operators/new-operator.md) operator.</span></span> <span data-ttu-id="b98a8-130">每个结构类型都至少有一个构造函数。</span><span class="sxs-lookup"><span data-stu-id="b98a8-130">Every structure type has at least one constructor.</span></span> <span data-ttu-id="b98a8-131">这是一个隐式无参数构造函数，用于生成类型的[默认值](default-values.md)。</span><span class="sxs-lookup"><span data-stu-id="b98a8-131">That's an implicit parameterless constructor, which produces the [default value](default-values.md) of the type.</span></span> <span data-ttu-id="b98a8-132">还可以使用[默认](../operators/default.md)运算符或文本来生成类型的默认值。</span><span class="sxs-lookup"><span data-stu-id="b98a8-132">You can also use the [default](../operators/default.md) operator or literal to produce the default value of a type.</span></span>

<span data-ttu-id="b98a8-133">如果结构类型的所有实例字段都是可访问的，则还可以在不使用 `new` 运算符的情况下对其进行实例化。</span><span class="sxs-lookup"><span data-stu-id="b98a8-133">If all instance fields of a structure type are accessible, you can also instantiate it without the `new` operator.</span></span> <span data-ttu-id="b98a8-134">在这种情况下，在首次使用实例之前必须初始化所有实例字段。</span><span class="sxs-lookup"><span data-stu-id="b98a8-134">In that case you must initialize all instance fields before the first use of the instance.</span></span> <span data-ttu-id="b98a8-135">下面的示例演示如何执行此操作：</span><span class="sxs-lookup"><span data-stu-id="b98a8-135">The following example shows how to do that:</span></span>

[!code-csharp[without new](snippets/StructType.cs#WithoutNew)]

<span data-ttu-id="b98a8-136">在处理[内置值类型](value-types.md#built-in-value-types)的情况下，请使用相应的文本来指定类型的值。</span><span class="sxs-lookup"><span data-stu-id="b98a8-136">In the case of the [built-in value types](value-types.md#built-in-value-types), use the corresponding literals to specify a value of the type.</span></span>

## <a name="passing-structure-type-variables-by-reference"></a><span data-ttu-id="b98a8-137">按引用传递结构类型变量</span><span class="sxs-lookup"><span data-stu-id="b98a8-137">Passing structure-type variables by reference</span></span>

<span data-ttu-id="b98a8-138">将结构类型变量作为参数传递给方法或从方法返回结构类型值时，将复制结构类型的整个实例。</span><span class="sxs-lookup"><span data-stu-id="b98a8-138">When you pass a structure-type variable to a method as an argument or return a structure-type value from a method, the whole instance of a structure type is copied.</span></span> <span data-ttu-id="b98a8-139">这可能会影响高性能方案中涉及大型结构类型的代码的性能。</span><span class="sxs-lookup"><span data-stu-id="b98a8-139">That can affect the performance of your code in high-performance scenarios that involve large structure types.</span></span> <span data-ttu-id="b98a8-140">通过按引用传递结构类型变量，可以避免值复制操作。</span><span class="sxs-lookup"><span data-stu-id="b98a8-140">You can avoid value copying by passing a structure-type variable by reference.</span></span> <span data-ttu-id="b98a8-141">使用 [`ref`](../keywords/ref.md#passing-an-argument-by-reference)、[`out`](../keywords/out-parameter-modifier.md) 或 [`in`](../keywords/in-parameter-modifier.md) 方法参数修饰符，指示必须按引用传递参数。</span><span class="sxs-lookup"><span data-stu-id="b98a8-141">Use the [`ref`](../keywords/ref.md#passing-an-argument-by-reference), [`out`](../keywords/out-parameter-modifier.md), or [`in`](../keywords/in-parameter-modifier.md) method parameter modifiers to indicate that an argument must be passed by reference.</span></span> <span data-ttu-id="b98a8-142">使用 [ref 返回值](../../programming-guide/classes-and-structs/ref-returns.md)按引用返回方法结果。</span><span class="sxs-lookup"><span data-stu-id="b98a8-142">Use [ref returns](../../programming-guide/classes-and-structs/ref-returns.md) to return a method result by reference.</span></span> <span data-ttu-id="b98a8-143">有关详细信息，请参阅[编写安全有效的 C# 代码](../../write-safe-efficient-code.md)。</span><span class="sxs-lookup"><span data-stu-id="b98a8-143">For more information, see [Write safe and efficient C# code](../../write-safe-efficient-code.md).</span></span>

## <a name="conversions"></a><span data-ttu-id="b98a8-144">转换</span><span class="sxs-lookup"><span data-stu-id="b98a8-144">Conversions</span></span>

<span data-ttu-id="b98a8-145">对于任何结构类型，都存在与 <xref:System.ValueType?displayProperty=nameWithType> 和 <xref:System.Object?displayProperty=nameWithType> 类型之间的[装箱和取消装箱](../../programming-guide/types/boxing-and-unboxing.md)相互转换。</span><span class="sxs-lookup"><span data-stu-id="b98a8-145">For any structure type, there exist [boxing and unboxing](../../programming-guide/types/boxing-and-unboxing.md) conversions to and from the <xref:System.ValueType?displayProperty=nameWithType> and <xref:System.Object?displayProperty=nameWithType> types.</span></span> <span data-ttu-id="b98a8-146">还存在结构类型和它所实现的任何接口之间的装箱和取消装箱转换。</span><span class="sxs-lookup"><span data-stu-id="b98a8-146">There exist also boxing and unboxing conversions between a structure type and any interface that it implements.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="b98a8-147">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="b98a8-147">C# language specification</span></span>

<span data-ttu-id="b98a8-148">有关详细信息，请参阅 [C# 语言规范](~/_csharplang/spec/introduction.md)中的[结构](~/_csharplang/spec/structs.md)部分。</span><span class="sxs-lookup"><span data-stu-id="b98a8-148">For more information, see the [Structs](~/_csharplang/spec/structs.md) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b98a8-149">请参阅</span><span class="sxs-lookup"><span data-stu-id="b98a8-149">See also</span></span>

- [<span data-ttu-id="b98a8-150">C# 参考</span><span class="sxs-lookup"><span data-stu-id="b98a8-150">C# reference</span></span>](../index.md)
- [<span data-ttu-id="b98a8-151">设计指南 - 在类和结构之间选择</span><span class="sxs-lookup"><span data-stu-id="b98a8-151">Design guidelines - Choosing between class and struct</span></span>](../../../standard/design-guidelines/choosing-between-class-and-struct.md)
- [<span data-ttu-id="b98a8-152">设计指南 - 结构设计</span><span class="sxs-lookup"><span data-stu-id="b98a8-152">Design guidelines - Struct design</span></span>](../../../standard/design-guidelines/struct.md)
- [<span data-ttu-id="b98a8-153">类和结构</span><span class="sxs-lookup"><span data-stu-id="b98a8-153">Classes and structs</span></span>](../../programming-guide/classes-and-structs/index.md)
