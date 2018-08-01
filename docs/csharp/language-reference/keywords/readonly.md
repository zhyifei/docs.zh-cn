---
title: readonly 关键字（C# 参考）
ms.date: 06/21/2018
f1_keywords:
- readonly_CSharpKeyword
- readonly
helpviewer_keywords:
- readonly keyword [C#]
ms.assetid: 2f8081f6-0de2-4903-898d-99696c48d2f4
ms.openlocfilehash: 96607f1dd7f019169446e29a08496fb54e1ed493
ms.sourcegitcommit: 60645077dc4b62178403145f8ef691b13ffec28e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2018
ms.locfileid: "37961178"
---
# <a name="readonly-c-reference"></a><span data-ttu-id="3f5e7-102">readonly（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="3f5e7-102">readonly (C# Reference)</span></span>

<span data-ttu-id="3f5e7-103">`readonly` 关键字是一个可在三个上下文中使用的修饰符：</span><span class="sxs-lookup"><span data-stu-id="3f5e7-103">The `readonly` keyword is a modifier that can be used in three contexts:</span></span>

- <span data-ttu-id="3f5e7-104">在[字段声明](#readonly-field-example)中，`readonly` 指示只能在声明期间或在同一个类的构造函数中向字段赋值。</span><span class="sxs-lookup"><span data-stu-id="3f5e7-104">In a [field declaration](#readonly-field-example), `readonly` indicates that assignment to the field can only occur as part of the declaration or in a constructor in the same class.</span></span>
- <span data-ttu-id="3f5e7-105">在 [`readonly struct` 定义](#readonly-struct-example)中，`readonly` 指示 `struct` 是不可变的。</span><span class="sxs-lookup"><span data-stu-id="3f5e7-105">In a [`readonly struct` definition](#readonly-struct-example), `readonly` indicates that the `struct` is immutable.</span></span>
- <span data-ttu-id="3f5e7-106">在 [`ref readonly` 方法返回](#ref-readonly-return-example)中，`readonly` 修饰符指示该方法返回一个引用，且不允许向该引用写入内容。</span><span class="sxs-lookup"><span data-stu-id="3f5e7-106">In a [`ref readonly` method return](#ref-readonly-return-example), the `readonly` modifier indicates that method returns a reference and writes are not allowed to that reference.</span></span>

<span data-ttu-id="3f5e7-107">C# 7.2 中添加了最后两个上下文。</span><span class="sxs-lookup"><span data-stu-id="3f5e7-107">The final two contexts were added in C# 7.2.</span></span>

## <a name="readonly-field-example"></a><span data-ttu-id="3f5e7-108">Readonly 字段示例</span><span class="sxs-lookup"><span data-stu-id="3f5e7-108">Readonly field example</span></span>  

<span data-ttu-id="3f5e7-109">在此示例中，即使在类构造函数中给字段 `year` 赋了值，它的值仍无法在 `ChangeYear` 方法中更改：</span><span class="sxs-lookup"><span data-stu-id="3f5e7-109">In this example, the value of the field `year` cannot be changed in the method `ChangeYear`, even though it is assigned a value in the class constructor:</span></span>  
  
[!code-csharp[Readonly Field example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyField)]  
  
<span data-ttu-id="3f5e7-110">只能在下列上下文中对 `readonly` 字段进行赋值：</span><span class="sxs-lookup"><span data-stu-id="3f5e7-110">You can assign a value to a `readonly` field only in the following contexts:</span></span>  
  
- <span data-ttu-id="3f5e7-111">在声明中初始化变量时，例如：</span><span class="sxs-lookup"><span data-stu-id="3f5e7-111">When the variable is initialized in the declaration, for example:</span></span>  

```csharp
public readonly int y = 5;  
```

- <span data-ttu-id="3f5e7-112">在包含实例字段声明的类的实例构造函数中。</span><span class="sxs-lookup"><span data-stu-id="3f5e7-112">In an instance constructor of the class that contains the instance field declaration.</span></span>
- <span data-ttu-id="3f5e7-113">在包含静态字段声明的类的静态构造函数中。</span><span class="sxs-lookup"><span data-stu-id="3f5e7-113">In the static constructor of the class that contains the static field declaration.</span></span>

<span data-ttu-id="3f5e7-114">只有在这些构造函数上下文中，将 `readonly` 字段作为 [out](out-parameter-modifier.md) 或 [ref](ref.md) 参数传递才有效。</span><span class="sxs-lookup"><span data-stu-id="3f5e7-114">These constructor contexts are also the only contexts in which it is valid to pass a `readonly` field as an [out](out-parameter-modifier.md) or [ref](ref.md) parameter.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3f5e7-115">`readonly` 关键字不同于 [const](const.md) 关键字。</span><span class="sxs-lookup"><span data-stu-id="3f5e7-115">The `readonly` keyword is different from the [const](const.md) keyword.</span></span> <span data-ttu-id="3f5e7-116">`const` 字段只能在该字段的声明中初始化。</span><span class="sxs-lookup"><span data-stu-id="3f5e7-116">A `const` field can only be initialized at the declaration of the field.</span></span> <span data-ttu-id="3f5e7-117">`readonly` 字段可以在声明或构造函数中初始化。</span><span class="sxs-lookup"><span data-stu-id="3f5e7-117">A `readonly` field can be initialized either at the declaration or in a constructor.</span></span> <span data-ttu-id="3f5e7-118">因此，根据所使用的构造函数，`readonly` 字段可能具有不同的值。</span><span class="sxs-lookup"><span data-stu-id="3f5e7-118">Therefore, `readonly` fields can have different values depending on the constructor used.</span></span> <span data-ttu-id="3f5e7-119">另外，虽然 `const` 字段是编译时常量，但 `readonly` 字段可用于运行时常量，如下面的示例所示： </span><span class="sxs-lookup"><span data-stu-id="3f5e7-119">Also, while a `const` field is a compile-time constant, the `readonly` field can be used for runtime constants as in the following example:</span></span>  

```csharp
public static readonly uint timeStamp = (uint)DateTime.Now.Ticks;  
```

[!code-csharp[Initialize readonly Field example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#InitReadonlyField)]  
  
<span data-ttu-id="3f5e7-120">在前面的示例中，如果使用类似以下示例的语句：</span><span class="sxs-lookup"><span data-stu-id="3f5e7-120">In the preceding example, if you use a statement like the following example:</span></span>  
  
`p2.y = 66;        // Error`  
  
<span data-ttu-id="3f5e7-121">将收到编译器错误消息：</span><span class="sxs-lookup"><span data-stu-id="3f5e7-121">you will get the compiler error message:</span></span>  
  
`The left-hand side of an assignment must be an l-value`  
  
<span data-ttu-id="3f5e7-122">这与尝试给常数赋值时收到的错误相同。</span><span class="sxs-lookup"><span data-stu-id="3f5e7-122">which is the same error you get when you attempt to assign a value to a constant.</span></span>  

## <a name="readonly-struct-example"></a><span data-ttu-id="3f5e7-123">只读结构示例</span><span class="sxs-lookup"><span data-stu-id="3f5e7-123">Readonly struct example</span></span>

<span data-ttu-id="3f5e7-124">`struct` 定义上的 `readonly` 修饰符声明该结构是不可变的。</span><span class="sxs-lookup"><span data-stu-id="3f5e7-124">The `readonly` modifier on a `struct` definition declares that the struct is **immutable**.</span></span> <span data-ttu-id="3f5e7-125">`struct` 的每个实例字段都必须被标记为 `readonly`，如下例所示：</span><span class="sxs-lookup"><span data-stu-id="3f5e7-125">Every instance field of the `struct` must be marked `readonly`, as shown in the following example:</span></span>

[!code-csharp[readonly struct example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyStruct)]  

<span data-ttu-id="3f5e7-126">前面的示例使用[只读自动属性](../../properties.md#read-only)来声明其存储。</span><span class="sxs-lookup"><span data-stu-id="3f5e7-126">The preceding example uses [readonly auto properties](../../properties.md#read-only) to declare its storage.</span></span> <span data-ttu-id="3f5e7-127">该操作指示编译器为这些属性创建 `readonly` 支持字段。</span><span class="sxs-lookup"><span data-stu-id="3f5e7-127">That instructs the compiler to create `readonly` backing fields for those properties.</span></span> <span data-ttu-id="3f5e7-128">还可以直接声明 `readonly` 字段：</span><span class="sxs-lookup"><span data-stu-id="3f5e7-128">You could also declare `readonly` fields directly:</span></span>

```csharp
public readonly struct Point
{
    public readonly double X;
    public readonly double Y;

    public Point(double x, double y) => (X, Y) = (x, y);

    public override string ToString() => $"({X}, {Y})";
}
```

<span data-ttu-id="3f5e7-129">添加未标记为 `readonly` 的字段，会产生编译器错误 `CS8340`：“只读结构的实例字段必须为只读。”</span><span class="sxs-lookup"><span data-stu-id="3f5e7-129">Adding a field not marked `readonly` generates compiler error `CS8340`: "Instance fields of readonly structs must be readonly."</span></span>

## <a name="ref-readonly-return-example"></a><span data-ttu-id="3f5e7-130">Ref readonly 返回示例</span><span class="sxs-lookup"><span data-stu-id="3f5e7-130">Ref readonly return example</span></span>

<span data-ttu-id="3f5e7-131">`ref return` 上的 `readonly` 修饰符指示返回的引用无法修改。</span><span class="sxs-lookup"><span data-stu-id="3f5e7-131">The `readonly` modifier on a `ref return` indicates that the returned reference cannot be modified.</span></span> <span data-ttu-id="3f5e7-132">下面的示例返回了一个对来源的引用。</span><span class="sxs-lookup"><span data-stu-id="3f5e7-132">The following example returns a reference to the origin.</span></span> <span data-ttu-id="3f5e7-133">它使用 `readonly` 修饰符来指示调用方无法修改来源：</span><span class="sxs-lookup"><span data-stu-id="3f5e7-133">It uses the `readonly` modifier to indicate that callers cannot modify the origin:</span></span>

[!code-csharp[readonly struct example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyReturn)]  
<span data-ttu-id="3f5e7-134">所返回的类型不需要为 `readonly struct`。</span><span class="sxs-lookup"><span data-stu-id="3f5e7-134">The type returned doesn't need to be a `readonly struct`.</span></span> <span data-ttu-id="3f5e7-135">`ref` 能返回的任何类型都能由 `ref readonly` 返回</span><span class="sxs-lookup"><span data-stu-id="3f5e7-135">Any type that can be returned by `ref` can be returned by `ref readonly`</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="3f5e7-136">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="3f5e7-136">C# Language Specification</span></span>  
[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3f5e7-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="3f5e7-137">See Also</span></span>  
[<span data-ttu-id="3f5e7-138">C# 参考</span><span class="sxs-lookup"><span data-stu-id="3f5e7-138">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
[<span data-ttu-id="3f5e7-139">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="3f5e7-139">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
[<span data-ttu-id="3f5e7-140">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="3f5e7-140">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
[<span data-ttu-id="3f5e7-141">修饰符</span><span class="sxs-lookup"><span data-stu-id="3f5e7-141">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)  
[<span data-ttu-id="3f5e7-142">const</span><span class="sxs-lookup"><span data-stu-id="3f5e7-142">const</span></span>](../../../csharp/language-reference/keywords/const.md)  
[<span data-ttu-id="3f5e7-143">字段</span><span class="sxs-lookup"><span data-stu-id="3f5e7-143">Fields</span></span>](../../../csharp/programming-guide/classes-and-structs/fields.md)
