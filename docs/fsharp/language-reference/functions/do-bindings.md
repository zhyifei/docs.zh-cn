---
title: "do 绑定 (F#)"
description: "了解如何 F # do 绑定使用执行代码，而定义的函数或值。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 4c1057a3-3aa1-4b64-b46a-25ffe33f0be9
ms.openlocfilehash: f2563d384b67c005c96c2ff487c786476d385e70
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="do-bindings"></a><span data-ttu-id="06b2d-104">do 绑定</span><span class="sxs-lookup"><span data-stu-id="06b2d-104">do Bindings</span></span>

<span data-ttu-id="06b2d-105">A`do`绑定用于执行代码，不定义函数或值。</span><span class="sxs-lookup"><span data-stu-id="06b2d-105">A `do` binding is used to execute code without defining a function or value.</span></span> <span data-ttu-id="06b2d-106">此外，不必绑定可以是在类中使用，请参阅[`do`类中的绑定](../members/do-bindings-in-classes.md)。</span><span class="sxs-lookup"><span data-stu-id="06b2d-106">Also, do bindings can be used in classes, see [`do` Bindings in Classes](../members/do-bindings-in-classes.md).</span></span>


## <a name="syntax"></a><span data-ttu-id="06b2d-107">语法</span><span class="sxs-lookup"><span data-stu-id="06b2d-107">Syntax</span></span>

```fsharp
[ attributes ]
[ do ]expression
```

## <a name="remarks"></a><span data-ttu-id="06b2d-108">备注</span><span class="sxs-lookup"><span data-stu-id="06b2d-108">Remarks</span></span>
<span data-ttu-id="06b2d-109">使用`do`绑定时要执行独立于函数或值定义的代码。</span><span class="sxs-lookup"><span data-stu-id="06b2d-109">Use a `do` binding when you want to execute code independently of a function or value definition.</span></span> <span data-ttu-id="06b2d-110">中的表达式`do`绑定必须返回`unit`。</span><span class="sxs-lookup"><span data-stu-id="06b2d-110">The expression in a `do` binding must return `unit`.</span></span> <span data-ttu-id="06b2d-111">中的顶级代码`do`初始化模块时执行绑定。</span><span class="sxs-lookup"><span data-stu-id="06b2d-111">Code in a top-level `do` binding is executed when the module is initialized.</span></span> <span data-ttu-id="06b2d-112">关键字`do`是可选的。</span><span class="sxs-lookup"><span data-stu-id="06b2d-112">The keyword `do` is optional.</span></span>

<span data-ttu-id="06b2d-113">特性可以应用于顶级`do`绑定。</span><span class="sxs-lookup"><span data-stu-id="06b2d-113">Attributes can be applied to a top-level `do` binding.</span></span> <span data-ttu-id="06b2d-114">例如，如果程序使用 COM 互操作，你可能想要应用`STAThread`属性到你的程序。</span><span class="sxs-lookup"><span data-stu-id="06b2d-114">For example, if your program uses COM interop, you might want to apply the `STAThread` attribute to your program.</span></span> <span data-ttu-id="06b2d-115">要做到这一点上使用属性`do`绑定，如下面的代码中所示。</span><span class="sxs-lookup"><span data-stu-id="06b2d-115">You can do this by using an attribute on a `do` binding, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet201.fs)]
    
## <a name="see-also"></a><span data-ttu-id="06b2d-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="06b2d-116">See Also</span></span>
[<span data-ttu-id="06b2d-117">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="06b2d-117">F# Language Reference</span></span>](../index.md)

[<span data-ttu-id="06b2d-118">函数</span><span class="sxs-lookup"><span data-stu-id="06b2d-118">Functions</span></span>](index.md)

