---
title: 对象表达式 (F#)
description: '了解如何使用 F # 对象表达式，如果你想要避免额外的代码和创建一个新的所需的开销命名类型。'
ms.date: 05/16/2016
ms.openlocfilehash: fed78e2be52838eedf55759b195696f1210a8a20
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33564386"
---
# <a name="object-expressions"></a><span data-ttu-id="a1560-103">对象表达式</span><span class="sxs-lookup"><span data-stu-id="a1560-103">Object Expressions</span></span>

<span data-ttu-id="a1560-104">*对象表达式*表达式，用于创建动态创建、 匿名对象类型的新实例，根据现有的基类型、 接口或组的接口。</span><span class="sxs-lookup"><span data-stu-id="a1560-104">An *object expression* is an expression that creates a new instance of a dynamically created, anonymous object type that is based on an existing base type, interface, or set of interfaces.</span></span>


## <a name="syntax"></a><span data-ttu-id="a1560-105">语法</span><span class="sxs-lookup"><span data-stu-id="a1560-105">Syntax</span></span>

```fsharp
// When typename is a class:
{ new typename [type-params]arguments with
    member-definitions
    [ additional-interface-definitions ]
}
// When typename is not a class:
{ new typename [generic-type-args] with
    member-definitions
    [ additional-interface-definitions ]
}
```

## <a name="remarks"></a><span data-ttu-id="a1560-106">备注</span><span class="sxs-lookup"><span data-stu-id="a1560-106">Remarks</span></span>
<span data-ttu-id="a1560-107">在上述语法中， *typename*表示的现有类类型或接口类型。</span><span class="sxs-lookup"><span data-stu-id="a1560-107">In the previous syntax, the *typename* represents an existing class type or interface type.</span></span> <span data-ttu-id="a1560-108">*类型参数*介绍可选的泛型类型参数。</span><span class="sxs-lookup"><span data-stu-id="a1560-108">*type-params* describes the optional generic type parameters.</span></span> <span data-ttu-id="a1560-109">*参数*仅用于类类型，需要构造函数参数。</span><span class="sxs-lookup"><span data-stu-id="a1560-109">The *arguments* are used only for class types, which require constructor parameters.</span></span> <span data-ttu-id="a1560-110">*成员定义*替代基类方法或抽象方法从基类或接口的实现。</span><span class="sxs-lookup"><span data-stu-id="a1560-110">The *member-definitions* are overrides of base class methods, or implementations of abstract methods from either a base class or an interface.</span></span>

<span data-ttu-id="a1560-111">下面的示例阐释了多种不同类型的对象表达式。</span><span class="sxs-lookup"><span data-stu-id="a1560-111">The following example illustrates several different types of object expressions.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4301.fs)]

## <a name="using-object-expressions"></a><span data-ttu-id="a1560-112">使用对象表达式</span><span class="sxs-lookup"><span data-stu-id="a1560-112">Using Object Expressions</span></span>
<span data-ttu-id="a1560-113">当你想要避免额外的代码和所需创建一个新的名为类型的开销时，您可以使用对象表达式。</span><span class="sxs-lookup"><span data-stu-id="a1560-113">You use object expressions when you want to avoid the extra code and overhead that is required to create a new, named type.</span></span> <span data-ttu-id="a1560-114">如果您使用对象表达式来创建在程序中的类型的数量降至最低，可以减少的代码的行数，并防止不必要的迅速普及的类型。</span><span class="sxs-lookup"><span data-stu-id="a1560-114">If you use object expressions to minimize the number of types created in a program, you can reduce the number of lines of code and prevent the unnecessary proliferation of types.</span></span> <span data-ttu-id="a1560-115">而不是创建许多类型只是为了处理的特定情况下，你可以使用自定义现有类型或为特定用例手头提供正确地实现接口的对象表达式。</span><span class="sxs-lookup"><span data-stu-id="a1560-115">Instead of creating many types just to handle specific situations, you can use an object expression that customizes an existing type or provides an appropriate implementation of an interface for the specific case at hand.</span></span>


## <a name="see-also"></a><span data-ttu-id="a1560-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="a1560-116">See Also</span></span>
[<span data-ttu-id="a1560-117">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="a1560-117">F# Language Reference</span></span>](index.md)
