---
title: "元组 (F#)"
description: "了解有关 F # 元组的未命名，但有序值，可能具有不同的类型的组。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 35069073-9a82-410f-8dea-912e2a152e6d
ms.openlocfilehash: 996566f2baaea8ab01e5c80e53caea82e9684714
ms.sourcegitcommit: d95a91d685565f4d95c8773b558752864a6a3d7e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2018
---
# <a name="tuples"></a><span data-ttu-id="00ad9-104">元组</span><span class="sxs-lookup"><span data-stu-id="00ad9-104">Tuples</span></span>

<span data-ttu-id="00ad9-105">A*元组*是未命名但有序值，可能具有不同的类型的分组。</span><span class="sxs-lookup"><span data-stu-id="00ad9-105">A *tuple* is a grouping of unnamed but ordered values, possibly of different types.</span></span>  <span data-ttu-id="00ad9-106">元组可以是引用类型或结构。</span><span class="sxs-lookup"><span data-stu-id="00ad9-106">Tuples can either be reference types or structs.</span></span>

## <a name="syntax"></a><span data-ttu-id="00ad9-107">语法</span><span class="sxs-lookup"><span data-stu-id="00ad9-107">Syntax</span></span>

```fsharp
(element, ... , element)
struct(element, ... ,element )
```
## <a name="remarks"></a><span data-ttu-id="00ad9-108">备注</span><span class="sxs-lookup"><span data-stu-id="00ad9-108">Remarks</span></span>
<span data-ttu-id="00ad9-109">每个*元素*在上述语法中可以是任何有效的 F # 表达式。</span><span class="sxs-lookup"><span data-stu-id="00ad9-109">Each *element* in the previous syntax can be any valid F# expression.</span></span>

## <a name="examples"></a><span data-ttu-id="00ad9-110">示例</span><span class="sxs-lookup"><span data-stu-id="00ad9-110">Examples</span></span>
<span data-ttu-id="00ad9-111">元组的示例包括对、 三元组和等等的相同或不同类型。</span><span class="sxs-lookup"><span data-stu-id="00ad9-111">Examples of tuples include pairs, triples, and so on, of the same or different types.</span></span> <span data-ttu-id="00ad9-112">在下面的代码阐释了一些示例。</span><span class="sxs-lookup"><span data-stu-id="00ad9-112">Some examples are illustrated in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L6-L21)]
    
## <a name="obtaining-individual-values"></a><span data-ttu-id="00ad9-113">获取单个值</span><span class="sxs-lookup"><span data-stu-id="00ad9-113">Obtaining Individual Values</span></span>
<span data-ttu-id="00ad9-114">你可以使用模式匹配来访问和分配名称对于元组元素，如下面的代码中所示。</span><span class="sxs-lookup"><span data-stu-id="00ad9-114">You can use pattern matching to access and assign names for tuple elements, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L27-L29)]

<span data-ttu-id="00ad9-115">你还可以解构通过外部的模式匹配的元组`match`通过表达式`let`绑定：</span><span class="sxs-lookup"><span data-stu-id="00ad9-115">You can also deconstruct a tuple via pattern matching outside of a `match` expression via  `let` binding:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L34-L37)]

<span data-ttu-id="00ad9-116">可以模式或作为函数的输入匹配的元组：</span><span class="sxs-lookup"><span data-stu-id="00ad9-116">Or you can pattern match on tuples as inputs to functions:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L43-L47)]

<span data-ttu-id="00ad9-117">如果你需要此元组仅有一个元素，可以使用通配符字符 （下划线），以避免创建一个值，不需要的新名称。</span><span class="sxs-lookup"><span data-stu-id="00ad9-117">If you need only one element of the tuple, the wildcard character (the underscore) can be used to avoid creating a new name for a value that you do not need.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L53-L54)]

<span data-ttu-id="00ad9-118">将引用元组中的元素复制到结构元组也非常简单：</span><span class="sxs-lookup"><span data-stu-id="00ad9-118">Copying elements from a reference tuple into a struct tuple is also simple:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L62-L66)]

<span data-ttu-id="00ad9-119">函数`fst`和`snd`（引用元组仅） 返回第一个和第二个元素的一个元组，将分别。</span><span class="sxs-lookup"><span data-stu-id="00ad9-119">The functions `fst` and `snd` (reference tuples only) return the first and second elements of a tuple, respectively.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L72-L73)]

<span data-ttu-id="00ad9-120">没有内置函数，它返回第三个元素的三元组，但你可以轻松地编写一个，如下所示。</span><span class="sxs-lookup"><span data-stu-id="00ad9-120">There is no built-in function that returns the third element of a triple, but you can easily write one as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L78-L78)]

<span data-ttu-id="00ad9-121">通常，最好使用模式匹配来访问各个元组元素。</span><span class="sxs-lookup"><span data-stu-id="00ad9-121">Generally, it is better to use pattern matching to access individual tuple elements.</span></span>

## <a name="using-tuples"></a><span data-ttu-id="00ad9-122">使用元组</span><span class="sxs-lookup"><span data-stu-id="00ad9-122">Using Tuples</span></span>
<span data-ttu-id="00ad9-123">元组提供一种简便方式从函数返回多个值，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="00ad9-123">Tuples provide a convenient way to return multiple values from a function, as shown in the following example.</span></span> <span data-ttu-id="00ad9-124">此示例对执行整数除法运算并返回的元组对的第一个成员操作，作为对的第二个成员的其余部分舍入的结果。</span><span class="sxs-lookup"><span data-stu-id="00ad9-124">This example performs integer division and returns the rounded result of the operation as a first member of a tuple pair and the remainder as a second member of the pair.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L83-L86)]

<span data-ttu-id="00ad9-125">元组也可用作函数自变量用在你想要避免通过常用函数语法隐式的函数自变量的隐式扩充时。</span><span class="sxs-lookup"><span data-stu-id="00ad9-125">Tuples can also be used as function arguments when you want to avoid the implicit currying of function arguments that is implied by the usual function syntax.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L88-L88)]

<span data-ttu-id="00ad9-126">用于定义函数的常见语法`let sum a b = a + b`可以定义一个函数，则部分应用函数的第一个参数，如下面的代码中所示。</span><span class="sxs-lookup"><span data-stu-id="00ad9-126">The usual syntax for defining the function `let sum a b = a + b` enables you to define a function that is the partial application of the first argument of the function, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L90-L94)]

<span data-ttu-id="00ad9-127">作为参数使用一个元组，将禁用扩充。</span><span class="sxs-lookup"><span data-stu-id="00ad9-127">Using a tuple as the parameter disables currying.</span></span> <span data-ttu-id="00ad9-128">有关详细信息，请参阅"部分应用程序的自变量"[函数](functions/index.md)。</span><span class="sxs-lookup"><span data-stu-id="00ad9-128">For more information, see "Partial Application of Arguments" in [Functions](functions/index.md).</span></span>

## <a name="names-of-tuple-types"></a><span data-ttu-id="00ad9-129">元组类型的名称</span><span class="sxs-lookup"><span data-stu-id="00ad9-129">Names of Tuple Types</span></span>
<span data-ttu-id="00ad9-130">在写出的类型是一个元组的名称时，你使用`*`符号来分隔元素。</span><span class="sxs-lookup"><span data-stu-id="00ad9-130">When you write out the name of a type that is a tuple, you use the `*` symbol to separate elements.</span></span> <span data-ttu-id="00ad9-131">Tuple 组成`int`、 `float`，和一个`string`，如`(10, 10.0, "ten")`，类型，则会写入，如下所示。</span><span class="sxs-lookup"><span data-stu-id="00ad9-131">For a tuple that consists of an `int`, a `float`, and a `string`, such as `(10, 10.0, "ten")`, the type would be written as follows.</span></span>

```fsharp
int * float * string
```

## <a name="interoperation-with-c-tuples"></a><span data-ttu-id="00ad9-132">与 C# 元组间的互操作</span><span class="sxs-lookup"><span data-stu-id="00ad9-132">Interoperation with C# Tuples</span></span>

<span data-ttu-id="00ad9-133">C# 7 引入语言的元组。</span><span class="sxs-lookup"><span data-stu-id="00ad9-133">C# 7 introduced tuples to the language.</span></span>  <span data-ttu-id="00ad9-134">在 C# 中的元组是结构，并且等效于在 F # 中的结构元组。</span><span class="sxs-lookup"><span data-stu-id="00ad9-134">Tuples in C# are structs, and are equivalent to struct tuples in F#.</span></span>  <span data-ttu-id="00ad9-135">如果你需要与 C# 进行互操作，你必须使用结构元组。</span><span class="sxs-lookup"><span data-stu-id="00ad9-135">If you need to interoperate with C#, you must use struct tuples.</span></span>

<span data-ttu-id="00ad9-136">这是很简单的操作。</span><span class="sxs-lookup"><span data-stu-id="00ad9-136">This is easy to do.</span></span>  <span data-ttu-id="00ad9-137">例如，假设你需要将元组传递给 C# 类并随后使用其结果，也是一个元组：</span><span class="sxs-lookup"><span data-stu-id="00ad9-137">For example, imagine you have to pass a tuple to a C# class and then consume its result, which is also a tuple:</span></span>

```csharp
namespace CSharpTupleInterop
{
    public static class Example
    {
        public static (int, int) AddOneToXAndY((int x, int y) a) =>
            (a.x + 1, a.y + 1);
    }
}
```

<span data-ttu-id="00ad9-138">在 F # 代码中，然后可以将作为参数传递结构元组并使用结构的元组形式的结果。</span><span class="sxs-lookup"><span data-stu-id="00ad9-138">In your F# code, you can then pass a struct tuple as the parameter and consume the result as a struct tuple.</span></span>

```fsharp
open TupleInterop

let struct (newX, newY) = Example.AddOneToXAndY(struct (1, 2))
// newX is now 2, and newY is now 3
```

### <a name="converting-between-reference-tuples-and-struct-tuples"></a><span data-ttu-id="00ad9-139">引用的元组和结构元组之间进行转换</span><span class="sxs-lookup"><span data-stu-id="00ad9-139">Converting between Reference Tuples and Struct Tuples</span></span>

<span data-ttu-id="00ad9-140">引用的元组和结构元组具有完全不同的基础表示形式，因为它们不是隐式转换。</span><span class="sxs-lookup"><span data-stu-id="00ad9-140">Because Reference Tuples and Struct Tuples have a completely different underlying representation, they are not implicitly convertible.</span></span>  <span data-ttu-id="00ad9-141">也就是说，如下所示的代码不会编译：</span><span class="sxs-lookup"><span data-stu-id="00ad9-141">That is, code such as the following won't compile:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/interop.fsx#L5-L12)]

<span data-ttu-id="00ad9-142">必须模式匹配上一个元组，并构造另一种具有构成部分。</span><span class="sxs-lookup"><span data-stu-id="00ad9-142">You must pattern match on one tuple and construct the other with the constituent parts.</span></span>  <span data-ttu-id="00ad9-143">例如:</span><span class="sxs-lookup"><span data-stu-id="00ad9-143">For example:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/interop.fsx#L18-L22)]

## <a name="compiled-form-of-reference-tuples"></a><span data-ttu-id="00ad9-144">引用的元组的已编译的形式</span><span class="sxs-lookup"><span data-stu-id="00ad9-144">Compiled Form of Reference Tuples</span></span>
<span data-ttu-id="00ad9-145">它们在编译时，本部分说明元组的形式。</span><span class="sxs-lookup"><span data-stu-id="00ad9-145">This section explains the form of tuples when they're compiled.</span></span>  <span data-ttu-id="00ad9-146">此处的信息不需要读取除非面向.NET Framework 3.5 或更低。</span><span class="sxs-lookup"><span data-stu-id="00ad9-146">The information here isn't necessary to read unless you are targeting .NET Framework 3.5 or lower.</span></span>

<span data-ttu-id="00ad9-147">元组被编译到的多个泛型类型之一，所有已命名的对象`System.Tuple`，该重载 arity 或数目的类型参数上。</span><span class="sxs-lookup"><span data-stu-id="00ad9-147">Tuples are compiled into objects of one of several generic types, all named `System.Tuple`, that are overloaded on the arity, or number of type parameters.</span></span> <span data-ttu-id="00ad9-148">当你从另一种语言，如 C# 或 Visual Basic 中，查看它们，或使用一种工具，不知道的 F # 构造时，元组类型出现在此窗体。</span><span class="sxs-lookup"><span data-stu-id="00ad9-148">Tuple types appear in this form when you view them from another language, such as C# or Visual Basic, or when you are using a tool that is not aware of F# constructs.</span></span> <span data-ttu-id="00ad9-149">`Tuple`类型在.NET Framework 4 中引入。</span><span class="sxs-lookup"><span data-stu-id="00ad9-149">The `Tuple` types were introduced in .NET Framework 4.</span></span> <span data-ttu-id="00ad9-150">如果你面向的.NET Framework 的早期版本，则编译器将使用的版本[System.Tuple](https://msdn.microsoft.com/library/5ac7953d-acdc-4a58-bfb7-c1f6406c0fa3)从 2.0 的 F # 核心库版本。</span><span class="sxs-lookup"><span data-stu-id="00ad9-150">If you are targeting an earlier version of the .NET Framework, the compiler uses versions of [System.Tuple](https://msdn.microsoft.com/library/5ac7953d-acdc-4a58-bfb7-c1f6406c0fa3) from the 2.0 version of the F# Core Library.</span></span> <span data-ttu-id="00ad9-151">此库中的类型仅用于面向 2.0、 3.0 和 3.5 版本的.NET Framework 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="00ad9-151">The types in this library are used only for applications that target the 2.0, 3.0, and 3.5 versions of the .NET Framework.</span></span> <span data-ttu-id="00ad9-152">类型转发用于确保.NET Framework 2.0 和.NET Framework 4 F # 组件之间的二进制兼容性。</span><span class="sxs-lookup"><span data-stu-id="00ad9-152">Type forwarding is used to ensure binary compatibility between .NET Framework 2.0 and .NET Framework 4 F# components.</span></span>

### <a name="compiled-form-of-struct-tuples"></a><span data-ttu-id="00ad9-153">结构元组的已编译的形式</span><span class="sxs-lookup"><span data-stu-id="00ad9-153">Compiled Form of Struct Tuples</span></span>

<span data-ttu-id="00ad9-154">结构元组 (例如， `struct (x, y)`)，从根本上不同于引用元组。</span><span class="sxs-lookup"><span data-stu-id="00ad9-154">Struct tuples (for example, `struct (x, y)`), are fundamentally different from reference tuples.</span></span>  <span data-ttu-id="00ad9-155">编译为<xref:System.ValueTuple>arity 或类型参数的数目的重载的类型。</span><span class="sxs-lookup"><span data-stu-id="00ad9-155">They are compiled into the <xref:System.ValueTuple> type, overloaded by arity, or the number of type parameters.</span></span>  <span data-ttu-id="00ad9-156">它们是等效于[C# 7 元组](../../csharp/tuples.md)和[Visual Basic 自 2017 年 1 元组](../../visual-basic/programming-guide/language-features/data-types/tuples.md)，又能交互双向。</span><span class="sxs-lookup"><span data-stu-id="00ad9-156">They are equivalent to [C# 7 Tuples](../../csharp/tuples.md) and [Visual Basic 2017 Tuples](../../visual-basic/programming-guide/language-features/data-types/tuples.md), and interoperate bidirectionally.</span></span>

## <a name="see-also"></a><span data-ttu-id="00ad9-157">请参阅</span><span class="sxs-lookup"><span data-stu-id="00ad9-157">See Also</span></span>
[<span data-ttu-id="00ad9-158">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="00ad9-158">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="00ad9-159">F# 类型</span><span class="sxs-lookup"><span data-stu-id="00ad9-159">F# Types</span></span>](fsharp-types.md)
