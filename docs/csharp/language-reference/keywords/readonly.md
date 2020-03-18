---
title: readonly 关键字 - C# 参考
ms.date: 06/21/2018
f1_keywords:
- readonly_CSharpKeyword
- readonly
helpviewer_keywords:
- readonly keyword [C#]
ms.assetid: 2f8081f6-0de2-4903-898d-99696c48d2f4
ms.openlocfilehash: 165b6287e1610e013b289601e1535a08fdd3b5c9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "79398123"
---
# <a name="readonly-c-reference"></a><span data-ttu-id="0fd32-102">readonly（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="0fd32-102">readonly (C# Reference)</span></span>

<span data-ttu-id="0fd32-103">`readonly` 关键字是一个可在四个上下文中使用的修饰符：</span><span class="sxs-lookup"><span data-stu-id="0fd32-103">The `readonly` keyword is a modifier that can be used in four contexts:</span></span>

- <span data-ttu-id="0fd32-104">在[字段声明](#readonly-field-example)中，`readonly` 指示只能在声明期间或在同一个类的构造函数中向字段赋值。</span><span class="sxs-lookup"><span data-stu-id="0fd32-104">In a [field declaration](#readonly-field-example), `readonly` indicates that assignment to the field can only occur as part of the declaration or in a constructor in the same class.</span></span> <span data-ttu-id="0fd32-105">可以在字段声明和构造函数中多次分配和重新分配只读字段。</span><span class="sxs-lookup"><span data-stu-id="0fd32-105">A readonly field can be assigned and reassigned multiple times within the field declaration and constructor.</span></span>
  
  <span data-ttu-id="0fd32-106">构造函数退出后，不能分配 `readonly` 字段。</span><span class="sxs-lookup"><span data-stu-id="0fd32-106">A `readonly` field can't be assigned after the constructor exits.</span></span> <span data-ttu-id="0fd32-107">此规则对于值类型和引用类型具有不同的含义：</span><span class="sxs-lookup"><span data-stu-id="0fd32-107">This rule has different implications for value types and reference types:</span></span>
  
  - <span data-ttu-id="0fd32-108">由于值类型直接包含数据，因此属于 `readonly` 值类型的字段不可变。</span><span class="sxs-lookup"><span data-stu-id="0fd32-108">Because value types directly contain their data, a field that is a  `readonly` value type is immutable.</span></span>
  - <span data-ttu-id="0fd32-109">由于引用类型包含对其数据的引用，因此属于 `readonly` 引用类型的字段必须始终引用同一对象。</span><span class="sxs-lookup"><span data-stu-id="0fd32-109">Because reference types contain a reference to their data, a field that is a `readonly` reference type must always refer to the same object.</span></span> <span data-ttu-id="0fd32-110">该对象是可变的。</span><span class="sxs-lookup"><span data-stu-id="0fd32-110">That object isn't immutable.</span></span> <span data-ttu-id="0fd32-111">`readonly` 修饰符可防止字段替换为引用类型的其他实例。</span><span class="sxs-lookup"><span data-stu-id="0fd32-111">The `readonly` modifier prevents the field from being replaced by a different instance of the reference type.</span></span> <span data-ttu-id="0fd32-112">但是，修饰符不会阻止通过只读字段修改字段的实例数据。</span><span class="sxs-lookup"><span data-stu-id="0fd32-112">However, the modifier doesn't prevent the instance data of the field from being modified through the read-only field.</span></span>

  > [!WARNING]
  > <span data-ttu-id="0fd32-113">包含属于可变引用类型的外部可见只读字段的外部可见类型可能存在安全漏洞，可能会触发警告 [CA2104](/visualstudio/code-quality/ca2104)：“不要声明只读可变引用类型。”</span><span class="sxs-lookup"><span data-stu-id="0fd32-113">An externally visible type that contains an externally visible read-only field that is a mutable reference type may be a security vulnerability and may trigger warning [CA2104](/visualstudio/code-quality/ca2104) : "Do not declare read only mutable reference types."</span></span>

- <span data-ttu-id="0fd32-114">在 [`readonly struct` 定义](#readonly-struct-example)中，`readonly` 指示 `struct` 是不可变的。</span><span class="sxs-lookup"><span data-stu-id="0fd32-114">In a [`readonly struct` definition](#readonly-struct-example), `readonly` indicates that the `struct` is immutable.</span></span>
- <span data-ttu-id="0fd32-115">在 [`readonly` 成员定义](#readonly-member-examples)中，`readonly` 表示 `struct` 的成员不会改变结构的内部状态。</span><span class="sxs-lookup"><span data-stu-id="0fd32-115">In a [`readonly` member definition](#readonly-member-examples), `readonly` indicates that a member of a `struct` doesn't mutate the struct's internal state.</span></span>
- <span data-ttu-id="0fd32-116">在 [`ref readonly` 方法返回](#ref-readonly-return-example)中，`readonly` 修饰符指示该方法返回一个引用，且不允许向该引用写入内容。</span><span class="sxs-lookup"><span data-stu-id="0fd32-116">In a [`ref readonly` method return](#ref-readonly-return-example), the `readonly` modifier indicates that method returns a reference and writes aren't allowed to that reference.</span></span>

<span data-ttu-id="0fd32-117">在 C# 7.2 中添加了 `readonly struct` 和 `ref readonly` 上下文。</span><span class="sxs-lookup"><span data-stu-id="0fd32-117">The `readonly struct` and `ref readonly` contexts were added in C# 7.2.</span></span> <span data-ttu-id="0fd32-118">在 C# 8.0 中添加了 `readonly` 结构成员</span><span class="sxs-lookup"><span data-stu-id="0fd32-118">`readonly` struct members were added in C# 8.0</span></span>

## <a name="readonly-field-example"></a><span data-ttu-id="0fd32-119">Readonly 字段示例</span><span class="sxs-lookup"><span data-stu-id="0fd32-119">Readonly field example</span></span>

<span data-ttu-id="0fd32-120">在此示例中，即使在类构造函数中给字段 `year` 赋了值，也无法在方法 `ChangeYear` 中更改其值：</span><span class="sxs-lookup"><span data-stu-id="0fd32-120">In this example, the value of the field `year` can't be changed in the method `ChangeYear`, even though it's assigned a value in the class constructor:</span></span>

[!code-csharp[Readonly Field example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyField)]

<span data-ttu-id="0fd32-121">只能在下列上下文中对 `readonly` 字段进行赋值：</span><span class="sxs-lookup"><span data-stu-id="0fd32-121">You can assign a value to a `readonly` field only in the following contexts:</span></span>

- <span data-ttu-id="0fd32-122">在声明中初始化变量时，例如：</span><span class="sxs-lookup"><span data-stu-id="0fd32-122">When the variable is initialized in the declaration, for example:</span></span>

  ```csharp
  public readonly int y = 5;
  ```

- <span data-ttu-id="0fd32-123">在包含实例字段声明的类的实例构造函数中。</span><span class="sxs-lookup"><span data-stu-id="0fd32-123">In an instance constructor of the class that contains the instance field declaration.</span></span>
- <span data-ttu-id="0fd32-124">在包含静态字段声明的类的静态构造函数中。</span><span class="sxs-lookup"><span data-stu-id="0fd32-124">In the static constructor of the class that contains the static field declaration.</span></span>

<span data-ttu-id="0fd32-125">只有在这些构造函数上下文中，将 `readonly` 字段作为 [out](out-parameter-modifier.md) 或 [ref](ref.md) 参数传递才有效。</span><span class="sxs-lookup"><span data-stu-id="0fd32-125">These constructor contexts are also the only contexts in which it's valid to pass a `readonly` field as an [out](out-parameter-modifier.md) or [ref](ref.md) parameter.</span></span>

> [!NOTE]
> <span data-ttu-id="0fd32-126">`readonly` 关键字不同于 [const](const.md) 关键字。</span><span class="sxs-lookup"><span data-stu-id="0fd32-126">The `readonly` keyword is different from the [const](const.md) keyword.</span></span> <span data-ttu-id="0fd32-127">`const` 字段只能在该字段的声明中初始化。</span><span class="sxs-lookup"><span data-stu-id="0fd32-127">A `const` field can only be initialized at the declaration of the field.</span></span> <span data-ttu-id="0fd32-128">可以在字段声明和任何构造函数中多次分配 `readonly` 字段。</span><span class="sxs-lookup"><span data-stu-id="0fd32-128">A `readonly` field can be assigned multiple times in the field declaration and in any constructor.</span></span> <span data-ttu-id="0fd32-129">因此，根据所使用的构造函数，`readonly` 字段可能具有不同的值。</span><span class="sxs-lookup"><span data-stu-id="0fd32-129">Therefore, `readonly` fields can have different values depending on the constructor used.</span></span> <span data-ttu-id="0fd32-130">另外，虽然 `const` 字段是编译时常量，但 `readonly` 字段可用于运行时常量，如下面的示例所示：</span><span class="sxs-lookup"><span data-stu-id="0fd32-130">Also, while a `const` field is a compile-time constant, the `readonly` field can be used for run-time constants as in the following example:</span></span>
>
> ```csharp
> public static readonly uint timeStamp = (uint)DateTime.Now.Ticks;
> ```

[!code-csharp[Initialize readonly Field example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#InitReadonlyField)]

<span data-ttu-id="0fd32-131">在前面的示例中，如果使用类似以下示例的语句：</span><span class="sxs-lookup"><span data-stu-id="0fd32-131">In the preceding example, if you use a statement like the following example:</span></span>

```csharp
p2.y = 66;        // Error
```

<span data-ttu-id="0fd32-132">你将收到编译器错误消息：</span><span class="sxs-lookup"><span data-stu-id="0fd32-132">you'll get the compiler error message:</span></span>

<span data-ttu-id="0fd32-133">**无法对只读的字段赋值（构造函数或变量初始值指定项中除外）**</span><span class="sxs-lookup"><span data-stu-id="0fd32-133">**A readonly field cannot be assigned to (except in a constructor or a variable initializer)**</span></span>

## <a name="readonly-struct-example"></a><span data-ttu-id="0fd32-134">只读结构示例</span><span class="sxs-lookup"><span data-stu-id="0fd32-134">Readonly struct example</span></span>

<span data-ttu-id="0fd32-135">`struct` 定义上的 `readonly` 修饰符声明该结构是不可变的  。</span><span class="sxs-lookup"><span data-stu-id="0fd32-135">The `readonly` modifier on a `struct` definition declares that the struct is **immutable**.</span></span> <span data-ttu-id="0fd32-136">`struct` 的每个实例字段都必须被标记为 `readonly`，如下例所示：</span><span class="sxs-lookup"><span data-stu-id="0fd32-136">Every instance field of the `struct` must be marked `readonly`, as shown in the following example:</span></span>

[!code-csharp[readonly struct example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyStruct)]

<span data-ttu-id="0fd32-137">前面的示例使用[只读自动属性](../../properties.md#read-only)来声明其存储。</span><span class="sxs-lookup"><span data-stu-id="0fd32-137">The preceding example uses [readonly auto properties](../../properties.md#read-only) to declare its storage.</span></span> <span data-ttu-id="0fd32-138">该操作指示编译器为这些属性创建 `readonly` 支持字段。</span><span class="sxs-lookup"><span data-stu-id="0fd32-138">That instructs the compiler to create `readonly` backing fields for those properties.</span></span> <span data-ttu-id="0fd32-139">还可以直接声明 `readonly` 字段：</span><span class="sxs-lookup"><span data-stu-id="0fd32-139">You could also declare `readonly` fields directly:</span></span>

```csharp
public readonly struct Point
{
    public readonly double X;
    public readonly double Y;

    public Point(double x, double y) => (X, Y) = (x, y);

    public override string ToString() => $"({X}, {Y})";
}
```

<span data-ttu-id="0fd32-140">添加未标记 `readonly` 的字段会生成编译器错误 `CS8340`：“只读结构的实例字段必须为只读。”</span><span class="sxs-lookup"><span data-stu-id="0fd32-140">Adding a field not marked `readonly` generates compiler error `CS8340`: "Instance fields of readonly structs must be readonly."</span></span>

## <a name="readonly-member-examples"></a><span data-ttu-id="0fd32-141">Readonly 成员示例</span><span class="sxs-lookup"><span data-stu-id="0fd32-141">Readonly member examples</span></span>

<span data-ttu-id="0fd32-142">其他情况下，你可以创建支持可变的结构。</span><span class="sxs-lookup"><span data-stu-id="0fd32-142">Other times, you may create a struct that supports mutation.</span></span> <span data-ttu-id="0fd32-143">在这些情况下，多个实例成员可能不会修改结构的内部状态。</span><span class="sxs-lookup"><span data-stu-id="0fd32-143">In those cases, several of the instance members likely won't modify the internal state of the struct.</span></span> <span data-ttu-id="0fd32-144">可以使用 `readonly` 修饰符声明那些实例成员。</span><span class="sxs-lookup"><span data-stu-id="0fd32-144">You can declare those instance members with the `readonly` modifier.</span></span> <span data-ttu-id="0fd32-145">编译器会强制执行你的意图。</span><span class="sxs-lookup"><span data-stu-id="0fd32-145">The compiler enforces your intent.</span></span> <span data-ttu-id="0fd32-146">如果该成员直接修改状态或访问未使用 `readonly` 修饰符声明的成员，则结果为编译时错误。</span><span class="sxs-lookup"><span data-stu-id="0fd32-146">If that member modifies state directly or accesses a member that isn't also declared with the `readonly` modifier, the result is a compile-time error.</span></span> <span data-ttu-id="0fd32-147">`readonly` 修饰符对 `struct` 成员有效，而对 `class` 或 `interface` 成员声明无效。</span><span class="sxs-lookup"><span data-stu-id="0fd32-147">The `readonly` modifier is valid on `struct` members, not `class` or `interface` member declarations.</span></span>

<span data-ttu-id="0fd32-148">通过将 `readonly` 修饰符应用于适用的 `struct` 方法，可以获得两个好处。</span><span class="sxs-lookup"><span data-stu-id="0fd32-148">You gain two advantages by applying the `readonly` modifier to applicable `struct` methods.</span></span> <span data-ttu-id="0fd32-149">最重要的是，编译器会强制执行你的意图。</span><span class="sxs-lookup"><span data-stu-id="0fd32-149">Most importantly, the compiler enforces your intent.</span></span> <span data-ttu-id="0fd32-150">修改状态的代码在 `readonly` 方法中无效。</span><span class="sxs-lookup"><span data-stu-id="0fd32-150">Code that modifies state isn't valid in a `readonly` method.</span></span> <span data-ttu-id="0fd32-151">编译器还可以使用 `readonly` 修饰符来实现性能优化。</span><span class="sxs-lookup"><span data-stu-id="0fd32-151">The compiler may also make use of the `readonly` modifier to enable performance optimizations.</span></span> <span data-ttu-id="0fd32-152">大型 `struct` 类型由 `in` 引用传递时，如果该结构的状态可以进行修改，则编译器必须生成一个防御性副本。</span><span class="sxs-lookup"><span data-stu-id="0fd32-152">When large `struct` types are passed by `in` reference, the compiler must generate a defensive copy if the state of the struct might be modified.</span></span> <span data-ttu-id="0fd32-153">如果仅访问 `readonly` 成员，则编译器可能不会创建防御性副本。</span><span class="sxs-lookup"><span data-stu-id="0fd32-153">If only `readonly` members are accessed, the compiler may not create the defensive copy.</span></span>

<span data-ttu-id="0fd32-154">`readonly` 修饰符对 `struct` 的大多数成员有效，包括重写在 <xref:System.Object?displayProperty=nameWithType> 中声明的方法的方法。</span><span class="sxs-lookup"><span data-stu-id="0fd32-154">The `readonly` modifier is valid on most members of a `struct`, including methods that override methods declared in <xref:System.Object?displayProperty=nameWithType>.</span></span> <span data-ttu-id="0fd32-155">但存在一些限制：</span><span class="sxs-lookup"><span data-stu-id="0fd32-155">There are some restrictions:</span></span>

- <span data-ttu-id="0fd32-156">不能声明 `readonly` 静态方法或属性。</span><span class="sxs-lookup"><span data-stu-id="0fd32-156">You can't declare `readonly` static methods or properties.</span></span>
- <span data-ttu-id="0fd32-157">无法声明 `readonly` 构造函数。</span><span class="sxs-lookup"><span data-stu-id="0fd32-157">You can't declare `readonly` constructors.</span></span>

<span data-ttu-id="0fd32-158">可将 `readonly` 修饰符添加到属性或索引器声明中：</span><span class="sxs-lookup"><span data-stu-id="0fd32-158">You can add the `readonly` modifier to a property or indexer declaration:</span></span>

```csharp
readonly public int Counter
{
  get { return 0; }
  set {} // not useful, but legal
}
```

<span data-ttu-id="0fd32-159">还可将 `readonly` 修饰符添加到属性或索引器的单个 `get` 或 `set` 访问器中：</span><span class="sxs-lookup"><span data-stu-id="0fd32-159">You may also add the `readonly` modifier to individual `get` or `set` accessors of a property or indexer:</span></span>

```csharp
public int Counter
{
  readonly get { return _counter; }
  set { _counter = value; }
}
int _counter;
```

<span data-ttu-id="0fd32-160">不能同时将 `readonly` 修饰符添加到一个属性以及同一属性的一个或多个访问器中。</span><span class="sxs-lookup"><span data-stu-id="0fd32-160">You may not add the `readonly` modifier to both a property and one or more of that same property's accessors.</span></span> <span data-ttu-id="0fd32-161">同样的限制也适用于索引器。</span><span class="sxs-lookup"><span data-stu-id="0fd32-161">That same restriction applies to indexers.</span></span>

<span data-ttu-id="0fd32-162">编译器隐式地将 `readonly` 修饰符应用于自动实现的属性，在这些属性中，编译器实现的代码不修改状态。</span><span class="sxs-lookup"><span data-stu-id="0fd32-162">The compiler implicitly applies the `readonly` modifier to auto-implemented properties where the compiler implemented code doesn't modify state.</span></span> <span data-ttu-id="0fd32-163">它等效于以下声明：</span><span class="sxs-lookup"><span data-stu-id="0fd32-163">It's equivalent to the following declarations:</span></span>

```csharp
public readonly int Index { get; }
// Or:
public int Number { readonly get; }
public string Message { readonly get; set; }
```

<span data-ttu-id="0fd32-164">可以在这些位置添加 `readonly` 修饰符，但不会产生任何有意义的效果。</span><span class="sxs-lookup"><span data-stu-id="0fd32-164">You may add the `readonly` modifier in those locations, but it will have no meaningful effect.</span></span> <span data-ttu-id="0fd32-165">不能将 `readonly` 修饰符添加到自动实现的属性资源库或读/写自动实现的属性中。</span><span class="sxs-lookup"><span data-stu-id="0fd32-165">You may not add the `readonly` modifier to an auto-implemented property setter, or to a read/write auto-implemented property.</span></span>

## <a name="ref-readonly-return-example"></a><span data-ttu-id="0fd32-166">Ref readonly 返回示例</span><span class="sxs-lookup"><span data-stu-id="0fd32-166">Ref readonly return example</span></span>

<span data-ttu-id="0fd32-167">`ref return` 上的 `readonly` 修饰符指示返回的引用无法修改。</span><span class="sxs-lookup"><span data-stu-id="0fd32-167">The `readonly` modifier on a `ref return` indicates that the returned reference can't be modified.</span></span> <span data-ttu-id="0fd32-168">下面的示例返回了一个对来源的引用。</span><span class="sxs-lookup"><span data-stu-id="0fd32-168">The following example returns a reference to the origin.</span></span> <span data-ttu-id="0fd32-169">它使用 `readonly` 修饰符来指示调用方无法修改来源：</span><span class="sxs-lookup"><span data-stu-id="0fd32-169">It uses the `readonly` modifier to indicate that callers can't modify the origin:</span></span>

[!code-csharp[readonly struct example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyReturn)]
<span data-ttu-id="0fd32-170">所返回的类型不需要为 `readonly struct`。</span><span class="sxs-lookup"><span data-stu-id="0fd32-170">The type returned doesn't need to be a `readonly struct`.</span></span> <span data-ttu-id="0fd32-171">`ref` 能返回的任何类型都能由 `ref readonly` 返回。</span><span class="sxs-lookup"><span data-stu-id="0fd32-171">Any type that can be returned by `ref` can be returned by `ref readonly`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="0fd32-172">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="0fd32-172">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

<span data-ttu-id="0fd32-173">你还可查看语言规范建议：</span><span class="sxs-lookup"><span data-stu-id="0fd32-173">You can also see the language specification proposals:</span></span>

- [<span data-ttu-id="0fd32-174">readonly ref 和 readonly 结构</span><span class="sxs-lookup"><span data-stu-id="0fd32-174">readonly ref and readonly struct</span></span>](~/_csharplang/proposals/csharp-7.2/readonly-ref.md)
- [<span data-ttu-id="0fd32-175">readonly 结构成员</span><span class="sxs-lookup"><span data-stu-id="0fd32-175">readonly struct members</span></span>](~/_csharplang/proposals/csharp-8.0/readonly-instance-members.md)

## <a name="see-also"></a><span data-ttu-id="0fd32-176">请参阅</span><span class="sxs-lookup"><span data-stu-id="0fd32-176">See also</span></span>

- [<span data-ttu-id="0fd32-177">C# 参考</span><span class="sxs-lookup"><span data-stu-id="0fd32-177">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="0fd32-178">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="0fd32-178">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="0fd32-179">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="0fd32-179">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="0fd32-180">修饰符</span><span class="sxs-lookup"><span data-stu-id="0fd32-180">Modifiers</span></span>](index.md)
- [<span data-ttu-id="0fd32-181">const</span><span class="sxs-lookup"><span data-stu-id="0fd32-181">const</span></span>](const.md)
- [<span data-ttu-id="0fd32-182">字段</span><span class="sxs-lookup"><span data-stu-id="0fd32-182">Fields</span></span>](../../programming-guide/classes-and-structs/fields.md)
