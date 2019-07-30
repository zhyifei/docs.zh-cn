---
title: 类型缩写
description: 若要F#使代码更易于阅读, 请了解类型缩写, 为类型提供更有意义的名称。
ms.date: 05/16/2016
ms.openlocfilehash: 339b22a675e3f1ad8a3da207053e611942b55a22
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630214"
---
# <a name="type-abbreviations"></a><span data-ttu-id="db445-103">类型缩写</span><span class="sxs-lookup"><span data-stu-id="db445-103">Type Abbreviations</span></span>

<span data-ttu-id="db445-104">*类型缩写*为类型的别名或替换名称。</span><span class="sxs-lookup"><span data-stu-id="db445-104">A *type abbreviation* is an alias or alternate name for a type.</span></span>

## <a name="syntax"></a><span data-ttu-id="db445-105">语法</span><span class="sxs-lookup"><span data-stu-id="db445-105">Syntax</span></span>

```fsharp
type [accessibility-modifier] type-abbreviation = type-name
```

## <a name="remarks"></a><span data-ttu-id="db445-106">备注</span><span class="sxs-lookup"><span data-stu-id="db445-106">Remarks</span></span>

<span data-ttu-id="db445-107">您可以使用类型缩写为类型提供更有意义的名称, 从而使代码更易于阅读。</span><span class="sxs-lookup"><span data-stu-id="db445-107">You can use type abbreviations to give a type a more meaningful name, in order to make code easier to read.</span></span> <span data-ttu-id="db445-108">你还可以使用它们为类型创建易于使用的名称, 此名称在编写时不太繁琐。此外, 还可以使用类型缩写来更轻松地更改基础类型, 而无需更改所有使用该类型的代码。</span><span class="sxs-lookup"><span data-stu-id="db445-108">You can also use them to create an easy to use name for a type that is otherwise cumbersome to write out. Additionally, you can use type abbreviations to make it easier to change an underlying type without changing all the code that uses the type.</span></span> <span data-ttu-id="db445-109">下面是一个简单的类型缩写。</span><span class="sxs-lookup"><span data-stu-id="db445-109">The following is a simple type abbreviation.</span></span>

<span data-ttu-id="db445-110">缩写词类型默认值为`public`。</span><span class="sxs-lookup"><span data-stu-id="db445-110">Accessibility of type abbreviations defaults to `public`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2301.fs)]

<span data-ttu-id="db445-111">类型缩写词可以包含泛型参数, 如以下代码所示。</span><span class="sxs-lookup"><span data-stu-id="db445-111">Type abbreviations can include generic parameters, as in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2302.fs)]

<span data-ttu-id="db445-112">在前面的代码中`Transform` , 是一种类型缩写, 它表示一个函数, 该函数采用任何类型的单个自变量, 并返回该类型的单个值。</span><span class="sxs-lookup"><span data-stu-id="db445-112">In the previous code, `Transform` is a type abbreviation that represents a function that takes a single argument of any type and that returns a single value of that same type.</span></span>

<span data-ttu-id="db445-113">不会在 .NET Framework MSIL 代码中保留类型缩写。</span><span class="sxs-lookup"><span data-stu-id="db445-113">Type abbreviations are not preserved in the .NET Framework MSIL code.</span></span> <span data-ttu-id="db445-114">因此, 当您使用另F#一个 .NET Framework 语言的程序集时, 您必须使用类型缩写的基础类型名称。</span><span class="sxs-lookup"><span data-stu-id="db445-114">Therefore, when you use an F# assembly from another .NET Framework language, you must use the underlying type name for a type abbreviation.</span></span>

<span data-ttu-id="db445-115">类型缩写还可用于度量单位。</span><span class="sxs-lookup"><span data-stu-id="db445-115">Type abbreviations can also be used on units of measure.</span></span> <span data-ttu-id="db445-116">有关详细信息, 请参阅[度量单位](units-of-measure.md)。</span><span class="sxs-lookup"><span data-stu-id="db445-116">For more information, see [Units of Measure](units-of-measure.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="db445-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="db445-117">See also</span></span>

- [<span data-ttu-id="db445-118">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="db445-118">F# Language Reference</span></span>](index.md)
