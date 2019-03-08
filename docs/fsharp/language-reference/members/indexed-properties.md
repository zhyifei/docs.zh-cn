---
title: 索引属性
description: 了解如何在中的索引属性F#，这允许对有序数据的类似数组的访问。
ms.date: 10/17/2018
ms.openlocfilehash: bc330641c451973ddefa0a34fe6e757a808f6cb7
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2019
ms.locfileid: "57678600"
---
# <a name="indexed-properties"></a><span data-ttu-id="1f81f-103">索引属性</span><span class="sxs-lookup"><span data-stu-id="1f81f-103">Indexed Properties</span></span>

<span data-ttu-id="1f81f-104">在定义类，用于对有序数据提取时，有时可能很有帮助，而无需公开基础的实现提供对该数据的索引的访问。</span><span class="sxs-lookup"><span data-stu-id="1f81f-104">When defining a class that abstracts over ordered data, it can sometimes be helpful to provide indexed access to that data without exposing the underlying implementation.</span></span> <span data-ttu-id="1f81f-105">这通过`Index`成员。</span><span class="sxs-lookup"><span data-stu-id="1f81f-105">This is done with the `Index` member.</span></span>

## <a name="syntax"></a><span data-ttu-id="1f81f-106">语法</span><span class="sxs-lookup"><span data-stu-id="1f81f-106">Syntax</span></span>

```fsharp
// Indexed property that has both get and set defined.
member self-identifier.Index
    with get(index-values) =
        get-member-body
    and set index-values values-to-set =
        set-member-body

// Indexed property with get only
member self-identifier.Index
    with get(index-values) =
        get-member-body

// Indexed property that has set only.
member self-identifier.Index
    with set index-values values-to-set =
        set-member-body
```

## <a name="remarks"></a><span data-ttu-id="1f81f-107">备注</span><span class="sxs-lookup"><span data-stu-id="1f81f-107">Remarks</span></span>

<span data-ttu-id="1f81f-108">上述语法中的窗体演示如何定义具有这两者的索引的属性`get`和一个`set`方法中，有`get`方法，或具有`set`方法仅。</span><span class="sxs-lookup"><span data-stu-id="1f81f-108">The forms of the previous syntax show how to define indexed properties that have both a `get` and a `set` method, have a `get` method only, or have a `set` method only.</span></span> <span data-ttu-id="1f81f-109">此外可以将两者合并为仅限获取和组，所示的语法所示的语法，并生成具有 get 和 set 的属性。</span><span class="sxs-lookup"><span data-stu-id="1f81f-109">You can also combine both the syntax shown for get only and the syntax shown for set only, and produce a property that has both get and set.</span></span> <span data-ttu-id="1f81f-110">这后一种形式，可将不同的可访问性修饰符和属性放在 get 和 set 方法。</span><span class="sxs-lookup"><span data-stu-id="1f81f-110">This latter form allows you to put different accessibility modifiers and attributes on the get and set methods.</span></span>

<span data-ttu-id="1f81f-111">使用名称`Item`，编译器会将属性视为默认索引属性。</span><span class="sxs-lookup"><span data-stu-id="1f81f-111">By using the name `Item`, the compiler treats the property as a default indexed property.</span></span> <span data-ttu-id="1f81f-112">一个*的默认索引属性*是一个属性，可以访问的对象实例上使用的类似数组的语法。</span><span class="sxs-lookup"><span data-stu-id="1f81f-112">A *default indexed property* is a property that you can access by using array-like syntax on the object instance.</span></span> <span data-ttu-id="1f81f-113">例如，如果`o`是用于定义此属性，该语法的类型的对象`o.[index]`用于访问属性。</span><span class="sxs-lookup"><span data-stu-id="1f81f-113">For example, if `o` is an object of the type that defines this property, the syntax `o.[index]` is used to access the property.</span></span>

<span data-ttu-id="1f81f-114">用于访问非默认索引的属性的语法是提供属性和中括号内，就像常规成员的索引的名称。</span><span class="sxs-lookup"><span data-stu-id="1f81f-114">The syntax for accessing a non-default indexed property is to provide the name of the property and the index in parentheses, just like a regular member.</span></span> <span data-ttu-id="1f81f-115">例如，如果上的属性`o`称为`Ordinal`，您编写`o.Ordinal(index)`来访问它。</span><span class="sxs-lookup"><span data-stu-id="1f81f-115">For example, if the property on `o` is called `Ordinal`, you write `o.Ordinal(index)` to access it.</span></span>

<span data-ttu-id="1f81f-116">无论使用哪种形式，应始终使用扩充窗体上的索引属性的集方法。</span><span class="sxs-lookup"><span data-stu-id="1f81f-116">Regardless of which form you use, you should always use the curried form for the set method on an indexed property.</span></span> <span data-ttu-id="1f81f-117">扩充函数有关的信息，请参阅[函数](../functions/index.md)。</span><span class="sxs-lookup"><span data-stu-id="1f81f-117">For information about curried functions, see [Functions](../functions/index.md).</span></span>

## <a name="example"></a><span data-ttu-id="1f81f-118">示例</span><span class="sxs-lookup"><span data-stu-id="1f81f-118">Example</span></span>

<span data-ttu-id="1f81f-119">下面的代码示例演示定义和使用的默认和非默认索引的属性具有 get 和 set 方法。</span><span class="sxs-lookup"><span data-stu-id="1f81f-119">The following code example illustrates the definition and use of default and non-default indexed properties that have get and set methods.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3301.fs)]

## <a name="output"></a><span data-ttu-id="1f81f-120">输出</span><span class="sxs-lookup"><span data-stu-id="1f81f-120">Output</span></span>

```console
ONE two three four five six seven eight nine ten
ONE first two second three third four fourth five fifth six 6th
seven seventh eight eighth nine ninth ten tenth
```

## <a name="indexed-properties-with-multiple-index-values"></a><span data-ttu-id="1f81f-121">具有多个索引值的索引的属性</span><span class="sxs-lookup"><span data-stu-id="1f81f-121">Indexed Properties with multiple index values</span></span>

<span data-ttu-id="1f81f-122">索引的属性可以具有多个索引值。</span><span class="sxs-lookup"><span data-stu-id="1f81f-122">Indexed properties can have more than one index value.</span></span> <span data-ttu-id="1f81f-123">在这种情况下，值是逗号分隔时使用的属性。</span><span class="sxs-lookup"><span data-stu-id="1f81f-123">In that case, the values are separated by commas when the property is used.</span></span> <span data-ttu-id="1f81f-124">在此类属性中的 set 方法必须具有两个扩充的参数，其中第一个是包含密钥的元组，其中第二个是要设置的值。</span><span class="sxs-lookup"><span data-stu-id="1f81f-124">The set method in such a property must have two curried arguments, the first of which is a tuple containing the keys, and the second of which is the value to set.</span></span>

<span data-ttu-id="1f81f-125">下面的代码演示如何将具有多个索引值的索引属性。</span><span class="sxs-lookup"><span data-stu-id="1f81f-125">The following code demonstrates the use of an indexed property with multiple index values.</span></span>

```fsharp
open System.Collections.Generic

/// Basic implementation of a sparse matrix based on a dictionary
type SparseMatrix() =
    let table = new Dictionary<(int * int), float>()
    member __.Item
        // Because the key is comprised of two values, 'get' has two index values
        with get(key1, key2) = table.[(key1, key2)]

        // 'set' has two index values and a new value to place in the key's position
        and set (key1, key2) value = table.[(key1, key2)] <- value

let sm = new SparseMatrix()
for i in 1..1000 do
    sm.[i, i] <- float i * float i
```

## <a name="see-also"></a><span data-ttu-id="1f81f-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="1f81f-126">See also</span></span>

- [<span data-ttu-id="1f81f-127">成员</span><span class="sxs-lookup"><span data-stu-id="1f81f-127">Members</span></span>](index.md)
