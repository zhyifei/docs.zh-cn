---
title: 布尔运算符 (F#)
description: '了解有关 F # 编程语言中可用的布尔运算符。'
ms.date: 05/16/2016
ms.openlocfilehash: faa181090efa7c4064a30b42d83afa4888e98b82
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2018
ms.locfileid: "44272314"
---
# <a name="boolean-operators"></a><span data-ttu-id="9f457-103">布尔运算符</span><span class="sxs-lookup"><span data-stu-id="9f457-103">Boolean Operators</span></span>

<span data-ttu-id="9f457-104">本主题介绍对 F # 语言中的布尔运算符的支持。</span><span class="sxs-lookup"><span data-stu-id="9f457-104">This topic describes the support for Boolean operators in the F# language.</span></span>

## <a name="summary-of-boolean-operators"></a><span data-ttu-id="9f457-105">布尔运算符的摘要</span><span class="sxs-lookup"><span data-stu-id="9f457-105">Summary of Boolean Operators</span></span>

<span data-ttu-id="9f457-106">下表汇总了 F # 语言中可用的布尔运算符。</span><span class="sxs-lookup"><span data-stu-id="9f457-106">The following table summarizes the Boolean operators that are available in the F# language.</span></span> <span data-ttu-id="9f457-107">这些运算符支持的唯一类型是`bool`类型。</span><span class="sxs-lookup"><span data-stu-id="9f457-107">The only type supported by these operators is the `bool` type.</span></span>

|<span data-ttu-id="9f457-108">运算符</span><span class="sxs-lookup"><span data-stu-id="9f457-108">Operator</span></span>|<span data-ttu-id="9f457-109">描述</span><span class="sxs-lookup"><span data-stu-id="9f457-109">Description</span></span>|
|--------|-----------|
|`not`|<span data-ttu-id="9f457-110">布尔值求反</span><span class="sxs-lookup"><span data-stu-id="9f457-110">Boolean negation</span></span>|
|<code>&#124;&#124;</code>|<span data-ttu-id="9f457-111">布尔 OR</span><span class="sxs-lookup"><span data-stu-id="9f457-111">Boolean OR</span></span>|
|`&&`|<span data-ttu-id="9f457-112">布尔 AND</span><span class="sxs-lookup"><span data-stu-id="9f457-112">Boolean AND</span></span>|

<span data-ttu-id="9f457-113">执行布尔 AND 和 OR 运算符*短路计算*，即，它们仅在必要时以确定总体结果表达式的计算运算符右侧的表达式。</span><span class="sxs-lookup"><span data-stu-id="9f457-113">The Boolean AND and OR operators perform *short-circuit evaluation*, that is, they evaluate the expression on the right of the operator only when it is necessary to determine the overall result of the expression.</span></span> <span data-ttu-id="9f457-114">第二个表达式`&&`仅当第一个表达式的计算结果为计算运算符`true`; 的第二个表达式`||`仅当第一个表达式的计算结果为计算运算符`false`。</span><span class="sxs-lookup"><span data-stu-id="9f457-114">The second expression of the `&&` operator is evaluated only if the first expression evaluates to `true`; the second expression of the `||` operator is evaluated only if the first expression evaluates to `false`.</span></span>

## <a name="see-also"></a><span data-ttu-id="9f457-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="9f457-115">See also</span></span>

- [<span data-ttu-id="9f457-116">位运算符</span><span class="sxs-lookup"><span data-stu-id="9f457-116">Bitwise Operators</span></span>](bitwise-operators.md)
- [<span data-ttu-id="9f457-117">算术运算符</span><span class="sxs-lookup"><span data-stu-id="9f457-117">Arithmetic Operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="9f457-118">符号和运算符参考</span><span class="sxs-lookup"><span data-stu-id="9f457-118">Symbol and Operator Reference</span></span>](index.md)
