---
title: "C# 类型和变量 - C# 语言介绍"
description: "了解如何在 C# 中定义类型和声明变量"
keywords: ".NET, C#, 类型, 引用类型, 值类型"
author: BillWagner
ms.author: wiwagn
ms.date: 08/10/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: f8a8051e-0049-43f1-b594-9c84cc7b1224
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 1f1031384520b9ed37246361da8bbc1b42addb0b
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---

# <a name="types-and-variables"></a><span data-ttu-id="74dc7-104">类型和变量</span><span class="sxs-lookup"><span data-stu-id="74dc7-104">Types and variables</span></span>

<span data-ttu-id="74dc7-105">C# 有两种类型：*值类型*和*引用类型*。</span><span class="sxs-lookup"><span data-stu-id="74dc7-105">There are two kinds of types in C#: *value types* and *reference types*.</span></span> <span data-ttu-id="74dc7-106">值类型的变量直接包含数据，而引用类型的变量则存储对数据（称为“对象”）的引用。</span><span class="sxs-lookup"><span data-stu-id="74dc7-106">Variables of value types directly contain their data whereas variables of reference types store references to their data, the latter being known as objects.</span></span> <span data-ttu-id="74dc7-107">借助引用类型，两个变量可以引用同一对象；因此，对一个变量执行的运算可能会影响另一个变量引用的对象。</span><span class="sxs-lookup"><span data-stu-id="74dc7-107">With reference types, it is possible for two variables to reference the same object and thus possible for operations on one variable to affect the object referenced by the other variable.</span></span> <span data-ttu-id="74dc7-108">借助值类型，每个变量都有自己的数据副本；因此，对一个变量执行的运算不会影响另一个变量（`ref` 和 `out` 参数变量除外）。</span><span class="sxs-lookup"><span data-stu-id="74dc7-108">With value types, the variables each have their own copy of the data, and it is not possible for operations on one to affect the other (except in the case of `ref` and `out` parameter variables).</span></span>

<span data-ttu-id="74dc7-109">C# 值类型又细分为*简单类型*、*枚举类型*、*结构类型*和*可以为 null 的值类型*。</span><span class="sxs-lookup"><span data-stu-id="74dc7-109">C#’s value types are further divided into *simple types*, *enum types*, *struct types*, and *nullable value types*.</span></span> <span data-ttu-id="74dc7-110">C# 引用类型又细分为*类类型*、*接口类型*、*数组类型*和*委托类型*。</span><span class="sxs-lookup"><span data-stu-id="74dc7-110">C#’s reference types are further divided into *class types*, *interface types*, *array types*, and *delegate types*.</span></span>

<span data-ttu-id="74dc7-111">下面概述了 C# 的类型系统。</span><span class="sxs-lookup"><span data-stu-id="74dc7-111">The following provides an overview of C#’s type system.</span></span>

* <span data-ttu-id="74dc7-112">值类型</span><span class="sxs-lookup"><span data-stu-id="74dc7-112">Value types</span></span>
    - <span data-ttu-id="74dc7-113">简单类型</span><span class="sxs-lookup"><span data-stu-id="74dc7-113">Simple Types</span></span>
        * <span data-ttu-id="74dc7-114">有符号的整型：`sbyte`、`short`、`int`、`long`</span><span class="sxs-lookup"><span data-stu-id="74dc7-114">Signed integral: `sbyte`, `short`, `int`, `long`</span></span>
        * <span data-ttu-id="74dc7-115">无符号的整型：`byte`、`ushort`、`uint`、`ulong`</span><span class="sxs-lookup"><span data-stu-id="74dc7-115">Unsigned integral: `byte`, `ushort`, `uint`, `ulong`</span></span>
        * <span data-ttu-id="74dc7-116">Unicode 字符：`char`</span><span class="sxs-lookup"><span data-stu-id="74dc7-116">Unicode characters: `char`</span></span>
        * <span data-ttu-id="74dc7-117">IEEE 浮点：`float`、`double`</span><span class="sxs-lookup"><span data-stu-id="74dc7-117">IEEE floating point: `float`, `double`</span></span>
        * <span data-ttu-id="74dc7-118">高精度小数：`decimal`</span><span class="sxs-lookup"><span data-stu-id="74dc7-118">High-precision decimal: `decimal`</span></span>
        * <span data-ttu-id="74dc7-119">布尔：`bool`</span><span class="sxs-lookup"><span data-stu-id="74dc7-119">Boolean: `bool`</span></span>
    - <span data-ttu-id="74dc7-120">枚举类型</span><span class="sxs-lookup"><span data-stu-id="74dc7-120">Enum types</span></span>
        * <span data-ttu-id="74dc7-121">格式为 `enum E {...}` 的用户定义类型</span><span class="sxs-lookup"><span data-stu-id="74dc7-121">User-defined types of the form `enum E {...}`</span></span>
    - <span data-ttu-id="74dc7-122">结构类型</span><span class="sxs-lookup"><span data-stu-id="74dc7-122">Struct types</span></span>
        * <span data-ttu-id="74dc7-123">格式为 `struct S {...}` 的用户定义类型</span><span class="sxs-lookup"><span data-stu-id="74dc7-123">User-defined types of the form `struct S {...}`</span></span>
    - <span data-ttu-id="74dc7-124">可以为 null 的值类型</span><span class="sxs-lookup"><span data-stu-id="74dc7-124">Nullable value types</span></span>
        * <span data-ttu-id="74dc7-125">值为 `null` 的其他所有值类型的扩展</span><span class="sxs-lookup"><span data-stu-id="74dc7-125">Extensions of all other value types with a `null` value</span></span>
* <span data-ttu-id="74dc7-126">引用类型</span><span class="sxs-lookup"><span data-stu-id="74dc7-126">Reference types</span></span>
    - <span data-ttu-id="74dc7-127">类类型</span><span class="sxs-lookup"><span data-stu-id="74dc7-127">Class types</span></span>
        * <span data-ttu-id="74dc7-128">其他所有类型的最终基类：`object`</span><span class="sxs-lookup"><span data-stu-id="74dc7-128">Ultimate base class of all other types: `object`</span></span>
        * <span data-ttu-id="74dc7-129">Unicode 字符串：`string`</span><span class="sxs-lookup"><span data-stu-id="74dc7-129">Unicode strings: `string`</span></span>
        * <span data-ttu-id="74dc7-130">格式为 `class C {...}` 的用户定义类型</span><span class="sxs-lookup"><span data-stu-id="74dc7-130">User-defined types of the form `class C {...}`</span></span>
    - <span data-ttu-id="74dc7-131">接口类型</span><span class="sxs-lookup"><span data-stu-id="74dc7-131">Interface types</span></span>
        * <span data-ttu-id="74dc7-132">格式为 `interface I {...}` 的用户定义类型</span><span class="sxs-lookup"><span data-stu-id="74dc7-132">User-defined types of the form `interface I {...}`</span></span>
    - <span data-ttu-id="74dc7-133">数组类型</span><span class="sxs-lookup"><span data-stu-id="74dc7-133">Array types</span></span>
        * <span data-ttu-id="74dc7-134">一维和多维，例如 `int[]` 和 `int[,]`</span><span class="sxs-lookup"><span data-stu-id="74dc7-134">Single- and multi-dimensional, for example, `int[]` and `int[,]`</span></span>
    - <span data-ttu-id="74dc7-135">委托类型</span><span class="sxs-lookup"><span data-stu-id="74dc7-135">Delegate types</span></span>
        * <span data-ttu-id="74dc7-136">格式为 `delegate int D(...)` 的用户定义类型</span><span class="sxs-lookup"><span data-stu-id="74dc7-136">User-defined types of the form `delegate int D(...)`</span></span>

<span data-ttu-id="74dc7-137">八个整型类型支持带符号或不带符号格式的 8 位、16 位、32 位和 64 位值。</span><span class="sxs-lookup"><span data-stu-id="74dc7-137">The eight integral types provide support for 8-bit, 16-bit, 32-bit, and 64-bit values in signed or unsigned form.</span></span>

<span data-ttu-id="74dc7-138">两个浮点类型（`float` 和 `double`）分别使用 32 位单精度和 64 位双精度 IEC-60559 格式表示。</span><span class="sxs-lookup"><span data-stu-id="74dc7-138">The two floating-point types, `float` and `double`, are represented using the 32-bit single-precision and 64-bit double-precision IEC-60559 formats, respectively.</span></span>

<span data-ttu-id="74dc7-139">`decimal` 类型是适用于财务和货币计算的 128 位数据类型。</span><span class="sxs-lookup"><span data-stu-id="74dc7-139">The `decimal` type is a 128-bit data type suitable for financial and monetary calculations.</span></span>

<span data-ttu-id="74dc7-140">C# 的 `bool` 类型用于表示布尔值（`true` 或 `false`）。</span><span class="sxs-lookup"><span data-stu-id="74dc7-140">C#’s `bool` type is used to represent Boolean values—values that are either `true` or `false`.</span></span>

<span data-ttu-id="74dc7-141">C# 使用 Unicode 编码处理字符和字符串。</span><span class="sxs-lookup"><span data-stu-id="74dc7-141">Character and string processing in C# uses Unicode encoding.</span></span> <span data-ttu-id="74dc7-142">`char` 类型表示 UTF-16 代码单元，`string` 类型表示一系列 UTF-16 代码单元。</span><span class="sxs-lookup"><span data-stu-id="74dc7-142">The `char` type represents a UTF-16 code unit, and the `string` type represents a sequence of UTF-16 code units.</span></span>

<span data-ttu-id="74dc7-143">下面总结了 C# 的数值类型。</span><span class="sxs-lookup"><span data-stu-id="74dc7-143">This summarizes C#’s numeric types.</span></span>

* <span data-ttu-id="74dc7-144">有符号的整型</span><span class="sxs-lookup"><span data-stu-id="74dc7-144">Signed Integral</span></span>
    - <span data-ttu-id="74dc7-145">`sbyte`：8 位，介于 -128 到 127 之间</span><span class="sxs-lookup"><span data-stu-id="74dc7-145">`sbyte`:  8 bits, range from -128 - 127</span></span>
    - <span data-ttu-id="74dc7-146">`short`：16 位，介于 -32,768 到 32,767 之间</span><span class="sxs-lookup"><span data-stu-id="74dc7-146">`short`: 16 bits, range from -32,768 - 32,767</span></span>
    - <span data-ttu-id="74dc7-147">`int`：32 位，介于 -2,147,483,648 到 2,147,483,647 之间</span><span class="sxs-lookup"><span data-stu-id="74dc7-147">`int`  : 32 bits, range from -2,147,483,648 - 2,147,483,647</span></span>
    - <span data-ttu-id="74dc7-148">`long`：64 位，介于 -9,223,372,036,854,775,808 到 9,223,372,036,854,775,807 之间</span><span class="sxs-lookup"><span data-stu-id="74dc7-148">`long` : 64 bits, range from –9,223,372,036,854,775,808 to 9,223,372,036,854,775,807</span></span>
* <span data-ttu-id="74dc7-149">无符号的整型</span><span class="sxs-lookup"><span data-stu-id="74dc7-149">Unsigned integral</span></span>
    - <span data-ttu-id="74dc7-150">`byte`：8 位，介于 0 到 255 之间</span><span class="sxs-lookup"><span data-stu-id="74dc7-150">`byte`   :  8 bits, range from 0 - 255</span></span>
    - <span data-ttu-id="74dc7-151">`ushort`：16 位，介于 0 到 65,535 之间</span><span class="sxs-lookup"><span data-stu-id="74dc7-151">`ushort` : 16 bits, range from 0 - 65,535</span></span>
    - <span data-ttu-id="74dc7-152">`uint`：32 位，介于 0 到 4,294,967,295 之间</span><span class="sxs-lookup"><span data-stu-id="74dc7-152">`uint`   : 32 bits, range from 0 - 4,294,967,295</span></span>
    - <span data-ttu-id="74dc7-153">`ulong`：64 位，介于 0 到 18,446,744,073,709,551,615 之间</span><span class="sxs-lookup"><span data-stu-id="74dc7-153">`ulong`  : 64 bits, range from 0 - 18,446,744,073,709,551,615</span></span>
* <span data-ttu-id="74dc7-154">浮点</span><span class="sxs-lookup"><span data-stu-id="74dc7-154">Floating point</span></span>
    - <span data-ttu-id="74dc7-155">`float`：32 位，介于 1.5 × 10<sup>-45</sup> 到 3.4 × 10<sup>38</sup> 之间，7 位精度</span><span class="sxs-lookup"><span data-stu-id="74dc7-155">`float`  : 32 bits, range from 1.5 × 10<sup>−45</sup> - 3.4 × 10<sup>38</sup>,    7-digit precision</span></span>
    - <span data-ttu-id="74dc7-156">`double`：64 位，介于 5.0 × 10<sup>-324</sup> 到 1.7 × 10<sup>308</sup> 之间，15 位精度</span><span class="sxs-lookup"><span data-stu-id="74dc7-156">`double` : 64 bits, range from 5.0 × 10<sup>−324</sup> - 1.7 × 10<sup>308</sup>, 15-digit precision</span></span>
* <span data-ttu-id="74dc7-157">Decimal</span><span class="sxs-lookup"><span data-stu-id="74dc7-157">Decimal</span></span>
    - <span data-ttu-id="74dc7-158">`decimal`：128 位，至少介于 -7.9 × 10<sup>-28</sup> 到 7.9 × 10<sup>28</sup> 之间，至少为 28 位精度</span><span class="sxs-lookup"><span data-stu-id="74dc7-158">`decimal` : 128 bits, range is at least –7.9 × 10<sup>−28</sup> -  7.9 × 10<sup>28</sup>, with at least 28-digit precision</span></span>
    
<span data-ttu-id="74dc7-159">C# 程序使用*类型声明*创建新类型。</span><span class="sxs-lookup"><span data-stu-id="74dc7-159">C# programs use *type declarations* to create new types.</span></span> <span data-ttu-id="74dc7-160">类型声明指定新类型的名称和成员。</span><span class="sxs-lookup"><span data-stu-id="74dc7-160">A type declaration specifies the name and the members of the new type.</span></span> <span data-ttu-id="74dc7-161">用户可定义以下五种 C# 类型：类类型、结构类型、接口类型、枚举类型和委托类型。</span><span class="sxs-lookup"><span data-stu-id="74dc7-161">Five of C#’s categories of types are user-definable: class types, struct types, interface types, enum types, and delegate types.</span></span>

<span data-ttu-id="74dc7-162">`class` 类型定义包含数据成员（字段）和函数成员（方法、属性及其他）的数据结构。</span><span class="sxs-lookup"><span data-stu-id="74dc7-162">A `class` type defines a data structure that contains data members (fields) and function members (methods, properties, and others).</span></span> <span data-ttu-id="74dc7-163">类类型支持单一继承和多形性，即派生类可以扩展和专门针对基类的机制。</span><span class="sxs-lookup"><span data-stu-id="74dc7-163">Class types support single inheritance and polymorphism, mechanisms whereby derived classes can extend and specialize base classes.</span></span>

<span data-ttu-id="74dc7-164">`struct` 类型定义包含数据成员和函数成员的结构，这一点与类类型相似。</span><span class="sxs-lookup"><span data-stu-id="74dc7-164">A `struct` type is similar to a class type in that it represents a structure with data members and function members.</span></span> <span data-ttu-id="74dc7-165">不过，与类不同的是，结构是值类型，通常不需要进行堆分配。</span><span class="sxs-lookup"><span data-stu-id="74dc7-165">However, unlike classes, structs are value types and do not typically require heap allocation.</span></span> <span data-ttu-id="74dc7-166">结构类型不支持用户指定的继承，并且所有结构类型均隐式继承自类型 `object`。</span><span class="sxs-lookup"><span data-stu-id="74dc7-166">Struct types do not support user-specified inheritance, and all struct types implicitly inherit from type `object`.</span></span>

<span data-ttu-id="74dc7-167">`interface` 类型将协定定义为一组已命名的公共函数成员。</span><span class="sxs-lookup"><span data-stu-id="74dc7-167">An `interface` type defines a contract as a named set of public function members.</span></span> <span data-ttu-id="74dc7-168">实现 `interface` 的 `class` 或 `struct` 必须提供接口函数成员的实现代码。</span><span class="sxs-lookup"><span data-stu-id="74dc7-168">A `class` or `struct` that implements an `interface` must provide implementations of the interface’s function members.</span></span> <span data-ttu-id="74dc7-169">`interface` 可以继承自多个基接口，`class` 和 `struct` 可以实现多个接口。</span><span class="sxs-lookup"><span data-stu-id="74dc7-169">An `interface` may inherit from multiple base interfaces, and a `class` or `struct` may implement multiple interfaces.</span></span>

<span data-ttu-id="74dc7-170">`delegate` 类型表示引用包含特定参数列表和返回类型的方法。</span><span class="sxs-lookup"><span data-stu-id="74dc7-170">A `delegate` type represents references to methods with a particular parameter list and return type.</span></span> <span data-ttu-id="74dc7-171">通过委托，可以将方法视为可分配给变量并可作为参数传递的实体。</span><span class="sxs-lookup"><span data-stu-id="74dc7-171">Delegates make it possible to treat methods as entities that can be assigned to variables and passed as parameters.</span></span> <span data-ttu-id="74dc7-172">委托类同于函数式语言提供的函数类型。</span><span class="sxs-lookup"><span data-stu-id="74dc7-172">Delegates are analogous to function types provided by functional languages.</span></span> <span data-ttu-id="74dc7-173">委托也类似于其他一些语言中的函数指针概念，但与函数指针不同的是，委托不仅面向对象，还类型安全。</span><span class="sxs-lookup"><span data-stu-id="74dc7-173">They are also similar to the concept of function pointers found in some other languages, but unlike function pointers, delegates are object-oriented and type-safe.</span></span>

<span data-ttu-id="74dc7-174">`class`、`struct`、`interface` 和 `delegate` 类型全部都支持泛型，因此可以使用其他类型对它们进行参数化。</span><span class="sxs-lookup"><span data-stu-id="74dc7-174">The `class`, `struct`, `interface` and `delegate` types all support generics, whereby they can be parameterized with other types.</span></span>

<span data-ttu-id="74dc7-175">`enum` 类型是一种包含已命名常量的独特类型。</span><span class="sxs-lookup"><span data-stu-id="74dc7-175">An `enum` type is a distinct type with named constants.</span></span> <span data-ttu-id="74dc7-176">每个 `enum` 类型都有一个基础类型（必须是八种整型类型之一）。</span><span class="sxs-lookup"><span data-stu-id="74dc7-176">Every `enum` type has an underlying type, which must be one of the eight integral types.</span></span> <span data-ttu-id="74dc7-177">`enum` 类型的值集与基础类型的值集相同。</span><span class="sxs-lookup"><span data-stu-id="74dc7-177">The set of values of an `enum` type is the same as the set of values of the underlying type.</span></span>

<span data-ttu-id="74dc7-178">C# 支持任意类型的一维和多维数组。</span><span class="sxs-lookup"><span data-stu-id="74dc7-178">C# supports single- and multi-dimensional arrays of any type.</span></span> <span data-ttu-id="74dc7-179">与上述类型不同，数组类型无需先声明即可使用。</span><span class="sxs-lookup"><span data-stu-id="74dc7-179">Unlike the types listed above, array types do not have to be declared before they can be used.</span></span> <span data-ttu-id="74dc7-180">相反，数组类型是通过在类型名称后面添加方括号构造而成。</span><span class="sxs-lookup"><span data-stu-id="74dc7-180">Instead, array types are constructed by following a type name with square brackets.</span></span> <span data-ttu-id="74dc7-181">例如，`int[]` 是 `int` 类型的一维数组，`int[,]` 是 `int` 类型的二维数组，`int[][]` 是由 `int` 类型的一维数组构成的一维数组。</span><span class="sxs-lookup"><span data-stu-id="74dc7-181">For example, `int[]` is a single-dimensional array of `int`, `int[,]` is a two-dimensional array of `int`, and `int[][]` is a single-dimensional array of single-dimensional array of `int`.</span></span>

<span data-ttu-id="74dc7-182">可以为 null 的值类型也无需先声明即可使用。</span><span class="sxs-lookup"><span data-stu-id="74dc7-182">Nullable value types also do not have to be declared before they can be used.</span></span> <span data-ttu-id="74dc7-183">对于所有不可以为 null 的值类型 `T`，都有对应的可以为 null 的值类型 `T?`，后者可以包含附加值 `null`。</span><span class="sxs-lookup"><span data-stu-id="74dc7-183">For each non-nullable value type `T` there is a corresponding nullable value type `T?`, which can hold an additional value, `null`.</span></span> <span data-ttu-id="74dc7-184">例如，`int?` 是可以包含任何 32 位整数或值 `null` 的类型。</span><span class="sxs-lookup"><span data-stu-id="74dc7-184">For instance, `int?` is a type that can hold any 32-bit integer or the value `null`.</span></span>

<span data-ttu-id="74dc7-185">C# 采用统一的类型系统，因此任意类型的值都可视为 `object`。</span><span class="sxs-lookup"><span data-stu-id="74dc7-185">C#’s type system is unified such that a value of any type can be treated as an `object`.</span></span> <span data-ttu-id="74dc7-186">每种 C# 类型都直接或间接地派生自 `object` 类类型，而 `object` 是所有类型的最终基类。</span><span class="sxs-lookup"><span data-stu-id="74dc7-186">Every type in C# directly or indirectly derives from the `object` class type, and `object` is the ultimate base class of all types.</span></span> <span data-ttu-id="74dc7-187">只需将值视为类型 `object`，即可将引用类型的值视为对象。</span><span class="sxs-lookup"><span data-stu-id="74dc7-187">Values of reference types are treated as objects simply by viewing the values as type `object`.</span></span> <span data-ttu-id="74dc7-188">通过执行*装箱*和*取消装箱操作*，可以将值类型的值视为对象。</span><span class="sxs-lookup"><span data-stu-id="74dc7-188">Values of value types are treated as objects by performing *boxing* and *unboxing operations*.</span></span> <span data-ttu-id="74dc7-189">在以下示例中，`int` 值被转换成 `object`，然后又恢复成 `int`。</span><span class="sxs-lookup"><span data-stu-id="74dc7-189">In the following example, an `int` value is converted to `object` and back again to `int`.</span></span>

<span data-ttu-id="74dc7-190">[!code-csharp[装箱](../../../samples/snippets/csharp/tour/types-and-variables/Program.cs#L1-L10)]</span><span class="sxs-lookup"><span data-stu-id="74dc7-190">[!code-csharp[Boxing](../../../samples/snippets/csharp/tour/types-and-variables/Program.cs#L1-L10)]</span></span>

<span data-ttu-id="74dc7-191">当值类型的值转换成 `object` 类型时，将分配 `object` 实例（亦称为“箱”）来包含值，然后该值会复制到相应的箱中。</span><span class="sxs-lookup"><span data-stu-id="74dc7-191">When a value of a value type is converted to type `object`, an `object` instance, also called a "box", is allocated to hold the value, and the value is copied into that box.</span></span> <span data-ttu-id="74dc7-192">相反，当 `object` 引用被显式转换成值类型时，将检查引用的 `object` 是否是具有正确值类型的箱；如果检查成功，则会将箱中的值复制出来。</span><span class="sxs-lookup"><span data-stu-id="74dc7-192">Conversely, when an `object` reference is cast to a value type, a check is made that the referenced `object` is a box of the correct value type, and, if the check succeeds, the value in the box is copied out.</span></span>

<span data-ttu-id="74dc7-193">C# 的统一类型系统实际上意味着可以“按需”将值类型转换成对象。</span><span class="sxs-lookup"><span data-stu-id="74dc7-193">C#’s unified type system effectively means that value types can become objects "on demand."</span></span> <span data-ttu-id="74dc7-194">鉴于这种统一性，使用类型 `object` 的常规用途库可以与引用类型和值类型结合使用。</span><span class="sxs-lookup"><span data-stu-id="74dc7-194">Because of the unification, general-purpose libraries that use type `object` can be used with both reference types and value types.</span></span>

<span data-ttu-id="74dc7-195">C# 有多种*变量*，其中包括字段、数组元素、局部变量和参数。</span><span class="sxs-lookup"><span data-stu-id="74dc7-195">There are several kinds of *variables* in C#, including fields, array elements, local variables, and parameters.</span></span> <span data-ttu-id="74dc7-196">变量表示存储位置，每个变量都具有一种类型，用于确定可以在变量中存储哪些值，如下文所述。</span><span class="sxs-lookup"><span data-stu-id="74dc7-196">Variables represent storage locations, and every variable has a type that determines what values can be stored in the variable, as shown below.</span></span>

* <span data-ttu-id="74dc7-197">不可以为 null 的值类型</span><span class="sxs-lookup"><span data-stu-id="74dc7-197">Non-nullable value type</span></span>
    - <span data-ttu-id="74dc7-198">具有精确类型的值</span><span class="sxs-lookup"><span data-stu-id="74dc7-198">A value of that exact type</span></span>
* <span data-ttu-id="74dc7-199">可以为 null 的值类型</span><span class="sxs-lookup"><span data-stu-id="74dc7-199">Nullable value type</span></span>
    - <span data-ttu-id="74dc7-200">`null` 值或具有精确类型的值</span><span class="sxs-lookup"><span data-stu-id="74dc7-200">A `null` value or a value of that exact type</span></span>
* <span data-ttu-id="74dc7-201">object</span><span class="sxs-lookup"><span data-stu-id="74dc7-201">object</span></span>
    - <span data-ttu-id="74dc7-202">`null` 引用、对任意引用类型的对象的引用，或对任意值类型的装箱值的引用</span><span class="sxs-lookup"><span data-stu-id="74dc7-202">A `null` reference, a reference to an object of any reference type, or a reference to a boxed value of any value type</span></span>
* <span data-ttu-id="74dc7-203">类类型</span><span class="sxs-lookup"><span data-stu-id="74dc7-203">Class type</span></span>
    - <span data-ttu-id="74dc7-204">`null` 引用、对类类型实例的引用，或对派生自类类型的类实例的引用</span><span class="sxs-lookup"><span data-stu-id="74dc7-204">A `null` reference, a reference to an instance of that class type, or a reference to an instance of a class derived from that class type</span></span>
* <span data-ttu-id="74dc7-205">接口类型</span><span class="sxs-lookup"><span data-stu-id="74dc7-205">Interface type</span></span>
    - <span data-ttu-id="74dc7-206">`null` 引用、对实现接口类型的类类型实例的引用，或对实现接口类型的值类型的装箱值的引用</span><span class="sxs-lookup"><span data-stu-id="74dc7-206">A `null` reference, a reference to an instance of a class type that implements that interface type, or a reference to a boxed value of a value type that implements that interface type</span></span>
* <span data-ttu-id="74dc7-207">数组类型</span><span class="sxs-lookup"><span data-stu-id="74dc7-207">Array type</span></span>
    - <span data-ttu-id="74dc7-208">`null` 引用、对数组类型实例的引用，或对兼容的数组类型实例的引用</span><span class="sxs-lookup"><span data-stu-id="74dc7-208">A `null` reference, a reference to an instance of that array type, or a reference to an instance of a compatible array type</span></span>
* <span data-ttu-id="74dc7-209">委托类型</span><span class="sxs-lookup"><span data-stu-id="74dc7-209">Delegate type</span></span>
    - <span data-ttu-id="74dc7-210">`null` 引用或对兼容的委托类型实例的引用</span><span class="sxs-lookup"><span data-stu-id="74dc7-210">A `null` reference or a reference to an instance of a compatible delegate type</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="74dc7-211">[上一页](program-structure.md)
[下一页](expressions.md)</span><span class="sxs-lookup"><span data-stu-id="74dc7-211">[Previous](program-structure.md)
[Next](expressions.md)</span></span>

