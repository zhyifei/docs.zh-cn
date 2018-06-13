---
title: 类型缩写 (F#)
description: '了解有关 F # 类型缩写为类型以使代码更易于读取指定的更有意义的名称。'
ms.date: 05/16/2016
ms.openlocfilehash: e222caa41a20a64071c94cffea6ea7b2bec8eb22
ms.sourcegitcommit: ff1d40507b3eb6e2185478e37c66c66be6de46f1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2018
ms.locfileid: "34058947"
---
# <a name="type-abbreviations"></a><span data-ttu-id="f5f01-103">类型缩写</span><span class="sxs-lookup"><span data-stu-id="f5f01-103">Type Abbreviations</span></span>

<span data-ttu-id="f5f01-104">A*类型缩写*是的别名或类型的备用名称。</span><span class="sxs-lookup"><span data-stu-id="f5f01-104">A *type abbreviation* is an alias or alternate name for a type.</span></span>

## <a name="syntax"></a><span data-ttu-id="f5f01-105">语法</span><span class="sxs-lookup"><span data-stu-id="f5f01-105">Syntax</span></span>

```fsharp
type [accessibility-modifier] type-abbreviation = type-name
```

## <a name="remarks"></a><span data-ttu-id="f5f01-106">备注</span><span class="sxs-lookup"><span data-stu-id="f5f01-106">Remarks</span></span>
<span data-ttu-id="f5f01-107">类型缩写可用于为指定类型的更有意义的名称，以使代码易于阅读。</span><span class="sxs-lookup"><span data-stu-id="f5f01-107">You can use type abbreviations to give a type a more meaningful name, in order to make code easier to read.</span></span> <span data-ttu-id="f5f01-108">你还可以使用它们创建为原本不方便，写出的类型的易于使用的名称。此外，你可以使用类型缩写要更加轻松地更改基础类型，而无需更改使用类型的所有代码。</span><span class="sxs-lookup"><span data-stu-id="f5f01-108">You can also use them to create an easy to use name for a type that is otherwise cumbersome to write out. Additionally, you can use type abbreviations to make it easier to change an underlying type without changing all the code that uses the type.</span></span> <span data-ttu-id="f5f01-109">下面是简单类型缩写。</span><span class="sxs-lookup"><span data-stu-id="f5f01-109">The following is a simple type abbreviation.</span></span>

<span data-ttu-id="f5f01-110">类型缩写的可访问性默认为`public`。</span><span class="sxs-lookup"><span data-stu-id="f5f01-110">Accessibility of type abbreviations defaults to `public`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2301.fs)]

<span data-ttu-id="f5f01-111">类型缩写可以包含泛型参数，如以下代码所示。</span><span class="sxs-lookup"><span data-stu-id="f5f01-111">Type abbreviations can include generic parameters, as in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2302.fs)]

<span data-ttu-id="f5f01-112">在前面的代码中，`Transform`是表示采用单个参数的任何类型的函数的类型缩写，将返回相同类型的单个值。</span><span class="sxs-lookup"><span data-stu-id="f5f01-112">In the previous code, `Transform` is a type abbreviation that represents a function that takes a single argument of any type and that returns a single value of that same type.</span></span>

<span data-ttu-id="f5f01-113">在.NET Framework MSIL 代码中，不会保留类型缩写。</span><span class="sxs-lookup"><span data-stu-id="f5f01-113">Type abbreviations are not preserved in the .NET Framework MSIL code.</span></span> <span data-ttu-id="f5f01-114">因此，当使用来自另一种.NET Framework 语言的 F # 程序集时，你必须使用类型缩写的基础类型名称。</span><span class="sxs-lookup"><span data-stu-id="f5f01-114">Therefore, when you use an F# assembly from another .NET Framework language, you must use the underlying type name for a type abbreviation.</span></span>

<span data-ttu-id="f5f01-115">类型缩写还可上的度量单位。</span><span class="sxs-lookup"><span data-stu-id="f5f01-115">Type abbreviations can also be used on units of measure.</span></span> <span data-ttu-id="f5f01-116">有关详细信息，请参阅[度量单位](units-of-measure.md)。</span><span class="sxs-lookup"><span data-stu-id="f5f01-116">For more information, see [Units of Measure](units-of-measure.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="f5f01-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="f5f01-117">See Also</span></span>
[<span data-ttu-id="f5f01-118">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="f5f01-118">F# Language Reference</span></span>](index.md)

