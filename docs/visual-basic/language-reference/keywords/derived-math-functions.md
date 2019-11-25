---
title: 派生的数学函数
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
ms.openlocfilehash: 73cf56dd72f2baac0474d6f5c4e88228a1fe38cf
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349854"
---
# <a name="derived-math-functions-visual-basic"></a><span data-ttu-id="be25f-102">派生的数学函数 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="be25f-102">Derived Math Functions (Visual Basic)</span></span>
<span data-ttu-id="be25f-103">The following table shows non-intrinsic math functions that can be derived from the intrinsic math functions of the <xref:System.Math?displayProperty=nameWithType> object.</span><span class="sxs-lookup"><span data-stu-id="be25f-103">The following table shows non-intrinsic math functions that can be derived from the intrinsic math functions of the <xref:System.Math?displayProperty=nameWithType> object.</span></span> <span data-ttu-id="be25f-104">You can access the intrinsic math functions by adding `Imports System.Math` to your file or project.</span><span class="sxs-lookup"><span data-stu-id="be25f-104">You can access the intrinsic math functions by adding `Imports System.Math` to your file or project.</span></span>  
  
|<span data-ttu-id="be25f-105">函数</span><span class="sxs-lookup"><span data-stu-id="be25f-105">Function</span></span>|<span data-ttu-id="be25f-106">Derived equivalents</span><span class="sxs-lookup"><span data-stu-id="be25f-106">Derived equivalents</span></span>|  
|--------------|-------------------------|  
|<span data-ttu-id="be25f-107">Secant (Sec(x))</span><span class="sxs-lookup"><span data-stu-id="be25f-107">Secant (Sec(x))</span></span>|<span data-ttu-id="be25f-108">1 / Cos(x)</span><span class="sxs-lookup"><span data-stu-id="be25f-108">1 / Cos(x)</span></span>|  
|<span data-ttu-id="be25f-109">Cosecant (Csc(x))</span><span class="sxs-lookup"><span data-stu-id="be25f-109">Cosecant (Csc(x))</span></span>|<span data-ttu-id="be25f-110">1 / Sin(x)</span><span class="sxs-lookup"><span data-stu-id="be25f-110">1 / Sin(x)</span></span>|  
|<span data-ttu-id="be25f-111">Cotangent (Ctan(x))</span><span class="sxs-lookup"><span data-stu-id="be25f-111">Cotangent (Ctan(x))</span></span>|<span data-ttu-id="be25f-112">1 / Tan(x)</span><span class="sxs-lookup"><span data-stu-id="be25f-112">1 / Tan(x)</span></span>|  
|<span data-ttu-id="be25f-113">Inverse sine (Asin(x))</span><span class="sxs-lookup"><span data-stu-id="be25f-113">Inverse sine (Asin(x))</span></span>|<span data-ttu-id="be25f-114">Atan(x / Sqrt(-x \* x + 1))</span><span class="sxs-lookup"><span data-stu-id="be25f-114">Atan(x / Sqrt(-x \* x + 1))</span></span>|  
|<span data-ttu-id="be25f-115">Inverse cosine (Acos(x))</span><span class="sxs-lookup"><span data-stu-id="be25f-115">Inverse cosine (Acos(x))</span></span>|<span data-ttu-id="be25f-116">Atan(-x / Sqrt(-x \* x + 1)) + 2 \* Atan(1)</span><span class="sxs-lookup"><span data-stu-id="be25f-116">Atan(-x / Sqrt(-x \* x + 1)) + 2 \* Atan(1)</span></span>|  
|<span data-ttu-id="be25f-117">Inverse secant (Asec(x))</span><span class="sxs-lookup"><span data-stu-id="be25f-117">Inverse secant (Asec(x))</span></span>|<span data-ttu-id="be25f-118">2 \* Atan(1) – Atan(Sign(x) / Sqrt(x \* x – 1))</span><span class="sxs-lookup"><span data-stu-id="be25f-118">2 \* Atan(1) – Atan(Sign(x) / Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="be25f-119">Inverse cosecant (Acsc(x))</span><span class="sxs-lookup"><span data-stu-id="be25f-119">Inverse cosecant (Acsc(x))</span></span>|<span data-ttu-id="be25f-120">Atan(Sign(x) / Sqrt(x \* x – 1))</span><span class="sxs-lookup"><span data-stu-id="be25f-120">Atan(Sign(x) / Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="be25f-121">Inverse cotangent (Acot(x))</span><span class="sxs-lookup"><span data-stu-id="be25f-121">Inverse cotangent (Acot(x))</span></span>|<span data-ttu-id="be25f-122">2 \* Atan(1) - Atan(x)</span><span class="sxs-lookup"><span data-stu-id="be25f-122">2 \* Atan(1) - Atan(x)</span></span>|  
|<span data-ttu-id="be25f-123">Hyperbolic sine (Sinh(x))</span><span class="sxs-lookup"><span data-stu-id="be25f-123">Hyperbolic sine (Sinh(x))</span></span>|<span data-ttu-id="be25f-124">(Exp(x) – Exp(-x)) / 2</span><span class="sxs-lookup"><span data-stu-id="be25f-124">(Exp(x) – Exp(-x)) / 2</span></span>|  
|<span data-ttu-id="be25f-125">Hyperbolic cosine (Cosh(x))</span><span class="sxs-lookup"><span data-stu-id="be25f-125">Hyperbolic cosine (Cosh(x))</span></span>|<span data-ttu-id="be25f-126">(Exp(x) + Exp(-x)) / 2</span><span class="sxs-lookup"><span data-stu-id="be25f-126">(Exp(x) + Exp(-x)) / 2</span></span>|  
|<span data-ttu-id="be25f-127">Hyperbolic tangent (Tanh(x))</span><span class="sxs-lookup"><span data-stu-id="be25f-127">Hyperbolic tangent (Tanh(x))</span></span>|<span data-ttu-id="be25f-128">(Exp(x) – Exp(-x)) / (Exp(x) + Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="be25f-128">(Exp(x) – Exp(-x)) / (Exp(x) + Exp(-x))</span></span>|  
|<span data-ttu-id="be25f-129">Hyperbolic secant (Sech(x))</span><span class="sxs-lookup"><span data-stu-id="be25f-129">Hyperbolic secant (Sech(x))</span></span>|<span data-ttu-id="be25f-130">2 / (Exp(x) + Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="be25f-130">2 / (Exp(x) + Exp(-x))</span></span>|  
|<span data-ttu-id="be25f-131">Hyperbolic cosecant (Csch(x))</span><span class="sxs-lookup"><span data-stu-id="be25f-131">Hyperbolic cosecant (Csch(x))</span></span>|<span data-ttu-id="be25f-132">2 / (Exp(x) – Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="be25f-132">2 / (Exp(x) – Exp(-x))</span></span>|  
|<span data-ttu-id="be25f-133">Hyperbolic cotangent (Coth(x))</span><span class="sxs-lookup"><span data-stu-id="be25f-133">Hyperbolic cotangent (Coth(x))</span></span>|<span data-ttu-id="be25f-134">(Exp(x) + Exp(-x)) / (Exp(x) – Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="be25f-134">(Exp(x) + Exp(-x)) / (Exp(x) – Exp(-x))</span></span>|  
|<span data-ttu-id="be25f-135">Inverse hyperbolic sine (Asinh(x))</span><span class="sxs-lookup"><span data-stu-id="be25f-135">Inverse hyperbolic sine (Asinh(x))</span></span>|<span data-ttu-id="be25f-136">Log(x + Sqrt(x \* x + 1))</span><span class="sxs-lookup"><span data-stu-id="be25f-136">Log(x + Sqrt(x \* x + 1))</span></span>|  
|<span data-ttu-id="be25f-137">Inverse hyperbolic cosine (Acosh(x))</span><span class="sxs-lookup"><span data-stu-id="be25f-137">Inverse hyperbolic cosine (Acosh(x))</span></span>|<span data-ttu-id="be25f-138">Log(x + Sqrt(x \* x – 1))</span><span class="sxs-lookup"><span data-stu-id="be25f-138">Log(x + Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="be25f-139">Inverse hyperbolic tangent (Atanh(x))</span><span class="sxs-lookup"><span data-stu-id="be25f-139">Inverse hyperbolic tangent (Atanh(x))</span></span>|<span data-ttu-id="be25f-140">Log((1 + x) / (1 – x)) / 2</span><span class="sxs-lookup"><span data-stu-id="be25f-140">Log((1 + x) / (1 – x)) / 2</span></span>|  
|<span data-ttu-id="be25f-141">Inverse hyperbolic secant (AsecH(x))</span><span class="sxs-lookup"><span data-stu-id="be25f-141">Inverse hyperbolic secant (AsecH(x))</span></span>|<span data-ttu-id="be25f-142">Log((Sqrt(-x \* x + 1) + 1) / x)</span><span class="sxs-lookup"><span data-stu-id="be25f-142">Log((Sqrt(-x \* x + 1) + 1) / x)</span></span>|  
|<span data-ttu-id="be25f-143">Inverse hyperbolic cosecant (Acsch(x))</span><span class="sxs-lookup"><span data-stu-id="be25f-143">Inverse hyperbolic cosecant (Acsch(x))</span></span>|<span data-ttu-id="be25f-144">Log((Sign(x) \* Sqrt(x \* x + 1) + 1) / x)</span><span class="sxs-lookup"><span data-stu-id="be25f-144">Log((Sign(x) \* Sqrt(x \* x + 1) + 1) / x)</span></span>|  
|<span data-ttu-id="be25f-145">Inverse hyperbolic cotangent (Acoth(x))</span><span class="sxs-lookup"><span data-stu-id="be25f-145">Inverse hyperbolic cotangent (Acoth(x))</span></span>|<span data-ttu-id="be25f-146">Log((x + 1) / (x – 1)) / 2</span><span class="sxs-lookup"><span data-stu-id="be25f-146">Log((x + 1) / (x – 1)) / 2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="be25f-147">请参阅</span><span class="sxs-lookup"><span data-stu-id="be25f-147">See also</span></span>

- [<span data-ttu-id="be25f-148">数学函数</span><span class="sxs-lookup"><span data-stu-id="be25f-148">Math Functions</span></span>](../../../visual-basic/language-reference/functions/math-functions.md)
