---
title: C# 枚举 - C# 语言介绍
description: 了解 C# 中的枚举，即离散的已命名常量
ms.date: 08/10/2016
ms.assetid: 7faba1cc-6ea9-4a19-adb9-0335e4b132e5
ms.openlocfilehash: d55462f0360b6896c398d581918a9c17a87583be
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53126649"
---
# <a name="enums"></a><span data-ttu-id="a9284-103">枚举</span><span class="sxs-lookup"><span data-stu-id="a9284-103">Enums</span></span>

<span data-ttu-id="a9284-104">***枚举类型***是包含一组已命名常量的独特值类型。</span><span class="sxs-lookup"><span data-stu-id="a9284-104">An ***enum type*** is a distinct value type with a set of named constants.</span></span> <span data-ttu-id="a9284-105">需要定义包含一组离散值的类型时，可以定义枚举。</span><span class="sxs-lookup"><span data-stu-id="a9284-105">You define enums when you need to define a type that can have a set of discrete values.</span></span> <span data-ttu-id="a9284-106">枚举使用一种整型值类型作为其基础存储，</span><span class="sxs-lookup"><span data-stu-id="a9284-106">They use one of the integral value types as their underlying storage.</span></span> <span data-ttu-id="a9284-107">并提供离散值的语义含义。</span><span class="sxs-lookup"><span data-stu-id="a9284-107">They provide semantic meaning to the discrete values.</span></span>

<span data-ttu-id="a9284-108">以下示例声明并使用名为“`Color`”的 `enum` 类型，其中包含三个常量值（`Red`、`Green` 和 `Blue`）。</span><span class="sxs-lookup"><span data-stu-id="a9284-108">The following example declares and uses an `enum` type named `Color` with three constant values, `Red`, `Green`, and `Blue`.</span></span>

[!code-csharp[EnumExample](../../../samples/snippets/csharp/tour/enums/Program.cs#L3-L36)]

<span data-ttu-id="a9284-109">每个 `enum` 类型都有对应的整型类型（称为 `enum` 类型的***基础类型***）。</span><span class="sxs-lookup"><span data-stu-id="a9284-109">Each `enum` type has a corresponding integral type called the ***underlying type*** of the `enum` type.</span></span> <span data-ttu-id="a9284-110">如果 `enum` 类型未显式声明基础类型，则基础类型为 `int`。</span><span class="sxs-lookup"><span data-stu-id="a9284-110">An `enum` type that does not explicitly declare an underlying type has an underlying type of `int`.</span></span> <span data-ttu-id="a9284-111">`enum` 类型的存储格式和可取值范围由基础类型决定。</span><span class="sxs-lookup"><span data-stu-id="a9284-111">An `enum` type’s storage format and range of possible values are determined by its underlying type.</span></span> <span data-ttu-id="a9284-112">`enum` 类型需要使用的一组值不受其 `enum` 成员限制。</span><span class="sxs-lookup"><span data-stu-id="a9284-112">The set of values that an `enum` type can take on is not limited by its `enum` members.</span></span> <span data-ttu-id="a9284-113">尤其是，基础类型的 `enum` 的任何值都可以显式转换成 `enum` 类型，并作为 `enum` 类型的不同有效值。</span><span class="sxs-lookup"><span data-stu-id="a9284-113">In particular, any value of the underlying type of an `enum` can be cast to the `enum` type and is a distinct valid value of that `enum` type.</span></span>

<span data-ttu-id="a9284-114">以下示例声明基础类型为 `sbyte` 且名为“`Alignment`”的 `enum` 类型。</span><span class="sxs-lookup"><span data-stu-id="a9284-114">The following example declares an `enum` type named `Alignment` with an underlying type of `sbyte`.</span></span>

[!code-csharp[EnumStorage](../../../samples/snippets/csharp/tour/enums/Program.cs#L38-L43)]

<span data-ttu-id="a9284-115">如上面的示例所示，`enum` 成员声明可以包含用于指定成员值的常数表达式。</span><span class="sxs-lookup"><span data-stu-id="a9284-115">As shown by the previous example, an `enum` member declaration can include a constant expression that specifies the value of the member.</span></span> <span data-ttu-id="a9284-116">每个 `enum` 成员的常量值都必须介于 `enum` 的基础类型范围内。</span><span class="sxs-lookup"><span data-stu-id="a9284-116">The constant value for each `enum` member must be in the range of the underlying type of the `enum`.</span></span> <span data-ttu-id="a9284-117">如果 `enum` 成员声明未显式指定值，那么会为成员指定值 0（如果是 `enum` 类型中的首个成员）或原文前一个 `enum` 成员的值加 1。</span><span class="sxs-lookup"><span data-stu-id="a9284-117">When an `enum` member declaration does not explicitly specify a value, the member is given the value zero (if it is the first member in the `enum` type) or the value of the textually preceding `enum` member plus one.</span></span>

<span data-ttu-id="a9284-118">可使用类型显式转换功能将 `Enum` 值转换成整型值，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="a9284-118">`Enum` values can be converted to integral values and vice versa using type casts.</span></span> <span data-ttu-id="a9284-119">例如:</span><span class="sxs-lookup"><span data-stu-id="a9284-119">For example:</span></span>

[!code-csharp[EnumStorage](../../../samples/snippets/csharp/tour/enums/Program.cs#L49-L50)]

<span data-ttu-id="a9284-120">任何 `enum` 类型的默认值都是已转换成 `enum` 类型的整型值 0。</span><span class="sxs-lookup"><span data-stu-id="a9284-120">The default value of any `enum` type is the integral value zero converted to the `enum` type.</span></span> <span data-ttu-id="a9284-121">如果变量被自动初始化为默认值，这就是为 `enum` 类型的变量指定的值。</span><span class="sxs-lookup"><span data-stu-id="a9284-121">In cases where variables are automatically initialized to a default value, this is the value given to variables of `enum` types.</span></span> <span data-ttu-id="a9284-122">为了让 `enum` 类型的默认值可供方便使用，文本类型 `0` 隐式转换成任意 `enum` 类型。</span><span class="sxs-lookup"><span data-stu-id="a9284-122">In order for the default value of an `enum` type to be easily available, the literal `0` implicitly converts to any `enum` type.</span></span> <span data-ttu-id="a9284-123">因此，可以运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="a9284-123">Thus, the following is permitted.</span></span>

[!code-csharp[EnumZero](../../../samples/snippets/csharp/tour/enums/Program.cs#L58-L58)]

>[!div class="step-by-step"]
><span data-ttu-id="a9284-124">[上一页](interfaces.md)
>[下一页](delegates.md)</span><span class="sxs-lookup"><span data-stu-id="a9284-124">[Previous](interfaces.md)
[Next](delegates.md)</span></span>