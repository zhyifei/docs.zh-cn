---
title: "类中的 do 绑定 (F#)"
description: "了解如何使用 F # do 在类定义中，该对象构造时或者如果第一次使用类型执行操作的绑定。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 78987cb8-bdba-46e2-b5b2-994c83fe42c4
ms.openlocfilehash: f9582338306d87c3dd799425083037cc95b31b1e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="do-bindings-in-classes"></a><span data-ttu-id="ec0bb-104">类中的 do 绑定</span><span class="sxs-lookup"><span data-stu-id="ec0bb-104">do Bindings in Classes</span></span>

<span data-ttu-id="ec0bb-105">A`do`类定义中的绑定操作时，对象构造或者执行，对于静态`do`绑定，当类型是首次使用。</span><span class="sxs-lookup"><span data-stu-id="ec0bb-105">A `do` binding in a class definition performs actions when the object is constructed or, for a static `do` binding, when the type is first used.</span></span>


## <a name="syntax"></a><span data-ttu-id="ec0bb-106">语法</span><span class="sxs-lookup"><span data-stu-id="ec0bb-106">Syntax</span></span>

```fsharp
[static] do expression
```

## <a name="remarks"></a><span data-ttu-id="ec0bb-107">备注</span><span class="sxs-lookup"><span data-stu-id="ec0bb-107">Remarks</span></span>
<span data-ttu-id="ec0bb-108">A`do`绑定出现连同或之后`let`绑定但之前的类定义中的成员定义。</span><span class="sxs-lookup"><span data-stu-id="ec0bb-108">A `do` binding appears together with or after `let` bindings but before member definitions in a class definition.</span></span> <span data-ttu-id="ec0bb-109">尽管`do`关键字是可选的`do`绑定在模块级别中，为不可选`do`类定义中的绑定。</span><span class="sxs-lookup"><span data-stu-id="ec0bb-109">Although the `do` keyword is optional for `do` bindings at the module level, it is not optional for `do` bindings in a class definition.</span></span>

<span data-ttu-id="ec0bb-110">有关构造的每个对象的任何给定类型，非静态`do`绑定和非静态`let`绑定执行类定义中出现的顺序。</span><span class="sxs-lookup"><span data-stu-id="ec0bb-110">For the construction of every object of any given type, non-static `do` bindings and non-static `let` bindings are executed in the order in which they appear in the class definition.</span></span> <span data-ttu-id="ec0bb-111">多个`do`绑定可以出现在一个类型。</span><span class="sxs-lookup"><span data-stu-id="ec0bb-111">Multiple `do` bindings can occur in one type.</span></span> <span data-ttu-id="ec0bb-112">非静态`let`绑定和非静态`do`绑定成为主构造函数的主体。</span><span class="sxs-lookup"><span data-stu-id="ec0bb-112">The non-static `let` bindings and the non-static `do` bindings become the body of the primary constructor.</span></span> <span data-ttu-id="ec0bb-113">中非静态的代码`do`主构造函数参数和任何值或定义中的函数，可以引用绑定部分`let`绑定部分。</span><span class="sxs-lookup"><span data-stu-id="ec0bb-113">The code in the non-static `do` bindings section can reference the primary constructor parameters and any values or functions that are defined in the `let` bindings section.</span></span>

<span data-ttu-id="ec0bb-114">非静态`do`绑定可以访问类的成员，只要类具有定义的自我标识符`as`类列名，和，只要这些成员的所有使用都限定为类的自我标识符中的关键字。</span><span class="sxs-lookup"><span data-stu-id="ec0bb-114">Non-static `do` bindings can access members of the class as long as the class has a self identifier that is defined by an `as` keyword in the class heading, and as long as all uses of those members are qualified with the self identifier for the class.</span></span>

<span data-ttu-id="ec0bb-115">因为`let`绑定初始化的私有字段的一个类，这通常是为保证成员正常工作所必需的`do`绑定通常置于后`let`绑定中的代码以便`do`绑定可以执行完全初始化的对象。</span><span class="sxs-lookup"><span data-stu-id="ec0bb-115">Because `let` bindings initialize the private fields of a class, which is often necessary to guarantee that members behave as expected, `do` bindings are usually put after `let` bindings so that code in the `do` binding can execute with a fully initialized object.</span></span> <span data-ttu-id="ec0bb-116">如果你的代码尝试使用成员之前初始化已完成，将引发 InvalidOperationException。</span><span class="sxs-lookup"><span data-stu-id="ec0bb-116">If your code attempts to use a member before the initialization is complete, an InvalidOperationException is raised.</span></span>

<span data-ttu-id="ec0bb-117">静态`do`绑定可以引用静态成员或字段的封闭类，但不是实例成员或字段。</span><span class="sxs-lookup"><span data-stu-id="ec0bb-117">Static `do` bindings can reference static members or fields of the enclosing class but not instance members or fields.</span></span> <span data-ttu-id="ec0bb-118">静态`do`绑定成为类，该类可保证执行之前第一次使用类的静态初始值设定项的一部分。</span><span class="sxs-lookup"><span data-stu-id="ec0bb-118">Static `do` bindings become part of the static initializer for the class, which is guaranteed to execute before the class is first used.</span></span>

<span data-ttu-id="ec0bb-119">属性为忽略`do`类型中的绑定。</span><span class="sxs-lookup"><span data-stu-id="ec0bb-119">Attributes are ignored for `do` bindings in types.</span></span> <span data-ttu-id="ec0bb-120">如果属性是必需中执行的代码的`do`绑定，它必须将应用于主构造函数。</span><span class="sxs-lookup"><span data-stu-id="ec0bb-120">If an attribute is required for code that executes in a `do` binding, it must be applied to the primary constructor.</span></span>

<span data-ttu-id="ec0bb-121">在下面的代码中，类具有静态`do`绑定和非静态`do`绑定。</span><span class="sxs-lookup"><span data-stu-id="ec0bb-121">In the following code, a class has a static `do` binding and a non-static `do` binding.</span></span> <span data-ttu-id="ec0bb-122">该对象具有具有两个参数的构造函数`a`和`b`，并且两个私有字段将在定义`let`类的绑定。</span><span class="sxs-lookup"><span data-stu-id="ec0bb-122">The object has a constructor that has two parameters, `a` and `b`, and two private fields are defined in the `let` bindings for the class.</span></span> <span data-ttu-id="ec0bb-123">此外定义了两个属性。</span><span class="sxs-lookup"><span data-stu-id="ec0bb-123">Two properties are also defined.</span></span> <span data-ttu-id="ec0bb-124">所有这些都在非静态的范围内`do`绑定部分中，将所有这些值输出的行所示。</span><span class="sxs-lookup"><span data-stu-id="ec0bb-124">All of these are in scope in the non-static `do` bindings section, as is illustrated by the line that prints all those values.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3101.fs)]

<span data-ttu-id="ec0bb-125">输出如下所示。</span><span class="sxs-lookup"><span data-stu-id="ec0bb-125">The output is as follows.</span></span>

```console
Initializing MyType.
Initializing object 1 2 2 4 8 16
```

## <a name="see-also"></a><span data-ttu-id="ec0bb-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ec0bb-126">See Also</span></span>
[<span data-ttu-id="ec0bb-127">成员</span><span class="sxs-lookup"><span data-stu-id="ec0bb-127">Members</span></span>](index.md)

[<span data-ttu-id="ec0bb-128">类</span><span class="sxs-lookup"><span data-stu-id="ec0bb-128">Classes</span></span>](../classes.md)

[<span data-ttu-id="ec0bb-129">构造函数</span><span class="sxs-lookup"><span data-stu-id="ec0bb-129">Constructors</span></span>](constructors.md)

[<span data-ttu-id="ec0bb-130">类中的 `let` 绑定</span><span class="sxs-lookup"><span data-stu-id="ec0bb-130">`let` Bindings in Classes</span></span>](let-bindings-in-classes.md)

[<span data-ttu-id="ec0bb-131">`do`绑定</span><span class="sxs-lookup"><span data-stu-id="ec0bb-131">`do` Bindings</span></span>](../functions/do-Bindings.md)
