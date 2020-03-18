---
title: class 关键字 - C# 参考
ms.date: 07/18/2017
f1_keywords:
- class_CSharpKeyword
- class
helpviewer_keywords:
- class keyword [C#]
ms.assetid: b95d8815-de18-4c3f-a8cc-a0a53bdf8690
ms.openlocfilehash: 500160d3bc9280b866e5f5ba24c5edc623e752c1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "77673090"
---
# <a name="class-c-reference"></a><span data-ttu-id="e84fe-102">class（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="e84fe-102">class (C# Reference)</span></span>

<span data-ttu-id="e84fe-103">使用 `class` 关键字声明类，如下例中所示：</span><span class="sxs-lookup"><span data-stu-id="e84fe-103">Classes are declared using the keyword `class`, as shown in the following example:</span></span>

```csharp
class TestClass
{
    // Methods, properties, fields, events, delegates
    // and nested classes go here.
}
```

## <a name="remarks"></a><span data-ttu-id="e84fe-104">备注</span><span class="sxs-lookup"><span data-stu-id="e84fe-104">Remarks</span></span>

<span data-ttu-id="e84fe-105">在 C# 中仅允许单一继承。</span><span class="sxs-lookup"><span data-stu-id="e84fe-105">Only single inheritance is allowed in C#.</span></span> <span data-ttu-id="e84fe-106">也就是说，一个类仅能从一个基类继承实现。</span><span class="sxs-lookup"><span data-stu-id="e84fe-106">In other words, a class can inherit implementation from one base class only.</span></span> <span data-ttu-id="e84fe-107">但是，一个类可实现多个接口。</span><span class="sxs-lookup"><span data-stu-id="e84fe-107">However, a class can implement more than one interface.</span></span> <span data-ttu-id="e84fe-108">下表显示类继承和接口实现的一些示例：</span><span class="sxs-lookup"><span data-stu-id="e84fe-108">The following table shows examples of class inheritance and interface implementation:</span></span>

|<span data-ttu-id="e84fe-109">继承</span><span class="sxs-lookup"><span data-stu-id="e84fe-109">Inheritance</span></span>|<span data-ttu-id="e84fe-110">示例</span><span class="sxs-lookup"><span data-stu-id="e84fe-110">Example</span></span>|
|-----------------|-------------|
|<span data-ttu-id="e84fe-111">None</span><span class="sxs-lookup"><span data-stu-id="e84fe-111">None</span></span>|`class ClassA { }`|
|<span data-ttu-id="e84fe-112">Single</span><span class="sxs-lookup"><span data-stu-id="e84fe-112">Single</span></span>|`class DerivedClass : BaseClass { }`|
|<span data-ttu-id="e84fe-113">无，实现两个接口</span><span class="sxs-lookup"><span data-stu-id="e84fe-113">None, implements two interfaces</span></span>|`class ImplClass : IFace1, IFace2 { }`|
|<span data-ttu-id="e84fe-114">单一，实现一个接口</span><span class="sxs-lookup"><span data-stu-id="e84fe-114">Single, implements one interface</span></span>|`class ImplDerivedClass : BaseClass, IFace1 { }`|

<span data-ttu-id="e84fe-115">直接在命名空间中声明的、未嵌套在其它类中的类，可以是[公共](./public.md)或[内部](./internal.md)。</span><span class="sxs-lookup"><span data-stu-id="e84fe-115">Classes that you declare directly within a namespace, not nested within other classes, can be either [public](./public.md) or [internal](./internal.md).</span></span> <span data-ttu-id="e84fe-116">默认情况下类为 `internal`。</span><span class="sxs-lookup"><span data-stu-id="e84fe-116">Classes are `internal` by default.</span></span>

<span data-ttu-id="e84fe-117">类成员（包括嵌套的类）可以是 [public](public.md)、[protected internal](protected-internal.md)、[protected](protected.md)、[internal](internal.md)、[private](private.md) 或 [private protected](private-protected.md)。</span><span class="sxs-lookup"><span data-stu-id="e84fe-117">Class members, including nested classes, can be [public](public.md), [protected internal](protected-internal.md), [protected](protected.md), [internal](internal.md), [private](private.md), or [private protected](private-protected.md).</span></span> <span data-ttu-id="e84fe-118">默认情况下成员为 `private`。</span><span class="sxs-lookup"><span data-stu-id="e84fe-118">Members are `private` by default.</span></span>

<span data-ttu-id="e84fe-119">有关详细信息，请参阅[访问修饰符](../../programming-guide/classes-and-structs/access-modifiers.md)。</span><span class="sxs-lookup"><span data-stu-id="e84fe-119">For more information, see [Access Modifiers](../../programming-guide/classes-and-structs/access-modifiers.md).</span></span>

<span data-ttu-id="e84fe-120">可以声明具有类型参数的泛型类。</span><span class="sxs-lookup"><span data-stu-id="e84fe-120">You can declare generic classes that have type parameters.</span></span> <span data-ttu-id="e84fe-121">有关更多信息，请参见[泛型类](../../programming-guide/generics/generic-classes.md)。</span><span class="sxs-lookup"><span data-stu-id="e84fe-121">For more information, see [Generic Classes](../../programming-guide/generics/generic-classes.md).</span></span>

<span data-ttu-id="e84fe-122">一个类可包含下列成员的声明：</span><span class="sxs-lookup"><span data-stu-id="e84fe-122">A class can contain declarations of the following members:</span></span>

- [<span data-ttu-id="e84fe-123">构造函数</span><span class="sxs-lookup"><span data-stu-id="e84fe-123">Constructors</span></span>](../../programming-guide/classes-and-structs/constructors.md)

- [<span data-ttu-id="e84fe-124">常量</span><span class="sxs-lookup"><span data-stu-id="e84fe-124">Constants</span></span>](../../programming-guide/classes-and-structs/constants.md)

- [<span data-ttu-id="e84fe-125">字段</span><span class="sxs-lookup"><span data-stu-id="e84fe-125">Fields</span></span>](../../programming-guide/classes-and-structs/fields.md)

- [<span data-ttu-id="e84fe-126">终结器</span><span class="sxs-lookup"><span data-stu-id="e84fe-126">Finalizers</span></span>](../../programming-guide/classes-and-structs/destructors.md)

- [<span data-ttu-id="e84fe-127">方法</span><span class="sxs-lookup"><span data-stu-id="e84fe-127">Methods</span></span>](../../programming-guide/classes-and-structs/methods.md)

- [<span data-ttu-id="e84fe-128">属性</span><span class="sxs-lookup"><span data-stu-id="e84fe-128">Properties</span></span>](../../programming-guide/classes-and-structs/properties.md)

- [<span data-ttu-id="e84fe-129">索引器</span><span class="sxs-lookup"><span data-stu-id="e84fe-129">Indexers</span></span>](../../programming-guide/indexers/index.md)

- [<span data-ttu-id="e84fe-130">运算符</span><span class="sxs-lookup"><span data-stu-id="e84fe-130">Operators</span></span>](../operators/index.md)

- [<span data-ttu-id="e84fe-131">事件</span><span class="sxs-lookup"><span data-stu-id="e84fe-131">Events</span></span>](../../programming-guide/events/index.md)

- [<span data-ttu-id="e84fe-132">委托</span><span class="sxs-lookup"><span data-stu-id="e84fe-132">Delegates</span></span>](../../programming-guide/delegates/index.md)

- [<span data-ttu-id="e84fe-133">类</span><span class="sxs-lookup"><span data-stu-id="e84fe-133">Classes</span></span>](../../programming-guide/classes-and-structs/classes.md)

- [<span data-ttu-id="e84fe-134">接口</span><span class="sxs-lookup"><span data-stu-id="e84fe-134">Interfaces</span></span>](../../programming-guide/interfaces/index.md)

- [<span data-ttu-id="e84fe-135">结构类型</span><span class="sxs-lookup"><span data-stu-id="e84fe-135">Structure types</span></span>](../builtin-types/struct.md)

- [<span data-ttu-id="e84fe-136">枚举类型</span><span class="sxs-lookup"><span data-stu-id="e84fe-136">Enumeration types</span></span>](../builtin-types/enum.md)

## <a name="example"></a><span data-ttu-id="e84fe-137">示例</span><span class="sxs-lookup"><span data-stu-id="e84fe-137">Example</span></span>

<span data-ttu-id="e84fe-138">下面的示例说明如何声明类字段、构造函数和方法。</span><span class="sxs-lookup"><span data-stu-id="e84fe-138">The following example demonstrates declaring class fields, constructors, and methods.</span></span> <span data-ttu-id="e84fe-139">该示例还说明如何实例化对象及如何打印实例数据。</span><span class="sxs-lookup"><span data-stu-id="e84fe-139">It also demonstrates object instantiation and printing instance data.</span></span> <span data-ttu-id="e84fe-140">本例声明了两个类。</span><span class="sxs-lookup"><span data-stu-id="e84fe-140">In this example, two classes are declared.</span></span> <span data-ttu-id="e84fe-141">第一个类 `Child` 包含两个私有字段（`name` 和 `age`）、两个公共构造函数和一个公共方法。</span><span class="sxs-lookup"><span data-stu-id="e84fe-141">The first class, `Child`, contains two private fields (`name` and `age`), two public constructors and one public method.</span></span> <span data-ttu-id="e84fe-142">第二个类 `StringTest` 用于包含 `Main`。</span><span class="sxs-lookup"><span data-stu-id="e84fe-142">The second class, `StringTest`, is used to contain `Main`.</span></span>

[!code-csharp[csrefKeywordsTypes#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#5)]

## <a name="comments"></a><span data-ttu-id="e84fe-143">注释</span><span class="sxs-lookup"><span data-stu-id="e84fe-143">Comments</span></span>

<span data-ttu-id="e84fe-144">注意：在上例中，私有字段（`name` 和 `age`）只能通过 `Child` 类的公共方法访问。</span><span class="sxs-lookup"><span data-stu-id="e84fe-144">Notice that in the previous example the private fields (`name` and `age`) can only be accessed through the public method of the `Child` class.</span></span> <span data-ttu-id="e84fe-145">例如，不能在 `Main` 方法中使用如下语句打印 Child 的名称：</span><span class="sxs-lookup"><span data-stu-id="e84fe-145">For example, you cannot print the child's name, from the `Main` method, using a statement like this:</span></span>

```csharp
Console.Write(child1.name);   // Error
```

<span data-ttu-id="e84fe-146">只有当 `Main` 是类的成员时，才能从 `Main` 访问 `Child` 的私有成员。</span><span class="sxs-lookup"><span data-stu-id="e84fe-146">Accessing private members of `Child` from `Main` would only be possible if `Main` were a member of the class.</span></span>

<span data-ttu-id="e84fe-147">类中不具有访问修饰符的已声明类型默认为 `private`，因此如果已删除关键字，则此示例中的数据成员将仍为 `private`。</span><span class="sxs-lookup"><span data-stu-id="e84fe-147">Types declared inside a class without an access modifier default to `private`, so the data members in this example would still be `private` if the keyword were removed.</span></span>

<span data-ttu-id="e84fe-148">最后要注意的是，默认情况下，对于使用无参数构造函数 (`child3`) 创建的对象，`age` 字段初始化为零。</span><span class="sxs-lookup"><span data-stu-id="e84fe-148">Finally, notice that for the object created using the parameterless constructor (`child3`), the `age` field was initialized to zero by default.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="e84fe-149">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="e84fe-149">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="e84fe-150">请参阅</span><span class="sxs-lookup"><span data-stu-id="e84fe-150">See also</span></span>

- [<span data-ttu-id="e84fe-151">C# 参考</span><span class="sxs-lookup"><span data-stu-id="e84fe-151">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="e84fe-152">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="e84fe-152">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="e84fe-153">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="e84fe-153">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="e84fe-154">引用类型</span><span class="sxs-lookup"><span data-stu-id="e84fe-154">Reference Types</span></span>](./reference-types.md)
