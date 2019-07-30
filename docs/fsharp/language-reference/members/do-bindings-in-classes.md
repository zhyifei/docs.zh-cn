---
title: 类中的 do 绑定
description: 了解如何在类定义F#中使用 "do" 绑定, 此类定义在构造对象或首次使用类型时执行操作。
ms.date: 05/16/2016
ms.openlocfilehash: ced4f1bb17d9e23bf51cc79b5a275cc334cca013
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627585"
---
# <a name="do-bindings-in-classes"></a><span data-ttu-id="1a84f-103">类中的 do 绑定</span><span class="sxs-lookup"><span data-stu-id="1a84f-103">do Bindings in Classes</span></span>

<span data-ttu-id="1a84f-104">构造`do`对象时, 类定义中的绑定将执行操作; 对于静态`do`绑定, 在首次使用该类型时执行操作。</span><span class="sxs-lookup"><span data-stu-id="1a84f-104">A `do` binding in a class definition performs actions when the object is constructed or, for a static `do` binding, when the type is first used.</span></span>

## <a name="syntax"></a><span data-ttu-id="1a84f-105">语法</span><span class="sxs-lookup"><span data-stu-id="1a84f-105">Syntax</span></span>

```fsharp
[static] do expression
```

## <a name="remarks"></a><span data-ttu-id="1a84f-106">备注</span><span class="sxs-lookup"><span data-stu-id="1a84f-106">Remarks</span></span>

<span data-ttu-id="1a84f-107">绑定与`let`绑定一起显示, 但在类定义中的成员定义之前。 `do`</span><span class="sxs-lookup"><span data-stu-id="1a84f-107">A `do` binding appears together with or after `let` bindings but before member definitions in a class definition.</span></span> <span data-ttu-id="1a84f-108">尽管关键字对于`do`模块级别的绑定是可选的, 但它对于`do`类定义中的绑定是不可选的。 `do`</span><span class="sxs-lookup"><span data-stu-id="1a84f-108">Although the `do` keyword is optional for `do` bindings at the module level, it is not optional for `do` bindings in a class definition.</span></span>

<span data-ttu-id="1a84f-109">对于任何给定类型的每个对象的构造, 将按照它们`do`在类定义中的`let`显示顺序来执行非静态绑定和非静态绑定。</span><span class="sxs-lookup"><span data-stu-id="1a84f-109">For the construction of every object of any given type, non-static `do` bindings and non-static `let` bindings are executed in the order in which they appear in the class definition.</span></span> <span data-ttu-id="1a84f-110">一`do`种类型可以发生多个绑定。</span><span class="sxs-lookup"><span data-stu-id="1a84f-110">Multiple `do` bindings can occur in one type.</span></span> <span data-ttu-id="1a84f-111">非静态`let`绑定和非静态`do`绑定成为主构造函数的主体。</span><span class="sxs-lookup"><span data-stu-id="1a84f-111">The non-static `let` bindings and the non-static `do` bindings become the body of the primary constructor.</span></span> <span data-ttu-id="1a84f-112">非静态`do`绑定部分中的代码可以引用主构造函数参数以及在 "绑定" `let`部分中定义的任何值或函数。</span><span class="sxs-lookup"><span data-stu-id="1a84f-112">The code in the non-static `do` bindings section can reference the primary constructor parameters and any values or functions that are defined in the `let` bindings section.</span></span>

<span data-ttu-id="1a84f-113">如果类具有`do` `as`由类标题中的关键字定义的自我标识符, 则非静态绑定可以访问类的成员, 只要这些成员的所有使用都是用类的 self 标识符限定的。</span><span class="sxs-lookup"><span data-stu-id="1a84f-113">Non-static `do` bindings can access members of the class as long as the class has a self identifier that is defined by an `as` keyword in the class heading, and as long as all uses of those members are qualified with the self identifier for the class.</span></span>

<span data-ttu-id="1a84f-114">由于`let`绑定初始化类的私有字段, 通常需要确保成员按预期方式运行, 因此绑定通常置于绑定`do`后`let` , 以便`do`绑定中的代码可以使用完全初始化的对象执行。</span><span class="sxs-lookup"><span data-stu-id="1a84f-114">Because `let` bindings initialize the private fields of a class, which is often necessary to guarantee that members behave as expected, `do` bindings are usually put after `let` bindings so that code in the `do` binding can execute with a fully initialized object.</span></span> <span data-ttu-id="1a84f-115">如果你的代码在初始化完成之前尝试使用成员, 则会引发 InvalidOperationException。</span><span class="sxs-lookup"><span data-stu-id="1a84f-115">If your code attempts to use a member before the initialization is complete, an InvalidOperationException is raised.</span></span>

<span data-ttu-id="1a84f-116">静态`do`绑定可以引用封闭类的静态成员或字段, 而不能引用实例成员或字段。</span><span class="sxs-lookup"><span data-stu-id="1a84f-116">Static `do` bindings can reference static members or fields of the enclosing class but not instance members or fields.</span></span> <span data-ttu-id="1a84f-117">静态`do`绑定成为类的静态初始值设定项的一部分, 保证在第一次使用类之前执行。</span><span class="sxs-lookup"><span data-stu-id="1a84f-117">Static `do` bindings become part of the static initializer for the class, which is guaranteed to execute before the class is first used.</span></span>

<span data-ttu-id="1a84f-118">对于类型中的`do`绑定, 将忽略属性。</span><span class="sxs-lookup"><span data-stu-id="1a84f-118">Attributes are ignored for `do` bindings in types.</span></span> <span data-ttu-id="1a84f-119">如果在`do`绑定中执行的代码需要特性, 则必须将该特性应用于主构造函数。</span><span class="sxs-lookup"><span data-stu-id="1a84f-119">If an attribute is required for code that executes in a `do` binding, it must be applied to the primary constructor.</span></span>

<span data-ttu-id="1a84f-120">在下面的代码中, 类具有静态`do`绑定和非静态`do`绑定。</span><span class="sxs-lookup"><span data-stu-id="1a84f-120">In the following code, a class has a static `do` binding and a non-static `do` binding.</span></span> <span data-ttu-id="1a84f-121">对象具有一个构造函数, 该构造函数具有`a`两`b`个参数: 和, 并且在类的`let`绑定中定义了两个私有字段。</span><span class="sxs-lookup"><span data-stu-id="1a84f-121">The object has a constructor that has two parameters, `a` and `b`, and two private fields are defined in the `let` bindings for the class.</span></span> <span data-ttu-id="1a84f-122">还定义了两个属性。</span><span class="sxs-lookup"><span data-stu-id="1a84f-122">Two properties are also defined.</span></span> <span data-ttu-id="1a84f-123">所有这些都在非静态`do`绑定部分的范围内, 如打印所有这些值的行所示。</span><span class="sxs-lookup"><span data-stu-id="1a84f-123">All of these are in scope in the non-static `do` bindings section, as is illustrated by the line that prints all those values.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3101.fs)]

<span data-ttu-id="1a84f-124">输出如下所示。</span><span class="sxs-lookup"><span data-stu-id="1a84f-124">The output is as follows.</span></span>

```console
Initializing MyType.
Initializing object 1 2 2 4 8 16
```

## <a name="see-also"></a><span data-ttu-id="1a84f-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="1a84f-125">See also</span></span>

- [<span data-ttu-id="1a84f-126">成员</span><span class="sxs-lookup"><span data-stu-id="1a84f-126">Members</span></span>](index.md)
- [<span data-ttu-id="1a84f-127">类</span><span class="sxs-lookup"><span data-stu-id="1a84f-127">Classes</span></span>](../classes.md)
- [<span data-ttu-id="1a84f-128">构造函数</span><span class="sxs-lookup"><span data-stu-id="1a84f-128">Constructors</span></span>](constructors.md)
- [<span data-ttu-id="1a84f-129">类中的 `let` 绑定</span><span class="sxs-lookup"><span data-stu-id="1a84f-129">`let` Bindings in Classes</span></span>](let-bindings-in-classes.md)
- [<span data-ttu-id="1a84f-130">`do`绑定</span><span class="sxs-lookup"><span data-stu-id="1a84f-130">`do` Bindings</span></span>](../functions/do-Bindings.md)
