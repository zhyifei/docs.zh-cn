---
title: 类中的 let 绑定
description: 了解如何通过在类定义中使用 "let F# " 绑定来定义类的私有字段和私有函数。
ms.date: 05/16/2016
ms.openlocfilehash: 1366ab8f1f4f606fe5947a8fc4df10de49346b3e
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216532"
---
# <a name="let-bindings-in-classes"></a><span data-ttu-id="36e65-103">类中的 let 绑定</span><span class="sxs-lookup"><span data-stu-id="36e65-103">let Bindings in Classes</span></span>

<span data-ttu-id="36e65-104">您可以使用`let`类定义中的绑定为F#类定义私有字段和私有函数。</span><span class="sxs-lookup"><span data-stu-id="36e65-104">You can define private fields and private functions for F# classes by using `let` bindings in the class definition.</span></span>

## <a name="syntax"></a><span data-ttu-id="36e65-105">语法</span><span class="sxs-lookup"><span data-stu-id="36e65-105">Syntax</span></span>

```fsharp
// Field.
[static] let [ mutable ] binding1 [ and ... binding-n ]

// Function.
[static] let [ rec ] binding1 [ and ... binding-n ]
```

## <a name="remarks"></a><span data-ttu-id="36e65-106">备注</span><span class="sxs-lookup"><span data-stu-id="36e65-106">Remarks</span></span>

<span data-ttu-id="36e65-107">前面的语法出现在类标题和继承声明之后，但在任何成员定义之前。</span><span class="sxs-lookup"><span data-stu-id="36e65-107">The previous syntax appears after the class heading and inheritance declarations but before any member definitions.</span></span> <span data-ttu-id="36e65-108">语法类似于`let`类之外的绑定，但类中定义的名称的作用域限制为类。</span><span class="sxs-lookup"><span data-stu-id="36e65-108">The syntax is like that of `let` bindings outside of classes, but the names defined in a class have a scope that is limited to the class.</span></span> <span data-ttu-id="36e65-109">`let`绑定创建私有字段或函数; 若要公开数据或函数，请声明属性或成员方法。</span><span class="sxs-lookup"><span data-stu-id="36e65-109">A `let` binding creates a private field or function; to expose data or functions publicly, declare a property or a member method.</span></span>

<span data-ttu-id="36e65-110">`let`非静态`let`绑定称为实例绑定。</span><span class="sxs-lookup"><span data-stu-id="36e65-110">A `let` binding that is not static is called an instance `let` binding.</span></span> <span data-ttu-id="36e65-111">创建`let`对象时将执行实例绑定。</span><span class="sxs-lookup"><span data-stu-id="36e65-111">Instance `let` bindings execute when objects are created.</span></span> <span data-ttu-id="36e65-112">静态`let`绑定是类的静态初始值设定项的一部分，可保证在第一次使用该类型之前执行。</span><span class="sxs-lookup"><span data-stu-id="36e65-112">Static `let` bindings are part of the static initializer for the class, which is guaranteed to execute before the type is first used.</span></span>

<span data-ttu-id="36e65-113">实例`let`绑定中的代码可以使用主构造函数的参数。</span><span class="sxs-lookup"><span data-stu-id="36e65-113">The code within instance `let` bindings can use the primary constructor's parameters.</span></span>

<span data-ttu-id="36e65-114">类中的`let`绑定不允许使用属性和可访问性修饰符。</span><span class="sxs-lookup"><span data-stu-id="36e65-114">Attributes and accessibility modifiers are not permitted on `let` bindings in classes.</span></span>

<span data-ttu-id="36e65-115">下面的代码示例演示类中的`let`几种类型的绑定。</span><span class="sxs-lookup"><span data-stu-id="36e65-115">The following code examples illustrate several types of `let` bindings in classes.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3001.fs)]

<span data-ttu-id="36e65-116">输出如下所示。</span><span class="sxs-lookup"><span data-stu-id="36e65-116">The output is as follows.</span></span>

```console
10 52 1 204
```

## <a name="alternative-ways-to-create-fields"></a><span data-ttu-id="36e65-117">创建字段的替代方法</span><span class="sxs-lookup"><span data-stu-id="36e65-117">Alternative Ways to Create Fields</span></span>

<span data-ttu-id="36e65-118">你还可以使用`val`关键字来创建私有字段。</span><span class="sxs-lookup"><span data-stu-id="36e65-118">You can also use the `val` keyword to create a private field.</span></span> <span data-ttu-id="36e65-119">使用`val`关键字时，在创建对象时不会为该字段指定值，而是使用默认值对其进行初始化。</span><span class="sxs-lookup"><span data-stu-id="36e65-119">When using the `val` keyword, the field is not given a value when the object is created, but instead is initialized with a default value.</span></span> <span data-ttu-id="36e65-120">有关详细信息, 请[参阅显式字段:Val 关键字](explicit-fields-the-val-keyword.md)。</span><span class="sxs-lookup"><span data-stu-id="36e65-120">For more information, see [Explicit Fields: The val Keyword](explicit-fields-the-val-keyword.md).</span></span>

<span data-ttu-id="36e65-121">还可以通过使用成员定义并向定义中添加关键字`private` ，在类中定义私有字段。</span><span class="sxs-lookup"><span data-stu-id="36e65-121">You can also define private fields in a class by using a member definition and adding the keyword `private` to the definition.</span></span> <span data-ttu-id="36e65-122">如果希望在不重写代码的情况下更改成员的可访问性，这会很有用。</span><span class="sxs-lookup"><span data-stu-id="36e65-122">This can be useful if you expect to change the accessibility of a member without rewriting your code.</span></span> <span data-ttu-id="36e65-123">有关详细信息，请参阅[访问控制](../access-control.md)。</span><span class="sxs-lookup"><span data-stu-id="36e65-123">For more information, see [Access Control](../access-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="36e65-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="36e65-124">See also</span></span>

- [<span data-ttu-id="36e65-125">成员</span><span class="sxs-lookup"><span data-stu-id="36e65-125">Members</span></span>](index.md)
- [<span data-ttu-id="36e65-126">类中的 `do` 绑定</span><span class="sxs-lookup"><span data-stu-id="36e65-126">`do` Bindings in Classes</span></span>](do-bindings-in-classes.md)
- [<span data-ttu-id="36e65-127">`let`绑定</span><span class="sxs-lookup"><span data-stu-id="36e65-127">`let` Bindings</span></span>](../functions/let-bindings.md)
