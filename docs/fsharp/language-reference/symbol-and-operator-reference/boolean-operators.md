---
title: 布尔运算符
description: 了解有关中可用的布尔运算符F#编程语言。
ms.date: 05/16/2016
ms.openlocfilehash: ad4bdd1121389f7e280647dbe0c4d0098ffb17df
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641898"
---
# <a name="boolean-operators"></a><span data-ttu-id="b303a-103">布尔运算符</span><span class="sxs-lookup"><span data-stu-id="b303a-103">Boolean Operators</span></span>

<span data-ttu-id="b303a-104">本主题介绍中的布尔运算符的支持F#语言。</span><span class="sxs-lookup"><span data-stu-id="b303a-104">This topic describes the support for Boolean operators in the F# language.</span></span>

## <a name="summary-of-boolean-operators"></a><span data-ttu-id="b303a-105">布尔运算符的摘要</span><span class="sxs-lookup"><span data-stu-id="b303a-105">Summary of Boolean Operators</span></span>

<span data-ttu-id="b303a-106">下表总结了中可用的布尔运算符F#语言。</span><span class="sxs-lookup"><span data-stu-id="b303a-106">The following table summarizes the Boolean operators that are available in the F# language.</span></span> <span data-ttu-id="b303a-107">这些运算符支持的唯一类型是`bool`类型。</span><span class="sxs-lookup"><span data-stu-id="b303a-107">The only type supported by these operators is the `bool` type.</span></span>

|<span data-ttu-id="b303a-108">运算符</span><span class="sxs-lookup"><span data-stu-id="b303a-108">Operator</span></span>|<span data-ttu-id="b303a-109">描述</span><span class="sxs-lookup"><span data-stu-id="b303a-109">Description</span></span>|
|--------|-----------|
|`not`|<span data-ttu-id="b303a-110">布尔值求反</span><span class="sxs-lookup"><span data-stu-id="b303a-110">Boolean negation</span></span>|
|<code>&#124;&#124;</code>|<span data-ttu-id="b303a-111">布尔 OR</span><span class="sxs-lookup"><span data-stu-id="b303a-111">Boolean OR</span></span>|
|`&&`|<span data-ttu-id="b303a-112">布尔 AND</span><span class="sxs-lookup"><span data-stu-id="b303a-112">Boolean AND</span></span>|

<span data-ttu-id="b303a-113">执行布尔 AND 和 OR 运算符*短路计算*，即，它们仅在必要时以确定总体结果表达式的计算运算符右侧的表达式。</span><span class="sxs-lookup"><span data-stu-id="b303a-113">The Boolean AND and OR operators perform *short-circuit evaluation*, that is, they evaluate the expression on the right of the operator only when it is necessary to determine the overall result of the expression.</span></span> <span data-ttu-id="b303a-114">第二个表达式`&&`仅当第一个表达式的计算结果为计算运算符`true`; 的第二个表达式`||`仅当第一个表达式的计算结果为计算运算符`false`。</span><span class="sxs-lookup"><span data-stu-id="b303a-114">The second expression of the `&&` operator is evaluated only if the first expression evaluates to `true`; the second expression of the `||` operator is evaluated only if the first expression evaluates to `false`.</span></span>

## <a name="see-also"></a><span data-ttu-id="b303a-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="b303a-115">See also</span></span>

- [<span data-ttu-id="b303a-116">位运算符</span><span class="sxs-lookup"><span data-stu-id="b303a-116">Bitwise Operators</span></span>](bitwise-operators.md)
- [<span data-ttu-id="b303a-117">算术运算符</span><span class="sxs-lookup"><span data-stu-id="b303a-117">Arithmetic Operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="b303a-118">符号和运算符参考</span><span class="sxs-lookup"><span data-stu-id="b303a-118">Symbol and Operator Reference</span></span>](index.md)
