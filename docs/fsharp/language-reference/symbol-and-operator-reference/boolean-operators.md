---
title: 布尔运算符 (F#)
description: '了解有关 F # 编程语言中可用的布尔运算符。'
ms.date: 05/16/2016
ms.openlocfilehash: faa181090efa7c4064a30b42d83afa4888e98b82
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2018
ms.locfileid: "45516628"
---
# <a name="boolean-operators"></a><span data-ttu-id="dc753-103">布尔运算符</span><span class="sxs-lookup"><span data-stu-id="dc753-103">Boolean Operators</span></span>

<span data-ttu-id="dc753-104">本主题介绍对 F # 语言中的布尔运算符的支持。</span><span class="sxs-lookup"><span data-stu-id="dc753-104">This topic describes the support for Boolean operators in the F# language.</span></span>

## <a name="summary-of-boolean-operators"></a><span data-ttu-id="dc753-105">布尔运算符的摘要</span><span class="sxs-lookup"><span data-stu-id="dc753-105">Summary of Boolean Operators</span></span>

<span data-ttu-id="dc753-106">下表汇总了 F # 语言中可用的布尔运算符。</span><span class="sxs-lookup"><span data-stu-id="dc753-106">The following table summarizes the Boolean operators that are available in the F# language.</span></span> <span data-ttu-id="dc753-107">这些运算符支持的唯一类型是`bool`类型。</span><span class="sxs-lookup"><span data-stu-id="dc753-107">The only type supported by these operators is the `bool` type.</span></span>

|<span data-ttu-id="dc753-108">运算符</span><span class="sxs-lookup"><span data-stu-id="dc753-108">Operator</span></span>|<span data-ttu-id="dc753-109">描述</span><span class="sxs-lookup"><span data-stu-id="dc753-109">Description</span></span>|
|--------|-----------|
|`not`|<span data-ttu-id="dc753-110">布尔值求反</span><span class="sxs-lookup"><span data-stu-id="dc753-110">Boolean negation</span></span>|
|<code>&#124;&#124;</code>|<span data-ttu-id="dc753-111">布尔 OR</span><span class="sxs-lookup"><span data-stu-id="dc753-111">Boolean OR</span></span>|
|`&&`|<span data-ttu-id="dc753-112">布尔 AND</span><span class="sxs-lookup"><span data-stu-id="dc753-112">Boolean AND</span></span>|

<span data-ttu-id="dc753-113">执行布尔 AND 和 OR 运算符*短路计算*，即，它们仅在必要时以确定总体结果表达式的计算运算符右侧的表达式。</span><span class="sxs-lookup"><span data-stu-id="dc753-113">The Boolean AND and OR operators perform *short-circuit evaluation*, that is, they evaluate the expression on the right of the operator only when it is necessary to determine the overall result of the expression.</span></span> <span data-ttu-id="dc753-114">第二个表达式`&&`仅当第一个表达式的计算结果为计算运算符`true`; 的第二个表达式`||`仅当第一个表达式的计算结果为计算运算符`false`。</span><span class="sxs-lookup"><span data-stu-id="dc753-114">The second expression of the `&&` operator is evaluated only if the first expression evaluates to `true`; the second expression of the `||` operator is evaluated only if the first expression evaluates to `false`.</span></span>

## <a name="see-also"></a><span data-ttu-id="dc753-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="dc753-115">See also</span></span>

- [<span data-ttu-id="dc753-116">位运算符</span><span class="sxs-lookup"><span data-stu-id="dc753-116">Bitwise Operators</span></span>](bitwise-operators.md)
- [<span data-ttu-id="dc753-117">算术运算符</span><span class="sxs-lookup"><span data-stu-id="dc753-117">Arithmetic Operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="dc753-118">符号和运算符参考</span><span class="sxs-lookup"><span data-stu-id="dc753-118">Symbol and Operator Reference</span></span>](index.md)
