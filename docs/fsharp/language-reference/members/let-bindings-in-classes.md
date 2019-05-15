---
title: 类中的 let 绑定
description: 了解如何定义私有字段和私有函数为F#类使用 let 中的类定义的绑定。
ms.date: 05/16/2016
ms.openlocfilehash: 29f843e3e065837a53fd5eb26c79088bc0778c76
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645176"
---
# <a name="let-bindings-in-classes"></a><span data-ttu-id="5a494-103">类中的 let 绑定</span><span class="sxs-lookup"><span data-stu-id="5a494-103">let Bindings in Classes</span></span>

<span data-ttu-id="5a494-104">你可以定义私有字段和私有函数为F#使用的类`let`类定义中的绑定。</span><span class="sxs-lookup"><span data-stu-id="5a494-104">You can define private fields and private functions for F# classes by using `let` bindings in the class definition.</span></span>

## <a name="syntax"></a><span data-ttu-id="5a494-105">语法</span><span class="sxs-lookup"><span data-stu-id="5a494-105">Syntax</span></span>

```fsharp
// Field.
[static] let [ mutable ] binding1 [ and ... binding-n ]

// Function.
[static] let [ rec ] binding1 [ and ... binding-n ]
```

## <a name="remarks"></a><span data-ttu-id="5a494-106">备注</span><span class="sxs-lookup"><span data-stu-id="5a494-106">Remarks</span></span>

<span data-ttu-id="5a494-107">类标题和继承声明之后的任何成员定义之前，会显示前面的语法。</span><span class="sxs-lookup"><span data-stu-id="5a494-107">The previous syntax appears after the class heading and inheritance declarations but before any member definitions.</span></span> <span data-ttu-id="5a494-108">语法是这样的`let`外部类，但在类中定义的名称的绑定具有作用域限制到类。</span><span class="sxs-lookup"><span data-stu-id="5a494-108">The syntax is like that of `let` bindings outside of classes, but the names defined in a class have a scope that is limited to the class.</span></span> <span data-ttu-id="5a494-109">一个`let`绑定创建的私有字段或函数; 若要公开的数据或函数公开，声明一个属性或成员方法。</span><span class="sxs-lookup"><span data-stu-id="5a494-109">A `let` binding creates a private field or function; to expose data or functions publicly, declare a property or a member method.</span></span>

<span data-ttu-id="5a494-110">一个`let`绑定，它不是静态调用实例`let`绑定。</span><span class="sxs-lookup"><span data-stu-id="5a494-110">A `let` binding that is not static is called an instance `let` binding.</span></span> <span data-ttu-id="5a494-111">实例`let`创建对象时将执行绑定。</span><span class="sxs-lookup"><span data-stu-id="5a494-111">Instance `let` bindings execute when objects are created.</span></span> <span data-ttu-id="5a494-112">静态`let`绑定是类，该类可保证执行之前首先使用的类型的静态初始值设定项的一部分。</span><span class="sxs-lookup"><span data-stu-id="5a494-112">Static `let` bindings are part of the static initializer for the class, which is guaranteed to execute before the type is first used.</span></span>

<span data-ttu-id="5a494-113">实例中的代码`let`绑定可以使用主构造函数的参数。</span><span class="sxs-lookup"><span data-stu-id="5a494-113">The code within instance `let` bindings can use the primary constructor's parameters.</span></span>

<span data-ttu-id="5a494-114">属性和可访问性修饰符不在允许`let`类中的绑定。</span><span class="sxs-lookup"><span data-stu-id="5a494-114">Attributes and accessibility modifiers are not permitted on `let` bindings in classes.</span></span>

<span data-ttu-id="5a494-115">下面的代码示例演示了几种类型的`let`类中的绑定。</span><span class="sxs-lookup"><span data-stu-id="5a494-115">The following code examples illustrate several types of `let` bindings in classes.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3001.fs)]

<span data-ttu-id="5a494-116">输出如下所示。</span><span class="sxs-lookup"><span data-stu-id="5a494-116">The output is as follows.</span></span>

```
10 52 1 204
```

## <a name="alternative-ways-to-create-fields"></a><span data-ttu-id="5a494-117">创建字段的替代方法</span><span class="sxs-lookup"><span data-stu-id="5a494-117">Alternative Ways to Create Fields</span></span>

<span data-ttu-id="5a494-118">此外可以使用`val`关键字创建的私有字段。</span><span class="sxs-lookup"><span data-stu-id="5a494-118">You can also use the `val` keyword to create a private field.</span></span> <span data-ttu-id="5a494-119">当使用`val`关键字，该字段没有指定值，该对象创建的但改为使用默认值初始化时。</span><span class="sxs-lookup"><span data-stu-id="5a494-119">When using the `val` keyword, the field is not given a value when the object is created, but instead is initialized with a default value.</span></span> <span data-ttu-id="5a494-120">有关详细信息，请参阅[显式字段：Val 关键字](explicit-fields-the-val-keyword.md)。</span><span class="sxs-lookup"><span data-stu-id="5a494-120">For more information, see [Explicit Fields: The val Keyword](explicit-fields-the-val-keyword.md).</span></span>

<span data-ttu-id="5a494-121">可以使用成员定义和添加关键字，还定义一个类的私有字段`private`到定义。</span><span class="sxs-lookup"><span data-stu-id="5a494-121">You can also define private fields in a class by using a member definition and adding the keyword `private` to the definition.</span></span> <span data-ttu-id="5a494-122">这很有用，如果您希望更改而无需重新编写代码的成员的可访问性。</span><span class="sxs-lookup"><span data-stu-id="5a494-122">This can be useful if you expect to change the accessibility of a member without rewriting your code.</span></span> <span data-ttu-id="5a494-123">有关详细信息，请参阅[访问控制](../access-control.md)。</span><span class="sxs-lookup"><span data-stu-id="5a494-123">For more information, see [Access Control](../access-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5a494-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="5a494-124">See also</span></span>

- [<span data-ttu-id="5a494-125">成员</span><span class="sxs-lookup"><span data-stu-id="5a494-125">Members</span></span>](index.md)
- [<span data-ttu-id="5a494-126">类中的 `do` 绑定</span><span class="sxs-lookup"><span data-stu-id="5a494-126">`do` Bindings in Classes</span></span>](do-bindings-in-classes.md)
- [<span data-ttu-id="5a494-127">`let` Bindings</span><span class="sxs-lookup"><span data-stu-id="5a494-127">`let` Bindings</span></span>](../functions/let-bindings.md)
