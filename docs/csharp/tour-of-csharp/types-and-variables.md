---
title: C# 类型和变量 - C# 语言介绍
description: 了解如何在 C# 中定义类型和声明变量
ms.date: 08/10/2016
ms.assetid: f8a8051e-0049-43f1-b594-9c84cc7b1224
ms.openlocfilehash: a3f31eca296265c1e7f0c14a9540e267a2165ec1
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/28/2019
ms.locfileid: "67423444"
---
# <a name="types-and-variables"></a><span data-ttu-id="26e16-103">类型和变量</span><span class="sxs-lookup"><span data-stu-id="26e16-103">Types and variables</span></span>

<span data-ttu-id="26e16-104">C# 有两种类型：*值类型*和*引用类型*。</span><span class="sxs-lookup"><span data-stu-id="26e16-104">There are two kinds of types in C#: *value types* and *reference types*.</span></span> <span data-ttu-id="26e16-105">值类型的变量直接包含数据，而引用类型的变量则存储对数据（称为“对象”）的引用。</span><span class="sxs-lookup"><span data-stu-id="26e16-105">Variables of value types directly contain their data whereas variables of reference types store references to their data, the latter being known as objects.</span></span> <span data-ttu-id="26e16-106">对于引用类型，两个变量可以引用同一对象；因此，对一个变量执行的运算可能会影响另一个变量引用的对象。</span><span class="sxs-lookup"><span data-stu-id="26e16-106">With reference types, it is possible for two variables to reference the same object and thus possible for operations on one variable to affect the object referenced by the other variable.</span></span> <span data-ttu-id="26e16-107">借助值类型，每个变量都有自己的数据副本；因此，对一个变量执行的运算不会影响另一个变量（`ref` 和 `out` 参数变量除外）。</span><span class="sxs-lookup"><span data-stu-id="26e16-107">With value types, the variables each have their own copy of the data, and it is not possible for operations on one to affect the other (except in the case of `ref` and `out` parameter variables).</span></span>

<span data-ttu-id="26e16-108">C# 值类型又细分为*简单类型*、*枚举类型*、*结构类型*和*可以为 null 的值类型*。</span><span class="sxs-lookup"><span data-stu-id="26e16-108">C#’s value types are further divided into *simple types*, *enum types*, *struct types*, and *nullable value types*.</span></span> <span data-ttu-id="26e16-109">C# 引用类型又细分为*类类型*、*接口类型*、*数组类型*和*委托类型*。</span><span class="sxs-lookup"><span data-stu-id="26e16-109">C#’s reference types are further divided into *class types*, *interface types*, *array types*, and *delegate types*.</span></span>

<span data-ttu-id="26e16-110">下面概述了 C# 的类型系统。</span><span class="sxs-lookup"><span data-stu-id="26e16-110">The following provides an overview of C#’s type system.</span></span>

* <span data-ttu-id="26e16-111">[值类型][ValueTypes]</span><span class="sxs-lookup"><span data-stu-id="26e16-111">[Value types][ValueTypes]</span></span>
  - <span data-ttu-id="26e16-112">[简单类型][SimpleTypes]</span><span class="sxs-lookup"><span data-stu-id="26e16-112">[Simple types][SimpleTypes]</span></span>
    * <span data-ttu-id="26e16-113">有符号的整型：`sbyte`、`short`、`int`、`long`</span><span class="sxs-lookup"><span data-stu-id="26e16-113">Signed integral: `sbyte`, `short`, `int`, `long`</span></span>
    * <span data-ttu-id="26e16-114">无符号的整型：`byte`、`ushort`、`uint`、`ulong`</span><span class="sxs-lookup"><span data-stu-id="26e16-114">Unsigned integral: `byte`, `ushort`, `uint`, `ulong`</span></span>
    * <span data-ttu-id="26e16-115">Unicode 字符：`char`</span><span class="sxs-lookup"><span data-stu-id="26e16-115">Unicode characters: `char`</span></span>
    * <span data-ttu-id="26e16-116">IEEE 二进制浮点：`float`、`double`</span><span class="sxs-lookup"><span data-stu-id="26e16-116">IEEE binary floating-point: `float`, `double`</span></span>
    * <span data-ttu-id="26e16-117">高精度十进制浮点数：`decimal`</span><span class="sxs-lookup"><span data-stu-id="26e16-117">High-precision decimal floating-point: `decimal`</span></span>
    * <span data-ttu-id="26e16-118">布尔：`bool`</span><span class="sxs-lookup"><span data-stu-id="26e16-118">Boolean: `bool`</span></span>
  - <span data-ttu-id="26e16-119">[枚举类型][EnumTypes]</span><span class="sxs-lookup"><span data-stu-id="26e16-119">[Enum types][EnumTypes]</span></span>
    * <span data-ttu-id="26e16-120">格式为 `enum E {...}` 的用户定义类型</span><span class="sxs-lookup"><span data-stu-id="26e16-120">User-defined types of the form `enum E {...}`</span></span>
  - <span data-ttu-id="26e16-121">[结构类型][StructTypes]</span><span class="sxs-lookup"><span data-stu-id="26e16-121">[Struct types][StructTypes]</span></span>
    * <span data-ttu-id="26e16-122">格式为 `struct S {...}` 的用户定义类型</span><span class="sxs-lookup"><span data-stu-id="26e16-122">User-defined types of the form `struct S {...}`</span></span>
  - <span data-ttu-id="26e16-123">[可以为 null 的值类型][NullableTypes]</span><span class="sxs-lookup"><span data-stu-id="26e16-123">[Nullable value types][NullableTypes]</span></span>
    * <span data-ttu-id="26e16-124">值为 `null` 的其他所有值类型的扩展</span><span class="sxs-lookup"><span data-stu-id="26e16-124">Extensions of all other value types with a `null` value</span></span>
* <span data-ttu-id="26e16-125">[引用类型][ReferenceTypes]</span><span class="sxs-lookup"><span data-stu-id="26e16-125">[Reference types][ReferenceTypes]</span></span>
  - <span data-ttu-id="26e16-126">[类类型][ClassTypes]</span><span class="sxs-lookup"><span data-stu-id="26e16-126">[Class types][ClassTypes]</span></span>
    * <span data-ttu-id="26e16-127">其他所有类型的最终基类：`object`</span><span class="sxs-lookup"><span data-stu-id="26e16-127">Ultimate base class of all other types: `object`</span></span>
    * <span data-ttu-id="26e16-128">Unicode 字符串：`string`</span><span class="sxs-lookup"><span data-stu-id="26e16-128">Unicode strings: `string`</span></span>
    * <span data-ttu-id="26e16-129">格式为 `class C {...}` 的用户定义类型</span><span class="sxs-lookup"><span data-stu-id="26e16-129">User-defined types of the form `class C {...}`</span></span>
  - <span data-ttu-id="26e16-130">[接口类型][InterfaceTypes]</span><span class="sxs-lookup"><span data-stu-id="26e16-130">[Interface types][InterfaceTypes]</span></span>
    * <span data-ttu-id="26e16-131">格式为 `interface I {...}` 的用户定义类型</span><span class="sxs-lookup"><span data-stu-id="26e16-131">User-defined types of the form `interface I {...}`</span></span>
  - <span data-ttu-id="26e16-132">[数组类型][ArrayTypes]</span><span class="sxs-lookup"><span data-stu-id="26e16-132">[Array types][ArrayTypes]</span></span>
    * <span data-ttu-id="26e16-133">一维和多维，例如 `int[]` 和 `int[,]`</span><span class="sxs-lookup"><span data-stu-id="26e16-133">Single- and multi-dimensional, for example, `int[]` and `int[,]`</span></span>
  - <span data-ttu-id="26e16-134">[委托类型][DelegateTypes]</span><span class="sxs-lookup"><span data-stu-id="26e16-134">[Delegate types][DelegateTypes]</span></span>
    * <span data-ttu-id="26e16-135">格式为 `delegate int D(...)` 的用户定义类型</span><span class="sxs-lookup"><span data-stu-id="26e16-135">User-defined types of the form `delegate int D(...)`</span></span>

[ValueTypes]: ../language-reference/keywords/value-types-table.md
[SimpleTypes]: ../language-reference/keywords/value-types.md#simple-types
[EnumTypes]: ../language-reference/keywords/enum.md
[StructTypes]: ../language-reference/keywords/struct.md
[NullableTypes]: ../programming-guide/nullable-types/index.md
[ReferenceTypes]: ../language-reference/keywords/reference-types.md
[ClassTypes]: ../language-reference/keywords/class.md
[InterfaceTypes]: ../language-reference/keywords/interface.md
[DelegateTypes]: ../language-reference/keywords/delegate.md
[ArrayTypes]: ../programming-guide/arrays/index.md

<span data-ttu-id="26e16-136">有关数值类型的详细信息，请参阅[整型类型](../language-reference/builtin-types/integral-numeric-types.md)和[浮点类型表](../language-reference/keywords/floating-point-types-table.md)。</span><span class="sxs-lookup"><span data-stu-id="26e16-136">For more information about numeric types, see [Integral types](../language-reference/builtin-types/integral-numeric-types.md) and [Floating-point types table](../language-reference/keywords/floating-point-types-table.md).</span></span>

<span data-ttu-id="26e16-137">C# 的 `bool` 类型用于表示布尔值（`true` 或 `false`）。</span><span class="sxs-lookup"><span data-stu-id="26e16-137">C#’s `bool` type is used to represent Boolean values—values that are either `true` or `false`.</span></span>

<span data-ttu-id="26e16-138">C# 使用 Unicode 编码处理字符和字符串。</span><span class="sxs-lookup"><span data-stu-id="26e16-138">Character and string processing in C# uses Unicode encoding.</span></span> <span data-ttu-id="26e16-139">`char` 类型表示 UTF-16 代码单元，`string` 类型表示一系列 UTF-16 代码单元。</span><span class="sxs-lookup"><span data-stu-id="26e16-139">The `char` type represents a UTF-16 code unit, and the `string` type represents a sequence of UTF-16 code units.</span></span>

<span data-ttu-id="26e16-140">C# 程序使用*类型声明*创建新类型。</span><span class="sxs-lookup"><span data-stu-id="26e16-140">C# programs use *type declarations* to create new types.</span></span> <span data-ttu-id="26e16-141">类型声明指定新类型的名称和成员。</span><span class="sxs-lookup"><span data-stu-id="26e16-141">A type declaration specifies the name and the members of the new type.</span></span> <span data-ttu-id="26e16-142">用户可定义以下五种 C# 类型：类类型、结构类型、接口类型、枚举类型和委托类型。</span><span class="sxs-lookup"><span data-stu-id="26e16-142">Five of C#’s categories of types are user-definable: class types, struct types, interface types, enum types, and delegate types.</span></span>

<span data-ttu-id="26e16-143">`class` 类型定义包含数据成员（字段）和函数成员（方法、属性及其他）的数据结构。</span><span class="sxs-lookup"><span data-stu-id="26e16-143">A `class` type defines a data structure that contains data members (fields) and function members (methods, properties, and others).</span></span> <span data-ttu-id="26e16-144">类类型支持单一继承和多形性，即派生类可以扩展和专门针对基类的机制。</span><span class="sxs-lookup"><span data-stu-id="26e16-144">Class types support single inheritance and polymorphism, mechanisms whereby derived classes can extend and specialize base classes.</span></span>

<span data-ttu-id="26e16-145">`struct` 类型定义包含数据成员和函数成员的结构，这一点与类类型相似。</span><span class="sxs-lookup"><span data-stu-id="26e16-145">A `struct` type is similar to a class type in that it represents a structure with data members and function members.</span></span> <span data-ttu-id="26e16-146">不过，与类不同的是，结构是值类型，通常不需要进行堆分配。</span><span class="sxs-lookup"><span data-stu-id="26e16-146">However, unlike classes, structs are value types and do not typically require heap allocation.</span></span> <span data-ttu-id="26e16-147">结构类型不支持用户指定的继承，并且所有结构类型均隐式继承自类型 `object`。</span><span class="sxs-lookup"><span data-stu-id="26e16-147">Struct types do not support user-specified inheritance, and all struct types implicitly inherit from type `object`.</span></span>

<span data-ttu-id="26e16-148">`interface` 类型将协定定义为一组已命名的公共函数成员。</span><span class="sxs-lookup"><span data-stu-id="26e16-148">An `interface` type defines a contract as a named set of public function members.</span></span> <span data-ttu-id="26e16-149">实现 `interface` 的 `class` 或 `struct` 必须提供接口函数成员的实现代码。</span><span class="sxs-lookup"><span data-stu-id="26e16-149">A `class` or `struct` that implements an `interface` must provide implementations of the interface’s function members.</span></span> <span data-ttu-id="26e16-150">`interface` 可以继承自多个基接口，`class` 和 `struct` 可以实现多个接口。</span><span class="sxs-lookup"><span data-stu-id="26e16-150">An `interface` may inherit from multiple base interfaces, and a `class` or `struct` may implement multiple interfaces.</span></span>

<span data-ttu-id="26e16-151">`delegate` 类型表示引用包含特定参数列表和返回类型的方法。</span><span class="sxs-lookup"><span data-stu-id="26e16-151">A `delegate` type represents references to methods with a particular parameter list and return type.</span></span> <span data-ttu-id="26e16-152">通过委托，可以将方法视为可分配给变量并可作为参数传递的实体。</span><span class="sxs-lookup"><span data-stu-id="26e16-152">Delegates make it possible to treat methods as entities that can be assigned to variables and passed as parameters.</span></span> <span data-ttu-id="26e16-153">委托类同于函数式语言提供的函数类型。</span><span class="sxs-lookup"><span data-stu-id="26e16-153">Delegates are analogous to function types provided by functional languages.</span></span> <span data-ttu-id="26e16-154">委托也类似于其他一些语言中的函数指针概念，但与函数指针不同的是，委托不仅面向对象，还类型安全。</span><span class="sxs-lookup"><span data-stu-id="26e16-154">They are also similar to the concept of function pointers found in some other languages, but unlike function pointers, delegates are object-oriented and type-safe.</span></span>

<span data-ttu-id="26e16-155">`class`、`struct`、`interface` 和 `delegate` 类型全部都支持泛型，因此可以使用其他类型对它们进行参数化。</span><span class="sxs-lookup"><span data-stu-id="26e16-155">The `class`, `struct`, `interface` and `delegate` types all support generics, whereby they can be parameterized with other types.</span></span>

<span data-ttu-id="26e16-156">`enum` 类型是一种包含已命名常量的独特类型。</span><span class="sxs-lookup"><span data-stu-id="26e16-156">An `enum` type is a distinct type with named constants.</span></span> <span data-ttu-id="26e16-157">每个 `enum` 类型都有一个基础类型（必须是八种整型类型之一）。</span><span class="sxs-lookup"><span data-stu-id="26e16-157">Every `enum` type has an underlying type, which must be one of the eight integral types.</span></span> <span data-ttu-id="26e16-158">`enum` 类型的值集与基础类型的值集相同。</span><span class="sxs-lookup"><span data-stu-id="26e16-158">The set of values of an `enum` type is the same as the set of values of the underlying type.</span></span>

<span data-ttu-id="26e16-159">C# 支持任意类型的一维和多维数组。</span><span class="sxs-lookup"><span data-stu-id="26e16-159">C# supports single- and multi-dimensional arrays of any type.</span></span> <span data-ttu-id="26e16-160">与上述类型不同，数组类型无需先声明即可使用。</span><span class="sxs-lookup"><span data-stu-id="26e16-160">Unlike the types listed above, array types do not have to be declared before they can be used.</span></span> <span data-ttu-id="26e16-161">相反，数组类型是通过在类型名称后面添加方括号构造而成。</span><span class="sxs-lookup"><span data-stu-id="26e16-161">Instead, array types are constructed by following a type name with square brackets.</span></span> <span data-ttu-id="26e16-162">例如，`int[]` 是 `int` 类型的一维数组，`int[,]` 是 `int` 类型的二维数组，`int[][]` 是由 `int` 类型的一维数组构成的一维数组。</span><span class="sxs-lookup"><span data-stu-id="26e16-162">For example, `int[]` is a single-dimensional array of `int`, `int[,]` is a two-dimensional array of `int`, and `int[][]` is a single-dimensional array of single-dimensional array of `int`.</span></span>

<span data-ttu-id="26e16-163">可以为 null 的值类型也无需先声明即可使用。</span><span class="sxs-lookup"><span data-stu-id="26e16-163">Nullable value types also do not have to be declared before they can be used.</span></span> <span data-ttu-id="26e16-164">对于所有不可以为 null 的值类型 `T`，都有对应的可以为 null 的值类型 `T?`，后者可以包含附加值 `null`。</span><span class="sxs-lookup"><span data-stu-id="26e16-164">For each non-nullable value type `T` there is a corresponding nullable value type `T?`, which can hold an additional value, `null`.</span></span> <span data-ttu-id="26e16-165">例如，`int?` 是可以包含任何 32 位整数或值 `null` 的类型。</span><span class="sxs-lookup"><span data-stu-id="26e16-165">For instance, `int?` is a type that can hold any 32-bit integer or the value `null`.</span></span>

<span data-ttu-id="26e16-166">C# 采用统一的类型系统，因此任意类型的值都可视为 `object`。</span><span class="sxs-lookup"><span data-stu-id="26e16-166">C#’s type system is unified such that a value of any type can be treated as an `object`.</span></span> <span data-ttu-id="26e16-167">每种 C# 类型都直接或间接地派生自 `object` 类类型，而 `object` 是所有类型的最终基类。</span><span class="sxs-lookup"><span data-stu-id="26e16-167">Every type in C# directly or indirectly derives from the `object` class type, and `object` is the ultimate base class of all types.</span></span> <span data-ttu-id="26e16-168">只需将值视为类型 `object`，即可将引用类型的值视为对象。</span><span class="sxs-lookup"><span data-stu-id="26e16-168">Values of reference types are treated as objects simply by viewing the values as type `object`.</span></span> <span data-ttu-id="26e16-169">通过执行*装箱*和*取消装箱操作*，可以将值类型的值视为对象。</span><span class="sxs-lookup"><span data-stu-id="26e16-169">Values of value types are treated as objects by performing *boxing* and *unboxing operations*.</span></span> <span data-ttu-id="26e16-170">在以下示例中，`int` 值被转换成 `object`，然后又恢复成 `int`。</span><span class="sxs-lookup"><span data-stu-id="26e16-170">In the following example, an `int` value is converted to `object` and back again to `int`.</span></span>

[!code-csharp[Boxing](../../../samples/snippets/csharp/tour/types-and-variables/Program.cs#L1-L10)]

<span data-ttu-id="26e16-171">当值类型的值转换成 `object` 类型时，将分配 `object` 实例（亦称为“箱”）来包含值，然后该值会复制到相应的箱中。</span><span class="sxs-lookup"><span data-stu-id="26e16-171">When a value of a value type is converted to type `object`, an `object` instance, also called a "box", is allocated to hold the value, and the value is copied into that box.</span></span> <span data-ttu-id="26e16-172">相反，当 `object` 引用被显式转换成值类型时，将检查引用的 `object` 是否是具有正确值类型的箱；如果检查成功，则会将箱中的值复制出来。</span><span class="sxs-lookup"><span data-stu-id="26e16-172">Conversely, when an `object` reference is cast to a value type, a check is made that the referenced `object` is a box of the correct value type, and, if the check succeeds, the value in the box is copied out.</span></span>

<span data-ttu-id="26e16-173">C# 的统一类型系统实际上意味着可以“按需”将值类型转换成对象。</span><span class="sxs-lookup"><span data-stu-id="26e16-173">C#’s unified type system effectively means that value types can become objects "on demand."</span></span> <span data-ttu-id="26e16-174">鉴于这种统一性，使用类型 `object` 的常规用途库可以与引用类型和值类型结合使用。</span><span class="sxs-lookup"><span data-stu-id="26e16-174">Because of the unification, general-purpose libraries that use type `object` can be used with both reference types and value types.</span></span>

<span data-ttu-id="26e16-175">C# 有多种*变量*，其中包括字段、数组元素、局部变量和参数。</span><span class="sxs-lookup"><span data-stu-id="26e16-175">There are several kinds of *variables* in C#, including fields, array elements, local variables, and parameters.</span></span> <span data-ttu-id="26e16-176">变量表示存储位置，每个变量都具有一种类型，用于确定可以在变量中存储哪些值，如下文所述。</span><span class="sxs-lookup"><span data-stu-id="26e16-176">Variables represent storage locations, and every variable has a type that determines what values can be stored in the variable, as shown below.</span></span>

* <span data-ttu-id="26e16-177">不可以为 null 的值类型</span><span class="sxs-lookup"><span data-stu-id="26e16-177">Non-nullable value type</span></span>
  - <span data-ttu-id="26e16-178">具有精确类型的值</span><span class="sxs-lookup"><span data-stu-id="26e16-178">A value of that exact type</span></span>
* <span data-ttu-id="26e16-179">可以为 null 的值类型</span><span class="sxs-lookup"><span data-stu-id="26e16-179">Nullable value type</span></span>
  - <span data-ttu-id="26e16-180">`null` 值或具有精确类型的值</span><span class="sxs-lookup"><span data-stu-id="26e16-180">A `null` value or a value of that exact type</span></span>
* <span data-ttu-id="26e16-181">object</span><span class="sxs-lookup"><span data-stu-id="26e16-181">object</span></span>
  - <span data-ttu-id="26e16-182">`null` 引用、对任意引用类型的对象的引用，或对任意值类型的装箱值的引用</span><span class="sxs-lookup"><span data-stu-id="26e16-182">A `null` reference, a reference to an object of any reference type, or a reference to a boxed value of any value type</span></span>
* <span data-ttu-id="26e16-183">类类型</span><span class="sxs-lookup"><span data-stu-id="26e16-183">Class type</span></span>
  - <span data-ttu-id="26e16-184">`null` 引用、对类类型实例的引用，或对派生自类类型的类实例的引用</span><span class="sxs-lookup"><span data-stu-id="26e16-184">A `null` reference, a reference to an instance of that class type, or a reference to an instance of a class derived from that class type</span></span>
* <span data-ttu-id="26e16-185">接口类型</span><span class="sxs-lookup"><span data-stu-id="26e16-185">Interface type</span></span>
  - <span data-ttu-id="26e16-186">`null` 引用、对实现接口类型的类类型实例的引用，或对实现接口类型的值类型的装箱值的引用</span><span class="sxs-lookup"><span data-stu-id="26e16-186">A `null` reference, a reference to an instance of a class type that implements that interface type, or a reference to a boxed value of a value type that implements that interface type</span></span>
* <span data-ttu-id="26e16-187">数组类型</span><span class="sxs-lookup"><span data-stu-id="26e16-187">Array type</span></span>
  - <span data-ttu-id="26e16-188">`null` 引用、对数组类型实例的引用，或对兼容的数组类型实例的引用</span><span class="sxs-lookup"><span data-stu-id="26e16-188">A `null` reference, a reference to an instance of that array type, or a reference to an instance of a compatible array type</span></span>
* <span data-ttu-id="26e16-189">委托类型</span><span class="sxs-lookup"><span data-stu-id="26e16-189">Delegate type</span></span>
  - <span data-ttu-id="26e16-190">`null` 引用或对兼容的委托类型实例的引用</span><span class="sxs-lookup"><span data-stu-id="26e16-190">A `null` reference or a reference to an instance of a compatible delegate type</span></span>

> [!div class="step-by-step"]
> <span data-ttu-id="26e16-191">[上一页](program-structure.md)
> [下一页](expressions.md)</span><span class="sxs-lookup"><span data-stu-id="26e16-191">[Previous](program-structure.md)
[Next](expressions.md)</span></span>
