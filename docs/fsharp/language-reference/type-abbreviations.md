---
title: "类型缩写 (F#)"
description: "了解有关 F # 类型缩写为类型以使代码更易于读取指定的更有意义的名称。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 560af74f-935f-415c-af56-604cddb9da6b
ms.openlocfilehash: 235c0240fe89d203b9474dec2b3f91947f453cd8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="type-abbreviations"></a><span data-ttu-id="6badf-104">类型缩写</span><span class="sxs-lookup"><span data-stu-id="6badf-104">Type Abbreviations</span></span>

<span data-ttu-id="6badf-105">A*类型缩写*是的别名或类型的备用名称。</span><span class="sxs-lookup"><span data-stu-id="6badf-105">A *type abbreviation* is an alias or alternate name for a type.</span></span>

## <a name="syntax"></a><span data-ttu-id="6badf-106">语法</span><span class="sxs-lookup"><span data-stu-id="6badf-106">Syntax</span></span>

```fsharp
type type-abbreviation = type-name
```

## <a name="remarks"></a><span data-ttu-id="6badf-107">备注</span><span class="sxs-lookup"><span data-stu-id="6badf-107">Remarks</span></span>
<span data-ttu-id="6badf-108">类型缩写可用于为指定类型的更有意义的名称，以使代码易于阅读。</span><span class="sxs-lookup"><span data-stu-id="6badf-108">You can use type abbreviations to give a type a more meaningful name, in order to make code easier to read.</span></span> <span data-ttu-id="6badf-109">你还可以使用它们创建为原本不方便，写出的类型的易于使用的名称。此外，你可以使用类型缩写要更加轻松地更改基础类型，而无需更改使用类型的所有代码。</span><span class="sxs-lookup"><span data-stu-id="6badf-109">You can also use them to create an easy to use name for a type that is otherwise cumbersome to write out. Additionally, you can use type abbreviations to make it easier to change an underlying type without changing all the code that uses the type.</span></span> <span data-ttu-id="6badf-110">下面是简单类型缩写。</span><span class="sxs-lookup"><span data-stu-id="6badf-110">The following is a simple type abbreviation.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2301.fs)]

<span data-ttu-id="6badf-111">类型缩写可以包含泛型参数，如以下代码所示。</span><span class="sxs-lookup"><span data-stu-id="6badf-111">Type abbreviations can include generic parameters, as in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2302.fs)]

<span data-ttu-id="6badf-112">在前面的代码中，`Transform`是表示采用单个参数的任何类型的函数的类型缩写，将返回相同类型的单个值。</span><span class="sxs-lookup"><span data-stu-id="6badf-112">In the previous code, `Transform` is a type abbreviation that represents a function that takes a single argument of any type and that returns a single value of that same type.</span></span>

<span data-ttu-id="6badf-113">在.NET Framework MSIL 代码中，不会保留类型缩写。</span><span class="sxs-lookup"><span data-stu-id="6badf-113">Type abbreviations are not preserved in the .NET Framework MSIL code.</span></span> <span data-ttu-id="6badf-114">因此，当使用来自另一种.NET Framework 语言的 F # 程序集时，你必须使用类型缩写的基础类型名称。</span><span class="sxs-lookup"><span data-stu-id="6badf-114">Therefore, when you use an F# assembly from another .NET Framework language, you must use the underlying type name for a type abbreviation.</span></span>

<span data-ttu-id="6badf-115">类型缩写还可上的度量单位。</span><span class="sxs-lookup"><span data-stu-id="6badf-115">Type abbreviations can also be used on units of measure.</span></span> <span data-ttu-id="6badf-116">有关详细信息，请参阅[度量单位](units-of-measure.md)。</span><span class="sxs-lookup"><span data-stu-id="6badf-116">For more information, see [Units of Measure](units-of-measure.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="6badf-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6badf-117">See Also</span></span>
[<span data-ttu-id="6badf-118">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="6badf-118">F# Language Reference</span></span>](index.md)

