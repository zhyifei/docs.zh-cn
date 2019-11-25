---
title: 索引属性
description: 了解中F#的索引属性，该属性允许对按序的数据进行类似数组的访问。
ms.date: 11/04/2019
ms.openlocfilehash: f6cf3bfa737d2bf458e379594be5884696cee3e1
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976601"
---
# <a name="indexed-properties"></a><span data-ttu-id="2d17d-103">索引属性</span><span class="sxs-lookup"><span data-stu-id="2d17d-103">Indexed Properties</span></span>

<span data-ttu-id="2d17d-104">定义对按序的数据进行抽象的类时，有时提供对该数据的索引访问会很有帮助，而无需公开基础实现。</span><span class="sxs-lookup"><span data-stu-id="2d17d-104">When defining a class that abstracts over ordered data, it can sometimes be helpful to provide indexed access to that data without exposing the underlying implementation.</span></span> <span data-ttu-id="2d17d-105">这是通过 `Item` 成员来完成的。</span><span class="sxs-lookup"><span data-stu-id="2d17d-105">This is done with the `Item` member.</span></span>

## <a name="syntax"></a><span data-ttu-id="2d17d-106">语法</span><span class="sxs-lookup"><span data-stu-id="2d17d-106">Syntax</span></span>

```fsharp
// Indexed property that can be read and written to
member self-identifier.Item
    with get(index-values) =
        get-member-body
    and set index-values values-to-set =
        set-member-body

// Indexed property can only be read
member self-identifier.Item
    with get(index-values) =
        get-member-body

// Indexed property that can only be set
member self-identifier.Item
    with set index-values values-to-set =
        set-member-body
```

## <a name="remarks"></a><span data-ttu-id="2d17d-107">备注</span><span class="sxs-lookup"><span data-stu-id="2d17d-107">Remarks</span></span>

<span data-ttu-id="2d17d-108">上述语法的形式显示了如何定义同时具有 `get` 和 `set` 方法的索引属性、仅具有 `get` 方法或仅具有 `set` 方法。</span><span class="sxs-lookup"><span data-stu-id="2d17d-108">The forms of the previous syntax show how to define indexed properties that have both a `get` and a `set` method, have a `get` method only, or have a `set` method only.</span></span> <span data-ttu-id="2d17d-109">你还可以将显示的语法和仅用于 get 的语法组合在一起，并生成同时具有 get 和 set 的语法。</span><span class="sxs-lookup"><span data-stu-id="2d17d-109">You can also combine both the syntax shown for get only and the syntax shown for set only, and produce a property that has both get and set.</span></span> <span data-ttu-id="2d17d-110">后一种形式允许将不同的可访问性修饰符和特性置于 get 和 set 方法上。</span><span class="sxs-lookup"><span data-stu-id="2d17d-110">This latter form allows you to put different accessibility modifiers and attributes on the get and set methods.</span></span>

<span data-ttu-id="2d17d-111">通过使用名称 `Item`，编译器将属性视为默认的索引属性。</span><span class="sxs-lookup"><span data-stu-id="2d17d-111">By using the name `Item`, the compiler treats the property as a default indexed property.</span></span> <span data-ttu-id="2d17d-112">*默认索引属性*是一个属性，可通过对对象实例使用类似数组的语法来访问它。</span><span class="sxs-lookup"><span data-stu-id="2d17d-112">A *default indexed property* is a property that you can access by using array-like syntax on the object instance.</span></span> <span data-ttu-id="2d17d-113">例如，如果 `o` 为定义此属性的类型的对象，则使用语法 `o.[index]` 来访问属性。</span><span class="sxs-lookup"><span data-stu-id="2d17d-113">For example, if `o` is an object of the type that defines this property, the syntax `o.[index]` is used to access the property.</span></span>

<span data-ttu-id="2d17d-114">用于访问非默认索引属性的语法是在括号中提供属性和索引的名称，就像常规成员一样。</span><span class="sxs-lookup"><span data-stu-id="2d17d-114">The syntax for accessing a non-default indexed property is to provide the name of the property and the index in parentheses, just like a regular member.</span></span> <span data-ttu-id="2d17d-115">例如，如果 `o` 上的属性称为 `Ordinal`，则可以编写 `o.Ordinal(index)` 来访问它。</span><span class="sxs-lookup"><span data-stu-id="2d17d-115">For example, if the property on `o` is called `Ordinal`, you write `o.Ordinal(index)` to access it.</span></span>

<span data-ttu-id="2d17d-116">无论使用哪种窗体，都应始终对索引属性使用 set 方法的扩充形式。</span><span class="sxs-lookup"><span data-stu-id="2d17d-116">Regardless of which form you use, you should always use the curried form for the set method on an indexed property.</span></span> <span data-ttu-id="2d17d-117">有关扩充函数的信息，请参阅[函数](../functions/index.md)。</span><span class="sxs-lookup"><span data-stu-id="2d17d-117">For information about curried functions, see [Functions](../functions/index.md).</span></span>

## <a name="example"></a><span data-ttu-id="2d17d-118">示例</span><span class="sxs-lookup"><span data-stu-id="2d17d-118">Example</span></span>

<span data-ttu-id="2d17d-119">下面的代码示例演示了具有 get 和 set 方法的默认和非默认索引属性的定义和使用。</span><span class="sxs-lookup"><span data-stu-id="2d17d-119">The following code example illustrates the definition and use of default and non-default indexed properties that have get and set methods.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3301.fs)]

## <a name="output"></a><span data-ttu-id="2d17d-120">Output</span><span class="sxs-lookup"><span data-stu-id="2d17d-120">Output</span></span>

```console
ONE two three four five six seven eight nine ten
ONE first two second three third four fourth five fifth six 6th
seven seventh eight eighth nine ninth ten tenth
```

## <a name="indexed-properties-with-multiple-index-values"></a><span data-ttu-id="2d17d-121">具有多个索引值的索引属性</span><span class="sxs-lookup"><span data-stu-id="2d17d-121">Indexed Properties with multiple index values</span></span>

<span data-ttu-id="2d17d-122">索引属性可以有多个索引值。</span><span class="sxs-lookup"><span data-stu-id="2d17d-122">Indexed properties can have more than one index value.</span></span> <span data-ttu-id="2d17d-123">在这种情况下，如果使用属性，则值用逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="2d17d-123">In that case, the values are separated by commas when the property is used.</span></span> <span data-ttu-id="2d17d-124">此类属性中的 set 方法必须具有两个扩充参数，其中第一个参数是包含键的元组，第二个参数是要设置的值。</span><span class="sxs-lookup"><span data-stu-id="2d17d-124">The set method in such a property must have two curried arguments, the first of which is a tuple containing the keys, and the second of which is the value to set.</span></span>

<span data-ttu-id="2d17d-125">下面的代码演示如何使用具有多个索引值的索引属性。</span><span class="sxs-lookup"><span data-stu-id="2d17d-125">The following code demonstrates the use of an indexed property with multiple index values.</span></span>

```fsharp
open System.Collections.Generic

/// Basic implementation of a sparse matrix based on a dictionary
type SparseMatrix() =
    let table = new Dictionary<(int * int), float>()
    member _.Item
        // Because the key is comprised of two values, 'get' has two index values
        with get(key1, key2) = table.[(key1, key2)]

        // 'set' has two index values and a new value to place in the key's position
        and set (key1, key2) value = table.[(key1, key2)] <- value

let sm = new SparseMatrix()
for i in 1..1000 do
    sm.[i, i] <- float i * float i
```

## <a name="see-also"></a><span data-ttu-id="2d17d-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="2d17d-126">See also</span></span>

- [<span data-ttu-id="2d17d-127">成员</span><span class="sxs-lookup"><span data-stu-id="2d17d-127">Members</span></span>](index.md)
