---
title: 索引属性 (F#)
description: '了解有关 F # 编制索引的属性提供对有序数据的类似数组的访问权限的属性。'
ms.date: 05/16/2016
ms.openlocfilehash: e56e4e2ea3f35df4c8ec46012357242cb6ce69f3
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2018
ms.locfileid: "45994255"
---
# <a name="indexed-properties"></a><span data-ttu-id="6a943-103">索引属性</span><span class="sxs-lookup"><span data-stu-id="6a943-103">Indexed Properties</span></span>

<span data-ttu-id="6a943-104">*索引属性*提供类似数组的访问权限的属性排序数据。</span><span class="sxs-lookup"><span data-stu-id="6a943-104">*Indexed properties* are properties that provide array-like access to ordered data.</span></span> <span data-ttu-id="6a943-105">它们分为三种形式：</span><span class="sxs-lookup"><span data-stu-id="6a943-105">They come in three forms:</span></span>

* `Item`
* `Ordinal`
* `Cardinal`

<span data-ttu-id="6a943-106">F # 成员必须具有名称以提供类似数组的访问这三个名称之一。</span><span class="sxs-lookup"><span data-stu-id="6a943-106">An F# member must be named one of these three names to provide array-like access.</span></span> <span data-ttu-id="6a943-107">`IndexerName` 用于表示任何以下三个选项：</span><span class="sxs-lookup"><span data-stu-id="6a943-107">`IndexerName` is used to represent any of the three options below:</span></span>

## <a name="syntax"></a><span data-ttu-id="6a943-108">语法</span><span class="sxs-lookup"><span data-stu-id="6a943-108">Syntax</span></span>

```fsharp
// Indexed property that has both get and set defined.
member self-identifier.IndexerName
    with get(index-variable) =
        get-function-body
    and set index-variablesvalue-variables =
        set-function-body

// Indexed property that has get only.
member self-identifier.IndexerName(index-variable) =
    get-function-body

// Alternative syntax for indexed property with get only
member self-identifier.IndexerName
    with get(index-variables) =
        get-function-body

// Indexed property that has set only.
member self-identifier.IndexerName
    with set index-variablesvalue-variables = 
        set-function-body
```

## <a name="remarks"></a><span data-ttu-id="6a943-109">备注</span><span class="sxs-lookup"><span data-stu-id="6a943-109">Remarks</span></span>

<span data-ttu-id="6a943-110">上述语法中的窗体演示如何定义具有这两者的索引的属性`get`和一个`set`方法中，有`get`方法，或具有`set`方法仅。</span><span class="sxs-lookup"><span data-stu-id="6a943-110">The forms of the previous syntax show how to define indexed properties that have both a `get` and a `set` method, have a `get` method only, or have a `set` method only.</span></span> <span data-ttu-id="6a943-111">此外可以将两者合并为仅限获取和组，所示的语法所示的语法，并生成具有 get 和 set 的属性。</span><span class="sxs-lookup"><span data-stu-id="6a943-111">You can also combine both the syntax shown for get only and the syntax shown for set only, and produce a property that has both get and set.</span></span> <span data-ttu-id="6a943-112">这后一种形式，可将不同的可访问性修饰符和属性放在 get 和 set 方法。</span><span class="sxs-lookup"><span data-stu-id="6a943-112">This latter form allows you to put different accessibility modifiers and attributes on the get and set methods.</span></span>

<span data-ttu-id="6a943-113">当*IndexerName*是`Item`，编译器会将属性视为默认索引属性。</span><span class="sxs-lookup"><span data-stu-id="6a943-113">When the *IndexerName* is `Item`, the compiler treats the property as a default indexed property.</span></span> <span data-ttu-id="6a943-114">一个*的默认索引属性*是一个属性，可以访问的对象实例上使用的类似数组的语法。</span><span class="sxs-lookup"><span data-stu-id="6a943-114">A *default indexed property* is a property that you can access by using array-like syntax on the object instance.</span></span> <span data-ttu-id="6a943-115">例如，如果`obj`是用于定义此属性，该语法的类型的对象`obj.[index]`用于访问属性。</span><span class="sxs-lookup"><span data-stu-id="6a943-115">For example, if `obj` is an object of the type that defines this property, the syntax `obj.[index]` is used to access the property.</span></span>

<span data-ttu-id="6a943-116">用于访问非默认索引属性的语法是提供属性和在括号中的索引的名称。</span><span class="sxs-lookup"><span data-stu-id="6a943-116">The syntax for accessing a nondefault indexed property is to provide the name of the property and the index in parentheses.</span></span> <span data-ttu-id="6a943-117">例如，如果该属性是`Ordinal`，您编写`obj.Ordinal(index)`来访问它。</span><span class="sxs-lookup"><span data-stu-id="6a943-117">For example, if the property is `Ordinal`, you write `obj.Ordinal(index)` to access it.</span></span>

<span data-ttu-id="6a943-118">无论使用哪种形式，您应始终使用为扩充的形式`set`索引属性的方法。</span><span class="sxs-lookup"><span data-stu-id="6a943-118">Regardless of which form you use, you should always use the curried form for the `set` method on an indexed property.</span></span> <span data-ttu-id="6a943-119">扩充函数有关的信息，请参阅[函数](../functions/index.md)。</span><span class="sxs-lookup"><span data-stu-id="6a943-119">For information about curried functions, see [Functions](../functions/index.md).</span></span>

## <a name="example"></a><span data-ttu-id="6a943-120">示例</span><span class="sxs-lookup"><span data-stu-id="6a943-120">Example</span></span>

<span data-ttu-id="6a943-121">下面的代码示例演示定义和使用的默认和非默认索引的属性具有 get 和 set 方法。</span><span class="sxs-lookup"><span data-stu-id="6a943-121">The following code example illustrates the definition and use of default and non-default indexed properties that have get and set methods.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3301.fs)]

## <a name="output"></a><span data-ttu-id="6a943-122">输出</span><span class="sxs-lookup"><span data-stu-id="6a943-122">Output</span></span>

```
ONE two three four five six seven eight nine ten
ONE first two second three third four fourth five fifth six 6th
seven seventh eight eighth nine ninth ten tenth
```

## <a name="indexed-properties-with-multiple-index-variables"></a><span data-ttu-id="6a943-123">通过多个索引变量的索引的属性</span><span class="sxs-lookup"><span data-stu-id="6a943-123">Indexed Properties with Multiple Index Variables</span></span>

<span data-ttu-id="6a943-124">索引的属性可以具有多个索引变量。</span><span class="sxs-lookup"><span data-stu-id="6a943-124">Indexed properties can have more than one index variable.</span></span> <span data-ttu-id="6a943-125">在这种情况下，变量用逗号分隔时使用的属性。</span><span class="sxs-lookup"><span data-stu-id="6a943-125">In that case, the variables are separated by commas when the property is used.</span></span> <span data-ttu-id="6a943-126">在此类属性中的 set 方法必须具有两个扩充的参数，其中第一个是包含密钥的元组和第二个是要设置的值。</span><span class="sxs-lookup"><span data-stu-id="6a943-126">The set method in such a property must have two curried arguments, the first of which is a tuple containing the keys, and the second of which is the value being set.</span></span>

<span data-ttu-id="6a943-127">下面的代码演示如何将具有多个索引变量的索引属性。</span><span class="sxs-lookup"><span data-stu-id="6a943-127">The following code demonstrates the use of an indexed property with multiple index variables.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3302.fs)]

## <a name="see-also"></a><span data-ttu-id="6a943-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="6a943-128">See also</span></span>

- [<span data-ttu-id="6a943-129">成员</span><span class="sxs-lookup"><span data-stu-id="6a943-129">Members</span></span>](index.md)
