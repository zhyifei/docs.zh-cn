---
title: 元组 (F#)
description: '了解有关 F # 元组，可能是不同类型的未命名但有序值的分组信息。'
ms.date: 05/16/2016
ms.openlocfilehash: e7628e4c4b538c2fe52fca25d2597b10fec28d1c
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "43749218"
---
# <a name="tuples"></a><span data-ttu-id="fdd02-103">元组</span><span class="sxs-lookup"><span data-stu-id="fdd02-103">Tuples</span></span>

<span data-ttu-id="fdd02-104">一个*元组*是不同类型的可能是未命名但有序值的分组。</span><span class="sxs-lookup"><span data-stu-id="fdd02-104">A *tuple* is a grouping of unnamed but ordered values, possibly of different types.</span></span>  <span data-ttu-id="fdd02-105">元组可以是引用类型或结构。</span><span class="sxs-lookup"><span data-stu-id="fdd02-105">Tuples can either be reference types or structs.</span></span>

## <a name="syntax"></a><span data-ttu-id="fdd02-106">语法</span><span class="sxs-lookup"><span data-stu-id="fdd02-106">Syntax</span></span>

```fsharp
(element, ... , element)
struct(element, ... ,element )
```

## <a name="remarks"></a><span data-ttu-id="fdd02-107">备注</span><span class="sxs-lookup"><span data-stu-id="fdd02-107">Remarks</span></span>

<span data-ttu-id="fdd02-108">每个*元素*在上述语法中可以是任何有效的 F # 表达式。</span><span class="sxs-lookup"><span data-stu-id="fdd02-108">Each *element* in the previous syntax can be any valid F# expression.</span></span>

## <a name="examples"></a><span data-ttu-id="fdd02-109">示例</span><span class="sxs-lookup"><span data-stu-id="fdd02-109">Examples</span></span>

<span data-ttu-id="fdd02-110">元组的示例包括对、 三元组和等等的相同或不同类型。</span><span class="sxs-lookup"><span data-stu-id="fdd02-110">Examples of tuples include pairs, triples, and so on, of the same or different types.</span></span> <span data-ttu-id="fdd02-111">在下面的代码阐释了一些示例。</span><span class="sxs-lookup"><span data-stu-id="fdd02-111">Some examples are illustrated in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L6-L21)]

## <a name="obtaining-individual-values"></a><span data-ttu-id="fdd02-112">获取单个值</span><span class="sxs-lookup"><span data-stu-id="fdd02-112">Obtaining Individual Values</span></span>

<span data-ttu-id="fdd02-113">可用于模式匹配访问和分配名称的元组元素，如下面的代码中所示。</span><span class="sxs-lookup"><span data-stu-id="fdd02-113">You can use pattern matching to access and assign names for tuple elements, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L27-L29)]

<span data-ttu-id="fdd02-114">此外可以通过模式匹配外部的元组析构`match`通过表达式`let`绑定：</span><span class="sxs-lookup"><span data-stu-id="fdd02-114">You can also deconstruct a tuple via pattern matching outside of a `match` expression via  `let` binding:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L34-L37)]

<span data-ttu-id="fdd02-115">或可以模式作为函数的输入匹配的元组：</span><span class="sxs-lookup"><span data-stu-id="fdd02-115">Or you can pattern match on tuples as inputs to functions:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L43-L47)]

<span data-ttu-id="fdd02-116">如果您需要的元组只有一个元素，可以使用通配符字符 （下划线） 以避免创建不需要值的新名称。</span><span class="sxs-lookup"><span data-stu-id="fdd02-116">If you need only one element of the tuple, the wildcard character (the underscore) can be used to avoid creating a new name for a value that you do not need.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L53-L54)]

<span data-ttu-id="fdd02-117">将引用元组中的元素复制到结构元组也很简单：</span><span class="sxs-lookup"><span data-stu-id="fdd02-117">Copying elements from a reference tuple into a struct tuple is also simple:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L62-L66)]

<span data-ttu-id="fdd02-118">函数`fst`和`snd`（引用仅元组） 返回第一个和第二个元素元组，分别。</span><span class="sxs-lookup"><span data-stu-id="fdd02-118">The functions `fst` and `snd` (reference tuples only) return the first and second elements of a tuple, respectively.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L72-L73)]

<span data-ttu-id="fdd02-119">返回构成三元组的第三个元素没有内置函数，但可轻松编写一个，如下所示。</span><span class="sxs-lookup"><span data-stu-id="fdd02-119">There is no built-in function that returns the third element of a triple, but you can easily write one as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L78-L78)]

<span data-ttu-id="fdd02-120">通常情况下，最好使用模式匹配来访问各个元组元素。</span><span class="sxs-lookup"><span data-stu-id="fdd02-120">Generally, it is better to use pattern matching to access individual tuple elements.</span></span>

## <a name="using-tuples"></a><span data-ttu-id="fdd02-121">使用元组</span><span class="sxs-lookup"><span data-stu-id="fdd02-121">Using Tuples</span></span>

<span data-ttu-id="fdd02-122">元组提供从函数返回多个值的简便方法，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="fdd02-122">Tuples provide a convenient way to return multiple values from a function, as shown in the following example.</span></span> <span data-ttu-id="fdd02-123">此示例执行整除并返回该操作，因为元组对的第一个成员，作为第二个成员对其余的舍入的结果。</span><span class="sxs-lookup"><span data-stu-id="fdd02-123">This example performs integer division and returns the rounded result of the operation as a first member of a tuple pair and the remainder as a second member of the pair.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L83-L86)]

<span data-ttu-id="fdd02-124">时您想要避免隐含的常用函数语法的函数参数的隐式扩充，也可以作为函数参数使用元组。</span><span class="sxs-lookup"><span data-stu-id="fdd02-124">Tuples can also be used as function arguments when you want to avoid the implicit currying of function arguments that is implied by the usual function syntax.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L88-L88)]

<span data-ttu-id="fdd02-125">用于定义函数的常见语法`let sum a b = a + b`使您能够定义函数，则部分应用函数的第一个参数，如下面的代码中所示。</span><span class="sxs-lookup"><span data-stu-id="fdd02-125">The usual syntax for defining the function `let sum a b = a + b` enables you to define a function that is the partial application of the first argument of the function, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L90-L94)]

<span data-ttu-id="fdd02-126">作为参数使用一个元组将禁用扩充。</span><span class="sxs-lookup"><span data-stu-id="fdd02-126">Using a tuple as the parameter disables currying.</span></span> <span data-ttu-id="fdd02-127">详细信息，请参阅"的参数的部分应用程序"中[函数](functions/index.md)。</span><span class="sxs-lookup"><span data-stu-id="fdd02-127">For more information, see "Partial Application of Arguments" in [Functions](functions/index.md).</span></span>

## <a name="names-of-tuple-types"></a><span data-ttu-id="fdd02-128">元组类型的名称</span><span class="sxs-lookup"><span data-stu-id="fdd02-128">Names of Tuple Types</span></span>

<span data-ttu-id="fdd02-129">在写出为一个元组类型的名称时，您使用`*`符号来分隔元素。</span><span class="sxs-lookup"><span data-stu-id="fdd02-129">When you write out the name of a type that is a tuple, you use the `*` symbol to separate elements.</span></span> <span data-ttu-id="fdd02-130">元组组成`int`、 一个`float`，和一个`string`，如`(10, 10.0, "ten")`，将按以下方式编写的类型。</span><span class="sxs-lookup"><span data-stu-id="fdd02-130">For a tuple that consists of an `int`, a `float`, and a `string`, such as `(10, 10.0, "ten")`, the type would be written as follows.</span></span>

```fsharp
int * float * string
```

## <a name="interoperation-with-c-tuples"></a><span data-ttu-id="fdd02-131">与 C# 元组互操作</span><span class="sxs-lookup"><span data-stu-id="fdd02-131">Interoperation with C# Tuples</span></span>

<span data-ttu-id="fdd02-132">C# 7.0 引入了语言的元组。</span><span class="sxs-lookup"><span data-stu-id="fdd02-132">C# 7.0 introduced tuples to the language.</span></span>  <span data-ttu-id="fdd02-133">在 C# 中的元组是结构，并且等效于 F # 中的结构元组。</span><span class="sxs-lookup"><span data-stu-id="fdd02-133">Tuples in C# are structs, and are equivalent to struct tuples in F#.</span></span>  <span data-ttu-id="fdd02-134">如果你需要与 C# 进行互操作，则必须使用结构元组。</span><span class="sxs-lookup"><span data-stu-id="fdd02-134">If you need to interoperate with C#, you must use struct tuples.</span></span>

<span data-ttu-id="fdd02-135">这很容易地执行操作。</span><span class="sxs-lookup"><span data-stu-id="fdd02-135">This is easy to do.</span></span>  <span data-ttu-id="fdd02-136">例如，假设您需要将元组传递给 C# 类，然后使用其结果，这也是一个元组：</span><span class="sxs-lookup"><span data-stu-id="fdd02-136">For example, imagine you have to pass a tuple to a C# class and then consume its result, which is also a tuple:</span></span>

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

<span data-ttu-id="fdd02-137">在 F # 代码中，然后可以将作为参数传递的结构元组并使用的结构元组形式的结果。</span><span class="sxs-lookup"><span data-stu-id="fdd02-137">In your F# code, you can then pass a struct tuple as the parameter and consume the result as a struct tuple.</span></span>

```fsharp
open TupleInterop

let struct (newX, newY) = Example.AddOneToXAndY(struct (1, 2))
// newX is now 2, and newY is now 3
```

### <a name="converting-between-reference-tuples-and-struct-tuples"></a><span data-ttu-id="fdd02-138">引用的元组和结构元组之间进行转换</span><span class="sxs-lookup"><span data-stu-id="fdd02-138">Converting between Reference Tuples and Struct Tuples</span></span>

<span data-ttu-id="fdd02-139">引用的元组和结构元组具有完全不同的基础表示形式，因为它们不是隐式转换。</span><span class="sxs-lookup"><span data-stu-id="fdd02-139">Because Reference Tuples and Struct Tuples have a completely different underlying representation, they are not implicitly convertible.</span></span>  <span data-ttu-id="fdd02-140">也就是说，将不会编译代码如下所示：</span><span class="sxs-lookup"><span data-stu-id="fdd02-140">That is, code such as the following won't compile:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/interop.fsx#L5-L12)]

<span data-ttu-id="fdd02-141">必须模式匹配上一个元组，并构建另一种具有的构成部分。</span><span class="sxs-lookup"><span data-stu-id="fdd02-141">You must pattern match on one tuple and construct the other with the constituent parts.</span></span>  <span data-ttu-id="fdd02-142">例如：</span><span class="sxs-lookup"><span data-stu-id="fdd02-142">For example:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/interop.fsx#L18-L22)]

## <a name="compiled-form-of-reference-tuples"></a><span data-ttu-id="fdd02-143">已编译的形式引用元组</span><span class="sxs-lookup"><span data-stu-id="fdd02-143">Compiled Form of Reference Tuples</span></span>

<span data-ttu-id="fdd02-144">本部分介绍元组的形式，它们在编译时。</span><span class="sxs-lookup"><span data-stu-id="fdd02-144">This section explains the form of tuples when they're compiled.</span></span>  <span data-ttu-id="fdd02-145">此处的信息不需读取除非面向.NET Framework 3.5 或更低。</span><span class="sxs-lookup"><span data-stu-id="fdd02-145">The information here isn't necessary to read unless you are targeting .NET Framework 3.5 or lower.</span></span>

<span data-ttu-id="fdd02-146">元组被编译到的一种多个泛型类型，所有命名对象`System.Tuple`，该重载上的实参数量或类型参数的数目。</span><span class="sxs-lookup"><span data-stu-id="fdd02-146">Tuples are compiled into objects of one of several generic types, all named `System.Tuple`, that are overloaded on the arity, or number of type parameters.</span></span> <span data-ttu-id="fdd02-147">查看从另一种语言，如 C# 或 Visual Basic 时，或使用一种工具，并不知道 F # 构造时，元组类型将显示在此窗体。</span><span class="sxs-lookup"><span data-stu-id="fdd02-147">Tuple types appear in this form when you view them from another language, such as C# or Visual Basic, or when you are using a tool that is not aware of F# constructs.</span></span> <span data-ttu-id="fdd02-148">`Tuple`类型在.NET Framework 4 中引入。</span><span class="sxs-lookup"><span data-stu-id="fdd02-148">The `Tuple` types were introduced in .NET Framework 4.</span></span> <span data-ttu-id="fdd02-149">如果面向.NET Framework 的早期版本，则编译器将使用的版本[System.Tuple](https://msdn.microsoft.com/library/5ac7953d-acdc-4a58-bfb7-c1f6406c0fa3)从 F # 核心库 2.0 版。</span><span class="sxs-lookup"><span data-stu-id="fdd02-149">If you are targeting an earlier version of the .NET Framework, the compiler uses versions of [System.Tuple](https://msdn.microsoft.com/library/5ac7953d-acdc-4a58-bfb7-c1f6406c0fa3) from the 2.0 version of the F# Core Library.</span></span> <span data-ttu-id="fdd02-150">此库中的类型仅用于面向 2.0、 3.0 和 3.5 版本的.NET Framework 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="fdd02-150">The types in this library are used only for applications that target the 2.0, 3.0, and 3.5 versions of the .NET Framework.</span></span> <span data-ttu-id="fdd02-151">类型转发用于确保.NET Framework 2.0 和.NET Framework 4 F # 组件之间的二进制文件兼容性。</span><span class="sxs-lookup"><span data-stu-id="fdd02-151">Type forwarding is used to ensure binary compatibility between .NET Framework 2.0 and .NET Framework 4 F# components.</span></span>

### <a name="compiled-form-of-struct-tuples"></a><span data-ttu-id="fdd02-152">已编译的形式的结构元组</span><span class="sxs-lookup"><span data-stu-id="fdd02-152">Compiled Form of Struct Tuples</span></span>

<span data-ttu-id="fdd02-153">结构元组 (例如， `struct (x, y)`)，从根本上不同于引用的元组。</span><span class="sxs-lookup"><span data-stu-id="fdd02-153">Struct tuples (for example, `struct (x, y)`), are fundamentally different from reference tuples.</span></span>  <span data-ttu-id="fdd02-154">编译为<xref:System.ValueTuple>重载的实参数量，或类型参数的数目的类型。</span><span class="sxs-lookup"><span data-stu-id="fdd02-154">They are compiled into the <xref:System.ValueTuple> type, overloaded by arity, or the number of type parameters.</span></span>  <span data-ttu-id="fdd02-155">它们等效于[C# 7.0 元组](../../csharp/tuples.md)并[Visual Basic 2017 元组](../../visual-basic/programming-guide/language-features/data-types/tuples.md)，并进行双向互操作。</span><span class="sxs-lookup"><span data-stu-id="fdd02-155">They are equivalent to [C# 7.0 Tuples](../../csharp/tuples.md) and [Visual Basic 2017 Tuples](../../visual-basic/programming-guide/language-features/data-types/tuples.md), and interoperate bidirectionally.</span></span>

## <a name="see-also"></a><span data-ttu-id="fdd02-156">请参阅</span><span class="sxs-lookup"><span data-stu-id="fdd02-156">See also</span></span>

- [<span data-ttu-id="fdd02-157">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="fdd02-157">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="fdd02-158">F# 类型</span><span class="sxs-lookup"><span data-stu-id="fdd02-158">F# Types</span></span>](fsharp-types.md)
