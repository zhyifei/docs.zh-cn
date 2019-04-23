---
title: 数值和比较运算符
ms.date: 03/30/2017
ms.assetid: 25b4a26a-06f2-4f80-87a9-76705ed46197
ms.openlocfilehash: b29f78a13d6d0313e0ad29754f6d13ac08be1092
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2019
ms.locfileid: "59973338"
---
# <a name="numeric-and-comparison-operators"></a><span data-ttu-id="91e45-102">数值和比较运算符</span><span class="sxs-lookup"><span data-stu-id="91e45-102">Numeric and Comparison Operators</span></span>

<span data-ttu-id="91e45-103">算术运算符和比较运算符在公共语言运行库 (CLR) 中按预期方式工作，但有以下几点例外：</span><span class="sxs-lookup"><span data-stu-id="91e45-103">Arithmetic and comparison operators work as expected in the common language runtime (CLR) except as follows:</span></span>

- <span data-ttu-id="91e45-104">SQL 不支持对浮点数字使用取模运算符。</span><span class="sxs-lookup"><span data-stu-id="91e45-104">SQL does not support the modulus operator on floating-point numbers.</span></span>

- <span data-ttu-id="91e45-105">SQL 不支持未校验的算法。</span><span class="sxs-lookup"><span data-stu-id="91e45-105">SQL does not support unchecked arithmetic.</span></span>

- <span data-ttu-id="91e45-106">在无法复制到 SQL 中的表达式中使用增量和减量运算符时会产生副作用，因而不支持此类运算符。</span><span class="sxs-lookup"><span data-stu-id="91e45-106">Increment and decrement operators cause side-effects when you use them in expressions that cannot be replicated in SQL and are, therefore, not supported.</span></span>

## <a name="supported-operators"></a><span data-ttu-id="91e45-107">支持的运算符</span><span class="sxs-lookup"><span data-stu-id="91e45-107">Supported Operators</span></span>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="91e45-108">支持以下运算符。</span><span class="sxs-lookup"><span data-stu-id="91e45-108">supports the following operators.</span></span>

- <span data-ttu-id="91e45-109">基本算术运算符：</span><span class="sxs-lookup"><span data-stu-id="91e45-109">Basic arithmetic operators:</span></span>

  - `+`

  - <span data-ttu-id="91e45-110">`-`（减号）</span><span class="sxs-lookup"><span data-stu-id="91e45-110">`-` (subtraction)</span></span>

  - `*`

  - `/`

  - <span data-ttu-id="91e45-111">Visual Basic 整除 (`\`)</span><span class="sxs-lookup"><span data-stu-id="91e45-111">Visual Basic integer division (`\`)</span></span>

  - <span data-ttu-id="91e45-112">`%` (Visual Basic `Mod`)</span><span class="sxs-lookup"><span data-stu-id="91e45-112">`%` (Visual Basic `Mod`)</span></span>

  - `<<`

  - `>>`

  - <span data-ttu-id="91e45-113">`-`（一元求反）</span><span class="sxs-lookup"><span data-stu-id="91e45-113">`-` (unary negation)</span></span>

- <span data-ttu-id="91e45-114">基本比较运算符：</span><span class="sxs-lookup"><span data-stu-id="91e45-114">Basic comparison operators:</span></span>

  - <span data-ttu-id="91e45-115">Visual Basic `=` 和 C# `==`</span><span class="sxs-lookup"><span data-stu-id="91e45-115">Visual Basic `=` and C# `==`</span></span>

  - <span data-ttu-id="91e45-116">Visual Basic `<>` 和 C# `!=`</span><span class="sxs-lookup"><span data-stu-id="91e45-116">Visual Basic `<>` and C# `!=`</span></span>

  - <span data-ttu-id="91e45-117">Visual Basic `Is/IsNot`</span><span class="sxs-lookup"><span data-stu-id="91e45-117">Visual Basic `Is/IsNot`</span></span>

  - `<`

  - `<=`

  - `>`

  - `>=`

## <a name="see-also"></a><span data-ttu-id="91e45-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="91e45-118">See also</span></span>

- [<span data-ttu-id="91e45-119">数据类型和函数</span><span class="sxs-lookup"><span data-stu-id="91e45-119">Data Types and Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
- [<span data-ttu-id="91e45-120">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="91e45-120">C# Operators</span></span>](../../../../../../docs/csharp/language-reference/operators/index.md)
- [<span data-ttu-id="91e45-121">运算符</span><span class="sxs-lookup"><span data-stu-id="91e45-121">Operators</span></span>](../../../../../visual-basic/language-reference/operators/index.md)
