---
title: 索引属性 (F#)
description: '了解有关 F # 索引属性，这些属性提供对已排序的数据类似数组的访问。'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 39396b3a5ec43f9a8ab0df96afeb69e05801c752
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2018
---
# <a name="indexed-properties"></a><span data-ttu-id="ebcfd-103">索引属性</span><span class="sxs-lookup"><span data-stu-id="ebcfd-103">Indexed Properties</span></span>

<span data-ttu-id="ebcfd-104">*索引属性*提供对类似数组的访问的属性排序数据。</span><span class="sxs-lookup"><span data-stu-id="ebcfd-104">*Indexed properties* are properties that provide array-like access to ordered data.</span></span>


## <a name="syntax"></a><span data-ttu-id="ebcfd-105">语法</span><span class="sxs-lookup"><span data-stu-id="ebcfd-105">Syntax</span></span>

```fsharp
// Indexed property that has both get and set defined.
member self-identifier.PropertyName
    with get(index-variable) =
        get-function-body
    and set index-variablesvalue-variables =
        set-function-body

// Indexed property that has get only.
member self-identifier.PropertyName(index-variable) =
    get-function-body

// Alternative syntax for indexed property with get only
member self-identifier.PropertyName
    with get(index-variables) =
        get-function-body

// Indexed property that has set only.
member self-identifier.PropertyName
    with set index-variablesvalue-variables = 
        set-function-body
```

## <a name="remarks"></a><span data-ttu-id="ebcfd-106">备注</span><span class="sxs-lookup"><span data-stu-id="ebcfd-106">Remarks</span></span>
<span data-ttu-id="ebcfd-107">前面的语法中的三个窗体演示如何定义同时具有的索引的属性`get`和`set`方法，具有`get`方法仅，或具有`set`仅限方法。</span><span class="sxs-lookup"><span data-stu-id="ebcfd-107">The three forms of the previous syntax show how to define indexed properties that have both a `get` and a `set` method, have a `get` method only, or have a `set` method only.</span></span> <span data-ttu-id="ebcfd-108">此外可以将两者结合使用仅限获取和集仅，所示的语法所示的语法，并生成具有 get 和 set 的属性。</span><span class="sxs-lookup"><span data-stu-id="ebcfd-108">You can also combine both the syntax shown for get only and the syntax shown for set only, and produce a property that has both get and set.</span></span> <span data-ttu-id="ebcfd-109">此后一种形式，可将不同的可访问性修饰符和属性放在 get 和 set 方法。</span><span class="sxs-lookup"><span data-stu-id="ebcfd-109">This latter form allows you to put different accessibility modifiers and attributes on the get and set methods.</span></span>

<span data-ttu-id="ebcfd-110">当*PropertyName*是`Item`，编译器将视为默认索引属性的属性。</span><span class="sxs-lookup"><span data-stu-id="ebcfd-110">When the *PropertyName* is `Item`, the compiler treats the property as a default indexed property.</span></span> <span data-ttu-id="ebcfd-111">A*默认索引属性*是一个属性，可以访问的对象实例上使用类似于数组的语法。</span><span class="sxs-lookup"><span data-stu-id="ebcfd-111">A *default indexed property* is a property that you can access by using array-like syntax on the object instance.</span></span> <span data-ttu-id="ebcfd-112">例如，如果`obj`是定义此属性，语法的类型的对象`obj.[index]`用于访问属性。</span><span class="sxs-lookup"><span data-stu-id="ebcfd-112">For example, if `obj` is an object of the type that defines this property, the syntax `obj.[index]` is used to access the property.</span></span>

<span data-ttu-id="ebcfd-113">用于访问非默认索引属性的语法是提供属性和在括号中的索引的名称。</span><span class="sxs-lookup"><span data-stu-id="ebcfd-113">The syntax for accessing a nondefault indexed property is to provide the name of the property and the index in parentheses.</span></span> <span data-ttu-id="ebcfd-114">例如，如果该属性是`Ordinal`，你编写`obj.Ordinal(index)`来访问它。</span><span class="sxs-lookup"><span data-stu-id="ebcfd-114">For example, if the property is `Ordinal`, you write `obj.Ordinal(index)` to access it.</span></span>

<span data-ttu-id="ebcfd-115">无论你使用的形式，你应始终使用的扩充窗体`set`索引属性的方法。</span><span class="sxs-lookup"><span data-stu-id="ebcfd-115">Regardless of which form you use, you should always use the curried form for the `set` method on an indexed property.</span></span> <span data-ttu-id="ebcfd-116">扩充函数有关的信息，请参阅[函数](../functions/index.md)。</span><span class="sxs-lookup"><span data-stu-id="ebcfd-116">For information about curried functions, see [Functions](../functions/index.md).</span></span>

## <a name="example"></a><span data-ttu-id="ebcfd-117">示例</span><span class="sxs-lookup"><span data-stu-id="ebcfd-117">Example</span></span>

<span data-ttu-id="ebcfd-118">下面的代码示例演示的定义和使用的默认和非默认索引的属性的具有 get 和 set 方法。</span><span class="sxs-lookup"><span data-stu-id="ebcfd-118">The following code example illustrates the definition and use of default and non-default indexed properties that have get and set methods.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3301.fs)]

## <a name="output"></a><span data-ttu-id="ebcfd-119">输出</span><span class="sxs-lookup"><span data-stu-id="ebcfd-119">Output</span></span>

```
ONE two three four five six seven eight nine ten
ONE first two second three third four fourth five fifth six 6th
seven seventh eight eighth nine ninth ten tenth
```

## <a name="indexed-properties-with-multiple-index-variables"></a><span data-ttu-id="ebcfd-120">使用多个索引变量的索引的属性</span><span class="sxs-lookup"><span data-stu-id="ebcfd-120">Indexed Properties with Multiple Index Variables</span></span>
<span data-ttu-id="ebcfd-121">索引的属性可以具有多个索引变量。</span><span class="sxs-lookup"><span data-stu-id="ebcfd-121">Indexed properties can have more than one index variable.</span></span> <span data-ttu-id="ebcfd-122">在这种情况下，变量用逗号分隔时使用的属性。</span><span class="sxs-lookup"><span data-stu-id="ebcfd-122">In that case, the variables are separated by commas when the property is used.</span></span> <span data-ttu-id="ebcfd-123">在这种属性中的 set 方法必须具有两个扩充的参数，其中第一个是包含键，一个元组和第二个是正在设置的值。</span><span class="sxs-lookup"><span data-stu-id="ebcfd-123">The set method in such a property must have two curried arguments, the first of which is a tuple containing the keys, and the second of which is the value being set.</span></span>

<span data-ttu-id="ebcfd-124">下面的代码演示了利用的多个索引变量的索引属性。</span><span class="sxs-lookup"><span data-stu-id="ebcfd-124">The following code demonstrates the use of an indexed property with multiple index variables.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3302.fs)]
    
## <a name="see-also"></a><span data-ttu-id="ebcfd-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="ebcfd-125">See Also</span></span>
[<span data-ttu-id="ebcfd-126">成员</span><span class="sxs-lookup"><span data-stu-id="ebcfd-126">Members</span></span>](index.md)
