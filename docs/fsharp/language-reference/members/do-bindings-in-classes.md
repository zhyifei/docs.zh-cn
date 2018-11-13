---
title: 类中的 do 绑定 (F#)
description: 了解如何使用 F# do 中的类定义，当构造对象或首次使用该类型时将执行操作的绑定。
ms.date: 05/16/2016
ms.openlocfilehash: e54a5bde52bf6973cc338c929ba99e6fd5b53127
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "43801513"
---
# <a name="do-bindings-in-classes"></a><span data-ttu-id="bb133-103">类中的 do 绑定</span><span class="sxs-lookup"><span data-stu-id="bb133-103">do Bindings in Classes</span></span>

<span data-ttu-id="bb133-104">一个`do`绑定类定义中的执行操作，当构造对象或时，对于静态`do`绑定，类型首次使用时。</span><span class="sxs-lookup"><span data-stu-id="bb133-104">A `do` binding in a class definition performs actions when the object is constructed or, for a static `do` binding, when the type is first used.</span></span>

## <a name="syntax"></a><span data-ttu-id="bb133-105">语法</span><span class="sxs-lookup"><span data-stu-id="bb133-105">Syntax</span></span>

```fsharp
[static] do expression
```

## <a name="remarks"></a><span data-ttu-id="bb133-106">备注</span><span class="sxs-lookup"><span data-stu-id="bb133-106">Remarks</span></span>

<span data-ttu-id="bb133-107">一个`do`一起使用或者之后，会显示绑定`let`绑定类定义中的成员定义之前。</span><span class="sxs-lookup"><span data-stu-id="bb133-107">A `do` binding appears together with or after `let` bindings but before member definitions in a class definition.</span></span> <span data-ttu-id="bb133-108">尽管`do`关键字是可选的`do`绑定在模块级别，它不是可选的`do`类定义中的绑定。</span><span class="sxs-lookup"><span data-stu-id="bb133-108">Although the `do` keyword is optional for `do` bindings at the module level, it is not optional for `do` bindings in a class definition.</span></span>

<span data-ttu-id="bb133-109">有关构造的每个对象的任何给定类型，非静态`do`绑定和非静态`let`类定义中出现的顺序会执行绑定。</span><span class="sxs-lookup"><span data-stu-id="bb133-109">For the construction of every object of any given type, non-static `do` bindings and non-static `let` bindings are executed in the order in which they appear in the class definition.</span></span> <span data-ttu-id="bb133-110">多个`do`绑定可以出现在一个类型中。</span><span class="sxs-lookup"><span data-stu-id="bb133-110">Multiple `do` bindings can occur in one type.</span></span> <span data-ttu-id="bb133-111">非静态`let`绑定和非静态`do`绑定将成为主构造函数的主体。</span><span class="sxs-lookup"><span data-stu-id="bb133-111">The non-static `let` bindings and the non-static `do` bindings become the body of the primary constructor.</span></span> <span data-ttu-id="bb133-112">中非静态的代码`do`主构造函数参数和任何值或函数中定义的绑定节可以引用`let`绑定部分。</span><span class="sxs-lookup"><span data-stu-id="bb133-112">The code in the non-static `do` bindings section can reference the primary constructor parameters and any values or functions that are defined in the `let` bindings section.</span></span>

<span data-ttu-id="bb133-113">非静态`do`绑定可以访问类的成员，只要类具有定义的自我标识符`as`类标题，并，只要这些成员的所有使用都限定为类的自我标识符中的关键字。</span><span class="sxs-lookup"><span data-stu-id="bb133-113">Non-static `do` bindings can access members of the class as long as the class has a self identifier that is defined by an `as` keyword in the class heading, and as long as all uses of those members are qualified with the self identifier for the class.</span></span>

<span data-ttu-id="bb133-114">因为`let`绑定将初始化一个类，这通常是为保证成员正常工作所必需的私有字段`do`绑定通常置于后`let`绑定中的代码的因此`do`绑定可以执行完全初始化的对象。</span><span class="sxs-lookup"><span data-stu-id="bb133-114">Because `let` bindings initialize the private fields of a class, which is often necessary to guarantee that members behave as expected, `do` bindings are usually put after `let` bindings so that code in the `do` binding can execute with a fully initialized object.</span></span> <span data-ttu-id="bb133-115">如果你的代码尝试使用成员初始化完成之前，将引发 InvalidOperationException。</span><span class="sxs-lookup"><span data-stu-id="bb133-115">If your code attempts to use a member before the initialization is complete, an InvalidOperationException is raised.</span></span>

<span data-ttu-id="bb133-116">静态`do`绑定可以引用静态成员或字段的封闭类，但不是实例成员或字段。</span><span class="sxs-lookup"><span data-stu-id="bb133-116">Static `do` bindings can reference static members or fields of the enclosing class but not instance members or fields.</span></span> <span data-ttu-id="bb133-117">静态`do`绑定将成为类，该类可保证执行之前先使用类的静态初始值设定项的一部分。</span><span class="sxs-lookup"><span data-stu-id="bb133-117">Static `do` bindings become part of the static initializer for the class, which is guaranteed to execute before the class is first used.</span></span>

<span data-ttu-id="bb133-118">属性被忽略的`do`中类型的绑定。</span><span class="sxs-lookup"><span data-stu-id="bb133-118">Attributes are ignored for `do` bindings in types.</span></span> <span data-ttu-id="bb133-119">如果属性是必需执行中的代码的`do`绑定，它必须将应用于主构造函数。</span><span class="sxs-lookup"><span data-stu-id="bb133-119">If an attribute is required for code that executes in a `do` binding, it must be applied to the primary constructor.</span></span>

<span data-ttu-id="bb133-120">在下面的代码中，类具有一个静态`do`绑定和非静态`do`绑定。</span><span class="sxs-lookup"><span data-stu-id="bb133-120">In the following code, a class has a static `do` binding and a non-static `do` binding.</span></span> <span data-ttu-id="bb133-121">该对象具有两个参数的构造函数`a`并`b`，和两个私有字段中定义`let`类的绑定。</span><span class="sxs-lookup"><span data-stu-id="bb133-121">The object has a constructor that has two parameters, `a` and `b`, and two private fields are defined in the `let` bindings for the class.</span></span> <span data-ttu-id="bb133-122">此外定义了两个属性。</span><span class="sxs-lookup"><span data-stu-id="bb133-122">Two properties are also defined.</span></span> <span data-ttu-id="bb133-123">所有这些处于作用域内非静态`do`绑定部分中，通过将所有这些值输出的行所示。</span><span class="sxs-lookup"><span data-stu-id="bb133-123">All of these are in scope in the non-static `do` bindings section, as is illustrated by the line that prints all those values.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3101.fs)]

<span data-ttu-id="bb133-124">输出如下所示。</span><span class="sxs-lookup"><span data-stu-id="bb133-124">The output is as follows.</span></span>

```console
Initializing MyType.
Initializing object 1 2 2 4 8 16
```

## <a name="see-also"></a><span data-ttu-id="bb133-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="bb133-125">See also</span></span>

- [<span data-ttu-id="bb133-126">成员</span><span class="sxs-lookup"><span data-stu-id="bb133-126">Members</span></span>](index.md)
- [<span data-ttu-id="bb133-127">类</span><span class="sxs-lookup"><span data-stu-id="bb133-127">Classes</span></span>](../classes.md)
- [<span data-ttu-id="bb133-128">构造函数</span><span class="sxs-lookup"><span data-stu-id="bb133-128">Constructors</span></span>](constructors.md)
- [<span data-ttu-id="bb133-129">类中的 `let` 绑定</span><span class="sxs-lookup"><span data-stu-id="bb133-129">`let` Bindings in Classes</span></span>](let-bindings-in-classes.md)
- [<span data-ttu-id="bb133-130">`do` 绑定</span><span class="sxs-lookup"><span data-stu-id="bb133-130">`do` Bindings</span></span>](../functions/do-Bindings.md)
