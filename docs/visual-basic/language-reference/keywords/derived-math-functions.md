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
ms.openlocfilehash: 1273871faf65afdd1a894c03f13a2c93507c1b13
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54505856"
---
# <a name="derived-math-functions-visual-basic"></a><span data-ttu-id="de5ed-102">派生的数学函数 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="de5ed-102">Derived Math Functions (Visual Basic)</span></span>
<span data-ttu-id="de5ed-103">下表显示了可以派生自的内部函数的数学函数的非内部函数的数学函数<xref:System.Math?displayProperty=nameWithType>对象。</span><span class="sxs-lookup"><span data-stu-id="de5ed-103">The following table shows non-intrinsic math functions that can be derived from the intrinsic math functions of the <xref:System.Math?displayProperty=nameWithType> object.</span></span> <span data-ttu-id="de5ed-104">可以通过添加访问内部函数的数学函数`Imports System.Math`到文件或项目。</span><span class="sxs-lookup"><span data-stu-id="de5ed-104">You can access the intrinsic math functions by adding `Imports System.Math` to your file or project.</span></span>  
  
|<span data-ttu-id="de5ed-105">函数</span><span class="sxs-lookup"><span data-stu-id="de5ed-105">Function</span></span>|<span data-ttu-id="de5ed-106">派生的等效项</span><span class="sxs-lookup"><span data-stu-id="de5ed-106">Derived equivalents</span></span>|  
|--------------|-------------------------|  
|<span data-ttu-id="de5ed-107">正割值 (Sec(x))</span><span class="sxs-lookup"><span data-stu-id="de5ed-107">Secant (Sec(x))</span></span>|<span data-ttu-id="de5ed-108">1 / Cos(x)</span><span class="sxs-lookup"><span data-stu-id="de5ed-108">1 / Cos(x)</span></span>|  
|<span data-ttu-id="de5ed-109">余割值 (Csc(x))</span><span class="sxs-lookup"><span data-stu-id="de5ed-109">Cosecant (Csc(x))</span></span>|<span data-ttu-id="de5ed-110">1 / Sin(x)</span><span class="sxs-lookup"><span data-stu-id="de5ed-110">1 / Sin(x)</span></span>|  
|<span data-ttu-id="de5ed-111">余切值 (Ctan(x))</span><span class="sxs-lookup"><span data-stu-id="de5ed-111">Cotangent (Ctan(x))</span></span>|<span data-ttu-id="de5ed-112">1 / Tan(x)</span><span class="sxs-lookup"><span data-stu-id="de5ed-112">1 / Tan(x)</span></span>|  
|<span data-ttu-id="de5ed-113">反正弦值 (Asin(x))</span><span class="sxs-lookup"><span data-stu-id="de5ed-113">Inverse sine (Asin(x))</span></span>|<span data-ttu-id="de5ed-114">Atan (x / Sqrt (-x \* x + 1))</span><span class="sxs-lookup"><span data-stu-id="de5ed-114">Atan(x / Sqrt(-x \* x + 1))</span></span>|  
|<span data-ttu-id="de5ed-115">反余弦值 (Acos(x))</span><span class="sxs-lookup"><span data-stu-id="de5ed-115">Inverse cosine (Acos(x))</span></span>|<span data-ttu-id="de5ed-116">Atan(-x / Sqrt(-x \* x + 1)) + 2 \* Atan(1)</span><span class="sxs-lookup"><span data-stu-id="de5ed-116">Atan(-x / Sqrt(-x \* x + 1)) + 2 \* Atan(1)</span></span>|  
|<span data-ttu-id="de5ed-117">反正割 (Asec(x))</span><span class="sxs-lookup"><span data-stu-id="de5ed-117">Inverse secant (Asec(x))</span></span>|<span data-ttu-id="de5ed-118">2 \* Atan(1) – Atan(Sign(x) / Sqrt (x \* x – 1))</span><span class="sxs-lookup"><span data-stu-id="de5ed-118">2 \* Atan(1) – Atan(Sign(x) / Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="de5ed-119">反余割值 (Acsc(x))</span><span class="sxs-lookup"><span data-stu-id="de5ed-119">Inverse cosecant (Acsc(x))</span></span>|<span data-ttu-id="de5ed-120">Atan(Sign(x) / Sqrt (x \* x – 1))</span><span class="sxs-lookup"><span data-stu-id="de5ed-120">Atan(Sign(x) / Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="de5ed-121">反余切值 (Acot(x))</span><span class="sxs-lookup"><span data-stu-id="de5ed-121">Inverse cotangent (Acot(x))</span></span>|<span data-ttu-id="de5ed-122">2 \* Atan(1) - Atan(x)</span><span class="sxs-lookup"><span data-stu-id="de5ed-122">2 \* Atan(1) - Atan(x)</span></span>|  
|<span data-ttu-id="de5ed-123">双曲正弦值 (Sinh(x))</span><span class="sxs-lookup"><span data-stu-id="de5ed-123">Hyperbolic sine (Sinh(x))</span></span>|<span data-ttu-id="de5ed-124">(Exp(x) – Exp(-x)) / 2</span><span class="sxs-lookup"><span data-stu-id="de5ed-124">(Exp(x) – Exp(-x)) / 2</span></span>|  
|<span data-ttu-id="de5ed-125">双曲余弦值 (Cosh(x))</span><span class="sxs-lookup"><span data-stu-id="de5ed-125">Hyperbolic cosine (Cosh(x))</span></span>|<span data-ttu-id="de5ed-126">(Exp(x) + Exp(-x)) / 2</span><span class="sxs-lookup"><span data-stu-id="de5ed-126">(Exp(x) + Exp(-x)) / 2</span></span>|  
|<span data-ttu-id="de5ed-127">双曲正切值 (Tanh(x))</span><span class="sxs-lookup"><span data-stu-id="de5ed-127">Hyperbolic tangent (Tanh(x))</span></span>|<span data-ttu-id="de5ed-128">(Exp(x) – Exp(-x)) / (Exp(x) + Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="de5ed-128">(Exp(x) – Exp(-x)) / (Exp(x) + Exp(-x))</span></span>|  
|<span data-ttu-id="de5ed-129">双曲正割值 (Sech(x))</span><span class="sxs-lookup"><span data-stu-id="de5ed-129">Hyperbolic secant (Sech(x))</span></span>|<span data-ttu-id="de5ed-130">2 / (Exp(x) + Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="de5ed-130">2 / (Exp(x) + Exp(-x))</span></span>|  
|<span data-ttu-id="de5ed-131">双曲余割值 (Csch(x))</span><span class="sxs-lookup"><span data-stu-id="de5ed-131">Hyperbolic cosecant (Csch(x))</span></span>|<span data-ttu-id="de5ed-132">2 / (Exp(x) – Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="de5ed-132">2 / (Exp(x) – Exp(-x))</span></span>|  
|<span data-ttu-id="de5ed-133">双曲余切值 (Coth(x))</span><span class="sxs-lookup"><span data-stu-id="de5ed-133">Hyperbolic cotangent (Coth(x))</span></span>|<span data-ttu-id="de5ed-134">(Exp(x) + Exp(-x)) / (Exp(x) – Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="de5ed-134">(Exp(x) + Exp(-x)) / (Exp(x) – Exp(-x))</span></span>|  
|<span data-ttu-id="de5ed-135">反双曲正弦值 (Asinh(x))</span><span class="sxs-lookup"><span data-stu-id="de5ed-135">Inverse hyperbolic sine (Asinh(x))</span></span>|<span data-ttu-id="de5ed-136">日志 (x + Sqrt (x \* x + 1))</span><span class="sxs-lookup"><span data-stu-id="de5ed-136">Log(x + Sqrt(x \* x + 1))</span></span>|  
|<span data-ttu-id="de5ed-137">反双曲余弦值 (Acosh(x))</span><span class="sxs-lookup"><span data-stu-id="de5ed-137">Inverse hyperbolic cosine (Acosh(x))</span></span>|<span data-ttu-id="de5ed-138">日志 (x + Sqrt (x \* x – 1))</span><span class="sxs-lookup"><span data-stu-id="de5ed-138">Log(x + Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="de5ed-139">反双曲正切值 (Atanh(x))</span><span class="sxs-lookup"><span data-stu-id="de5ed-139">Inverse hyperbolic tangent (Atanh(x))</span></span>|<span data-ttu-id="de5ed-140">日志 ((1 + x) / (1 – x)) / 2</span><span class="sxs-lookup"><span data-stu-id="de5ed-140">Log((1 + x) / (1 – x)) / 2</span></span>|  
|<span data-ttu-id="de5ed-141">反双曲正割值 (AsecH(x))</span><span class="sxs-lookup"><span data-stu-id="de5ed-141">Inverse hyperbolic secant (AsecH(x))</span></span>|<span data-ttu-id="de5ed-142">Log ((Sqrt (-x \* x + 1) + 1) / x)</span><span class="sxs-lookup"><span data-stu-id="de5ed-142">Log((Sqrt(-x \* x + 1) + 1) / x)</span></span>|  
|<span data-ttu-id="de5ed-143">反双曲余割值 (Acsch(x))</span><span class="sxs-lookup"><span data-stu-id="de5ed-143">Inverse hyperbolic cosecant (Acsch(x))</span></span>|<span data-ttu-id="de5ed-144">Log((Sign(x) \* Sqrt (x \* x + 1) + 1) / x)</span><span class="sxs-lookup"><span data-stu-id="de5ed-144">Log((Sign(x) \* Sqrt(x \* x + 1) + 1) / x)</span></span>|  
|<span data-ttu-id="de5ed-145">反双曲余切值 (Acoth(x))</span><span class="sxs-lookup"><span data-stu-id="de5ed-145">Inverse hyperbolic cotangent (Acoth(x))</span></span>|<span data-ttu-id="de5ed-146">日志 ((x + 1) / (x – 1)) / 2</span><span class="sxs-lookup"><span data-stu-id="de5ed-146">Log((x + 1) / (x – 1)) / 2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="de5ed-147">请参阅</span><span class="sxs-lookup"><span data-stu-id="de5ed-147">See also</span></span>
- [<span data-ttu-id="de5ed-148">数学函数</span><span class="sxs-lookup"><span data-stu-id="de5ed-148">Math Functions</span></span>](../../../visual-basic/language-reference/functions/math-functions.md)
