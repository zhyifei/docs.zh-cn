---
title: "布尔运算符 (F#)"
description: "了解有关 F # 编程语言中可用的布尔运算符。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: f79370b8-4bc2-4704-b514-d392c80942bd
ms.openlocfilehash: 63588f2e371bf2c0f15de0b8a26a46be82f832c7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="boolean-operators"></a><span data-ttu-id="6dc15-104">布尔运算符</span><span class="sxs-lookup"><span data-stu-id="6dc15-104">Boolean Operators</span></span>

<span data-ttu-id="6dc15-105">本主题介绍对 F # 语言中的布尔运算符的支持。</span><span class="sxs-lookup"><span data-stu-id="6dc15-105">This topic describes the support for Boolean operators in the F# language.</span></span>


## <a name="summary-of-boolean-operators"></a><span data-ttu-id="6dc15-106">布尔运算符的摘要</span><span class="sxs-lookup"><span data-stu-id="6dc15-106">Summary of Boolean Operators</span></span>
<span data-ttu-id="6dc15-107">下表总结了在 F # 语言中可用的布尔运算符。</span><span class="sxs-lookup"><span data-stu-id="6dc15-107">The following table summarizes the Boolean operators that are available in the F# language.</span></span> <span data-ttu-id="6dc15-108">支持这些运算符的唯一类型是`bool`类型。</span><span class="sxs-lookup"><span data-stu-id="6dc15-108">The only type supported by these operators is the `bool` type.</span></span>

|<span data-ttu-id="6dc15-109">运算符</span><span class="sxs-lookup"><span data-stu-id="6dc15-109">Operator</span></span>|<span data-ttu-id="6dc15-110">描述</span><span class="sxs-lookup"><span data-stu-id="6dc15-110">Description</span></span>|
|--------|-----------|
|`not`|<span data-ttu-id="6dc15-111">布尔求反</span><span class="sxs-lookup"><span data-stu-id="6dc15-111">Boolean negation</span></span>|
|<code>&#124;&#124;</code>|<span data-ttu-id="6dc15-112">布尔 OR</span><span class="sxs-lookup"><span data-stu-id="6dc15-112">Boolean OR</span></span>|
|`&&`|<span data-ttu-id="6dc15-113">布尔 AND</span><span class="sxs-lookup"><span data-stu-id="6dc15-113">Boolean AND</span></span>|

<span data-ttu-id="6dc15-114">布尔 AND 和 OR 运算符执行*短路计算*，必要以确定表达式的总体结果时，即它们评估运算符右侧的表达式。</span><span class="sxs-lookup"><span data-stu-id="6dc15-114">The Boolean AND and OR operators perform *short-circuit evaluation*, that is, they evaluate the expression on the right of the operator only when it is necessary to determine the overall result of the expression.</span></span> <span data-ttu-id="6dc15-115">第二个表达式`&&`运算符计算仅当第一个表达式的计算结果为`true`; 的第二个表达式`||`运算符计算仅当第一个表达式的计算结果为`false`。</span><span class="sxs-lookup"><span data-stu-id="6dc15-115">The second expression of the `&&` operator is evaluated only if the first expression evaluates to `true`; the second expression of the `||` operator is evaluated only if the first expression evaluates to `false`.</span></span>

## <a name="see-also"></a><span data-ttu-id="6dc15-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6dc15-116">See Also</span></span>
[<span data-ttu-id="6dc15-117">位运算符</span><span class="sxs-lookup"><span data-stu-id="6dc15-117">Bitwise Operators</span></span>](bitwise-operators.md)

[<span data-ttu-id="6dc15-118">算术运算符</span><span class="sxs-lookup"><span data-stu-id="6dc15-118">Arithmetic Operators</span></span>](arithmetic-operators.md)

[<span data-ttu-id="6dc15-119">符号和运算符参考</span><span class="sxs-lookup"><span data-stu-id="6dc15-119">Symbol and Operator Reference</span></span>](index.md)
