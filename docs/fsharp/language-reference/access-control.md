---
title: "访问控制 (F#)"
description: "了解如何控制到编程元素，如类型、 方法和函数，F # 编程语言中的访问。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 955b06fe-d1cd-431d-8db6-93e83b697453
ms.openlocfilehash: a02e20a585a0456577901f2762a0eeb0e3ecd2f0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="access-control"></a><span data-ttu-id="39f48-104">访问控制</span><span class="sxs-lookup"><span data-stu-id="39f48-104">Access Control</span></span>

<span data-ttu-id="39f48-105">*访问控制*指声明哪些客户端可以使用程序的特定元素，如类型、 方法和函数。</span><span class="sxs-lookup"><span data-stu-id="39f48-105">*Access control* refers to declaring which clients can use certain program elements, such as types, methods, and functions.</span></span>


## <a name="basics-of-access-control"></a><span data-ttu-id="39f48-106">访问控制的基础知识</span><span class="sxs-lookup"><span data-stu-id="39f48-106">Basics of Access Control</span></span>
<span data-ttu-id="39f48-107">在 F # 中，将访问控制说明符`public`， `internal`，和`private`可以应用于模块、 类型、 方法、 值定义、 函数、 属性和显式字段。</span><span class="sxs-lookup"><span data-stu-id="39f48-107">In F#, the access control specifiers `public`, `internal`, and `private` can be applied to modules, types, methods, value definitions, functions, properties, and explicit fields.</span></span>


- <span data-ttu-id="39f48-108">`public`指示所有调用方可以访问该实体。</span><span class="sxs-lookup"><span data-stu-id="39f48-108">`public` indicates that the entity can be accessed by all callers.</span></span>

- <span data-ttu-id="39f48-109">`internal`指示该实体，可以访问只能从同一程序集。</span><span class="sxs-lookup"><span data-stu-id="39f48-109">`internal` indicates that the entity can be accessed only from the same assembly.</span></span>

- <span data-ttu-id="39f48-110">`private`指示该实体，可以访问只能从封闭类型或模块。</span><span class="sxs-lookup"><span data-stu-id="39f48-110">`private` indicates that the entity can be accessed only from the enclosing type or module.</span></span>


>[!NOTE] 
<span data-ttu-id="39f48-111">访问说明符`protected`不用在 F # 中，尽管它是可接受的如果你使用的在支持的语言中编写的类型`protected`访问。</span><span class="sxs-lookup"><span data-stu-id="39f48-111">The access specifier `protected` is not used in F#, although it is acceptable if you are using types authored in languages that do support `protected` access.</span></span> <span data-ttu-id="39f48-112">因此，如果你重写的受保护的方法，仍然只能在类及其后代中访问你的方法。</span><span class="sxs-lookup"><span data-stu-id="39f48-112">Therefore, if you override a protected method, your method remains accessible only within the class and its descendents.</span></span>

<span data-ttu-id="39f48-113">一般情况下，使用说明符放在前面的实体，除非`mutable`或`inline`使用说明符时，在访问控制说明符后显示的哪一。</span><span class="sxs-lookup"><span data-stu-id="39f48-113">In general, the specifier is put in front of the name of the entity, except when a `mutable` or `inline` specifier is used, which appear after the access control specifier.</span></span>

<span data-ttu-id="39f48-114">如果使用没有访问说明符时，默认值是`public`，除`let`类型中的绑定，后者始终是`private`为的类型。</span><span class="sxs-lookup"><span data-stu-id="39f48-114">If no access specifier is used, the default is `public`, except for `let` bindings in a type, which are always `private` to the type.</span></span>

<span data-ttu-id="39f48-115">F # 中的签名提供另一种机制，用于控制对 F # 程序元素的访问。</span><span class="sxs-lookup"><span data-stu-id="39f48-115">Signatures in F# provide another mechanism for controlling access to F# program elements.</span></span> <span data-ttu-id="39f48-116">签名不需要的访问控制。</span><span class="sxs-lookup"><span data-stu-id="39f48-116">Signatures are not required for access control.</span></span> <span data-ttu-id="39f48-117">有关详细信息，请参阅[签名](signatures.md)。</span><span class="sxs-lookup"><span data-stu-id="39f48-117">For more information, see [Signatures](signatures.md).</span></span>


## <a name="rules-for-access-control"></a><span data-ttu-id="39f48-118">访问控制规则</span><span class="sxs-lookup"><span data-stu-id="39f48-118">Rules for Access Control</span></span>
<span data-ttu-id="39f48-119">访问控制是需遵循以下规则：</span><span class="sxs-lookup"><span data-stu-id="39f48-119">Access control is subject to the following rules:</span></span>


- <span data-ttu-id="39f48-120">继承声明 (即，使用`inherit`指定的类的基类)、 接口声明 （即，指定类将实现接口），和抽象成员始终具有与封闭类型相同的可访问性。</span><span class="sxs-lookup"><span data-stu-id="39f48-120">Inheritance declarations (that is, the use of `inherit` to specify a base class for a class), interface declarations (that is, specifying that a class implements an interface), and abstract members always have the same accessibility as the enclosing type.</span></span> <span data-ttu-id="39f48-121">因此，这些构造不能用于访问控制说明符。</span><span class="sxs-lookup"><span data-stu-id="39f48-121">Therefore, an access control specifier cannot be used on these constructs.</span></span>

- <span data-ttu-id="39f48-122">可区分联合中的各个事例不能具有自己独立于联合类型的访问控制修饰符。</span><span class="sxs-lookup"><span data-stu-id="39f48-122">Individual cases in a discriminated union cannot have their own access control modifiers separate from the union type.</span></span>

- <span data-ttu-id="39f48-123">每个字段的记录类型不能具有自己独立于记录类型的访问控制修饰符。</span><span class="sxs-lookup"><span data-stu-id="39f48-123">Individual fields of a record type cannot have their own access control modifiers separate from the record type.</span></span>


## <a name="example"></a><span data-ttu-id="39f48-124">示例</span><span class="sxs-lookup"><span data-stu-id="39f48-124">Example</span></span>
<span data-ttu-id="39f48-125">下面的代码演示如何使用访问控制说明符。</span><span class="sxs-lookup"><span data-stu-id="39f48-125">The following code illustrates the use of access control specifiers.</span></span> <span data-ttu-id="39f48-126">在项目中，有两个文件`Module1.fs`和`Module2.fs`。</span><span class="sxs-lookup"><span data-stu-id="39f48-126">There are two files in the project, `Module1.fs` and `Module2.fs`.</span></span> <span data-ttu-id="39f48-127">每个文件隐式是一个模块。</span><span class="sxs-lookup"><span data-stu-id="39f48-127">Each file is implicitly a module.</span></span> <span data-ttu-id="39f48-128">因此，有两个模块，`Module1`和`Module2`。</span><span class="sxs-lookup"><span data-stu-id="39f48-128">Therefore, there are two modules, `Module1` and `Module2`.</span></span> <span data-ttu-id="39f48-129">中的私有类型和内部类型的定义`Module1`。</span><span class="sxs-lookup"><span data-stu-id="39f48-129">A private type and an internal type are defined in `Module1`.</span></span> <span data-ttu-id="39f48-130">不能从访问私有类型`Module2`，但可以将内部类型。</span><span class="sxs-lookup"><span data-stu-id="39f48-130">The private type cannot be accessed from `Module2`, but the internal type can.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/access-control/snippet1.fs)]
    
<span data-ttu-id="39f48-131">下面的代码测试中创建的类型的可访问性`Module1.fs`。</span><span class="sxs-lookup"><span data-stu-id="39f48-131">The following code tests the accessibility of the types created in `Module1.fs`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/access-control/snippet2.fs)]
    
## <a name="see-also"></a><span data-ttu-id="39f48-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="39f48-132">See Also</span></span>
[<span data-ttu-id="39f48-133">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="39f48-133">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="39f48-134">签名</span><span class="sxs-lookup"><span data-stu-id="39f48-134">Signatures</span></span>](signatures.md)
