---
title: do 绑定
description: 了解如何使用F# "do" 绑定来执行代码, 而无需定义函数或值。
ms.date: 05/16/2016
ms.openlocfilehash: f98f523296bfaceeda35d4861eafbfeaa5a60c32
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630540"
---
# <a name="do-bindings"></a><span data-ttu-id="25529-103">do 绑定</span><span class="sxs-lookup"><span data-stu-id="25529-103">do Bindings</span></span>

<span data-ttu-id="25529-104">`do`绑定用于在不定义函数或值的情况下执行代码。</span><span class="sxs-lookup"><span data-stu-id="25529-104">A `do` binding is used to execute code without defining a function or value.</span></span> <span data-ttu-id="25529-105">此外, do 绑定可以在类中使用, 请参阅[ `do`类中的绑定](../members/do-bindings-in-classes.md)。</span><span class="sxs-lookup"><span data-stu-id="25529-105">Also, do bindings can be used in classes, see [`do` Bindings in Classes](../members/do-bindings-in-classes.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="25529-106">语法</span><span class="sxs-lookup"><span data-stu-id="25529-106">Syntax</span></span>

```fsharp
[ attributes ]
[ do ]expression
```

## <a name="remarks"></a><span data-ttu-id="25529-107">备注</span><span class="sxs-lookup"><span data-stu-id="25529-107">Remarks</span></span>

<span data-ttu-id="25529-108">当你想要独立于函数或值定义执行代码时, 请使用绑定。`do`</span><span class="sxs-lookup"><span data-stu-id="25529-108">Use a `do` binding when you want to execute code independently of a function or value definition.</span></span> <span data-ttu-id="25529-109">`do`绑定中的表达式必须返回`unit`。</span><span class="sxs-lookup"><span data-stu-id="25529-109">The expression in a `do` binding must return `unit`.</span></span> <span data-ttu-id="25529-110">初始化模块时, 将执行`do`顶级绑定中的代码。</span><span class="sxs-lookup"><span data-stu-id="25529-110">Code in a top-level `do` binding is executed when the module is initialized.</span></span> <span data-ttu-id="25529-111">关键字`do`是可选的。</span><span class="sxs-lookup"><span data-stu-id="25529-111">The keyword `do` is optional.</span></span>

<span data-ttu-id="25529-112">特性可应用于顶级`do`绑定。</span><span class="sxs-lookup"><span data-stu-id="25529-112">Attributes can be applied to a top-level `do` binding.</span></span> <span data-ttu-id="25529-113">例如, 如果您的程序使用 COM 互操作, 则您可能需要将`STAThread`该属性应用于程序。</span><span class="sxs-lookup"><span data-stu-id="25529-113">For example, if your program uses COM interop, you might want to apply the `STAThread` attribute to your program.</span></span> <span data-ttu-id="25529-114">为此, 可以使用`do`绑定上的属性, 如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="25529-114">You can do this by using an attribute on a `do` binding, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet201.fs)]

## <a name="see-also"></a><span data-ttu-id="25529-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="25529-115">See also</span></span>

- [<span data-ttu-id="25529-116">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="25529-116">F# Language Reference</span></span>](../index.md)
- [<span data-ttu-id="25529-117">函数</span><span class="sxs-lookup"><span data-stu-id="25529-117">Functions</span></span>](index.md)
