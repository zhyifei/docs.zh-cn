---
title: 分部类和方法 - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- partial methods [C#]
- partial classes [C#]
- C# language, partial classes and methods
ms.assetid: 804cecb7-62db-4f97-a99f-60975bd59fa1
ms.openlocfilehash: 0d54101badab297457e8d8ecf277898fc6908779
ms.sourcegitcommit: 859b2ba0c74a1a5a4ad0d59a3c3af23450995981
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/11/2019
ms.locfileid: "59481050"
---
# <a name="partial-classes-and-methods-c-programming-guide"></a><span data-ttu-id="20583-102">分部类和方法（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="20583-102">Partial Classes and Methods (C# Programming Guide)</span></span>

<span data-ttu-id="20583-103">拆分一个[类](../../../csharp/language-reference/keywords/class.md)、一个[结构](../../../csharp/language-reference/keywords/struct.md)、一个[接口](../../../csharp/language-reference/keywords/interface.md)或一个方法的定义到两个或更多的文件中是可能的。</span><span class="sxs-lookup"><span data-stu-id="20583-103">It is possible to split the definition of a [class](../../../csharp/language-reference/keywords/class.md), a [struct](../../../csharp/language-reference/keywords/struct.md), an [interface](../../../csharp/language-reference/keywords/interface.md) or a method over two or more source files.</span></span> <span data-ttu-id="20583-104">每个源文件包含类型或方法定义的一部分，编译应用程序时将把所有部分组合起来。</span><span class="sxs-lookup"><span data-stu-id="20583-104">Each source file contains a section of the type or method definition, and all parts are combined when the application is compiled.</span></span>

## <a name="partial-classes"></a><span data-ttu-id="20583-105">分部类</span><span class="sxs-lookup"><span data-stu-id="20583-105">Partial Classes</span></span>

<span data-ttu-id="20583-106">在以下几种情况下需要拆分类定义：</span><span class="sxs-lookup"><span data-stu-id="20583-106">There are several situations when splitting a class definition is desirable:</span></span>

- <span data-ttu-id="20583-107">处理大型项目时，使一个类分布于多个独立文件中可以让多位程序员同时对该类进行处理。</span><span class="sxs-lookup"><span data-stu-id="20583-107">When working on large projects, spreading a class over separate files enables multiple programmers to work on it at the same time.</span></span>

- <span data-ttu-id="20583-108">当使用自动生成的源文件时，你可以添加代码而不需要重新创建源文件。</span><span class="sxs-lookup"><span data-stu-id="20583-108">When working with automatically generated source, code can be added to the class without having to recreate the source file.</span></span> <span data-ttu-id="20583-109">Visual Studio 在创建Windows 窗体、Web 服务包装器代码等时会使用这种方法。</span><span class="sxs-lookup"><span data-stu-id="20583-109">Visual Studio uses this approach when it creates Windows Forms, Web service wrapper code, and so on.</span></span> <span data-ttu-id="20583-110">你可以创建使用这些类的代码，这样就不需要修改由Visual Studio生成的文件。</span><span class="sxs-lookup"><span data-stu-id="20583-110">You can create code that uses these classes without having to modify the file created by Visual Studio.</span></span>

- <span data-ttu-id="20583-111">若要拆分类定义，请使用 [partial](../../../csharp/language-reference/keywords/partial-type.md) 关键字修饰符，如下所示：</span><span class="sxs-lookup"><span data-stu-id="20583-111">To split a class definition, use the [partial](../../../csharp/language-reference/keywords/partial-type.md) keyword modifier, as shown here:</span></span>

  [!code-csharp[csProgGuideObjects#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#26)]

<span data-ttu-id="20583-112">`partial` 关键字指示可在命名空间中定义该类、结构或接口的其他部分。</span><span class="sxs-lookup"><span data-stu-id="20583-112">The `partial` keyword indicates that other parts of the class, struct, or interface can be defined in the namespace.</span></span> <span data-ttu-id="20583-113">所有部分都必须使用 `partial` 关键字。</span><span class="sxs-lookup"><span data-stu-id="20583-113">All the parts must use the `partial` keyword.</span></span> <span data-ttu-id="20583-114">在编译时，各个部分都必须可用来形成最终的类型。</span><span class="sxs-lookup"><span data-stu-id="20583-114">All the parts must be available at compile time to form the final type.</span></span> <span data-ttu-id="20583-115">各个部分必须具有相同的可访问性，如 `public`、`private` 等。</span><span class="sxs-lookup"><span data-stu-id="20583-115">All the parts must have the same accessibility, such as `public`, `private`, and so on.</span></span>

<span data-ttu-id="20583-116">如果将任意部分声明为抽象的，则整个类型都被视为抽象的。</span><span class="sxs-lookup"><span data-stu-id="20583-116">If any part is declared abstract, then the whole type is considered abstract.</span></span> <span data-ttu-id="20583-117">如果将任意部分声明为密封的，则整个类型都被视为密封的。</span><span class="sxs-lookup"><span data-stu-id="20583-117">If any part is declared sealed, then the whole type is considered sealed.</span></span> <span data-ttu-id="20583-118">如果任意部分声明基类型，则整个类型都将继承该类。</span><span class="sxs-lookup"><span data-stu-id="20583-118">If any part declares a base type, then the whole type inherits that class.</span></span>

<span data-ttu-id="20583-119">指定基类的所有部分必须一致，但忽略基类的部分仍继承该基类型。</span><span class="sxs-lookup"><span data-stu-id="20583-119">All the parts that specify a base class must agree, but parts that omit a base class still inherit the base type.</span></span> <span data-ttu-id="20583-120">各个部分可以指定不同的基接口，最终类型将实现所有分部声明所列出的全部接口。</span><span class="sxs-lookup"><span data-stu-id="20583-120">Parts can specify different base interfaces, and the final type implements all the interfaces listed by all the partial declarations.</span></span> <span data-ttu-id="20583-121">在某一分部定义中声明的任何类、结构或接口成员可供所有其他部分使用。</span><span class="sxs-lookup"><span data-stu-id="20583-121">Any class, struct, or interface members declared in a partial definition are available to all the other parts.</span></span> <span data-ttu-id="20583-122">最终类型是所有部分在编译时的组合。</span><span class="sxs-lookup"><span data-stu-id="20583-122">The final type is the combination of all the parts at compile time.</span></span>

> [!NOTE]
> <span data-ttu-id="20583-123">`partial` 修饰符不可用于委托或枚举声明中。</span><span class="sxs-lookup"><span data-stu-id="20583-123">The `partial` modifier is not available on delegate or enumeration declarations.</span></span>

<span data-ttu-id="20583-124">下面的示例演示嵌套类型可以是分部的，即使它们所嵌套于的类型本身并不是分部的也如此。</span><span class="sxs-lookup"><span data-stu-id="20583-124">The following example shows that nested types can be partial, even if the type they are nested within is not partial itself.</span></span>

[!code-csharp[csProgGuideObjects#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#25)]

<span data-ttu-id="20583-125">编译时会对分部类型定义的属性进行合并。</span><span class="sxs-lookup"><span data-stu-id="20583-125">At compile time, attributes of partial-type definitions are merged.</span></span> <span data-ttu-id="20583-126">以下面的声明为例：</span><span class="sxs-lookup"><span data-stu-id="20583-126">For example, consider the following declarations:</span></span>

[!code-csharp[csProgGuideObjects#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#23)]

<span data-ttu-id="20583-127">它们等效于以下声明：</span><span class="sxs-lookup"><span data-stu-id="20583-127">They are equivalent to the following declarations:</span></span>

[!code-csharp[csProgGuideObjects#24](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#24)]

<span data-ttu-id="20583-128">将从所有分部类型定义中对以下内容进行合并：</span><span class="sxs-lookup"><span data-stu-id="20583-128">The following are merged from all the partial-type definitions:</span></span>

- <span data-ttu-id="20583-129">XML 注释</span><span class="sxs-lookup"><span data-stu-id="20583-129">XML comments</span></span>

- <span data-ttu-id="20583-130">接口</span><span class="sxs-lookup"><span data-stu-id="20583-130">interfaces</span></span>

- <span data-ttu-id="20583-131">泛型类型参数属性</span><span class="sxs-lookup"><span data-stu-id="20583-131">generic-type parameter attributes</span></span>

- <span data-ttu-id="20583-132">class 特性</span><span class="sxs-lookup"><span data-stu-id="20583-132">class attributes</span></span>

- <span data-ttu-id="20583-133">成员</span><span class="sxs-lookup"><span data-stu-id="20583-133">members</span></span>

<span data-ttu-id="20583-134">以下面的声明为例：</span><span class="sxs-lookup"><span data-stu-id="20583-134">For example, consider the following declarations:</span></span>

[!code-csharp[csProgGuideObjects#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#21)]

<span data-ttu-id="20583-135">它们等效于以下声明：</span><span class="sxs-lookup"><span data-stu-id="20583-135">They are equivalent to the following declarations:</span></span>

[!code-csharp[csProgGuideObjects#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#22)]

### <a name="restrictions"></a><span data-ttu-id="20583-136">限制</span><span class="sxs-lookup"><span data-stu-id="20583-136">Restrictions</span></span>

<span data-ttu-id="20583-137">处理分部类定义时需遵循下面的几个规则：</span><span class="sxs-lookup"><span data-stu-id="20583-137">There are several rules to follow when you are working with partial class definitions:</span></span>

- <span data-ttu-id="20583-138">要作为同一类型的各个部分的所有分部类型定义都必须使用 `partial` 进行修饰。</span><span class="sxs-lookup"><span data-stu-id="20583-138">All partial-type definitions meant to be parts of the same type must be modified with `partial`.</span></span> <span data-ttu-id="20583-139">例如，下面的类声明会生成错误：</span><span class="sxs-lookup"><span data-stu-id="20583-139">For example, the following class declarations generate an error:</span></span>

  [!code-csharp[csProgGuideObjects#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#20)]

- <span data-ttu-id="20583-140">`partial` 修饰符只能出现在紧靠关键字 `class`、`struct` 或 `interface` 前面的位置。</span><span class="sxs-lookup"><span data-stu-id="20583-140">The `partial` modifier can only appear immediately before the keywords `class`, `struct`, or `interface`.</span></span>

- <span data-ttu-id="20583-141">分部类型定义中允许使用嵌套的分部类型，如下面的示例中所示：</span><span class="sxs-lookup"><span data-stu-id="20583-141">Nested partial types are allowed in partial-type definitions as illustrated in the following example:</span></span>

  [!code-csharp[csProgGuideObjects#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#19)]

- <span data-ttu-id="20583-142">要成为同一类型的各个部分的所有分部类型定义都必须在同一程序集和同一模块（.exe 或 .dll 文件）中进行定义。</span><span class="sxs-lookup"><span data-stu-id="20583-142">All partial-type definitions meant to be parts of the same type must be defined in the same assembly and the same module (.exe or .dll file).</span></span> <span data-ttu-id="20583-143">分部定义不能跨越多个模块。</span><span class="sxs-lookup"><span data-stu-id="20583-143">Partial definitions cannot span multiple modules.</span></span>

- <span data-ttu-id="20583-144">类名和泛型类型参数在所有的分部类型定义中都必须匹配。</span><span class="sxs-lookup"><span data-stu-id="20583-144">The class name and generic-type parameters must match on all partial-type definitions.</span></span> <span data-ttu-id="20583-145">泛型类型可以是分部的。</span><span class="sxs-lookup"><span data-stu-id="20583-145">Generic types can be partial.</span></span> <span data-ttu-id="20583-146">每个分部声明都必须以相同的顺序使用相同的参数名。</span><span class="sxs-lookup"><span data-stu-id="20583-146">Each partial declaration must use the same parameter names in the same order.</span></span>

- <span data-ttu-id="20583-147">下面用于分部类型定义中的关键字是可选的，但是如果某关键字出现在一个分部类型定义中，则该关键字不能与在同一类型的其他分部定义中指定的关键字冲突：</span><span class="sxs-lookup"><span data-stu-id="20583-147">The following keywords on a partial-type definition are optional, but if present on one partial-type definition, cannot conflict with the keywords specified on another partial definition for the same type:</span></span>

  - [<span data-ttu-id="20583-148">public</span><span class="sxs-lookup"><span data-stu-id="20583-148">public</span></span>](../../../csharp/language-reference/keywords/public.md)

  - [<span data-ttu-id="20583-149">private</span><span class="sxs-lookup"><span data-stu-id="20583-149">private</span></span>](../../../csharp/language-reference/keywords/private.md)

  - [<span data-ttu-id="20583-150">protected</span><span class="sxs-lookup"><span data-stu-id="20583-150">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)

  - [<span data-ttu-id="20583-151">internal</span><span class="sxs-lookup"><span data-stu-id="20583-151">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)

  - [<span data-ttu-id="20583-152">abstract</span><span class="sxs-lookup"><span data-stu-id="20583-152">abstract</span></span>](../../../csharp/language-reference/keywords/abstract.md)

  - [<span data-ttu-id="20583-153">sealed</span><span class="sxs-lookup"><span data-stu-id="20583-153">sealed</span></span>](../../../csharp/language-reference/keywords/sealed.md)

  - <span data-ttu-id="20583-154">基类</span><span class="sxs-lookup"><span data-stu-id="20583-154">base class</span></span>

  - <span data-ttu-id="20583-155">[new](../../../csharp/language-reference/keywords/new.md) 修饰符（嵌套部分）</span><span class="sxs-lookup"><span data-stu-id="20583-155">[new](../../../csharp/language-reference/keywords/new.md) modifier (nested parts)</span></span>

  - <span data-ttu-id="20583-156">泛型约束</span><span class="sxs-lookup"><span data-stu-id="20583-156">generic constraints</span></span>

<span data-ttu-id="20583-157">有关详细信息，请参阅[类型参数的约束](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)。</span><span class="sxs-lookup"><span data-stu-id="20583-157">For more information, see [Constraints on Type Parameters](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md).</span></span>

## <a name="example-1"></a><span data-ttu-id="20583-158">示例 1</span><span class="sxs-lookup"><span data-stu-id="20583-158">Example 1</span></span>

### <a name="description"></a><span data-ttu-id="20583-159">说明</span><span class="sxs-lookup"><span data-stu-id="20583-159">Description</span></span>

<span data-ttu-id="20583-160">下面的示例在一个分部类定义中声明 `Coords` 类的字段和构造函数，在另一个分部类定义中声明成员 `PrintCoords`。</span><span class="sxs-lookup"><span data-stu-id="20583-160">In the following example, the fields and the constructor of the class, `Coords`, are declared in one partial class definition, and the member, `PrintCoords`, is declared in another partial class definition.</span></span>

### <a name="code"></a><span data-ttu-id="20583-161">代码</span><span class="sxs-lookup"><span data-stu-id="20583-161">Code</span></span>

[!code-csharp[csProgGuideObjects#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#17)]

## <a name="example-2"></a><span data-ttu-id="20583-162">示例 2</span><span class="sxs-lookup"><span data-stu-id="20583-162">Example 2</span></span>

### <a name="description"></a><span data-ttu-id="20583-163">说明</span><span class="sxs-lookup"><span data-stu-id="20583-163">Description</span></span>

<span data-ttu-id="20583-164">从下面的示例可以看出，你也可以开发分部结构和接口。</span><span class="sxs-lookup"><span data-stu-id="20583-164">The following example shows that you can also develop partial structs and interfaces.</span></span>

### <a name="code"></a><span data-ttu-id="20583-165">代码</span><span class="sxs-lookup"><span data-stu-id="20583-165">Code</span></span>

[!code-csharp[csProgGuideObjects#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#18)]

## <a name="partial-methods"></a><span data-ttu-id="20583-166">分部方法</span><span class="sxs-lookup"><span data-stu-id="20583-166">Partial Methods</span></span>

<span data-ttu-id="20583-167">分部类或结构可以包含分部方法。</span><span class="sxs-lookup"><span data-stu-id="20583-167">A partial class or struct may contain a partial method.</span></span> <span data-ttu-id="20583-168">类的一个部分包含方法的签名。</span><span class="sxs-lookup"><span data-stu-id="20583-168">One part of the class contains the signature of the method.</span></span> <span data-ttu-id="20583-169">可以在同一部分或另一个部分中定义可选实现。</span><span class="sxs-lookup"><span data-stu-id="20583-169">An optional implementation may be defined in the same part or another part.</span></span> <span data-ttu-id="20583-170">如果未提供该实现，则会在编译时删除方法以及对方法的所有调用。</span><span class="sxs-lookup"><span data-stu-id="20583-170">If the implementation is not supplied, then the method and all calls to the method are removed at compile time.</span></span>

<span data-ttu-id="20583-171">分部方法使类的某个部分的实施者能够定义方法（类似于事件）。</span><span class="sxs-lookup"><span data-stu-id="20583-171">Partial methods enable the implementer of one part of a class to define a method, similar to an event.</span></span> <span data-ttu-id="20583-172">类的另一部分的实施者可以决定是否实现该方法。</span><span class="sxs-lookup"><span data-stu-id="20583-172">The implementer of the other part of the class can decide whether to implement the method or not.</span></span> <span data-ttu-id="20583-173">如果未实现该方法，编译器会删除方法签名以及对该方法的所有调用。</span><span class="sxs-lookup"><span data-stu-id="20583-173">If the method is not implemented, then the compiler removes the method signature and all calls to the method.</span></span> <span data-ttu-id="20583-174">调用该方法（包括调用中的任何参数计算结果）在运行时没有任何影响。</span><span class="sxs-lookup"><span data-stu-id="20583-174">The calls to the method, including any results that would occur from evaluation of arguments in the calls, have no effect at run time.</span></span> <span data-ttu-id="20583-175">因此，分部类中的任何代码都可以随意地使用分部方法，即使未提供实现也是如此。</span><span class="sxs-lookup"><span data-stu-id="20583-175">Therefore, any code in the partial class can freely use a partial method, even if the implementation is not supplied.</span></span> <span data-ttu-id="20583-176">调用但不实现该方法不会导致编译时错误或运行时错误。</span><span class="sxs-lookup"><span data-stu-id="20583-176">No compile-time or run-time errors will result if the method is called but not implemented.</span></span>

<span data-ttu-id="20583-177">在自定义生成的代码时，分部方法特别有用。</span><span class="sxs-lookup"><span data-stu-id="20583-177">Partial methods are especially useful as a way to customize generated code.</span></span> <span data-ttu-id="20583-178">这些方法允许保留方法名称和签名，因此生成的代码可以调用方法，而开发人员可以决定是否实现方法。</span><span class="sxs-lookup"><span data-stu-id="20583-178">They allow for a method name and signature to be reserved, so that generated code can call the method but the developer can decide whether to implement the method.</span></span> <span data-ttu-id="20583-179">与分部类非常类似，分部方法使代码生成器创建的代码和开发人员创建的代码能够协同工作，而不会产生运行时开销。</span><span class="sxs-lookup"><span data-stu-id="20583-179">Much like partial classes, partial methods enable code created by a code generator and code created by a human developer to work together without run-time costs.</span></span>

<span data-ttu-id="20583-180">分部方法声明由两个部分组成：定义和实现。</span><span class="sxs-lookup"><span data-stu-id="20583-180">A partial method declaration consists of two parts: the definition, and the implementation.</span></span> <span data-ttu-id="20583-181">它们可以位于分部类的不同部分中，也可以位于同一部分中。</span><span class="sxs-lookup"><span data-stu-id="20583-181">These may be in separate parts of a partial class, or in the same part.</span></span> <span data-ttu-id="20583-182">如果不存在实现声明，则编译器会优化定义声明和对方法的所有调用。</span><span class="sxs-lookup"><span data-stu-id="20583-182">If there is no implementation declaration, then the compiler optimizes away both the defining declaration and all calls to the method.</span></span>

```csharp
// Definition in file1.cs
partial void onNameChanged();

// Implementation in file2.cs
partial void onNameChanged()
{
  // method body
}
```

- <span data-ttu-id="20583-183">分部方法声明必须以上下文关键字 [partial](../../../csharp/language-reference/keywords/partial-type.md) 开头，并且方法必须返回 [void](../../../csharp/language-reference/keywords/void.md)。</span><span class="sxs-lookup"><span data-stu-id="20583-183">Partial method declarations must begin with the contextual keyword [partial](../../../csharp/language-reference/keywords/partial-type.md) and the method must return [void](../../../csharp/language-reference/keywords/void.md).</span></span>

- <span data-ttu-id="20583-184">分部方法可以有 [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md) 或 [ref](../../../csharp/language-reference/keywords/ref.md) 参数，但不能有 [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) 参数。</span><span class="sxs-lookup"><span data-stu-id="20583-184">Partial methods can have [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md) or [ref](../../../csharp/language-reference/keywords/ref.md) but not [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) parameters.</span></span>

- <span data-ttu-id="20583-185">分部方法为隐式 [private](../../../csharp/language-reference/keywords/private.md) 方法，因此不能为 [virtual](../../../csharp/language-reference/keywords/virtual.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="20583-185">Partial methods are implicitly [private](../../../csharp/language-reference/keywords/private.md), and therefore they cannot be [virtual](../../../csharp/language-reference/keywords/virtual.md).</span></span>

- <span data-ttu-id="20583-186">分部方法不能为 [extern](../../../csharp/language-reference/keywords/extern.md) 方法，因为主体的存在确定了方法是在定义还是在实现。</span><span class="sxs-lookup"><span data-stu-id="20583-186">Partial methods cannot be [extern](../../../csharp/language-reference/keywords/extern.md), because the presence of the body determines whether they are defining or implementing.</span></span>

- <span data-ttu-id="20583-187">分部方法可以有 [static](../../../csharp/language-reference/keywords/static.md) 和 [unsafe](../../../csharp/language-reference/keywords/unsafe.md) 修饰符。</span><span class="sxs-lookup"><span data-stu-id="20583-187">Partial methods can have [static](../../../csharp/language-reference/keywords/static.md) and [unsafe](../../../csharp/language-reference/keywords/unsafe.md) modifiers.</span></span>

- <span data-ttu-id="20583-188">分部方法可以是泛型的。</span><span class="sxs-lookup"><span data-stu-id="20583-188">Partial methods can be generic.</span></span> <span data-ttu-id="20583-189">约束将放在定义分部方法声明上，但也可以选择重复放在实现声明上。</span><span class="sxs-lookup"><span data-stu-id="20583-189">Constraints are put on the defining partial method declaration, and may optionally be repeated on the implementing one.</span></span> <span data-ttu-id="20583-190">参数和类型参数名称在实现声明和定义声明中不必相同。</span><span class="sxs-lookup"><span data-stu-id="20583-190">Parameter and type parameter names do not have to be the same in the implementing declaration as in the defining one.</span></span>

- <span data-ttu-id="20583-191">你可以为已定义并实现的分部方法生成[委托](../../../csharp/language-reference/keywords/delegate.md)，但不能为已经定义但未实现的分部方法生成委托。</span><span class="sxs-lookup"><span data-stu-id="20583-191">You can make a [delegate](../../../csharp/language-reference/keywords/delegate.md) to a partial method that has been defined and implemented, but not to a partial method that has only been defined.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="20583-192">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="20583-192">C# Language Specification</span></span>

<span data-ttu-id="20583-193">有关详细信息，请参阅 [C# 语言规范](../../language-reference/language-specification/index.md)中的[分部类型](~/_csharplang/spec/classes.md#partial-types)。</span><span class="sxs-lookup"><span data-stu-id="20583-193">For more information, see [Partial types](~/_csharplang/spec/classes.md#partial-types) in the [C# Language Specification](../../language-reference/language-specification/index.md).</span></span> <span data-ttu-id="20583-194">该语言规范是 C# 语法和用法的权威资料。</span><span class="sxs-lookup"><span data-stu-id="20583-194">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="20583-195">请参阅</span><span class="sxs-lookup"><span data-stu-id="20583-195">See also</span></span>

- [<span data-ttu-id="20583-196">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="20583-196">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="20583-197">类</span><span class="sxs-lookup"><span data-stu-id="20583-197">Classes</span></span>](../../../csharp/programming-guide/classes-and-structs/classes.md)
- [<span data-ttu-id="20583-198">结构</span><span class="sxs-lookup"><span data-stu-id="20583-198">Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/structs.md)
- [<span data-ttu-id="20583-199">接口</span><span class="sxs-lookup"><span data-stu-id="20583-199">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)
- [<span data-ttu-id="20583-200">partial（类型）</span><span class="sxs-lookup"><span data-stu-id="20583-200">partial (Type)</span></span>](../../../csharp/language-reference/keywords/partial-type.md)
