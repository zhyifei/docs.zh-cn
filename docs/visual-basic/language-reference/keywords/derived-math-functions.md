---
title: 派生的数学函数 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- arithmetic operations, derived math functions
- cosecant function
- arcsecant function
- arccotangent function
- functions [Visual Basic], derived math functions
- inverse functions
- math functions, derived
- derived math functions
- cotangent function
- angles
- secant function
- trigonometric functions
- logarithms
- arccosecant function
- hyperbolic functions
- arcsine function
- degrees
- arccosine function
ms.assetid: 63e449d8-9444-44fb-8db1-6d9cf346e2aa
ms.openlocfilehash: 0d0606c52d1d50fcc2fd8eea3ad2851c95b18a69
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58836579"
---
# <a name="derived-math-functions-visual-basic"></a><span data-ttu-id="573e0-102">派生的数学函数 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="573e0-102">Derived Math Functions (Visual Basic)</span></span>
<span data-ttu-id="573e0-103">下表显示了可以派生自的内部函数的数学函数的非内部函数的数学函数<xref:System.Math?displayProperty=nameWithType>对象。</span><span class="sxs-lookup"><span data-stu-id="573e0-103">The following table shows non-intrinsic math functions that can be derived from the intrinsic math functions of the <xref:System.Math?displayProperty=nameWithType> object.</span></span> <span data-ttu-id="573e0-104">可以通过添加访问内部函数的数学函数`Imports System.Math`到文件或项目。</span><span class="sxs-lookup"><span data-stu-id="573e0-104">You can access the intrinsic math functions by adding `Imports System.Math` to your file or project.</span></span>  
  
|<span data-ttu-id="573e0-105">函数</span><span class="sxs-lookup"><span data-stu-id="573e0-105">Function</span></span>|<span data-ttu-id="573e0-106">派生的等效项</span><span class="sxs-lookup"><span data-stu-id="573e0-106">Derived equivalents</span></span>|  
|--------------|-------------------------|  
|<span data-ttu-id="573e0-107">正割值 (Sec(x))</span><span class="sxs-lookup"><span data-stu-id="573e0-107">Secant (Sec(x))</span></span>|<span data-ttu-id="573e0-108">1 / Cos(x)</span><span class="sxs-lookup"><span data-stu-id="573e0-108">1 / Cos(x)</span></span>|  
|<span data-ttu-id="573e0-109">余割值 (Csc(x))</span><span class="sxs-lookup"><span data-stu-id="573e0-109">Cosecant (Csc(x))</span></span>|<span data-ttu-id="573e0-110">1 / Sin(x)</span><span class="sxs-lookup"><span data-stu-id="573e0-110">1 / Sin(x)</span></span>|  
|<span data-ttu-id="573e0-111">余切值 (Ctan(x))</span><span class="sxs-lookup"><span data-stu-id="573e0-111">Cotangent (Ctan(x))</span></span>|<span data-ttu-id="573e0-112">1 / Tan(x)</span><span class="sxs-lookup"><span data-stu-id="573e0-112">1 / Tan(x)</span></span>|  
|<span data-ttu-id="573e0-113">反正弦值 (Asin(x))</span><span class="sxs-lookup"><span data-stu-id="573e0-113">Inverse sine (Asin(x))</span></span>|<span data-ttu-id="573e0-114">Atan (x / Sqrt (-x \* x + 1))</span><span class="sxs-lookup"><span data-stu-id="573e0-114">Atan(x / Sqrt(-x \* x + 1))</span></span>|  
|<span data-ttu-id="573e0-115">反余弦值 (Acos(x))</span><span class="sxs-lookup"><span data-stu-id="573e0-115">Inverse cosine (Acos(x))</span></span>|<span data-ttu-id="573e0-116">Atan(-x / Sqrt(-x \* x + 1)) + 2 \* Atan(1)</span><span class="sxs-lookup"><span data-stu-id="573e0-116">Atan(-x / Sqrt(-x \* x + 1)) + 2 \* Atan(1)</span></span>|  
|<span data-ttu-id="573e0-117">反正割 (Asec(x))</span><span class="sxs-lookup"><span data-stu-id="573e0-117">Inverse secant (Asec(x))</span></span>|<span data-ttu-id="573e0-118">2 \* Atan(1) – Atan(Sign(x) / Sqrt (x \* x – 1))</span><span class="sxs-lookup"><span data-stu-id="573e0-118">2 \* Atan(1) – Atan(Sign(x) / Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="573e0-119">反余割值 (Acsc(x))</span><span class="sxs-lookup"><span data-stu-id="573e0-119">Inverse cosecant (Acsc(x))</span></span>|<span data-ttu-id="573e0-120">Atan(Sign(x) / Sqrt (x \* x – 1))</span><span class="sxs-lookup"><span data-stu-id="573e0-120">Atan(Sign(x) / Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="573e0-121">反余切值 (Acot(x))</span><span class="sxs-lookup"><span data-stu-id="573e0-121">Inverse cotangent (Acot(x))</span></span>|<span data-ttu-id="573e0-122">2 \* Atan(1) - Atan(x)</span><span class="sxs-lookup"><span data-stu-id="573e0-122">2 \* Atan(1) - Atan(x)</span></span>|  
|<span data-ttu-id="573e0-123">双曲正弦值 (Sinh(x))</span><span class="sxs-lookup"><span data-stu-id="573e0-123">Hyperbolic sine (Sinh(x))</span></span>|<span data-ttu-id="573e0-124">(Exp(x) – Exp(-x)) / 2</span><span class="sxs-lookup"><span data-stu-id="573e0-124">(Exp(x) – Exp(-x)) / 2</span></span>|  
|<span data-ttu-id="573e0-125">双曲余弦值 (Cosh(x))</span><span class="sxs-lookup"><span data-stu-id="573e0-125">Hyperbolic cosine (Cosh(x))</span></span>|<span data-ttu-id="573e0-126">(Exp(x) + Exp(-x)) / 2</span><span class="sxs-lookup"><span data-stu-id="573e0-126">(Exp(x) + Exp(-x)) / 2</span></span>|  
|<span data-ttu-id="573e0-127">双曲正切值 (Tanh(x))</span><span class="sxs-lookup"><span data-stu-id="573e0-127">Hyperbolic tangent (Tanh(x))</span></span>|<span data-ttu-id="573e0-128">(Exp(x) – Exp(-x)) / (Exp(x) + Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="573e0-128">(Exp(x) – Exp(-x)) / (Exp(x) + Exp(-x))</span></span>|  
|<span data-ttu-id="573e0-129">双曲正割值 (Sech(x))</span><span class="sxs-lookup"><span data-stu-id="573e0-129">Hyperbolic secant (Sech(x))</span></span>|<span data-ttu-id="573e0-130">2 / (Exp(x) + Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="573e0-130">2 / (Exp(x) + Exp(-x))</span></span>|  
|<span data-ttu-id="573e0-131">双曲余割值 (Csch(x))</span><span class="sxs-lookup"><span data-stu-id="573e0-131">Hyperbolic cosecant (Csch(x))</span></span>|<span data-ttu-id="573e0-132">2 / (Exp(x) – Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="573e0-132">2 / (Exp(x) – Exp(-x))</span></span>|  
|<span data-ttu-id="573e0-133">双曲余切值 (Coth(x))</span><span class="sxs-lookup"><span data-stu-id="573e0-133">Hyperbolic cotangent (Coth(x))</span></span>|<span data-ttu-id="573e0-134">(Exp(x) + Exp(-x)) / (Exp(x) – Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="573e0-134">(Exp(x) + Exp(-x)) / (Exp(x) – Exp(-x))</span></span>|  
|<span data-ttu-id="573e0-135">反双曲正弦值 (Asinh(x))</span><span class="sxs-lookup"><span data-stu-id="573e0-135">Inverse hyperbolic sine (Asinh(x))</span></span>|<span data-ttu-id="573e0-136">日志 (x + Sqrt (x \* x + 1))</span><span class="sxs-lookup"><span data-stu-id="573e0-136">Log(x + Sqrt(x \* x + 1))</span></span>|  
|<span data-ttu-id="573e0-137">反双曲余弦值 (Acosh(x))</span><span class="sxs-lookup"><span data-stu-id="573e0-137">Inverse hyperbolic cosine (Acosh(x))</span></span>|<span data-ttu-id="573e0-138">日志 (x + Sqrt (x \* x – 1))</span><span class="sxs-lookup"><span data-stu-id="573e0-138">Log(x + Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="573e0-139">反双曲正切值 (Atanh(x))</span><span class="sxs-lookup"><span data-stu-id="573e0-139">Inverse hyperbolic tangent (Atanh(x))</span></span>|<span data-ttu-id="573e0-140">日志 ((1 + x) / (1 – x)) / 2</span><span class="sxs-lookup"><span data-stu-id="573e0-140">Log((1 + x) / (1 – x)) / 2</span></span>|  
|<span data-ttu-id="573e0-141">反双曲正割值 (AsecH(x))</span><span class="sxs-lookup"><span data-stu-id="573e0-141">Inverse hyperbolic secant (AsecH(x))</span></span>|<span data-ttu-id="573e0-142">Log ((Sqrt (-x \* x + 1) + 1) / x)</span><span class="sxs-lookup"><span data-stu-id="573e0-142">Log((Sqrt(-x \* x + 1) + 1) / x)</span></span>|  
|<span data-ttu-id="573e0-143">反双曲余割值 (Acsch(x))</span><span class="sxs-lookup"><span data-stu-id="573e0-143">Inverse hyperbolic cosecant (Acsch(x))</span></span>|<span data-ttu-id="573e0-144">Log((Sign(x) \* Sqrt (x \* x + 1) + 1) / x)</span><span class="sxs-lookup"><span data-stu-id="573e0-144">Log((Sign(x) \* Sqrt(x \* x + 1) + 1) / x)</span></span>|  
|<span data-ttu-id="573e0-145">反双曲余切值 (Acoth(x))</span><span class="sxs-lookup"><span data-stu-id="573e0-145">Inverse hyperbolic cotangent (Acoth(x))</span></span>|<span data-ttu-id="573e0-146">日志 ((x + 1) / (x – 1)) / 2</span><span class="sxs-lookup"><span data-stu-id="573e0-146">Log((x + 1) / (x – 1)) / 2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="573e0-147">请参阅</span><span class="sxs-lookup"><span data-stu-id="573e0-147">See also</span></span>

- [<span data-ttu-id="573e0-148">数学函数</span><span class="sxs-lookup"><span data-stu-id="573e0-148">Math Functions</span></span>](../../../visual-basic/language-reference/functions/math-functions.md)
