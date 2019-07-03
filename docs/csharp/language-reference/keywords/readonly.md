---
title: readonly 关键字 - C# 参考
ms.custom: seodec18
ms.date: 06/21/2018
f1_keywords:
- readonly_CSharpKeyword
- readonly
helpviewer_keywords:
- readonly keyword [C#]
ms.assetid: 2f8081f6-0de2-4903-898d-99696c48d2f4
ms.openlocfilehash: 4a51bb0e854de127c632c28f613a7602bf09f432
ms.sourcegitcommit: 127343afce8422bfa944c8b0c4ecc8f79f653255
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/25/2019
ms.locfileid: "67348009"
---
# <a name="readonly-c-reference"></a><span data-ttu-id="6e02e-102">readonly（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="6e02e-102">readonly (C# Reference)</span></span>

<span data-ttu-id="6e02e-103">`readonly` 关键字是一个可在三个上下文中使用的修饰符：</span><span class="sxs-lookup"><span data-stu-id="6e02e-103">The `readonly` keyword is a modifier that can be used in three contexts:</span></span>

- <span data-ttu-id="6e02e-104">在[字段声明](#readonly-field-example)中，`readonly` 指示只能在声明期间或在同一个类的构造函数中向字段赋值。</span><span class="sxs-lookup"><span data-stu-id="6e02e-104">In a [field declaration](#readonly-field-example), `readonly` indicates that assignment to the field can only occur as part of the declaration or in a constructor in the same class.</span></span> <span data-ttu-id="6e02e-105">可以在字段声明和构造函数中多次分配和重新分配只读字段。</span><span class="sxs-lookup"><span data-stu-id="6e02e-105">A readonly field can be assigned and reassigned multiple times within the field declaration and constructor.</span></span> 
  
  <span data-ttu-id="6e02e-106">构造函数退出后，不能分配 `readonly` 字段。</span><span class="sxs-lookup"><span data-stu-id="6e02e-106">A `readonly` field cannot be assigned after the constructor exits.</span></span> <span data-ttu-id="6e02e-107">值类型和引用类型具有不同的含义：</span><span class="sxs-lookup"><span data-stu-id="6e02e-107">That has different implications for value types and reference types:</span></span>
  
  - <span data-ttu-id="6e02e-108">由于值类型直接包含数据，因此属于 `readonly` 值类型的字段不可变。</span><span class="sxs-lookup"><span data-stu-id="6e02e-108">Because value types directly contain their data, a field that is a  `readonly` value type is immutable.</span></span> 
  - <span data-ttu-id="6e02e-109">由于引用类型包含对其数据的引用，因此属于 `readonly` 引用类型的字段必须始终引用同一对象。</span><span class="sxs-lookup"><span data-stu-id="6e02e-109">Because reference types contain a reference to their data, a field that is a `readonly` reference type must always refer to the same object.</span></span> <span data-ttu-id="6e02e-110">该对象不是不可变的。</span><span class="sxs-lookup"><span data-stu-id="6e02e-110">That object is not immutable.</span></span> <span data-ttu-id="6e02e-111">`readonly` 修饰符可防止字段替换为引用类型的其他实例。</span><span class="sxs-lookup"><span data-stu-id="6e02e-111">The `readonly` modifier prevents the field from being replaced by a different instance of the reference type.</span></span> <span data-ttu-id="6e02e-112">但是，修饰符不会阻止通过只读字段修改字段的实例数据。</span><span class="sxs-lookup"><span data-stu-id="6e02e-112">However, the modifier does not prevent the instance data of the field from being modified through the read-only field.</span></span>

  > [!WARNING]
  > <span data-ttu-id="6e02e-113">包含属于可变引用类型的外部可见只读字段的外部可见类型可能存在安全漏洞，可能会触发警告 [CA2104](/visualstudio/code-quality/ca2104-do-not-declare-read-only-mutable-reference-types)：“不要声明只读可变引用类型。”</span><span class="sxs-lookup"><span data-stu-id="6e02e-113">An externally visible type that contains an externally visible read-only field that is a mutable reference type may be a security vulnerability and may trigger warning [CA2104](/visualstudio/code-quality/ca2104-do-not-declare-read-only-mutable-reference-types) : "Do not declare read only mutable reference types."</span></span>

- <span data-ttu-id="6e02e-114">在 [`readonly struct` 定义](#readonly-struct-example)中，`readonly` 指示 `struct` 是不可变的。</span><span class="sxs-lookup"><span data-stu-id="6e02e-114">In a [`readonly struct` definition](#readonly-struct-example), `readonly` indicates that the `struct` is immutable.</span></span>
- <span data-ttu-id="6e02e-115">在 [`ref readonly` 方法返回](#ref-readonly-return-example)中，`readonly` 修饰符指示该方法返回一个引用，且不允许向该引用写入内容。</span><span class="sxs-lookup"><span data-stu-id="6e02e-115">In a [`ref readonly` method return](#ref-readonly-return-example), the `readonly` modifier indicates that method returns a reference and writes are not allowed to that reference.</span></span>

<span data-ttu-id="6e02e-116">C# 7.2 中添加了最后两个上下文。</span><span class="sxs-lookup"><span data-stu-id="6e02e-116">The final two contexts were added in C# 7.2.</span></span>

## <a name="readonly-field-example"></a><span data-ttu-id="6e02e-117">Readonly 字段示例</span><span class="sxs-lookup"><span data-stu-id="6e02e-117">Readonly field example</span></span>

<span data-ttu-id="6e02e-118">在此示例中，即使在类构造函数中给字段 `year` 赋了值，它的值仍无法在 `ChangeYear` 方法中更改：</span><span class="sxs-lookup"><span data-stu-id="6e02e-118">In this example, the value of the field `year` cannot be changed in the method `ChangeYear`, even though it is assigned a value in the class constructor:</span></span>

[!code-csharp[Readonly Field example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyField)]

<span data-ttu-id="6e02e-119">只能在下列上下文中对 `readonly` 字段进行赋值：</span><span class="sxs-lookup"><span data-stu-id="6e02e-119">You can assign a value to a `readonly` field only in the following contexts:</span></span>

- <span data-ttu-id="6e02e-120">在声明中初始化变量时，例如：</span><span class="sxs-lookup"><span data-stu-id="6e02e-120">When the variable is initialized in the declaration, for example:</span></span>

  ```csharp
  public readonly int y = 5;
  ```

- <span data-ttu-id="6e02e-121">在包含实例字段声明的类的实例构造函数中。</span><span class="sxs-lookup"><span data-stu-id="6e02e-121">In an instance constructor of the class that contains the instance field declaration.</span></span>
- <span data-ttu-id="6e02e-122">在包含静态字段声明的类的静态构造函数中。</span><span class="sxs-lookup"><span data-stu-id="6e02e-122">In the static constructor of the class that contains the static field declaration.</span></span>

<span data-ttu-id="6e02e-123">只有在这些构造函数上下文中，将 `readonly` 字段作为 [out](out-parameter-modifier.md) 或 [ref](ref.md) 参数传递才有效。</span><span class="sxs-lookup"><span data-stu-id="6e02e-123">These constructor contexts are also the only contexts in which it is valid to pass a `readonly` field as an [out](out-parameter-modifier.md) or [ref](ref.md) parameter.</span></span>

> [!NOTE]
> <span data-ttu-id="6e02e-124">`readonly` 关键字不同于 [const](const.md) 关键字。</span><span class="sxs-lookup"><span data-stu-id="6e02e-124">The `readonly` keyword is different from the [const](const.md) keyword.</span></span> <span data-ttu-id="6e02e-125">`const` 字段只能在该字段的声明中初始化。</span><span class="sxs-lookup"><span data-stu-id="6e02e-125">A `const` field can only be initialized at the declaration of the field.</span></span> <span data-ttu-id="6e02e-126">可以在字段声明和任何构造函数中多次分配 `readonly` 字段。</span><span class="sxs-lookup"><span data-stu-id="6e02e-126">A `readonly` field can be assigned multiple times in the field declaration and in any constructor.</span></span> <span data-ttu-id="6e02e-127">因此，根据所使用的构造函数，`readonly` 字段可能具有不同的值。</span><span class="sxs-lookup"><span data-stu-id="6e02e-127">Therefore, `readonly` fields can have different values depending on the constructor used.</span></span> <span data-ttu-id="6e02e-128">另外，虽然 `const` 字段是编译时常量，但 `readonly` 字段可用于运行时常量，如下面的示例所示：</span><span class="sxs-lookup"><span data-stu-id="6e02e-128">Also, while a `const` field is a compile-time constant, the `readonly` field can be used for runtime constants as in the following example:</span></span>
>
> ```csharp
> public static readonly uint timeStamp = (uint)DateTime.Now.Ticks;
> ```

[!code-csharp[Initialize readonly Field example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#InitReadonlyField)]

<span data-ttu-id="6e02e-129">在前面的示例中，如果使用类似以下示例的语句：</span><span class="sxs-lookup"><span data-stu-id="6e02e-129">In the preceding example, if you use a statement like the following example:</span></span>

```csharp
p2.y = 66;        // Error
```

<span data-ttu-id="6e02e-130">将收到编译器错误消息：</span><span class="sxs-lookup"><span data-stu-id="6e02e-130">you will get the compiler error message:</span></span>

`A readonly field cannot be assigned to (except in a constructor or a variable initializer)`

## <a name="readonly-struct-example"></a><span data-ttu-id="6e02e-131">只读结构示例</span><span class="sxs-lookup"><span data-stu-id="6e02e-131">Readonly struct example</span></span>

<span data-ttu-id="6e02e-132">`struct` 定义上的 `readonly` 修饰符声明该结构是不可变的  。</span><span class="sxs-lookup"><span data-stu-id="6e02e-132">The `readonly` modifier on a `struct` definition declares that the struct is **immutable**.</span></span> <span data-ttu-id="6e02e-133">`struct` 的每个实例字段都必须被标记为 `readonly`，如下例所示：</span><span class="sxs-lookup"><span data-stu-id="6e02e-133">Every instance field of the `struct` must be marked `readonly`, as shown in the following example:</span></span>

[!code-csharp[readonly struct example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyStruct)]

<span data-ttu-id="6e02e-134">前面的示例使用[只读自动属性](../../properties.md#read-only)来声明其存储。</span><span class="sxs-lookup"><span data-stu-id="6e02e-134">The preceding example uses [readonly auto properties](../../properties.md#read-only) to declare its storage.</span></span> <span data-ttu-id="6e02e-135">该操作指示编译器为这些属性创建 `readonly` 支持字段。</span><span class="sxs-lookup"><span data-stu-id="6e02e-135">That instructs the compiler to create `readonly` backing fields for those properties.</span></span> <span data-ttu-id="6e02e-136">还可以直接声明 `readonly` 字段：</span><span class="sxs-lookup"><span data-stu-id="6e02e-136">You could also declare `readonly` fields directly:</span></span>

```csharp
public readonly struct Point
{
    public readonly double X;
    public readonly double Y;

    public Point(double x, double y) => (X, Y) = (x, y);

    public override string ToString() => $"({X}, {Y})";
}
```

<span data-ttu-id="6e02e-137">添加未标记 `readonly` 的字段会生成编译器错误 `CS8340`：“只读结构的实例字段必须为只读。”</span><span class="sxs-lookup"><span data-stu-id="6e02e-137">Adding a field not marked `readonly` generates compiler error `CS8340`: "Instance fields of readonly structs must be readonly."</span></span>

## <a name="ref-readonly-return-example"></a><span data-ttu-id="6e02e-138">Ref readonly 返回示例</span><span class="sxs-lookup"><span data-stu-id="6e02e-138">Ref readonly return example</span></span>

<span data-ttu-id="6e02e-139">`ref return` 上的 `readonly` 修饰符指示返回的引用无法修改。</span><span class="sxs-lookup"><span data-stu-id="6e02e-139">The `readonly` modifier on a `ref return` indicates that the returned reference cannot be modified.</span></span> <span data-ttu-id="6e02e-140">下面的示例返回了一个对来源的引用。</span><span class="sxs-lookup"><span data-stu-id="6e02e-140">The following example returns a reference to the origin.</span></span> <span data-ttu-id="6e02e-141">它使用 `readonly` 修饰符来指示调用方无法修改来源：</span><span class="sxs-lookup"><span data-stu-id="6e02e-141">It uses the `readonly` modifier to indicate that callers cannot modify the origin:</span></span>

[!code-csharp[readonly struct example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyReturn)]
<span data-ttu-id="6e02e-142">所返回的类型不需要为 `readonly struct`。</span><span class="sxs-lookup"><span data-stu-id="6e02e-142">The type returned doesn't need to be a `readonly struct`.</span></span> <span data-ttu-id="6e02e-143">`ref` 能返回的任何类型都能由 `ref readonly` 返回。</span><span class="sxs-lookup"><span data-stu-id="6e02e-143">Any type that can be returned by `ref` can be returned by `ref readonly`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="6e02e-144">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="6e02e-144">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="6e02e-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="6e02e-145">See also</span></span>

- [<span data-ttu-id="6e02e-146">C# 参考</span><span class="sxs-lookup"><span data-stu-id="6e02e-146">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="6e02e-147">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="6e02e-147">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="6e02e-148">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="6e02e-148">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="6e02e-149">修饰符</span><span class="sxs-lookup"><span data-stu-id="6e02e-149">Modifiers</span></span>](modifiers.md)
- [<span data-ttu-id="6e02e-150">const</span><span class="sxs-lookup"><span data-stu-id="6e02e-150">const</span></span>](const.md)
- [<span data-ttu-id="6e02e-151">字段</span><span class="sxs-lookup"><span data-stu-id="6e02e-151">Fields</span></span>](../../programming-guide/classes-and-structs/fields.md)
