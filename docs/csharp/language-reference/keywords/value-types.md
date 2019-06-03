---
title: 值类型 - C# 参考
ms.custom: seodec18
ms.date: 11/26/2018
f1_keywords:
- cs.valuetypes
helpviewer_keywords:
- value types [C#]
- types [C#], value types
- C# language, value types
ms.assetid: 471eb994-2958-49d5-a6be-19b4313f80a3
ms.openlocfilehash: af3eab1c2453f37aa5bd881dc9804d7504c89298
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/31/2019
ms.locfileid: "66422119"
---
# <a name="value-types-c-reference"></a><span data-ttu-id="48cd7-102">值类型（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="48cd7-102">Value types (C# Reference)</span></span>

<span data-ttu-id="48cd7-103">有两种值类型：</span><span class="sxs-lookup"><span data-stu-id="48cd7-103">There are two kinds of value types:</span></span>

- [<span data-ttu-id="48cd7-104">结构</span><span class="sxs-lookup"><span data-stu-id="48cd7-104">Structs</span></span>](struct.md)

- [<span data-ttu-id="48cd7-105">枚举</span><span class="sxs-lookup"><span data-stu-id="48cd7-105">Enumerations</span></span>](enum.md)

## <a name="main-features-of-value-types"></a><span data-ttu-id="48cd7-106">值类型的主要功能</span><span class="sxs-lookup"><span data-stu-id="48cd7-106">Main features of value types</span></span>

<span data-ttu-id="48cd7-107">值类型的变量包含类型的值。</span><span class="sxs-lookup"><span data-stu-id="48cd7-107">A variable of a value type contains a value of the type.</span></span> <span data-ttu-id="48cd7-108">例如，`int` 类型的变量可以包含值 `42`。</span><span class="sxs-lookup"><span data-stu-id="48cd7-108">For example, a variable of the `int` type might contain the value `42`.</span></span> <span data-ttu-id="48cd7-109">它不同于引用类型的变量，后者（也称为对象）包含对类型实例的引用。</span><span class="sxs-lookup"><span data-stu-id="48cd7-109">This differs from a variable of a reference type, which contains a reference to an instance of the type, also known as an object.</span></span> <span data-ttu-id="48cd7-110">将新的值分配到值类型的变量时，会复制该值。</span><span class="sxs-lookup"><span data-stu-id="48cd7-110">When you assign a new value to a variable of a value type, that value is copied.</span></span> <span data-ttu-id="48cd7-111">将新的值分配到引用类型的变量时，会复制引用，而不复制对象本身。</span><span class="sxs-lookup"><span data-stu-id="48cd7-111">When you assign a new value to a variable of a reference type, the reference is copied, not the object itself.</span></span>

<span data-ttu-id="48cd7-112">所有值类型都隐式派生自 <xref:System.ValueType?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="48cd7-112">All value types are derived implicitly from the <xref:System.ValueType?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="48cd7-113">与引用类型不同，不能从值类型派生新类型。</span><span class="sxs-lookup"><span data-stu-id="48cd7-113">Unlike with reference types, you cannot derive a new type from a value type.</span></span> <span data-ttu-id="48cd7-114">但是，与引用类型一样，结构可以实现接口。</span><span class="sxs-lookup"><span data-stu-id="48cd7-114">However, like reference types, structs can implement interfaces.</span></span>

<span data-ttu-id="48cd7-115">值类型变量不能默认为 `null`。</span><span class="sxs-lookup"><span data-stu-id="48cd7-115">Value type variables cannot be `null` by default.</span></span> <span data-ttu-id="48cd7-116">但相应的[可以为空的类型](../../../csharp/programming-guide/nullable-types/index.md)的变量可以为 `null`。</span><span class="sxs-lookup"><span data-stu-id="48cd7-116">However, variables of the corresponding [nullable types](../../../csharp/programming-guide/nullable-types/index.md) can be `null`.</span></span>

<span data-ttu-id="48cd7-117">每个值类型都有一个隐式无参数构造函数，用于初始化该类型的默认值。</span><span class="sxs-lookup"><span data-stu-id="48cd7-117">Each value type has an implicit parameterless constructor that initializes the default value of that type.</span></span> <span data-ttu-id="48cd7-118">有关值类型的默认值的信息，请参阅[默认值表](default-values-table.md)。</span><span class="sxs-lookup"><span data-stu-id="48cd7-118">For information about default values of value types, see [Default values table](default-values-table.md).</span></span>

## <a name="simple-types"></a><span data-ttu-id="48cd7-119">简单类型</span><span class="sxs-lookup"><span data-stu-id="48cd7-119">Simple types</span></span>

<span data-ttu-id="48cd7-120">简单类型是 C# 提供的一组预定义的结构类型，其中包括以下类型： </span><span class="sxs-lookup"><span data-stu-id="48cd7-120">The *simple types* are a set of predefined struct types provided by C# and comprise the following types:</span></span>

- <span data-ttu-id="48cd7-121">[整型类型](integral-types-table.md)：整数类型和 [字符型](char.md)类型</span><span class="sxs-lookup"><span data-stu-id="48cd7-121">[Integral types](integral-types-table.md): integer numeric types and the [char](char.md) type</span></span>
- [<span data-ttu-id="48cd7-122">浮点类型</span><span class="sxs-lookup"><span data-stu-id="48cd7-122">Floating-point types</span></span>](floating-point-types-table.md)
- [<span data-ttu-id="48cd7-123">bool</span><span class="sxs-lookup"><span data-stu-id="48cd7-123">bool</span></span>](bool.md)

<span data-ttu-id="48cd7-124">简单类型通过关键字标识，但这些关键字只是 <xref:System> 命名空间中的预定义结构类型的别名。</span><span class="sxs-lookup"><span data-stu-id="48cd7-124">The simple types are identified through keywords, but these keywords are simply aliases for predefined struct types in the <xref:System> namespace.</span></span> <span data-ttu-id="48cd7-125">例如， [int](int.md) 是 <xref:System.Int32?displayProperty=nameWithType> 的别名。</span><span class="sxs-lookup"><span data-stu-id="48cd7-125">For example, [int](int.md) is an alias of <xref:System.Int32?displayProperty=nameWithType>.</span></span> <span data-ttu-id="48cd7-126">有关别名的完整列表，请参阅[内置类型表](built-in-types-table.md)。</span><span class="sxs-lookup"><span data-stu-id="48cd7-126">For a complete list of aliases, see [Built-in types table](built-in-types-table.md).</span></span>

<span data-ttu-id="48cd7-127">简单类型不同于其他结构类型，简单类型允许某些附加操作：</span><span class="sxs-lookup"><span data-stu-id="48cd7-127">The simple types differ from other struct types in that they permit certain additional operations:</span></span>

- <span data-ttu-id="48cd7-128">可以使用文本初始化简单类型。</span><span class="sxs-lookup"><span data-stu-id="48cd7-128">Simple types can be initialized by using literals.</span></span> <span data-ttu-id="48cd7-129">例如，`'A'` 是类型 `char` 的文本，`2001` 是类型 `int` 的文本。</span><span class="sxs-lookup"><span data-stu-id="48cd7-129">For example, `'A'` is a literal of the type `char` and `2001` is a literal of the type `int`.</span></span>

- <span data-ttu-id="48cd7-130">可以使用 [const](const.md) 关键字声明简单类型的常数。</span><span class="sxs-lookup"><span data-stu-id="48cd7-130">You can declare constants of the simple types with the [const](const.md) keyword.</span></span> <span data-ttu-id="48cd7-131">无法包含其他结构类型的常数。</span><span class="sxs-lookup"><span data-stu-id="48cd7-131">It's not possible to have constants of other struct types.</span></span>

- <span data-ttu-id="48cd7-132">其操作数都是简单类型常数的常量表达式在编译时进行评估。</span><span class="sxs-lookup"><span data-stu-id="48cd7-132">Constant expressions, whose operands are all simple type constants, are evaluated at compile time.</span></span>

<span data-ttu-id="48cd7-133">有关详细信息，请参阅 [C# 语言规范](../language-specification/index.md)中的[简单类型](~/_csharplang/spec/types.md#simple-types)部分。</span><span class="sxs-lookup"><span data-stu-id="48cd7-133">For more information, see the [Simple types](~/_csharplang/spec/types.md#simple-types) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="initializing-value-types"></a><span data-ttu-id="48cd7-134">初始化值类型</span><span class="sxs-lookup"><span data-stu-id="48cd7-134">Initializing value types</span></span>

<span data-ttu-id="48cd7-135">在使用 C# 中的本地变量之前，必须对其进行初始化。</span><span class="sxs-lookup"><span data-stu-id="48cd7-135">Local variables in C# must be initialized before they are used.</span></span> <span data-ttu-id="48cd7-136">例如，可以声明未初始化的本地变量，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="48cd7-136">For example, you might declare a local variable without initialization as in the following example:</span></span>

```csharp
int myInt;
```

<span data-ttu-id="48cd7-137">在未初始化之前，无法使用。</span><span class="sxs-lookup"><span data-stu-id="48cd7-137">You cannot use it before you initialize it.</span></span> <span data-ttu-id="48cd7-138">可以使用以下语句将其初始化：</span><span class="sxs-lookup"><span data-stu-id="48cd7-138">You can initialize it using the following statement:</span></span>

```csharp
myInt = new int();  // Invoke parameterless constructor for int type.
```

<span data-ttu-id="48cd7-139">此语句等效于以下语句：</span><span class="sxs-lookup"><span data-stu-id="48cd7-139">This statement is equivalent to the following statement:</span></span>

```csharp
myInt = 0;         // Assign an initial value, 0 in this example.
```

<span data-ttu-id="48cd7-140">当然，可以在同一语句中进行声明和初始化，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="48cd7-140">You can, of course, have the declaration and the initialization in the same statement as in the following examples:</span></span>

```csharp
int myInt = new int();
```

<span data-ttu-id="48cd7-141">- 或 -</span><span class="sxs-lookup"><span data-stu-id="48cd7-141">–or–</span></span>

```csharp
int myInt = 0;
```

<span data-ttu-id="48cd7-142">使用 [new](new.md) 运算符调用特定类型的无参数构造函数，并将默认值赋给变量。</span><span class="sxs-lookup"><span data-stu-id="48cd7-142">Using the [new](new.md) operator calls the parameterless constructor of the specific type and assigns the default value to the variable.</span></span> <span data-ttu-id="48cd7-143">在上述示例中，无参数构造函数将值 `0` 赋给 `myInt`。</span><span class="sxs-lookup"><span data-stu-id="48cd7-143">In the preceding example, the parameterless constructor assigned the value `0` to `myInt`.</span></span> <span data-ttu-id="48cd7-144">有关通过调用默认构造函数所赋予的值的详细信息，请参阅[默认值表](default-values-table.md)。</span><span class="sxs-lookup"><span data-stu-id="48cd7-144">For more information about values assigned by calling default constructors, see [Default values table](default-values-table.md).</span></span>

<span data-ttu-id="48cd7-145">对于用户定义类型，使用 [new](new.md) 调用无参数构造函数。</span><span class="sxs-lookup"><span data-stu-id="48cd7-145">With user-defined types, use [new](new.md) to invoke the parameterless constructor.</span></span> <span data-ttu-id="48cd7-146">例如，以下语句调用 `Point` 结构的无参数构造函数：</span><span class="sxs-lookup"><span data-stu-id="48cd7-146">For example, the following statement invokes the parameterless constructor of the `Point` struct:</span></span>

```csharp
Point p = new Point(); // Invoke parameterless constructor for the struct.
```

<span data-ttu-id="48cd7-147">进行此调用后，该结构被视为已明确赋值；即，它的所有成员都被初始化为其默认值。</span><span class="sxs-lookup"><span data-stu-id="48cd7-147">After this call, the struct is considered to be definitely assigned; that is, all its members are initialized to their default values.</span></span>

<span data-ttu-id="48cd7-148">有关 `new` 运算符的详细信息，请参阅 [new](new.md)。</span><span class="sxs-lookup"><span data-stu-id="48cd7-148">For more information about the `new` operator, see [new](new.md).</span></span>

<span data-ttu-id="48cd7-149">有关设置数值类型的输出格式的信息，请参阅[设置数值结果表的格式](formatting-numeric-results-table.md)。</span><span class="sxs-lookup"><span data-stu-id="48cd7-149">For information about formatting the output of numeric types, see [Formatting numeric results table](formatting-numeric-results-table.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="48cd7-150">请参阅</span><span class="sxs-lookup"><span data-stu-id="48cd7-150">See also</span></span>

- [<span data-ttu-id="48cd7-151">C# 参考</span><span class="sxs-lookup"><span data-stu-id="48cd7-151">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="48cd7-152">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="48cd7-152">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="48cd7-153">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="48cd7-153">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="48cd7-154">类型</span><span class="sxs-lookup"><span data-stu-id="48cd7-154">Types</span></span>](types.md)
- [<span data-ttu-id="48cd7-155">引用类型</span><span class="sxs-lookup"><span data-stu-id="48cd7-155">Reference Types</span></span>](reference-types.md)
- [<span data-ttu-id="48cd7-156">可以为 null 的类型</span><span class="sxs-lookup"><span data-stu-id="48cd7-156">Nullable types</span></span>](../../programming-guide/nullable-types/index.md)
