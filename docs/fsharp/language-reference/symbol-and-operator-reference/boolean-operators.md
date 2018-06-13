---
title: 布尔运算符 (F#)
description: '了解有关 F # 编程语言中可用的布尔运算符。'
ms.date: 05/16/2016
ms.openlocfilehash: f8516ceb531907400f98dc4226d2985d3119e9e9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33563423"
---
# <a name="boolean-operators"></a><span data-ttu-id="38752-103">布尔运算符</span><span class="sxs-lookup"><span data-stu-id="38752-103">Boolean Operators</span></span>

<span data-ttu-id="38752-104">本主题介绍对 F # 语言中的布尔运算符的支持。</span><span class="sxs-lookup"><span data-stu-id="38752-104">This topic describes the support for Boolean operators in the F# language.</span></span>


## <a name="summary-of-boolean-operators"></a><span data-ttu-id="38752-105">布尔运算符的摘要</span><span class="sxs-lookup"><span data-stu-id="38752-105">Summary of Boolean Operators</span></span>
<span data-ttu-id="38752-106">下表总结了在 F # 语言中可用的布尔运算符。</span><span class="sxs-lookup"><span data-stu-id="38752-106">The following table summarizes the Boolean operators that are available in the F# language.</span></span> <span data-ttu-id="38752-107">支持这些运算符的唯一类型是`bool`类型。</span><span class="sxs-lookup"><span data-stu-id="38752-107">The only type supported by these operators is the `bool` type.</span></span>

|<span data-ttu-id="38752-108">运算符</span><span class="sxs-lookup"><span data-stu-id="38752-108">Operator</span></span>|<span data-ttu-id="38752-109">描述</span><span class="sxs-lookup"><span data-stu-id="38752-109">Description</span></span>|
|--------|-----------|
|`not`|<span data-ttu-id="38752-110">布尔求反</span><span class="sxs-lookup"><span data-stu-id="38752-110">Boolean negation</span></span>|
|<code>&#124;&#124;</code>|<span data-ttu-id="38752-111">布尔 OR</span><span class="sxs-lookup"><span data-stu-id="38752-111">Boolean OR</span></span>|
|`&&`|<span data-ttu-id="38752-112">布尔 AND</span><span class="sxs-lookup"><span data-stu-id="38752-112">Boolean AND</span></span>|

<span data-ttu-id="38752-113">布尔 AND 和 OR 运算符执行*短路计算*，必要以确定表达式的总体结果时，即它们评估运算符右侧的表达式。</span><span class="sxs-lookup"><span data-stu-id="38752-113">The Boolean AND and OR operators perform *short-circuit evaluation*, that is, they evaluate the expression on the right of the operator only when it is necessary to determine the overall result of the expression.</span></span> <span data-ttu-id="38752-114">第二个表达式`&&`运算符计算仅当第一个表达式的计算结果为`true`; 的第二个表达式`||`运算符计算仅当第一个表达式的计算结果为`false`。</span><span class="sxs-lookup"><span data-stu-id="38752-114">The second expression of the `&&` operator is evaluated only if the first expression evaluates to `true`; the second expression of the `||` operator is evaluated only if the first expression evaluates to `false`.</span></span>

## <a name="see-also"></a><span data-ttu-id="38752-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="38752-115">See Also</span></span>
[<span data-ttu-id="38752-116">位运算符</span><span class="sxs-lookup"><span data-stu-id="38752-116">Bitwise Operators</span></span>](bitwise-operators.md)

[<span data-ttu-id="38752-117">算术运算符</span><span class="sxs-lookup"><span data-stu-id="38752-117">Arithmetic Operators</span></span>](arithmetic-operators.md)

[<span data-ttu-id="38752-118">符号和运算符参考</span><span class="sxs-lookup"><span data-stu-id="38752-118">Symbol and Operator Reference</span></span>](index.md)
