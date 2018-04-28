---
title: 类中的 let 绑定 (F#)
description: '了解如何通过使用 let 绑定的类定义中定义私有字段和私有函数对于 F # 类。'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: c4511a541403dde517acaf902e86de8d48f13781
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2018
---
# <a name="let-bindings-in-classes"></a><span data-ttu-id="161ec-103">类中的 let 绑定</span><span class="sxs-lookup"><span data-stu-id="161ec-103">let Bindings in Classes</span></span>

<span data-ttu-id="161ec-104">可以通过定义私有字段和 F # 类的私有函数`let`类定义中的绑定。</span><span class="sxs-lookup"><span data-stu-id="161ec-104">You can define private fields and private functions for F# classes by using `let` bindings in the class definition.</span></span>


## <a name="syntax"></a><span data-ttu-id="161ec-105">语法</span><span class="sxs-lookup"><span data-stu-id="161ec-105">Syntax</span></span>

```fsharp
// Field.
[static] let [ mutable ] binding1 [ and ... binding-n ]

// Function.
[static] let [ rec ] binding1 [ and ... binding-n ]
```

## <a name="remarks"></a><span data-ttu-id="161ec-106">备注</span><span class="sxs-lookup"><span data-stu-id="161ec-106">Remarks</span></span>
<span data-ttu-id="161ec-107">上面的语法显示类标题和继承声明之后但在任何成员定义之前。</span><span class="sxs-lookup"><span data-stu-id="161ec-107">The previous syntax appears after the class heading and inheritance declarations but before any member definitions.</span></span> <span data-ttu-id="161ec-108">语法是类似的`let`外部类，但类中定义的名称的绑定都具有仅限于类的作用域。</span><span class="sxs-lookup"><span data-stu-id="161ec-108">The syntax is like that of `let` bindings outside of classes, but the names defined in a class have a scope that is limited to the class.</span></span> <span data-ttu-id="161ec-109">A`let`绑定创建的私有字段或函数; 来公开数据或函数公开，声明属性或成员方法。</span><span class="sxs-lookup"><span data-stu-id="161ec-109">A `let` binding creates a private field or function; to expose data or functions publicly, declare a property or a member method.</span></span>

<span data-ttu-id="161ec-110">A`let`绑定，它不是静态称为实例`let`绑定。</span><span class="sxs-lookup"><span data-stu-id="161ec-110">A `let` binding that is not static is called an instance `let` binding.</span></span> <span data-ttu-id="161ec-111">实例`let`绑定执行创建对象时。</span><span class="sxs-lookup"><span data-stu-id="161ec-111">Instance `let` bindings execute when objects are created.</span></span> <span data-ttu-id="161ec-112">静态`let`绑定是类，该类可保证执行之前将首先使用该类型的静态初始值设定项的一部分。</span><span class="sxs-lookup"><span data-stu-id="161ec-112">Static `let` bindings are part of the static initializer for the class, which is guaranteed to execute before the type is first used.</span></span>

<span data-ttu-id="161ec-113">实例中的代码`let`绑定可以使用主构造函数的参数。</span><span class="sxs-lookup"><span data-stu-id="161ec-113">The code within instance `let` bindings can use the primary constructor's parameters.</span></span>

<span data-ttu-id="161ec-114">特性和可访问性修饰符不允许对`let`类中的绑定。</span><span class="sxs-lookup"><span data-stu-id="161ec-114">Attributes and accessibility modifiers are not permitted on `let` bindings in classes.</span></span>

<span data-ttu-id="161ec-115">下面的代码示例阐释几种类型的`let`类中的绑定。</span><span class="sxs-lookup"><span data-stu-id="161ec-115">The following code examples illustrate several types of `let` bindings in classes.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3001.fs)]

<span data-ttu-id="161ec-116">输出如下所示。</span><span class="sxs-lookup"><span data-stu-id="161ec-116">The output is as follows.</span></span>

```
10 52 1 204
```

## <a name="alternative-ways-to-create-fields"></a><span data-ttu-id="161ec-117">用于创建字段的其他方法</span><span class="sxs-lookup"><span data-stu-id="161ec-117">Alternative Ways to Create Fields</span></span>
<span data-ttu-id="161ec-118">你还可以使用`val`关键字来创建私有字段。</span><span class="sxs-lookup"><span data-stu-id="161ec-118">You can also use the `val` keyword to create a private field.</span></span> <span data-ttu-id="161ec-119">使用时`val`关键字，该字段不建议提供一个值时创建对象，，但改为使用默认值初始化。</span><span class="sxs-lookup"><span data-stu-id="161ec-119">When using the `val` keyword, the field is not given a value when the object is created, but instead is initialized with a default value.</span></span> <span data-ttu-id="161ec-120">有关详细信息，请参阅[显式字段： val 关键字](explicit-fields-the-val-keyword.md)。</span><span class="sxs-lookup"><span data-stu-id="161ec-120">For more information, see [Explicit Fields: The val Keyword](explicit-fields-the-val-keyword.md).</span></span>

<span data-ttu-id="161ec-121">可以使用成员定义和添加关键字，还定义一个类私有字段`private`到定义。</span><span class="sxs-lookup"><span data-stu-id="161ec-121">You can also define private fields in a class by using a member definition and adding the keyword `private` to the definition.</span></span> <span data-ttu-id="161ec-122">这很有用，如果您希望无需重写你的代码更改成员的可访问性。</span><span class="sxs-lookup"><span data-stu-id="161ec-122">This can be useful if you expect to change the accessibility of a member without rewriting your code.</span></span> <span data-ttu-id="161ec-123">有关详细信息，请参阅[访问控制](../access-control.md)。</span><span class="sxs-lookup"><span data-stu-id="161ec-123">For more information, see [Access Control](../access-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="161ec-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="161ec-124">See Also</span></span>
[<span data-ttu-id="161ec-125">成员</span><span class="sxs-lookup"><span data-stu-id="161ec-125">Members</span></span>](index.md)

[<span data-ttu-id="161ec-126">类中的 `do` 绑定</span><span class="sxs-lookup"><span data-stu-id="161ec-126">`do` Bindings in Classes</span></span>](do-bindings-in-classes.md)

[<span data-ttu-id="161ec-127">`let` 绑定</span><span class="sxs-lookup"><span data-stu-id="161ec-127">`let` Bindings</span></span>](../functions/let-bindings.md)
