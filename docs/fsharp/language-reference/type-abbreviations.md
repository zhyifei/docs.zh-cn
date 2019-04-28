---
title: 类型缩写
description: 了解如何F#类型缩写，用来以使代码更易于读取为类型更有意义的名称。
ms.date: 05/16/2016
ms.openlocfilehash: 0deaef789367aad413e5a537bf7164034e1275c0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61683335"
---
# <a name="type-abbreviations"></a><span data-ttu-id="d9656-103">类型缩写</span><span class="sxs-lookup"><span data-stu-id="d9656-103">Type Abbreviations</span></span>

<span data-ttu-id="d9656-104">一个*类型缩写*是别名或备用名称的类型。</span><span class="sxs-lookup"><span data-stu-id="d9656-104">A *type abbreviation* is an alias or alternate name for a type.</span></span>

## <a name="syntax"></a><span data-ttu-id="d9656-105">语法</span><span class="sxs-lookup"><span data-stu-id="d9656-105">Syntax</span></span>

```fsharp
type [accessibility-modifier] type-abbreviation = type-name
```

## <a name="remarks"></a><span data-ttu-id="d9656-106">备注</span><span class="sxs-lookup"><span data-stu-id="d9656-106">Remarks</span></span>

<span data-ttu-id="d9656-107">类型缩写可用于为指定类型的更有意义的名称，以使代码易于阅读。</span><span class="sxs-lookup"><span data-stu-id="d9656-107">You can use type abbreviations to give a type a more meaningful name, in order to make code easier to read.</span></span> <span data-ttu-id="d9656-108">此外可以使用它们创建易于使用为原本不方便，写出的类型名称。此外，可以使用类型缩写来轻松地更改基础类型，而无需更改使用类型的所有代码。</span><span class="sxs-lookup"><span data-stu-id="d9656-108">You can also use them to create an easy to use name for a type that is otherwise cumbersome to write out. Additionally, you can use type abbreviations to make it easier to change an underlying type without changing all the code that uses the type.</span></span> <span data-ttu-id="d9656-109">下面是简单类型缩写。</span><span class="sxs-lookup"><span data-stu-id="d9656-109">The following is a simple type abbreviation.</span></span>

<span data-ttu-id="d9656-110">类型缩写的可访问性默认为`public`。</span><span class="sxs-lookup"><span data-stu-id="d9656-110">Accessibility of type abbreviations defaults to `public`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2301.fs)]

<span data-ttu-id="d9656-111">类型缩写可以包含泛型参数，如以下代码所示。</span><span class="sxs-lookup"><span data-stu-id="d9656-111">Type abbreviations can include generic parameters, as in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2302.fs)]

<span data-ttu-id="d9656-112">在前面的代码，`Transform`是表示任何类型的一个自变量的函数的类型缩写，将返回相同类型的单个值。</span><span class="sxs-lookup"><span data-stu-id="d9656-112">In the previous code, `Transform` is a type abbreviation that represents a function that takes a single argument of any type and that returns a single value of that same type.</span></span>

<span data-ttu-id="d9656-113">类型缩写不会保留在.NET Framework MSIL 代码。</span><span class="sxs-lookup"><span data-stu-id="d9656-113">Type abbreviations are not preserved in the .NET Framework MSIL code.</span></span> <span data-ttu-id="d9656-114">因此，当你使用F#程序集从另一种.NET Framework 语言，必须使用类型缩写的基础类型名称。</span><span class="sxs-lookup"><span data-stu-id="d9656-114">Therefore, when you use an F# assembly from another .NET Framework language, you must use the underlying type name for a type abbreviation.</span></span>

<span data-ttu-id="d9656-115">此外可以上度量单位的使用类型缩写。</span><span class="sxs-lookup"><span data-stu-id="d9656-115">Type abbreviations can also be used on units of measure.</span></span> <span data-ttu-id="d9656-116">有关详细信息，请参阅[度量单位](units-of-measure.md)。</span><span class="sxs-lookup"><span data-stu-id="d9656-116">For more information, see [Units of Measure](units-of-measure.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d9656-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="d9656-117">See also</span></span>

- [<span data-ttu-id="d9656-118">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="d9656-118">F# Language Reference</span></span>](index.md)