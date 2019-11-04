---
title: 访问控制
description: 了解如何以F#编程语言控制对编程元素（如类型、方法和函数）的访问。
ms.date: 05/16/2016
ms.openlocfilehash: fe204a883a440794fdd033c54d6d8d4fb68e0ce2
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2019
ms.locfileid: "73425114"
---
# <a name="access-control"></a><span data-ttu-id="2d055-103">访问控制</span><span class="sxs-lookup"><span data-stu-id="2d055-103">Access Control</span></span>

<span data-ttu-id="2d055-104">*访问控制*是指声明哪些客户端可以使用某些程序元素，例如类型、方法和函数。</span><span class="sxs-lookup"><span data-stu-id="2d055-104">*Access control* refers to declaring which clients can use certain program elements, such as types, methods, and functions.</span></span>

## <a name="basics-of-access-control"></a><span data-ttu-id="2d055-105">访问控制基础知识</span><span class="sxs-lookup"><span data-stu-id="2d055-105">Basics of Access Control</span></span>

<span data-ttu-id="2d055-106">在F#中，可以将访问控制说明符 `public`、`internal`和 `private` 应用于模块、类型、方法、值定义、函数、属性和显式字段。</span><span class="sxs-lookup"><span data-stu-id="2d055-106">In F#, the access control specifiers `public`, `internal`, and `private` can be applied to modules, types, methods, value definitions, functions, properties, and explicit fields.</span></span>

- <span data-ttu-id="2d055-107">`public` 指示所有调用方都可以访问该实体。</span><span class="sxs-lookup"><span data-stu-id="2d055-107">`public` indicates that the entity can be accessed by all callers.</span></span>

- <span data-ttu-id="2d055-108">`internal` 指示只能从同一程序集访问实体。</span><span class="sxs-lookup"><span data-stu-id="2d055-108">`internal` indicates that the entity can be accessed only from the same assembly.</span></span>

- <span data-ttu-id="2d055-109">`private` 指示只能从封闭类型或模块访问实体。</span><span class="sxs-lookup"><span data-stu-id="2d055-109">`private` indicates that the entity can be accessed only from the enclosing type or module.</span></span>

> [!NOTE]
> <span data-ttu-id="2d055-110">访问说明符 `protected` 未在中F#使用，但如果您使用的是在支持 `protected` 访问的语言中创作的类型，则可接受。</span><span class="sxs-lookup"><span data-stu-id="2d055-110">The access specifier `protected` is not used in F#, although it is acceptable if you are using types authored in languages that do support `protected` access.</span></span> <span data-ttu-id="2d055-111">因此，如果你重写受保护的方法，则方法只能在类及其子代内访问。</span><span class="sxs-lookup"><span data-stu-id="2d055-111">Therefore, if you override a protected method, your method remains accessible only within the class and its descendents.</span></span>

<span data-ttu-id="2d055-112">通常，说明符放置在实体名称之前，但在使用 `mutable` 或 `inline` 说明符时除外，后者显示在访问控制说明符之后。</span><span class="sxs-lookup"><span data-stu-id="2d055-112">In general, the specifier is put in front of the name of the entity, except when a `mutable` or `inline` specifier is used, which appear after the access control specifier.</span></span>

<span data-ttu-id="2d055-113">如果未使用任何访问说明符，则默认值为 `public`，类型中的 `let` 绑定（始终 `private` 类型）除外。</span><span class="sxs-lookup"><span data-stu-id="2d055-113">If no access specifier is used, the default is `public`, except for `let` bindings in a type, which are always `private` to the type.</span></span>

<span data-ttu-id="2d055-114">中的F#签名提供了另一种机制F#来控制对程序元素的访问。</span><span class="sxs-lookup"><span data-stu-id="2d055-114">Signatures in F# provide another mechanism for controlling access to F# program elements.</span></span> <span data-ttu-id="2d055-115">访问控制不需要签名。</span><span class="sxs-lookup"><span data-stu-id="2d055-115">Signatures are not required for access control.</span></span> <span data-ttu-id="2d055-116">有关详细信息，请参阅[签名](signature-files.md)。</span><span class="sxs-lookup"><span data-stu-id="2d055-116">For more information, see [Signatures](signature-files.md).</span></span>

## <a name="rules-for-access-control"></a><span data-ttu-id="2d055-117">访问控制规则</span><span class="sxs-lookup"><span data-stu-id="2d055-117">Rules for Access Control</span></span>

<span data-ttu-id="2d055-118">访问控制遵循以下规则：</span><span class="sxs-lookup"><span data-stu-id="2d055-118">Access control is subject to the following rules:</span></span>

- <span data-ttu-id="2d055-119">继承声明（即，使用 `inherit` 来指定类的基类）、接口声明（即指定类实现接口），而抽象成员始终具有与封闭类型相同的可访问性。</span><span class="sxs-lookup"><span data-stu-id="2d055-119">Inheritance declarations (that is, the use of `inherit` to specify a base class for a class), interface declarations (that is, specifying that a class implements an interface), and abstract members always have the same accessibility as the enclosing type.</span></span> <span data-ttu-id="2d055-120">因此，不能对这些构造使用访问控制说明符。</span><span class="sxs-lookup"><span data-stu-id="2d055-120">Therefore, an access control specifier cannot be used on these constructs.</span></span>

- <span data-ttu-id="2d055-121">可区分联合中各个事例的可访问性取决于可区分联合本身的可访问性。</span><span class="sxs-lookup"><span data-stu-id="2d055-121">Accessibility for individual cases in a discriminated union is determined by the accessibility of the discriminated union itself.</span></span> <span data-ttu-id="2d055-122">也就是说，特定联合用例的可访问性不如联合本身。</span><span class="sxs-lookup"><span data-stu-id="2d055-122">That is, a particular union case is no less accessible than the union itself.</span></span>

- <span data-ttu-id="2d055-123">记录类型的单个字段的可访问性由记录本身的可访问性决定。</span><span class="sxs-lookup"><span data-stu-id="2d055-123">Accessibility for individual fields of a record type is determined by the accessibility of the record itself.</span></span> <span data-ttu-id="2d055-124">也就是说，特定记录标签的可访问性比记录本身的可访问性低。</span><span class="sxs-lookup"><span data-stu-id="2d055-124">That is, a particular record label is no less accessible than the record itself.</span></span>

## <a name="example"></a><span data-ttu-id="2d055-125">示例</span><span class="sxs-lookup"><span data-stu-id="2d055-125">Example</span></span>

<span data-ttu-id="2d055-126">下面的代码演示如何使用访问控制说明符。</span><span class="sxs-lookup"><span data-stu-id="2d055-126">The following code illustrates the use of access control specifiers.</span></span> <span data-ttu-id="2d055-127">项目中有两个文件，`Module1.fs` 和 `Module2.fs`。</span><span class="sxs-lookup"><span data-stu-id="2d055-127">There are two files in the project, `Module1.fs` and `Module2.fs`.</span></span> <span data-ttu-id="2d055-128">每个文件都是隐式的模块。</span><span class="sxs-lookup"><span data-stu-id="2d055-128">Each file is implicitly a module.</span></span> <span data-ttu-id="2d055-129">因此，`Module1` 和 `Module2`有两个模块。</span><span class="sxs-lookup"><span data-stu-id="2d055-129">Therefore, there are two modules, `Module1` and `Module2`.</span></span> <span data-ttu-id="2d055-130">私有类型和内部类型是在 `Module1`中定义的。</span><span class="sxs-lookup"><span data-stu-id="2d055-130">A private type and an internal type are defined in `Module1`.</span></span> <span data-ttu-id="2d055-131">无法从 `Module2`访问私有类型，但内部类型可以。</span><span class="sxs-lookup"><span data-stu-id="2d055-131">The private type cannot be accessed from `Module2`, but the internal type can.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/access-control/snippet1.fs)]

<span data-ttu-id="2d055-132">下面的代码测试在 `Module1.fs`中创建的类型的可访问性。</span><span class="sxs-lookup"><span data-stu-id="2d055-132">The following code tests the accessibility of the types created in `Module1.fs`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/access-control/snippet2.fs)]

## <a name="see-also"></a><span data-ttu-id="2d055-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="2d055-133">See also</span></span>

- [<span data-ttu-id="2d055-134">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="2d055-134">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="2d055-135">签名</span><span class="sxs-lookup"><span data-stu-id="2d055-135">Signatures</span></span>](signature-files.md)
