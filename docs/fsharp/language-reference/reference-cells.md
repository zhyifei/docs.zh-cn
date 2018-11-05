---
title: 引用单元格 (F#)
description: 了解 F# 引用单元格的存储位置，您可以创建具有引用语义的可变值的方式。
ms.date: 05/16/2016
ms.openlocfilehash: e2e1a91c62fd76e4992bc5ae11bb672766850718
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "44192246"
---
# <a name="reference-cells"></a><span data-ttu-id="758d7-103">引用单元格</span><span class="sxs-lookup"><span data-stu-id="758d7-103">Reference Cells</span></span>

<span data-ttu-id="758d7-104">*引用单元格*是使您能够创建具有引用语义的可变值的存储位置。</span><span class="sxs-lookup"><span data-stu-id="758d7-104">*Reference cells* are storage locations that enable you to create mutable values with reference semantics.</span></span>

## <a name="syntax"></a><span data-ttu-id="758d7-105">语法</span><span class="sxs-lookup"><span data-stu-id="758d7-105">Syntax</span></span>

```fsharp
ref expression
```

## <a name="remarks"></a><span data-ttu-id="758d7-106">备注</span><span class="sxs-lookup"><span data-stu-id="758d7-106">Remarks</span></span>

<span data-ttu-id="758d7-107">可以在值前面使用 `ref` 运算符来创建用于封装该值的新引用单元格。</span><span class="sxs-lookup"><span data-stu-id="758d7-107">You use the `ref` operator before a value to create a new reference cell that encapsulates the value.</span></span> <span data-ttu-id="758d7-108">然后，您可以更改基础值，因为该值是可变的。</span><span class="sxs-lookup"><span data-stu-id="758d7-108">You can then change the underlying value because it is mutable.</span></span>

<span data-ttu-id="758d7-109">引用单元格容纳实际值；它不仅仅是一个地址。</span><span class="sxs-lookup"><span data-stu-id="758d7-109">A reference cell holds an actual value; it is not just an address.</span></span> <span data-ttu-id="758d7-110">使用 `ref` 运算符创建引用单元格时，将以封装的可变值的形式创建基础值的副本。</span><span class="sxs-lookup"><span data-stu-id="758d7-110">When you create a reference cell by using the `ref` operator, you create a copy of the underlying value as an encapsulated mutable value.</span></span>

<span data-ttu-id="758d7-111">可以使用 `!`（感叹号）运算符取消对引用单元格的引用。</span><span class="sxs-lookup"><span data-stu-id="758d7-111">You can dereference a reference cell by using the `!` (bang) operator.</span></span>

<span data-ttu-id="758d7-112">下面的代码示例阐释了引用单元格的声明和用法。</span><span class="sxs-lookup"><span data-stu-id="758d7-112">The following code example illustrates the declaration and use of reference cells.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2201.fs)]

<span data-ttu-id="758d7-113">输出为 `50`。</span><span class="sxs-lookup"><span data-stu-id="758d7-113">The output is `50`.</span></span>

<span data-ttu-id="758d7-114">引用单元格是 `Ref` 泛型记录类型的实例，声明方式如下所示。</span><span class="sxs-lookup"><span data-stu-id="758d7-114">Reference cells are instances of the `Ref` generic record type, which is declared as follows.</span></span>

```fsharp
type Ref<'a> =
{ mutable contents: 'a }
```

<span data-ttu-id="758d7-115">类型 `'a ref` 是 `Ref<'a>` 的同义词。</span><span class="sxs-lookup"><span data-stu-id="758d7-115">The type `'a ref` is a synonym for `Ref<'a>`.</span></span> <span data-ttu-id="758d7-116">IDE 中的编译器和 IntelliSense 显示此类型的前者，而基础定义是后者。</span><span class="sxs-lookup"><span data-stu-id="758d7-116">The compiler and IntelliSense in the IDE display the former for this type, but the underlying definition is the latter.</span></span>

<span data-ttu-id="758d7-117">`ref` 运算符创建新引用单元格。</span><span class="sxs-lookup"><span data-stu-id="758d7-117">The `ref` operator creates a new reference cell.</span></span> <span data-ttu-id="758d7-118">下面的代码声明 `ref` 运算符。</span><span class="sxs-lookup"><span data-stu-id="758d7-118">The following code is the declaration of the `ref` operator.</span></span>

```fsharp
let ref x = { contents = x }
```

<span data-ttu-id="758d7-119">下表显示了可用于引用单元格的功能。</span><span class="sxs-lookup"><span data-stu-id="758d7-119">The following table shows the features that are available on the reference cell.</span></span>

|<span data-ttu-id="758d7-120">运算符、成员或字段</span><span class="sxs-lookup"><span data-stu-id="758d7-120">Operator, member, or field</span></span>|<span data-ttu-id="758d7-121">描述</span><span class="sxs-lookup"><span data-stu-id="758d7-121">Description</span></span>|<span data-ttu-id="758d7-122">类型</span><span class="sxs-lookup"><span data-stu-id="758d7-122">Type</span></span>|<span data-ttu-id="758d7-123">定义</span><span class="sxs-lookup"><span data-stu-id="758d7-123">Definition</span></span>|
|--------------------------|-----------|----|----------|
|<span data-ttu-id="758d7-124">`!`（取消引用运算符）</span><span class="sxs-lookup"><span data-stu-id="758d7-124">`!` (dereference operator)</span></span>|<span data-ttu-id="758d7-125">返回基础值。</span><span class="sxs-lookup"><span data-stu-id="758d7-125">Returns the underlying value.</span></span>|`'a ref -> 'a`|`let (!) r = r.contents`|
|<span data-ttu-id="758d7-126">`:=`（赋值运算符）</span><span class="sxs-lookup"><span data-stu-id="758d7-126">`:=` (assignment operator)</span></span>|<span data-ttu-id="758d7-127">更改基础值。</span><span class="sxs-lookup"><span data-stu-id="758d7-127">Changes the underlying value.</span></span>|`'a ref -> 'a -> unit`|`let (:=) r x = r.contents <- x`|
|<span data-ttu-id="758d7-128">`ref`（运算符）</span><span class="sxs-lookup"><span data-stu-id="758d7-128">`ref` (operator)</span></span>|<span data-ttu-id="758d7-129">将值封装到新的引用单元格中。</span><span class="sxs-lookup"><span data-stu-id="758d7-129">Encapsulates a value into a new reference cell.</span></span>|`'a -> 'a ref`|`let ref x = { contents = x }`|
|<span data-ttu-id="758d7-130">`Value`（属性）</span><span class="sxs-lookup"><span data-stu-id="758d7-130">`Value` (property)</span></span>|<span data-ttu-id="758d7-131">获取或设置基础值。</span><span class="sxs-lookup"><span data-stu-id="758d7-131">Gets or sets the underlying value.</span></span>|`unit -> 'a`|`member x.Value = x.contents`|
|<span data-ttu-id="758d7-132">`contents`（记录字段）</span><span class="sxs-lookup"><span data-stu-id="758d7-132">`contents` (record field)</span></span>|<span data-ttu-id="758d7-133">获取或设置基础值。</span><span class="sxs-lookup"><span data-stu-id="758d7-133">Gets or sets the underlying value.</span></span>|`'a`|`let ref x = { contents = x }`|
<span data-ttu-id="758d7-134">可通过多种方式来访问基础值。</span><span class="sxs-lookup"><span data-stu-id="758d7-134">There are several ways to access the underlying value.</span></span> <span data-ttu-id="758d7-135">取消引用运算符 (`!`) 返回的值不是可赋值的值。</span><span class="sxs-lookup"><span data-stu-id="758d7-135">The value returned by the dereference operator (`!`) is not an assignable value.</span></span> <span data-ttu-id="758d7-136">因此，如果要修改基础值，您必须改用赋值运算符 (`:=`)。</span><span class="sxs-lookup"><span data-stu-id="758d7-136">Therefore, if you are modifying the underlying value, you must use the assignment operator (`:=`) instead.</span></span>

<span data-ttu-id="758d7-137">`Value` 属性和 `contents` 字段都是可赋值的值。</span><span class="sxs-lookup"><span data-stu-id="758d7-137">Both the `Value` property and the `contents` field are assignable values.</span></span> <span data-ttu-id="758d7-138">因此，你可以使用它们来访问或更改基础值，如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="758d7-138">Therefore, you can use these to either access or change the underlying value, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2203.fs)]

<span data-ttu-id="758d7-139">输出如下所示。</span><span class="sxs-lookup"><span data-stu-id="758d7-139">The output is as follows.</span></span>

```
10
10
11
12
```

<span data-ttu-id="758d7-140">提供字段 `contents` 的目的是为了与其他版本的 ML 兼容，并且该字段将在编译过程中产生警告。</span><span class="sxs-lookup"><span data-stu-id="758d7-140">The field `contents` is provided for compatibility with other versions of ML and will produce a warning during compilation.</span></span> <span data-ttu-id="758d7-141">若要禁用警告，请使用 `--mlcompatibility` 编译器选项。</span><span class="sxs-lookup"><span data-stu-id="758d7-141">To disable the warning, use the `--mlcompatibility` compiler option.</span></span> <span data-ttu-id="758d7-142">有关详细信息，请参阅[编译器选项](compiler-options.md)。</span><span class="sxs-lookup"><span data-stu-id="758d7-142">For more information, see [Compiler Options](compiler-options.md).</span></span>

<span data-ttu-id="758d7-143">C# 程序员应知道`ref`C# 中不是是与相同的`ref`F# 中。</span><span class="sxs-lookup"><span data-stu-id="758d7-143">C# programmers should know that `ref` in C# is not the same thing as `ref` in F#.</span></span> <span data-ttu-id="758d7-144">F# 中的等效构造是[byref](byrefs.md)，这是从引用单元格不同的概念。</span><span class="sxs-lookup"><span data-stu-id="758d7-144">The equivalent constructs in F# are [byrefs](byrefs.md), which are a different concept from reference cells.</span></span>

<span data-ttu-id="758d7-145">值标记为`mutable`可能会自动提升为`'a ref`如果捕获的闭包中; 请参阅[值](values/index.md)。</span><span class="sxs-lookup"><span data-stu-id="758d7-145">Values marked as `mutable`may be automatically promoted to `'a ref` if captured by a closure; see [Values](values/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="758d7-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="758d7-146">See also</span></span>

- [<span data-ttu-id="758d7-147">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="758d7-147">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="758d7-148">参数和自变量</span><span class="sxs-lookup"><span data-stu-id="758d7-148">Parameters and Arguments</span></span>](parameters-and-arguments.md)
- [<span data-ttu-id="758d7-149">符号和运算符参考</span><span class="sxs-lookup"><span data-stu-id="758d7-149">Symbol and Operator Reference</span></span>](symbol-and-operator-reference/index.md)
- [<span data-ttu-id="758d7-150">值</span><span class="sxs-lookup"><span data-stu-id="758d7-150">Values</span></span>](values/index.md)
