---
title: 索引属性 (F#)
description: '了解有关 F # 索引属性，这些属性提供对已排序的数据类似数组的访问。'
ms.date: 05/16/2016
ms.openlocfilehash: 503cef9693cfe5e13d4e2d19a721d65bff1ce749
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2018
ms.locfileid: "34235936"
---
# <a name="indexed-properties"></a><span data-ttu-id="1a529-103">索引属性</span><span class="sxs-lookup"><span data-stu-id="1a529-103">Indexed Properties</span></span>

<span data-ttu-id="1a529-104">*索引属性*提供对类似数组的访问的属性排序数据。</span><span class="sxs-lookup"><span data-stu-id="1a529-104">*Indexed properties* are properties that provide array-like access to ordered data.</span></span> <span data-ttu-id="1a529-105">它们分为三种形式：</span><span class="sxs-lookup"><span data-stu-id="1a529-105">They come in three forms:</span></span>

* `Item`
* `Ordinal`
* `Cardinal`

<span data-ttu-id="1a529-106">F # 成员必须具有名称以提供类似于数组的访问这三个名称之一。</span><span class="sxs-lookup"><span data-stu-id="1a529-106">An F# member must be named one of these three names to provide array-like access.</span></span> <span data-ttu-id="1a529-107">`IndexerName` 用于表示任何以下三个选项：</span><span class="sxs-lookup"><span data-stu-id="1a529-107">`IndexerName` is used to represent any of the three options below:</span></span>


## <a name="syntax"></a><span data-ttu-id="1a529-108">语法</span><span class="sxs-lookup"><span data-stu-id="1a529-108">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="1a529-109">备注</span><span class="sxs-lookup"><span data-stu-id="1a529-109">Remarks</span></span>
<span data-ttu-id="1a529-110">前面的语法中的窗体演示如何定义同时具有的索引的属性`get`和`set`方法，具有`get`方法仅，或具有`set`仅限方法。</span><span class="sxs-lookup"><span data-stu-id="1a529-110">The forms of the previous syntax show how to define indexed properties that have both a `get` and a `set` method, have a `get` method only, or have a `set` method only.</span></span> <span data-ttu-id="1a529-111">此外可以将两者结合使用仅限获取和集仅，所示的语法所示的语法，并生成具有 get 和 set 的属性。</span><span class="sxs-lookup"><span data-stu-id="1a529-111">You can also combine both the syntax shown for get only and the syntax shown for set only, and produce a property that has both get and set.</span></span> <span data-ttu-id="1a529-112">此后一种形式，可将不同的可访问性修饰符和属性放在 get 和 set 方法。</span><span class="sxs-lookup"><span data-stu-id="1a529-112">This latter form allows you to put different accessibility modifiers and attributes on the get and set methods.</span></span>

<span data-ttu-id="1a529-113">当*IndexerName*是`Item`，编译器将视为默认索引属性的属性。</span><span class="sxs-lookup"><span data-stu-id="1a529-113">When the *IndexerName* is `Item`, the compiler treats the property as a default indexed property.</span></span> <span data-ttu-id="1a529-114">A*默认索引属性*是一个属性，可以访问的对象实例上使用类似于数组的语法。</span><span class="sxs-lookup"><span data-stu-id="1a529-114">A *default indexed property* is a property that you can access by using array-like syntax on the object instance.</span></span> <span data-ttu-id="1a529-115">例如，如果`obj`是定义此属性，语法的类型的对象`obj.[index]`用于访问属性。</span><span class="sxs-lookup"><span data-stu-id="1a529-115">For example, if `obj` is an object of the type that defines this property, the syntax `obj.[index]` is used to access the property.</span></span>

<span data-ttu-id="1a529-116">用于访问非默认索引属性的语法是提供属性和在括号中的索引的名称。</span><span class="sxs-lookup"><span data-stu-id="1a529-116">The syntax for accessing a nondefault indexed property is to provide the name of the property and the index in parentheses.</span></span> <span data-ttu-id="1a529-117">例如，如果该属性是`Ordinal`，你编写`obj.Ordinal(index)`来访问它。</span><span class="sxs-lookup"><span data-stu-id="1a529-117">For example, if the property is `Ordinal`, you write `obj.Ordinal(index)` to access it.</span></span>

<span data-ttu-id="1a529-118">无论你使用的形式，你应始终使用的扩充窗体`set`索引属性的方法。</span><span class="sxs-lookup"><span data-stu-id="1a529-118">Regardless of which form you use, you should always use the curried form for the `set` method on an indexed property.</span></span> <span data-ttu-id="1a529-119">扩充函数有关的信息，请参阅[函数](../functions/index.md)。</span><span class="sxs-lookup"><span data-stu-id="1a529-119">For information about curried functions, see [Functions](../functions/index.md).</span></span>

## <a name="example"></a><span data-ttu-id="1a529-120">示例</span><span class="sxs-lookup"><span data-stu-id="1a529-120">Example</span></span>

<span data-ttu-id="1a529-121">下面的代码示例演示的定义和使用的默认和非默认索引的属性的具有 get 和 set 方法。</span><span class="sxs-lookup"><span data-stu-id="1a529-121">The following code example illustrates the definition and use of default and non-default indexed properties that have get and set methods.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3301.fs)]

## <a name="output"></a><span data-ttu-id="1a529-122">输出</span><span class="sxs-lookup"><span data-stu-id="1a529-122">Output</span></span>

```
ONE two three four five six seven eight nine ten
ONE first two second three third four fourth five fifth six 6th
seven seventh eight eighth nine ninth ten tenth
```

## <a name="indexed-properties-with-multiple-index-variables"></a><span data-ttu-id="1a529-123">使用多个索引变量的索引的属性</span><span class="sxs-lookup"><span data-stu-id="1a529-123">Indexed Properties with Multiple Index Variables</span></span>
<span data-ttu-id="1a529-124">索引的属性可以具有多个索引变量。</span><span class="sxs-lookup"><span data-stu-id="1a529-124">Indexed properties can have more than one index variable.</span></span> <span data-ttu-id="1a529-125">在这种情况下，变量用逗号分隔时使用的属性。</span><span class="sxs-lookup"><span data-stu-id="1a529-125">In that case, the variables are separated by commas when the property is used.</span></span> <span data-ttu-id="1a529-126">在这种属性中的 set 方法必须具有两个扩充的参数，其中第一个是包含键，一个元组和第二个是正在设置的值。</span><span class="sxs-lookup"><span data-stu-id="1a529-126">The set method in such a property must have two curried arguments, the first of which is a tuple containing the keys, and the second of which is the value being set.</span></span>

<span data-ttu-id="1a529-127">下面的代码演示了利用的多个索引变量的索引属性。</span><span class="sxs-lookup"><span data-stu-id="1a529-127">The following code demonstrates the use of an indexed property with multiple index variables.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3302.fs)]
    
## <a name="see-also"></a><span data-ttu-id="1a529-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="1a529-128">See Also</span></span>
[<span data-ttu-id="1a529-129">成员</span><span class="sxs-lookup"><span data-stu-id="1a529-129">Members</span></span>](index.md)
