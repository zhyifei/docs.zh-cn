---
title: "引用单元格 (F#)"
description: "了解如何使您能够创建具有引用语义的可变值的存储位置 F # 引用单元格。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 09a0b221-ea21-45c4-bae8-5e4a339750c4
ms.openlocfilehash: c7470c9a36cf2cd24dd89ceffcf6e90c6dc4d2dd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="reference-cells"></a><span data-ttu-id="4225f-104">引用单元格</span><span class="sxs-lookup"><span data-stu-id="4225f-104">Reference Cells</span></span>

<span data-ttu-id="4225f-105">*引用单元格*使您能够创建具有引用语义的可变值的存储位置。</span><span class="sxs-lookup"><span data-stu-id="4225f-105">*Reference cells* are storage locations that enable you to create mutable values with reference semantics.</span></span>

## <a name="syntax"></a><span data-ttu-id="4225f-106">语法</span><span class="sxs-lookup"><span data-stu-id="4225f-106">Syntax</span></span>

```fsharp
ref expression
```

## <a name="remarks"></a><span data-ttu-id="4225f-107">备注</span><span class="sxs-lookup"><span data-stu-id="4225f-107">Remarks</span></span>
<span data-ttu-id="4225f-108">可以在值前面使用 `ref` 运算符来创建用于封装该值的新引用单元格。</span><span class="sxs-lookup"><span data-stu-id="4225f-108">You use the `ref` operator before a value to create a new reference cell that encapsulates the value.</span></span> <span data-ttu-id="4225f-109">然后，您可以更改基础值，因为该值是可变的。</span><span class="sxs-lookup"><span data-stu-id="4225f-109">You can then change the underlying value because it is mutable.</span></span>

<span data-ttu-id="4225f-110">引用单元格容纳实际值；它不仅仅是一个地址。</span><span class="sxs-lookup"><span data-stu-id="4225f-110">A reference cell holds an actual value; it is not just an address.</span></span> <span data-ttu-id="4225f-111">使用 `ref` 运算符创建引用单元格时，将以封装的可变值的形式创建基础值的副本。</span><span class="sxs-lookup"><span data-stu-id="4225f-111">When you create a reference cell by using the `ref` operator, you create a copy of the underlying value as an encapsulated mutable value.</span></span>

<span data-ttu-id="4225f-112">可以使用 `!`（感叹号）运算符取消对引用单元格的引用。</span><span class="sxs-lookup"><span data-stu-id="4225f-112">You can dereference a reference cell by using the `!` (bang) operator.</span></span>

<span data-ttu-id="4225f-113">下面的代码示例阐释了引用单元格的声明和用法。</span><span class="sxs-lookup"><span data-stu-id="4225f-113">The following code example illustrates the declaration and use of reference cells.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2201.fs)]

<span data-ttu-id="4225f-114">输出为 `50`。</span><span class="sxs-lookup"><span data-stu-id="4225f-114">The output is `50`.</span></span>

<span data-ttu-id="4225f-115">引用单元格是 `Ref` 泛型记录类型的实例，声明方式如下所示。</span><span class="sxs-lookup"><span data-stu-id="4225f-115">Reference cells are instances of the `Ref` generic record type, which is declared as follows.</span></span>

```fsharp
type Ref<'a> =
{ mutable contents: 'a }
```

<span data-ttu-id="4225f-116">类型 `'a ref` 是 `Ref<'a>` 的同义词。</span><span class="sxs-lookup"><span data-stu-id="4225f-116">The type `'a ref` is a synonym for `Ref<'a>`.</span></span> <span data-ttu-id="4225f-117">IDE 中的编译器和 IntelliSense 显示此类型的前者，而基础定义是后者。</span><span class="sxs-lookup"><span data-stu-id="4225f-117">The compiler and IntelliSense in the IDE display the former for this type, but the underlying definition is the latter.</span></span>

<span data-ttu-id="4225f-118">`ref` 运算符创建新引用单元格。</span><span class="sxs-lookup"><span data-stu-id="4225f-118">The `ref` operator creates a new reference cell.</span></span> <span data-ttu-id="4225f-119">下面的代码声明 `ref` 运算符。</span><span class="sxs-lookup"><span data-stu-id="4225f-119">The following code is the declaration of the `ref` operator.</span></span>

```fsharp
let ref x = { contents = x }
```

<span data-ttu-id="4225f-120">下表显示了可用于引用单元格的功能。</span><span class="sxs-lookup"><span data-stu-id="4225f-120">The following table shows the features that are available on the reference cell.</span></span>

|<span data-ttu-id="4225f-121">运算符、成员或字段</span><span class="sxs-lookup"><span data-stu-id="4225f-121">Operator, member, or field</span></span>|<span data-ttu-id="4225f-122">描述</span><span class="sxs-lookup"><span data-stu-id="4225f-122">Description</span></span>|<span data-ttu-id="4225f-123">类型</span><span class="sxs-lookup"><span data-stu-id="4225f-123">Type</span></span>|<span data-ttu-id="4225f-124">定义</span><span class="sxs-lookup"><span data-stu-id="4225f-124">Definition</span></span>|
|--------------------------|-----------|----|----------|
|<span data-ttu-id="4225f-125">`!`（取消引用运算符）</span><span class="sxs-lookup"><span data-stu-id="4225f-125">`!` (dereference operator)</span></span>|<span data-ttu-id="4225f-126">返回基础值。</span><span class="sxs-lookup"><span data-stu-id="4225f-126">Returns the underlying value.</span></span>|`'a ref -> 'a`|`let (!) r = r.contents`|
|<span data-ttu-id="4225f-127">`:=`（赋值运算符）</span><span class="sxs-lookup"><span data-stu-id="4225f-127">`:=` (assignment operator)</span></span>|<span data-ttu-id="4225f-128">更改基础值。</span><span class="sxs-lookup"><span data-stu-id="4225f-128">Changes the underlying value.</span></span>|`'a ref -> 'a -> unit`|`let (:=) r x = r.contents <- x`|
|<span data-ttu-id="4225f-129">`ref`（运算符）</span><span class="sxs-lookup"><span data-stu-id="4225f-129">`ref` (operator)</span></span>|<span data-ttu-id="4225f-130">将值封装到新的引用单元格中。</span><span class="sxs-lookup"><span data-stu-id="4225f-130">Encapsulates a value into a new reference cell.</span></span>|`'a -> 'a ref`|`let ref x = { contents = x }`|
|<span data-ttu-id="4225f-131">`Value`（属性）</span><span class="sxs-lookup"><span data-stu-id="4225f-131">`Value` (property)</span></span>|<span data-ttu-id="4225f-132">获取或设置基础值。</span><span class="sxs-lookup"><span data-stu-id="4225f-132">Gets or sets the underlying value.</span></span>|`unit -> 'a`|`member x.Value = x.contents`|
|<span data-ttu-id="4225f-133">`contents`（记录字段）</span><span class="sxs-lookup"><span data-stu-id="4225f-133">`contents` (record field)</span></span>|<span data-ttu-id="4225f-134">获取或设置基础值。</span><span class="sxs-lookup"><span data-stu-id="4225f-134">Gets or sets the underlying value.</span></span>|`'a`|`let ref x = { contents = x }`|
<span data-ttu-id="4225f-135">可通过多种方式来访问基础值。</span><span class="sxs-lookup"><span data-stu-id="4225f-135">There are several ways to access the underlying value.</span></span> <span data-ttu-id="4225f-136">取消引用运算符 (`!`) 返回的值不是可赋值的值。</span><span class="sxs-lookup"><span data-stu-id="4225f-136">The value returned by the dereference operator (`!`) is not an assignable value.</span></span> <span data-ttu-id="4225f-137">因此，如果要修改基础值，您必须改用赋值运算符 (`:=`)。</span><span class="sxs-lookup"><span data-stu-id="4225f-137">Therefore, if you are modifying the underlying value, you must use the assignment operator (`:=`) instead.</span></span>

<span data-ttu-id="4225f-138">`Value` 属性和 `contents` 字段都是可赋值的值。</span><span class="sxs-lookup"><span data-stu-id="4225f-138">Both the `Value` property and the `contents` field are assignable values.</span></span> <span data-ttu-id="4225f-139">因此，你可以使用它们来访问或更改基础值，如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="4225f-139">Therefore, you can use these to either access or change the underlying value, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2203.fs)]

<span data-ttu-id="4225f-140">输出如下所示。</span><span class="sxs-lookup"><span data-stu-id="4225f-140">The output is as follows.</span></span>

```
10
10
11
12
```

<span data-ttu-id="4225f-141">提供字段 `contents` 的目的是为了与其他版本的 ML 兼容，并且该字段将在编译过程中产生警告。</span><span class="sxs-lookup"><span data-stu-id="4225f-141">The field `contents` is provided for compatibility with other versions of ML and will produce a warning during compilation.</span></span> <span data-ttu-id="4225f-142">若要禁用警告，请使用 `--mlcompatibility` 编译器选项。</span><span class="sxs-lookup"><span data-stu-id="4225f-142">To disable the warning, use the `--mlcompatibility` compiler option.</span></span> <span data-ttu-id="4225f-143">有关详细信息，请参阅[编译器选项](compiler-options.md)。</span><span class="sxs-lookup"><span data-stu-id="4225f-143">For more information, see [Compiler Options](compiler-options.md).</span></span>

<span data-ttu-id="4225f-144">下面的代码阐释了参数传递中引用单元格的用法。</span><span class="sxs-lookup"><span data-stu-id="4225f-144">The following code illustrates the use of reference cells in parameter passing.</span></span> <span data-ttu-id="4225f-145">增量类型有一个方法采用一个参数以包括 byref 参数类型中的增量。</span><span class="sxs-lookup"><span data-stu-id="4225f-145">The Incrementor type has a method Increment that takes a parameter that includes byref in the parameter type.</span></span> <span data-ttu-id="4225f-146">中的参数类型 byref 指示，调用方必须传递引用单元格或指定类型的典型变量的地址在此案例 int。其余的代码演示如何使用这两种类型的参数，调用递增和上一个变量来创建引用单元格 (ref myDelta1) 演示了如何使用 ref 运算符。</span><span class="sxs-lookup"><span data-stu-id="4225f-146">The byref in the parameter type indicates that callers must pass a reference cell or the address of a typical variable of the specified type, in this case int. The remaining code illustrates how to call Increment with both of these types of arguments, and shows the use of the ref operator on a variable to create a reference cell (ref myDelta1).</span></span> <span data-ttu-id="4225f-147">然后，它演示了如何使用 address-of 运算符 (&amp;) 来生成相应的参数。</span><span class="sxs-lookup"><span data-stu-id="4225f-147">It then shows the use of the address-of operator (&amp;) to generate an appropriate argument.</span></span> <span data-ttu-id="4225f-148">最后，由使用让的绑定声明的引用单元格再次调用 Increment 方法。</span><span class="sxs-lookup"><span data-stu-id="4225f-148">Finally, the Increment method is called again by using a reference cell that is declared by using a let binding.</span></span> <span data-ttu-id="4225f-149">代码的最后一行演示如何使用 ！</span><span class="sxs-lookup"><span data-stu-id="4225f-149">The final line of code demonstrates the use of the !</span></span> <span data-ttu-id="4225f-150">运算符来取消引用用于打印的单元格。</span><span class="sxs-lookup"><span data-stu-id="4225f-150">operator to dereference the reference cell for printing.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2204.fs)]

<span data-ttu-id="4225f-151">有关如何按引用传递的详细信息，请参阅[参数和自变量](parameters-and-arguments.md)。</span><span class="sxs-lookup"><span data-stu-id="4225f-151">For more information about how to pass by reference, see [Parameters and Arguments](parameters-and-arguments.md).</span></span>

>[!NOTE]
<span data-ttu-id="4225f-152">C# 程序员应知道该 ref 的工作方式在 F # 与在 C#。</span><span class="sxs-lookup"><span data-stu-id="4225f-152">C# programmers should know that ref works differently in F# than it does in C#.</span></span> <span data-ttu-id="4225f-153">例如，使用 ref 时传递了参数没有相同的效果在 F # 中 C# 中的一样。</span><span class="sxs-lookup"><span data-stu-id="4225f-153">For example, the use of ref when you pass an argument does not have the same effect in F# as it does in C#.</span></span>

## <a name="consuming-c-ref-returns"></a><span data-ttu-id="4225f-154">使用 C#`ref`返回</span><span class="sxs-lookup"><span data-stu-id="4225f-154">Consuming C# `ref` returns</span></span>

<span data-ttu-id="4225f-155">F # 4.1 开始，你可以使用`ref`返回在 C# 中生成。</span><span class="sxs-lookup"><span data-stu-id="4225f-155">Starting with F# 4.1, you can consume `ref` returns generated in C#.</span></span>  <span data-ttu-id="4225f-156">此类调用的结果是`byref<_>`指针。</span><span class="sxs-lookup"><span data-stu-id="4225f-156">The result of such a call is a `byref<_>` pointer.</span></span>

<span data-ttu-id="4225f-157">以下 C# 方法：</span><span class="sxs-lookup"><span data-stu-id="4225f-157">The following C# method:</span></span>

```csharp
namespace RefReturns
{
    public static class RefClass
    {
        public static ref int Find(int val, int[] vals)
        {
            for (int i = 0; i < vals.Length; i++)
            {
                if (vals[i] == val)
                {
                    return ref numbers[i]; // Returns the location, not the value
                }
            }

            throw new IndexOutOfRangeException($"{nameof(number)} not found");
        }
    }
}
```

<span data-ttu-id="4225f-158">可以以透明方式由调用 F # 与任何特殊的语法：</span><span class="sxs-lookup"><span data-stu-id="4225f-158">Can be transparently called by F# with no special syntax:</span></span>

```fsharp
open RefReturns

let consumeRefReturn() =
    let result = RefClass.Find(3, [| 1; 2; 3; 4; 5 |]) // 'result' is of type 'byref<int>'.
    ()
```

<span data-ttu-id="4225f-159">您还可以声明函数可能需要`ref`返回作为输入，例如：</span><span class="sxs-lookup"><span data-stu-id="4225f-159">You can also declare functions which could take a `ref` return as input, for example:</span></span>

```fsharp
let f (x: byref<int>) = &x
```

<span data-ttu-id="4225f-160">当前没有方法来生成`ref`返回在 F # 无法在 C# 中使用。</span><span class="sxs-lookup"><span data-stu-id="4225f-160">There is currently no way to generate a `ref` return in F# which could be consumed in C#.</span></span>

## <a name="see-also"></a><span data-ttu-id="4225f-161">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4225f-161">See Also</span></span>
[<span data-ttu-id="4225f-162">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="4225f-162">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="4225f-163">参数和自变量</span><span class="sxs-lookup"><span data-stu-id="4225f-163">Parameters and Arguments</span></span>](parameters-and-arguments.md)

[<span data-ttu-id="4225f-164">符号和运算符参考</span><span class="sxs-lookup"><span data-stu-id="4225f-164">Symbol and Operator Reference</span></span>](symbol-and-operator-reference/index.md)
