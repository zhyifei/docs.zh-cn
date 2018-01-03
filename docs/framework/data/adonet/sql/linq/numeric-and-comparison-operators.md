---
title: "数值和比较运算符"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 25b4a26a-06f2-4f80-87a9-76705ed46197
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 0b89555bc71d95291c096d2e694c315720cfb41c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="numeric-and-comparison-operators"></a><span data-ttu-id="b26fd-102">数值和比较运算符</span><span class="sxs-lookup"><span data-stu-id="b26fd-102">Numeric and Comparison Operators</span></span>
<span data-ttu-id="b26fd-103">算术运算符和比较运算符在公共语言运行库 (CLR) 中按预期方式工作，但有以下几点例外：</span><span class="sxs-lookup"><span data-stu-id="b26fd-103">Arithmetic and comparison operators work as expected in the common language runtime (CLR) except as follows:</span></span>  
  
-   <span data-ttu-id="b26fd-104">SQL 不支持对浮点数字使用取模运算符。</span><span class="sxs-lookup"><span data-stu-id="b26fd-104">SQL does not support the modulus operator on floating-point numbers.</span></span>  
  
-   <span data-ttu-id="b26fd-105">SQL 不支持未校验的算法。</span><span class="sxs-lookup"><span data-stu-id="b26fd-105">SQL does not support unchecked arithmetic.</span></span>  
  
-   <span data-ttu-id="b26fd-106">在无法复制到 SQL 中的表达式中使用增量和减量运算符时会产生副作用，因而不支持此类运算符。</span><span class="sxs-lookup"><span data-stu-id="b26fd-106">Increment and decrement operators cause side-effects when you use them in expressions that cannot be replicated in SQL and are, therefore, not supported.</span></span>  
  
## <a name="supported-operators"></a><span data-ttu-id="b26fd-107">支持的运算符</span><span class="sxs-lookup"><span data-stu-id="b26fd-107">Supported Operators</span></span>  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="b26fd-108"> 支持以下运算符。</span><span class="sxs-lookup"><span data-stu-id="b26fd-108"> supports the following operators.</span></span>  
  
-   <span data-ttu-id="b26fd-109">基本算术运算符：</span><span class="sxs-lookup"><span data-stu-id="b26fd-109">Basic arithmetic operators:</span></span>  
  
    -   `+`  
  
    -   <span data-ttu-id="b26fd-110">`-`（减号）</span><span class="sxs-lookup"><span data-stu-id="b26fd-110">`-` (subtraction)</span></span>  
  
    -   `*`  
  
    -   `/`  
  
    -   <span data-ttu-id="b26fd-111">Visual Basic 整除 (`\`)</span><span class="sxs-lookup"><span data-stu-id="b26fd-111">Visual Basic integer division (`\`)</span></span>  
  
    -   <span data-ttu-id="b26fd-112">`%` (Visual Basic `Mod`)</span><span class="sxs-lookup"><span data-stu-id="b26fd-112">`%` (Visual Basic `Mod`)</span></span>  
  
    -   `<<`  
  
    -   `>>`  
  
    -   <span data-ttu-id="b26fd-113">`-`（一元求反）</span><span class="sxs-lookup"><span data-stu-id="b26fd-113">`-` (unary negation)</span></span>  
  
-   <span data-ttu-id="b26fd-114">基本比较运算符：</span><span class="sxs-lookup"><span data-stu-id="b26fd-114">Basic comparison operators:</span></span>  
  
    -   <span data-ttu-id="b26fd-115">Visual Basic `=` 和 C# `==`</span><span class="sxs-lookup"><span data-stu-id="b26fd-115">Visual Basic `=` and C# `==`</span></span>  
  
    -   <span data-ttu-id="b26fd-116">Visual Basic `<>` 和 C# `!=`</span><span class="sxs-lookup"><span data-stu-id="b26fd-116">Visual Basic `<>` and C# `!=`</span></span>  
  
    -   <span data-ttu-id="b26fd-117">Visual Basic `Is/IsNot`</span><span class="sxs-lookup"><span data-stu-id="b26fd-117">Visual Basic `Is/IsNot`</span></span>  
  
    -   `<`  
  
    -   `<=`  
  
    -   `>`  
  
    -   `>=`  
  
## <a name="see-also"></a><span data-ttu-id="b26fd-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="b26fd-118">See Also</span></span>  
 [<span data-ttu-id="b26fd-119">数据类型和函数</span><span class="sxs-lookup"><span data-stu-id="b26fd-119">Data Types and Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)  
 [<span data-ttu-id="b26fd-120">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="b26fd-120">C# Operators</span></span>](http://msdn.microsoft.com/library/0301e31f-22ad-49af-ac3c-d5eae7f0ac43)  
 [<span data-ttu-id="b26fd-121">运算符</span><span class="sxs-lookup"><span data-stu-id="b26fd-121">Operators</span></span>](../../../../../visual-basic/language-reference/operators/index.md)
