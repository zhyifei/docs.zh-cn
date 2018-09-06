---
title: do 绑定 (F#)
description: '了解如何将 F # do 绑定用来执行代码而无需定义的函数或值。'
ms.date: 05/16/2016
ms.openlocfilehash: 78dbf8da0fe40b5af566ad98693df1109eede7e4
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43882728"
---
# <a name="do-bindings"></a><span data-ttu-id="aeada-103">do 绑定</span><span class="sxs-lookup"><span data-stu-id="aeada-103">do Bindings</span></span>

<span data-ttu-id="aeada-104">一个`do`绑定用于执行代码而无需定义的函数或值。</span><span class="sxs-lookup"><span data-stu-id="aeada-104">A `do` binding is used to execute code without defining a function or value.</span></span> <span data-ttu-id="aeada-105">此外，不要绑定可以是在类中使用，请参阅[`do`类中的绑定](../members/do-bindings-in-classes.md)。</span><span class="sxs-lookup"><span data-stu-id="aeada-105">Also, do bindings can be used in classes, see [`do` Bindings in Classes](../members/do-bindings-in-classes.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="aeada-106">语法</span><span class="sxs-lookup"><span data-stu-id="aeada-106">Syntax</span></span>

```fsharp
[ attributes ]
[ do ]expression
```

## <a name="remarks"></a><span data-ttu-id="aeada-107">备注</span><span class="sxs-lookup"><span data-stu-id="aeada-107">Remarks</span></span>

<span data-ttu-id="aeada-108">使用`do`绑定时要执行独立于函数或值定义的代码。</span><span class="sxs-lookup"><span data-stu-id="aeada-108">Use a `do` binding when you want to execute code independently of a function or value definition.</span></span> <span data-ttu-id="aeada-109">中的表达式`do`绑定必须返回`unit`。</span><span class="sxs-lookup"><span data-stu-id="aeada-109">The expression in a `do` binding must return `unit`.</span></span> <span data-ttu-id="aeada-110">中的顶级代码`do`初始化模块时执行绑定。</span><span class="sxs-lookup"><span data-stu-id="aeada-110">Code in a top-level `do` binding is executed when the module is initialized.</span></span> <span data-ttu-id="aeada-111">关键字`do`是可选的。</span><span class="sxs-lookup"><span data-stu-id="aeada-111">The keyword `do` is optional.</span></span>

<span data-ttu-id="aeada-112">特性可以应用于顶级`do`绑定。</span><span class="sxs-lookup"><span data-stu-id="aeada-112">Attributes can be applied to a top-level `do` binding.</span></span> <span data-ttu-id="aeada-113">例如，如果程序使用 COM 互操作，你可能想要应用`STAThread`属性到你的程序。</span><span class="sxs-lookup"><span data-stu-id="aeada-113">For example, if your program uses COM interop, you might want to apply the `STAThread` attribute to your program.</span></span> <span data-ttu-id="aeada-114">要做到这一点上使用属性`do`绑定，如下面的代码中所示。</span><span class="sxs-lookup"><span data-stu-id="aeada-114">You can do this by using an attribute on a `do` binding, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet201.fs)]

## <a name="see-also"></a><span data-ttu-id="aeada-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="aeada-115">See also</span></span>

- [<span data-ttu-id="aeada-116">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="aeada-116">F# Language Reference</span></span>](../index.md)
- [<span data-ttu-id="aeada-117">函数</span><span class="sxs-lookup"><span data-stu-id="aeada-117">Functions</span></span>](index.md)
