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
# <a name="derived-math-functions-visual-basic"></a><span data-ttu-id="09985-102">派生的数学函数 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="09985-102">Derived Math Functions (Visual Basic)</span></span>
<span data-ttu-id="09985-103">下表显示了可以从 <xref:System.Math?displayProperty=nameWithType> 对象的内部数学函数派生的非内部数学函数。</span><span class="sxs-lookup"><span data-stu-id="09985-103">The following table shows non-intrinsic math functions that can be derived from the intrinsic math functions of the <xref:System.Math?displayProperty=nameWithType> object.</span></span> <span data-ttu-id="09985-104">您可以通过将 `Imports System.Math` 添加到您的文件或项目来访问内部数学函数。</span><span class="sxs-lookup"><span data-stu-id="09985-104">You can access the intrinsic math functions by adding `Imports System.Math` to your file or project.</span></span>  
  
|<span data-ttu-id="09985-105">函数</span><span class="sxs-lookup"><span data-stu-id="09985-105">Function</span></span>|<span data-ttu-id="09985-106">派生等效项</span><span class="sxs-lookup"><span data-stu-id="09985-106">Derived equivalents</span></span>|  
|--------------|-------------------------|  
|<span data-ttu-id="09985-107">正割（秒（x））</span><span class="sxs-lookup"><span data-stu-id="09985-107">Secant (Sec(x))</span></span>|<span data-ttu-id="09985-108">1/Cos （x）</span><span class="sxs-lookup"><span data-stu-id="09985-108">1 / Cos(x)</span></span>|  
|<span data-ttu-id="09985-109">余割（Csc （x））</span><span class="sxs-lookup"><span data-stu-id="09985-109">Cosecant (Csc(x))</span></span>|<span data-ttu-id="09985-110">1/Sin （x）</span><span class="sxs-lookup"><span data-stu-id="09985-110">1 / Sin(x)</span></span>|  
|<span data-ttu-id="09985-111">余切（Ctan （x））</span><span class="sxs-lookup"><span data-stu-id="09985-111">Cotangent (Ctan(x))</span></span>|<span data-ttu-id="09985-112">1/Tan （x）</span><span class="sxs-lookup"><span data-stu-id="09985-112">1 / Tan(x)</span></span>|  
|<span data-ttu-id="09985-113">反正弦值（Asin （x））</span><span class="sxs-lookup"><span data-stu-id="09985-113">Inverse sine (Asin(x))</span></span>|<span data-ttu-id="09985-114">Atan （x/Sqrt （-x \* x + 1））</span><span class="sxs-lookup"><span data-stu-id="09985-114">Atan(x / Sqrt(-x \* x + 1))</span></span>|  
|<span data-ttu-id="09985-115">反余弦（Acos （x））</span><span class="sxs-lookup"><span data-stu-id="09985-115">Inverse cosine (Acos(x))</span></span>|<span data-ttu-id="09985-116">Atan （-x/Sqrt （-x \* x + 1）） + 2 \* Atan （1）</span><span class="sxs-lookup"><span data-stu-id="09985-116">Atan(-x / Sqrt(-x \* x + 1)) + 2 \* Atan(1)</span></span>|  
|<span data-ttu-id="09985-117">反正割（Asec （x））</span><span class="sxs-lookup"><span data-stu-id="09985-117">Inverse secant (Asec(x))</span></span>|<span data-ttu-id="09985-118">2 \* Atan （1）– Atan （Sign （x）/Sqrt （x \* x –1））</span><span class="sxs-lookup"><span data-stu-id="09985-118">2 \* Atan(1) – Atan(Sign(x) / Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="09985-119">反余割（Acsc （x））</span><span class="sxs-lookup"><span data-stu-id="09985-119">Inverse cosecant (Acsc(x))</span></span>|<span data-ttu-id="09985-120">Atan （Sign （x）/Sqrt （x \* x –1））</span><span class="sxs-lookup"><span data-stu-id="09985-120">Atan(Sign(x) / Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="09985-121">反余切（Acot （x））</span><span class="sxs-lookup"><span data-stu-id="09985-121">Inverse cotangent (Acot(x))</span></span>|<span data-ttu-id="09985-122">2 \* Atan （1）-Atan （x）</span><span class="sxs-lookup"><span data-stu-id="09985-122">2 \* Atan(1) - Atan(x)</span></span>|  
|<span data-ttu-id="09985-123">双曲正弦值（Sinh （x））</span><span class="sxs-lookup"><span data-stu-id="09985-123">Hyperbolic sine (Sinh(x))</span></span>|<span data-ttu-id="09985-124">(Exp(x) – Exp(-x)) / 2</span><span class="sxs-lookup"><span data-stu-id="09985-124">(Exp(x) – Exp(-x)) / 2</span></span>|  
|<span data-ttu-id="09985-125">双曲余弦值（Cosh （x））</span><span class="sxs-lookup"><span data-stu-id="09985-125">Hyperbolic cosine (Cosh(x))</span></span>|<span data-ttu-id="09985-126">(Exp(x) + Exp(-x)) / 2</span><span class="sxs-lookup"><span data-stu-id="09985-126">(Exp(x) + Exp(-x)) / 2</span></span>|  
|<span data-ttu-id="09985-127">双曲正切值（Tanh （x））</span><span class="sxs-lookup"><span data-stu-id="09985-127">Hyperbolic tangent (Tanh(x))</span></span>|<span data-ttu-id="09985-128">(Exp(x) – Exp(-x)) / (Exp(x) + Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="09985-128">(Exp(x) – Exp(-x)) / (Exp(x) + Exp(-x))</span></span>|  
|<span data-ttu-id="09985-129">双曲正割（Sech （x））</span><span class="sxs-lookup"><span data-stu-id="09985-129">Hyperbolic secant (Sech(x))</span></span>|<span data-ttu-id="09985-130">2 / (Exp(x) + Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="09985-130">2 / (Exp(x) + Exp(-x))</span></span>|  
|<span data-ttu-id="09985-131">双曲余割（Csch （x））</span><span class="sxs-lookup"><span data-stu-id="09985-131">Hyperbolic cosecant (Csch(x))</span></span>|<span data-ttu-id="09985-132">2 / (Exp(x) – Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="09985-132">2 / (Exp(x) – Exp(-x))</span></span>|  
|<span data-ttu-id="09985-133">双曲余切（Coth （x））</span><span class="sxs-lookup"><span data-stu-id="09985-133">Hyperbolic cotangent (Coth(x))</span></span>|<span data-ttu-id="09985-134">(Exp(x) + Exp(-x)) / (Exp(x) – Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="09985-134">(Exp(x) + Exp(-x)) / (Exp(x) – Exp(-x))</span></span>|  
|<span data-ttu-id="09985-135">反双曲正弦值（Asinh （x））</span><span class="sxs-lookup"><span data-stu-id="09985-135">Inverse hyperbolic sine (Asinh(x))</span></span>|<span data-ttu-id="09985-136">Log （x + Sqrt （x \* x + 1））</span><span class="sxs-lookup"><span data-stu-id="09985-136">Log(x + Sqrt(x \* x + 1))</span></span>|  
|<span data-ttu-id="09985-137">反双曲余弦（Acosh （x））</span><span class="sxs-lookup"><span data-stu-id="09985-137">Inverse hyperbolic cosine (Acosh(x))</span></span>|<span data-ttu-id="09985-138">Log （x + Sqrt （x \* x –1））</span><span class="sxs-lookup"><span data-stu-id="09985-138">Log(x + Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="09985-139">反双曲正切值（Atanh （x））</span><span class="sxs-lookup"><span data-stu-id="09985-139">Inverse hyperbolic tangent (Atanh(x))</span></span>|<span data-ttu-id="09985-140">Log （（1 + x）/（1– x））/2</span><span class="sxs-lookup"><span data-stu-id="09985-140">Log((1 + x) / (1 – x)) / 2</span></span>|  
|<span data-ttu-id="09985-141">反双曲正割（AsecH （x））</span><span class="sxs-lookup"><span data-stu-id="09985-141">Inverse hyperbolic secant (AsecH(x))</span></span>|<span data-ttu-id="09985-142">Log （（Sqrt （-x \* x + 1） + 1）/x）</span><span class="sxs-lookup"><span data-stu-id="09985-142">Log((Sqrt(-x \* x + 1) + 1) / x)</span></span>|  
|<span data-ttu-id="09985-143">反双曲余割（Acsch （x））</span><span class="sxs-lookup"><span data-stu-id="09985-143">Inverse hyperbolic cosecant (Acsch(x))</span></span>|<span data-ttu-id="09985-144">Log （（Sign （x） \* Sqrt （x \* x + 1） + 1）/x）</span><span class="sxs-lookup"><span data-stu-id="09985-144">Log((Sign(x) \* Sqrt(x \* x + 1) + 1) / x)</span></span>|  
|<span data-ttu-id="09985-145">反双曲余切（Acoth （x））</span><span class="sxs-lookup"><span data-stu-id="09985-145">Inverse hyperbolic cotangent (Acoth(x))</span></span>|<span data-ttu-id="09985-146">Log （（x + 1）/（x –1））/2</span><span class="sxs-lookup"><span data-stu-id="09985-146">Log((x + 1) / (x – 1)) / 2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="09985-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="09985-147">See also</span></span>

- [<span data-ttu-id="09985-148">数学函数</span><span class="sxs-lookup"><span data-stu-id="09985-148">Math Functions</span></span>](../../../visual-basic/language-reference/functions/math-functions.md)
