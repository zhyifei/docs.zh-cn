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
ms.openlocfilehash: 87faa623f5b145eec8b88e350fce4171125324dc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33596803"
---
# <a name="derived-math-functions-visual-basic"></a><span data-ttu-id="184d1-102">派生的数学函数 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="184d1-102">Derived Math Functions (Visual Basic)</span></span>
<span data-ttu-id="184d1-103">下表显示可以派生自的内部函数的数学函数的非内部的数学函数<xref:System.Math?displayProperty=nameWithType>对象。</span><span class="sxs-lookup"><span data-stu-id="184d1-103">The following table shows non-intrinsic math functions that can be derived from the intrinsic math functions of the <xref:System.Math?displayProperty=nameWithType> object.</span></span> <span data-ttu-id="184d1-104">你可以通过添加访问内部函数的数学函数`Imports System.Math`向你的文件或项目。</span><span class="sxs-lookup"><span data-stu-id="184d1-104">You can access the intrinsic math functions by adding `Imports System.Math` to your file or project.</span></span>  
  
|<span data-ttu-id="184d1-105">函数</span><span class="sxs-lookup"><span data-stu-id="184d1-105">Function</span></span>|<span data-ttu-id="184d1-106">派生的等效项</span><span class="sxs-lookup"><span data-stu-id="184d1-106">Derived equivalents</span></span>|  
|--------------|-------------------------|  
|<span data-ttu-id="184d1-107">正割值 (Sec(x))</span><span class="sxs-lookup"><span data-stu-id="184d1-107">Secant (Sec(x))</span></span>|<span data-ttu-id="184d1-108">1 / Cos(x)</span><span class="sxs-lookup"><span data-stu-id="184d1-108">1 / Cos(x)</span></span>|  
|<span data-ttu-id="184d1-109">余割值 (Csc(x))</span><span class="sxs-lookup"><span data-stu-id="184d1-109">Cosecant (Csc(x))</span></span>|<span data-ttu-id="184d1-110">1 / sin （x)</span><span class="sxs-lookup"><span data-stu-id="184d1-110">1 / Sin(x)</span></span>|  
|<span data-ttu-id="184d1-111">余切值 (Ctan(x))</span><span class="sxs-lookup"><span data-stu-id="184d1-111">Cotangent (Ctan(x))</span></span>|<span data-ttu-id="184d1-112">1 / Tan(x)</span><span class="sxs-lookup"><span data-stu-id="184d1-112">1 / Tan(x)</span></span>|  
|<span data-ttu-id="184d1-113">反正弦值 (Asin(x))</span><span class="sxs-lookup"><span data-stu-id="184d1-113">Inverse sine (Asin(x))</span></span>|<span data-ttu-id="184d1-114">Atan (x / Sqrt (-x \* x + 1))</span><span class="sxs-lookup"><span data-stu-id="184d1-114">Atan(x / Sqrt(-x \* x + 1))</span></span>|  
|<span data-ttu-id="184d1-115">反余弦值 (Acos(x))</span><span class="sxs-lookup"><span data-stu-id="184d1-115">Inverse cosine (Acos(x))</span></span>|<span data-ttu-id="184d1-116">Atan (-x / Sqrt (-x * x + 1)) + 2 \* Atan(1)</span><span class="sxs-lookup"><span data-stu-id="184d1-116">Atan(-x / Sqrt(-x * x + 1)) + 2 \* Atan(1)</span></span>|  
|<span data-ttu-id="184d1-117">反正割 (Asec(x))</span><span class="sxs-lookup"><span data-stu-id="184d1-117">Inverse secant (Asec(x))</span></span>|<span data-ttu-id="184d1-118">2 * Atan(1) – Atan(Sign(x) / Sqrt (x \* x-1))</span><span class="sxs-lookup"><span data-stu-id="184d1-118">2 * Atan(1) – Atan(Sign(x) / Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="184d1-119">反余割值 (Acsc(x))</span><span class="sxs-lookup"><span data-stu-id="184d1-119">Inverse cosecant (Acsc(x))</span></span>|<span data-ttu-id="184d1-120">Atan(Sign(x) / Sqrt (x \* x-1))</span><span class="sxs-lookup"><span data-stu-id="184d1-120">Atan(Sign(x) / Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="184d1-121">反余切值 (Acot(x))</span><span class="sxs-lookup"><span data-stu-id="184d1-121">Inverse cotangent (Acot(x))</span></span>|<span data-ttu-id="184d1-122">2 \* Atan(1)-Atan(x)</span><span class="sxs-lookup"><span data-stu-id="184d1-122">2 \* Atan(1) - Atan(x)</span></span>|  
|<span data-ttu-id="184d1-123">双曲正弦值 (Sinh(x))</span><span class="sxs-lookup"><span data-stu-id="184d1-123">Hyperbolic sine (Sinh(x))</span></span>|<span data-ttu-id="184d1-124">(Exp(x) – Exp(-x)) / 2</span><span class="sxs-lookup"><span data-stu-id="184d1-124">(Exp(x) – Exp(-x)) / 2</span></span>|  
|<span data-ttu-id="184d1-125">双曲余弦值 (Cosh(x))</span><span class="sxs-lookup"><span data-stu-id="184d1-125">Hyperbolic cosine (Cosh(x))</span></span>|<span data-ttu-id="184d1-126">(Exp(x) + Exp(-x)) / 2</span><span class="sxs-lookup"><span data-stu-id="184d1-126">(Exp(x) + Exp(-x)) / 2</span></span>|  
|<span data-ttu-id="184d1-127">双曲正切值 (Tanh(x))</span><span class="sxs-lookup"><span data-stu-id="184d1-127">Hyperbolic tangent (Tanh(x))</span></span>|<span data-ttu-id="184d1-128">(Exp(x) – Exp(-x)) / （Exp(x) + Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="184d1-128">(Exp(x) – Exp(-x)) / (Exp(x) + Exp(-x))</span></span>|  
|<span data-ttu-id="184d1-129">双曲正割值 (Sech(x))</span><span class="sxs-lookup"><span data-stu-id="184d1-129">Hyperbolic secant (Sech(x))</span></span>|<span data-ttu-id="184d1-130">2 / （Exp(x) + Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="184d1-130">2 / (Exp(x) + Exp(-x))</span></span>|  
|<span data-ttu-id="184d1-131">双曲余割值 (Csch(x))</span><span class="sxs-lookup"><span data-stu-id="184d1-131">Hyperbolic cosecant (Csch(x))</span></span>|<span data-ttu-id="184d1-132">2 / (Exp(x) – Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="184d1-132">2 / (Exp(x) – Exp(-x))</span></span>|  
|<span data-ttu-id="184d1-133">双曲余切值 (Coth(x))</span><span class="sxs-lookup"><span data-stu-id="184d1-133">Hyperbolic cotangent (Coth(x))</span></span>|<span data-ttu-id="184d1-134">(Exp(x) + Exp(-x)) / (Exp(x) – Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="184d1-134">(Exp(x) + Exp(-x)) / (Exp(x) – Exp(-x))</span></span>|  
|<span data-ttu-id="184d1-135">反双曲正弦值 (Asinh(x))</span><span class="sxs-lookup"><span data-stu-id="184d1-135">Inverse hyperbolic sine (Asinh(x))</span></span>|<span data-ttu-id="184d1-136">日志 (x + Sqrt (x \* x + 1))</span><span class="sxs-lookup"><span data-stu-id="184d1-136">Log(x + Sqrt(x \* x + 1))</span></span>|  
|<span data-ttu-id="184d1-137">反双曲余弦值 (Acosh(x))</span><span class="sxs-lookup"><span data-stu-id="184d1-137">Inverse hyperbolic cosine (Acosh(x))</span></span>|<span data-ttu-id="184d1-138">日志 (x + Sqrt (x \* x-1))</span><span class="sxs-lookup"><span data-stu-id="184d1-138">Log(x + Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="184d1-139">反双曲正切值 (Atanh(x))</span><span class="sxs-lookup"><span data-stu-id="184d1-139">Inverse hyperbolic tangent (Atanh(x))</span></span>|<span data-ttu-id="184d1-140">日志 ((1 + x) / (1-x)) / 2</span><span class="sxs-lookup"><span data-stu-id="184d1-140">Log((1 + x) / (1 – x)) / 2</span></span>|  
|<span data-ttu-id="184d1-141">反双曲正割值 (AsecH(x))</span><span class="sxs-lookup"><span data-stu-id="184d1-141">Inverse hyperbolic secant (AsecH(x))</span></span>|<span data-ttu-id="184d1-142">日志 ((Sqrt (-x \* x + 1) + 1) / x)</span><span class="sxs-lookup"><span data-stu-id="184d1-142">Log((Sqrt(-x \* x + 1) + 1) / x)</span></span>|  
|<span data-ttu-id="184d1-143">反双曲余割值 (Acsch(x))</span><span class="sxs-lookup"><span data-stu-id="184d1-143">Inverse hyperbolic cosecant (Acsch(x))</span></span>|<span data-ttu-id="184d1-144">Log((Sign(x) * Sqrt (x \* x + 1) + 1) / x)</span><span class="sxs-lookup"><span data-stu-id="184d1-144">Log((Sign(x) * Sqrt(x \* x + 1) + 1) / x)</span></span>|  
|<span data-ttu-id="184d1-145">反双曲余切值 (Acoth(x))</span><span class="sxs-lookup"><span data-stu-id="184d1-145">Inverse hyperbolic cotangent (Acoth(x))</span></span>|<span data-ttu-id="184d1-146">日志 ((x + 1) / (x-1)) / 2</span><span class="sxs-lookup"><span data-stu-id="184d1-146">Log((x + 1) / (x – 1)) / 2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="184d1-147">请参阅</span><span class="sxs-lookup"><span data-stu-id="184d1-147">See Also</span></span>  
 [<span data-ttu-id="184d1-148">数学函数</span><span class="sxs-lookup"><span data-stu-id="184d1-148">Math Functions</span></span>](../../../visual-basic/language-reference/functions/math-functions.md)
