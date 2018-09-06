---
title: 引用单元格 (F#)
description: '了解 F # 引用单元格的存储位置，您可以创建具有引用语义的可变值的方式。'
ms.date: 05/16/2016
ms.openlocfilehash: 133aec6b162a13306a05c9afa172f859890565eb
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43892411"
---
# <a name="reference-cells"></a><span data-ttu-id="5d07e-103">引用单元格</span><span class="sxs-lookup"><span data-stu-id="5d07e-103">Reference Cells</span></span>

<span data-ttu-id="5d07e-104">*引用单元格*是使您能够创建具有引用语义的可变值的存储位置。</span><span class="sxs-lookup"><span data-stu-id="5d07e-104">*Reference cells* are storage locations that enable you to create mutable values with reference semantics.</span></span>

## <a name="syntax"></a><span data-ttu-id="5d07e-105">语法</span><span class="sxs-lookup"><span data-stu-id="5d07e-105">Syntax</span></span>

```fsharp
ref expression
```

## <a name="remarks"></a><span data-ttu-id="5d07e-106">备注</span><span class="sxs-lookup"><span data-stu-id="5d07e-106">Remarks</span></span>

<span data-ttu-id="5d07e-107">可以在值前面使用 `ref` 运算符来创建用于封装该值的新引用单元格。</span><span class="sxs-lookup"><span data-stu-id="5d07e-107">You use the `ref` operator before a value to create a new reference cell that encapsulates the value.</span></span> <span data-ttu-id="5d07e-108">然后，您可以更改基础值，因为该值是可变的。</span><span class="sxs-lookup"><span data-stu-id="5d07e-108">You can then change the underlying value because it is mutable.</span></span>

<span data-ttu-id="5d07e-109">引用单元格容纳实际值；它不仅仅是一个地址。</span><span class="sxs-lookup"><span data-stu-id="5d07e-109">A reference cell holds an actual value; it is not just an address.</span></span> <span data-ttu-id="5d07e-110">使用 `ref` 运算符创建引用单元格时，将以封装的可变值的形式创建基础值的副本。</span><span class="sxs-lookup"><span data-stu-id="5d07e-110">When you create a reference cell by using the `ref` operator, you create a copy of the underlying value as an encapsulated mutable value.</span></span>

<span data-ttu-id="5d07e-111">可以使用 `!`（感叹号）运算符取消对引用单元格的引用。</span><span class="sxs-lookup"><span data-stu-id="5d07e-111">You can dereference a reference cell by using the `!` (bang) operator.</span></span>

<span data-ttu-id="5d07e-112">下面的代码示例阐释了引用单元格的声明和用法。</span><span class="sxs-lookup"><span data-stu-id="5d07e-112">The following code example illustrates the declaration and use of reference cells.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2201.fs)]

<span data-ttu-id="5d07e-113">输出为 `50`。</span><span class="sxs-lookup"><span data-stu-id="5d07e-113">The output is `50`.</span></span>

<span data-ttu-id="5d07e-114">引用单元格是 `Ref` 泛型记录类型的实例，声明方式如下所示。</span><span class="sxs-lookup"><span data-stu-id="5d07e-114">Reference cells are instances of the `Ref` generic record type, which is declared as follows.</span></span>

```fsharp
type Ref<'a> =
{ mutable contents: 'a }
```

<span data-ttu-id="5d07e-115">类型 `'a ref` 是 `Ref<'a>` 的同义词。</span><span class="sxs-lookup"><span data-stu-id="5d07e-115">The type `'a ref` is a synonym for `Ref<'a>`.</span></span> <span data-ttu-id="5d07e-116">IDE 中的编译器和 IntelliSense 显示此类型的前者，而基础定义是后者。</span><span class="sxs-lookup"><span data-stu-id="5d07e-116">The compiler and IntelliSense in the IDE display the former for this type, but the underlying definition is the latter.</span></span>

<span data-ttu-id="5d07e-117">`ref` 运算符创建新引用单元格。</span><span class="sxs-lookup"><span data-stu-id="5d07e-117">The `ref` operator creates a new reference cell.</span></span> <span data-ttu-id="5d07e-118">下面的代码声明 `ref` 运算符。</span><span class="sxs-lookup"><span data-stu-id="5d07e-118">The following code is the declaration of the `ref` operator.</span></span>

```fsharp
let ref x = { contents = x }
```

<span data-ttu-id="5d07e-119">下表显示了可用于引用单元格的功能。</span><span class="sxs-lookup"><span data-stu-id="5d07e-119">The following table shows the features that are available on the reference cell.</span></span>

|<span data-ttu-id="5d07e-120">运算符、成员或字段</span><span class="sxs-lookup"><span data-stu-id="5d07e-120">Operator, member, or field</span></span>|<span data-ttu-id="5d07e-121">描述</span><span class="sxs-lookup"><span data-stu-id="5d07e-121">Description</span></span>|<span data-ttu-id="5d07e-122">类型</span><span class="sxs-lookup"><span data-stu-id="5d07e-122">Type</span></span>|<span data-ttu-id="5d07e-123">定义</span><span class="sxs-lookup"><span data-stu-id="5d07e-123">Definition</span></span>|
|--------------------------|-----------|----|----------|
|<span data-ttu-id="5d07e-124">`!`（取消引用运算符）</span><span class="sxs-lookup"><span data-stu-id="5d07e-124">`!` (dereference operator)</span></span>|<span data-ttu-id="5d07e-125">返回基础值。</span><span class="sxs-lookup"><span data-stu-id="5d07e-125">Returns the underlying value.</span></span>|`'a ref -> 'a`|`let (!) r = r.contents`|
|<span data-ttu-id="5d07e-126">`:=`（赋值运算符）</span><span class="sxs-lookup"><span data-stu-id="5d07e-126">`:=` (assignment operator)</span></span>|<span data-ttu-id="5d07e-127">更改基础值。</span><span class="sxs-lookup"><span data-stu-id="5d07e-127">Changes the underlying value.</span></span>|`'a ref -> 'a -> unit`|`let (:=) r x = r.contents <- x`|
|<span data-ttu-id="5d07e-128">`ref`（运算符）</span><span class="sxs-lookup"><span data-stu-id="5d07e-128">`ref` (operator)</span></span>|<span data-ttu-id="5d07e-129">将值封装到新的引用单元格中。</span><span class="sxs-lookup"><span data-stu-id="5d07e-129">Encapsulates a value into a new reference cell.</span></span>|`'a -> 'a ref`|`let ref x = { contents = x }`|
|<span data-ttu-id="5d07e-130">`Value`（属性）</span><span class="sxs-lookup"><span data-stu-id="5d07e-130">`Value` (property)</span></span>|<span data-ttu-id="5d07e-131">获取或设置基础值。</span><span class="sxs-lookup"><span data-stu-id="5d07e-131">Gets or sets the underlying value.</span></span>|`unit -> 'a`|`member x.Value = x.contents`|
|<span data-ttu-id="5d07e-132">`contents`（记录字段）</span><span class="sxs-lookup"><span data-stu-id="5d07e-132">`contents` (record field)</span></span>|<span data-ttu-id="5d07e-133">获取或设置基础值。</span><span class="sxs-lookup"><span data-stu-id="5d07e-133">Gets or sets the underlying value.</span></span>|`'a`|`let ref x = { contents = x }`|
<span data-ttu-id="5d07e-134">可通过多种方式来访问基础值。</span><span class="sxs-lookup"><span data-stu-id="5d07e-134">There are several ways to access the underlying value.</span></span> <span data-ttu-id="5d07e-135">取消引用运算符 (`!`) 返回的值不是可赋值的值。</span><span class="sxs-lookup"><span data-stu-id="5d07e-135">The value returned by the dereference operator (`!`) is not an assignable value.</span></span> <span data-ttu-id="5d07e-136">因此，如果要修改基础值，您必须改用赋值运算符 (`:=`)。</span><span class="sxs-lookup"><span data-stu-id="5d07e-136">Therefore, if you are modifying the underlying value, you must use the assignment operator (`:=`) instead.</span></span>

<span data-ttu-id="5d07e-137">`Value` 属性和 `contents` 字段都是可赋值的值。</span><span class="sxs-lookup"><span data-stu-id="5d07e-137">Both the `Value` property and the `contents` field are assignable values.</span></span> <span data-ttu-id="5d07e-138">因此，你可以使用它们来访问或更改基础值，如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="5d07e-138">Therefore, you can use these to either access or change the underlying value, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2203.fs)]

<span data-ttu-id="5d07e-139">输出如下所示。</span><span class="sxs-lookup"><span data-stu-id="5d07e-139">The output is as follows.</span></span>

```
10
10
11
12
```

<span data-ttu-id="5d07e-140">提供字段 `contents` 的目的是为了与其他版本的 ML 兼容，并且该字段将在编译过程中产生警告。</span><span class="sxs-lookup"><span data-stu-id="5d07e-140">The field `contents` is provided for compatibility with other versions of ML and will produce a warning during compilation.</span></span> <span data-ttu-id="5d07e-141">若要禁用警告，请使用 `--mlcompatibility` 编译器选项。</span><span class="sxs-lookup"><span data-stu-id="5d07e-141">To disable the warning, use the `--mlcompatibility` compiler option.</span></span> <span data-ttu-id="5d07e-142">有关详细信息，请参阅[编译器选项](compiler-options.md)。</span><span class="sxs-lookup"><span data-stu-id="5d07e-142">For more information, see [Compiler Options](compiler-options.md).</span></span>

<span data-ttu-id="5d07e-143">下面的代码阐释了参数传递中引用单元格的用法。</span><span class="sxs-lookup"><span data-stu-id="5d07e-143">The following code illustrates the use of reference cells in parameter passing.</span></span> <span data-ttu-id="5d07e-144">增量类型有一个方法采用一个参数以包括 byref 参数类型中的增量。</span><span class="sxs-lookup"><span data-stu-id="5d07e-144">The Incrementor type has a method Increment that takes a parameter that includes byref in the parameter type.</span></span> <span data-ttu-id="5d07e-145">Byref 参数类型中的表示，调用方必须传递引用单元格或指定类型的典型变量的地址在此事例的 int。剩余的代码演示如何使用这两种类型的参数，调用增量和显示 ref 运算符使用了一个变量来创建引用单元格 (ref myDelta1) 上。</span><span class="sxs-lookup"><span data-stu-id="5d07e-145">The byref in the parameter type indicates that callers must pass a reference cell or the address of a typical variable of the specified type, in this case int. The remaining code illustrates how to call Increment with both of these types of arguments, and shows the use of the ref operator on a variable to create a reference cell (ref myDelta1).</span></span> <span data-ttu-id="5d07e-146">然后，它演示了如何使用 address-of 运算符 (&amp;) 来生成相应的参数。</span><span class="sxs-lookup"><span data-stu-id="5d07e-146">It then shows the use of the address-of operator (&amp;) to generate an appropriate argument.</span></span> <span data-ttu-id="5d07e-147">最后，通过使用 let 的绑定声明的引用单元格再次调用增量方法。</span><span class="sxs-lookup"><span data-stu-id="5d07e-147">Finally, the Increment method is called again by using a reference cell that is declared by using a let binding.</span></span> <span data-ttu-id="5d07e-148">最后一行代码演示如何使用 ！</span><span class="sxs-lookup"><span data-stu-id="5d07e-148">The final line of code demonstrates the use of the !</span></span> <span data-ttu-id="5d07e-149">若要取消引用引用单元格进行打印的运算符。</span><span class="sxs-lookup"><span data-stu-id="5d07e-149">operator to dereference the reference cell for printing.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2204.fs)]

<span data-ttu-id="5d07e-150">有关如何按引用传递的详细信息，请参阅[形参和实参](parameters-and-arguments.md)。</span><span class="sxs-lookup"><span data-stu-id="5d07e-150">For more information about how to pass by reference, see [Parameters and Arguments](parameters-and-arguments.md).</span></span>

>[!NOTE]
<span data-ttu-id="5d07e-151">C# 程序员应知道该 ref 的工作方式在 F # 与在 C#。</span><span class="sxs-lookup"><span data-stu-id="5d07e-151">C# programmers should know that ref works differently in F# than it does in C#.</span></span> <span data-ttu-id="5d07e-152">例如，ref 时传递自变量的使用没有相同的效果在 F # 中 C# 中的一样。</span><span class="sxs-lookup"><span data-stu-id="5d07e-152">For example, the use of ref when you pass an argument does not have the same effect in F# as it does in C#.</span></span>

>[!NOTE]
<span data-ttu-id="5d07e-153">`mutable` 变量可以自动升级到`'a ref`如果捕获的闭包中; 请参阅[值](values/index.md)。</span><span class="sxs-lookup"><span data-stu-id="5d07e-153">`mutable` variables may be automatically promoted to `'a ref` if captured by a closure; see [Values](values/index.md).</span></span>

## <a name="consuming-c-ref-returns"></a><span data-ttu-id="5d07e-154">使用 C#`ref`返回</span><span class="sxs-lookup"><span data-stu-id="5d07e-154">Consuming C# `ref` returns</span></span>

<span data-ttu-id="5d07e-155">从 F # 4.1 开始，你可以使用`ref`返回在 C# 中生成。</span><span class="sxs-lookup"><span data-stu-id="5d07e-155">Starting with F# 4.1, you can consume `ref` returns generated in C#.</span></span>  <span data-ttu-id="5d07e-156">此类调用的结果是`byref<_>`指针。</span><span class="sxs-lookup"><span data-stu-id="5d07e-156">The result of such a call is a `byref<_>` pointer.</span></span>

<span data-ttu-id="5d07e-157">以下 C# 方法：</span><span class="sxs-lookup"><span data-stu-id="5d07e-157">The following C# method:</span></span>

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

<span data-ttu-id="5d07e-158">可以以透明方式调用 F # 与任何特殊的语法：</span><span class="sxs-lookup"><span data-stu-id="5d07e-158">Can be transparently called by F# with no special syntax:</span></span>

```fsharp
open RefReturns

let consumeRefReturn() =
    let result = RefClass.Find(3, [| 1; 2; 3; 4; 5 |]) // 'result' is of type 'byref<int>'.
    ()
```

<span data-ttu-id="5d07e-159">你还可以声明函数，这可能需要`ref`返回作为输入，例如：</span><span class="sxs-lookup"><span data-stu-id="5d07e-159">You can also declare functions which could take a `ref` return as input, for example:</span></span>

```fsharp
let f (x: byref<int>) = &x
```

<span data-ttu-id="5d07e-160">当前没有方法来生成`ref`F # 中可使用 C# 中返回。</span><span class="sxs-lookup"><span data-stu-id="5d07e-160">There is currently no way to generate a `ref` return in F# which could be consumed in C#.</span></span>

## <a name="see-also"></a><span data-ttu-id="5d07e-161">请参阅</span><span class="sxs-lookup"><span data-stu-id="5d07e-161">See also</span></span>

- [<span data-ttu-id="5d07e-162">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="5d07e-162">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="5d07e-163">参数和自变量</span><span class="sxs-lookup"><span data-stu-id="5d07e-163">Parameters and Arguments</span></span>](parameters-and-arguments.md)
- [<span data-ttu-id="5d07e-164">符号和运算符参考</span><span class="sxs-lookup"><span data-stu-id="5d07e-164">Symbol and Operator Reference</span></span>](symbol-and-operator-reference/index.md)
- [<span data-ttu-id="5d07e-165">值</span><span class="sxs-lookup"><span data-stu-id="5d07e-165">Values</span></span>](values/index.md)
