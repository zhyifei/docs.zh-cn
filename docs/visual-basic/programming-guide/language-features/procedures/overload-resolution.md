---
title: 重载决策 (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic code, procedures
- overload resolution
- procedures [Visual Basic], overloading
- procedures [Visual Basic], calling
- procedure overloading [Visual Basic], overload resolution
- signatures [Visual Basic], procedure
- overloads [Visual Basic], resolution
ms.assetid: 766115d1-4352-45fb-859f-6063e0de0ec0
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e62560d853c95bc4bba6ba829d8579ee4388858e
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="overload-resolution-visual-basic"></a><span data-ttu-id="5ed93-102">重载决策 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5ed93-102">Overload Resolution (Visual Basic)</span></span>
<span data-ttu-id="5ed93-103">当 Visual Basic 编译器遇到对多个重载版本中定义的过程的调用时，编译器必须确定哪个要调用的重载。</span><span class="sxs-lookup"><span data-stu-id="5ed93-103">When the Visual Basic compiler encounters a call to a procedure that is defined in several overloaded versions, the compiler must decide which of the overloads to call.</span></span> <span data-ttu-id="5ed93-104">这是通过执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="5ed93-104">It does this by performing the following steps:</span></span>  
  
1.  <span data-ttu-id="5ed93-105">**辅助功能。**</span><span class="sxs-lookup"><span data-stu-id="5ed93-105">**Accessibility.**</span></span> <span data-ttu-id="5ed93-106">它会消除任何重载具有阻止调用代码中调用它的访问级别。</span><span class="sxs-lookup"><span data-stu-id="5ed93-106">It eliminates any overload with an access level that prevents the calling code from calling it.</span></span>  
  
2.  <span data-ttu-id="5ed93-107">**参数数目。**</span><span class="sxs-lookup"><span data-stu-id="5ed93-107">**Number of Parameters.**</span></span> <span data-ttu-id="5ed93-108">它会消除定义不同数量的参数提供的调用中的任何重载。</span><span class="sxs-lookup"><span data-stu-id="5ed93-108">It eliminates any overload that defines a different number of parameters than are supplied in the call.</span></span>  
  
3.  <span data-ttu-id="5ed93-109">**参数数据类型。**</span><span class="sxs-lookup"><span data-stu-id="5ed93-109">**Parameter Data Types.**</span></span> <span data-ttu-id="5ed93-110">编译器会通过扩展方法的实例方法的优先级。</span><span class="sxs-lookup"><span data-stu-id="5ed93-110">The compiler gives instance methods preference over extension methods.</span></span> <span data-ttu-id="5ed93-111">如果需要仅扩大转换来匹配的过程调用找到的任何实例方法，则所有扩展方法将都删除并编译器继续使用实例的方法候选。</span><span class="sxs-lookup"><span data-stu-id="5ed93-111">If any instance method is found that requires only widening conversions to match the procedure call, all extension methods are dropped and the compiler continues with only the instance method candidates.</span></span> <span data-ttu-id="5ed93-112">如果未不找到任何此类的实例方法，它将使用实例方法和扩展方法继续。</span><span class="sxs-lookup"><span data-stu-id="5ed93-112">If no such instance method is found, it continues with both instance and extension methods.</span></span>  
  
     <span data-ttu-id="5ed93-113">在此步骤中，它会消除任何重载的调用的自变量的数据类型无法转换到的重载中定义的参数类型。</span><span class="sxs-lookup"><span data-stu-id="5ed93-113">In this step, it eliminates any overload for which the data types of the calling arguments cannot be converted to the parameter types defined in the overload.</span></span>  
  
4.  <span data-ttu-id="5ed93-114">**收缩转换。**</span><span class="sxs-lookup"><span data-stu-id="5ed93-114">**Narrowing Conversions.**</span></span> <span data-ttu-id="5ed93-115">它消除了需要从调用的自变量类型收缩转换为已定义的参数类型的任何重载。</span><span class="sxs-lookup"><span data-stu-id="5ed93-115">It eliminates any overload that requires a narrowing conversion from the calling argument types to the defined parameter types.</span></span> <span data-ttu-id="5ed93-116">这是 true 是否类型检查开关 ([Option Strict 语句](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) 是`On`或`Off`。</span><span class="sxs-lookup"><span data-stu-id="5ed93-116">This is true whether the type checking switch ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) is `On` or `Off`.</span></span>  
  
5.  <span data-ttu-id="5ed93-117">**最小扩大。**</span><span class="sxs-lookup"><span data-stu-id="5ed93-117">**Least Widening.**</span></span> <span data-ttu-id="5ed93-118">编译器会将对其余的重载。</span><span class="sxs-lookup"><span data-stu-id="5ed93-118">The compiler considers the remaining overloads in pairs.</span></span> <span data-ttu-id="5ed93-119">对于每个对，它将进行比较已定义的参数的数据的类型。</span><span class="sxs-lookup"><span data-stu-id="5ed93-119">For each pair, it compares the data types of the defined parameters.</span></span> <span data-ttu-id="5ed93-120">如果所有的重载之一中的类型扩大到另一部分中的相应类型，编译器可以消除后者。</span><span class="sxs-lookup"><span data-stu-id="5ed93-120">If the types in one of the overloads all widen to the corresponding types in the other, the compiler eliminates the latter.</span></span> <span data-ttu-id="5ed93-121">也就是说，它将保留要求最少量的扩大转换的重载。</span><span class="sxs-lookup"><span data-stu-id="5ed93-121">That is, it retains the overload that requires the least amount of widening.</span></span>  
  
6.  <span data-ttu-id="5ed93-122">**单个候选项。**</span><span class="sxs-lookup"><span data-stu-id="5ed93-122">**Single Candidate.**</span></span> <span data-ttu-id="5ed93-123">它将继续考虑重载成对直到只有一个重载仍将保留，并解决了对该重载的调用。</span><span class="sxs-lookup"><span data-stu-id="5ed93-123">It continues considering overloads in pairs until only one overload remains, and it resolves the call to that overload.</span></span> <span data-ttu-id="5ed93-124">如果编译器不能减少为单个候选重载，它会生成错误。</span><span class="sxs-lookup"><span data-stu-id="5ed93-124">If the compiler cannot reduce the overloads to a single candidate, it generates an error.</span></span>  
  
 <span data-ttu-id="5ed93-125">下图显示了确定其中的一组要调用的重载版本的过程。</span><span class="sxs-lookup"><span data-stu-id="5ed93-125">The following illustration shows the process that determines which of a set of overloaded versions to call.</span></span>  
  
 <span data-ttu-id="5ed93-126">![重载解析过程的流程图](./media/overloadres.gif "OverloadRes")</span><span class="sxs-lookup"><span data-stu-id="5ed93-126">![Flow diagram of overload resolution process](./media/overloadres.gif "OverloadRes")</span></span>  
<span data-ttu-id="5ed93-127">在重载版本中</span><span class="sxs-lookup"><span data-stu-id="5ed93-127">Resolving among overloaded versions</span></span>  
  
 <span data-ttu-id="5ed93-128">下面的示例阐释了此重载决策过程。</span><span class="sxs-lookup"><span data-stu-id="5ed93-128">The following example illustrates this overload resolution process.</span></span>  
  
 [!code-vb[VbVbcnProcedures#62](./codesnippet/VisualBasic/overload-resolution_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#63](./codesnippet/VisualBasic/overload-resolution_2.vb)]  
  
 <span data-ttu-id="5ed93-129">在第一个调用中，编译器消除第一个重载，因为第一个参数的类型 (`Short`) 收缩到相应的参数的类型 (`Byte`)。</span><span class="sxs-lookup"><span data-stu-id="5ed93-129">In the first call, the compiler eliminates the first overload because the type of the first argument (`Short`) narrows to the type of the corresponding parameter (`Byte`).</span></span> <span data-ttu-id="5ed93-130">因为每个自变量类型中的第二个重载，它会然后消除第三个重载 (`Short`和`Single`) 扩大到第三个重载中的对应类型 (`Integer`和`Single`)。</span><span class="sxs-lookup"><span data-stu-id="5ed93-130">It then eliminates the third overload because each argument type in the second overload (`Short` and `Single`) widens to the corresponding type in the third overload (`Integer` and `Single`).</span></span> <span data-ttu-id="5ed93-131">第二个重载都需要较少扩大转换，因此编译器将使用它的调用。</span><span class="sxs-lookup"><span data-stu-id="5ed93-131">The second overload requires less widening, so the compiler uses it for the call.</span></span>  
  
 <span data-ttu-id="5ed93-132">在第二个调用中，编译器不能消除任何基于收缩的重载。</span><span class="sxs-lookup"><span data-stu-id="5ed93-132">In the second call, the compiler cannot eliminate any of the overloads on the basis of narrowing.</span></span> <span data-ttu-id="5ed93-133">因为它可以调用使用最少扩大量自变量类型的第二个重载，它会出于同一原因如下所示的第一个调用，消除第三个重载。</span><span class="sxs-lookup"><span data-stu-id="5ed93-133">It eliminates the third overload for the same reason as in the first call, because it can call the second overload with less widening of the argument types.</span></span> <span data-ttu-id="5ed93-134">但是，编译器无法解析的第一个和第二个重载之间。</span><span class="sxs-lookup"><span data-stu-id="5ed93-134">However, the compiler cannot resolve between the first and second overloads.</span></span> <span data-ttu-id="5ed93-135">每个具有一个已定义的参数类型扩大到另一部分中的相应类型 (`Byte`到`Short`，但`Single`到`Double`)。</span><span class="sxs-lookup"><span data-stu-id="5ed93-135">Each has one defined parameter type that widens to the corresponding type in the other (`Byte` to `Short`, but `Single` to `Double`).</span></span> <span data-ttu-id="5ed93-136">因此，编译器将生成重载解析错误。</span><span class="sxs-lookup"><span data-stu-id="5ed93-136">The compiler therefore generates an overload resolution error.</span></span>  
  
## <a name="overloaded-optional-and-paramarray-arguments"></a><span data-ttu-id="5ed93-137">重载可选和 ParamArray 自变量</span><span class="sxs-lookup"><span data-stu-id="5ed93-137">Overloaded Optional and ParamArray Arguments</span></span>  
 <span data-ttu-id="5ed93-138">如果过程的两个重载具有完全相同的签名，只不过声明的最后一个参数[可选](../../../../visual-basic/language-reference/modifiers/optional.md)之一中和[ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)中另一个，则编译器将解析对作为该过程的调用如下所示：</span><span class="sxs-lookup"><span data-stu-id="5ed93-138">If two overloads of a procedure have identical signatures except that the last parameter is declared [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) in one and [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) in the other, the compiler resolves a call to that procedure as follows:</span></span>  
  
|<span data-ttu-id="5ed93-139">如果调用提供了最后一个参数为</span><span class="sxs-lookup"><span data-stu-id="5ed93-139">If the call supplies the last argument as</span></span>|<span data-ttu-id="5ed93-140">编译器将解析对声明为最后一个参数的重载的调用</span><span class="sxs-lookup"><span data-stu-id="5ed93-140">The compiler resolves the call to the overload declaring the last argument as</span></span>|  
|---|---|  
|<span data-ttu-id="5ed93-141">（省略自变量） 没有值</span><span class="sxs-lookup"><span data-stu-id="5ed93-141">No value (argument omitted)</span></span>|`Optional`|  
|<span data-ttu-id="5ed93-142">单个值</span><span class="sxs-lookup"><span data-stu-id="5ed93-142">A single value</span></span>|`Optional`|  
|<span data-ttu-id="5ed93-143">以逗号分隔的列表中的两个或多个值</span><span class="sxs-lookup"><span data-stu-id="5ed93-143">Two or more values in a comma-separated list</span></span>|`ParamArray`|  
|<span data-ttu-id="5ed93-144">（包括空数组） 任何长度的数组</span><span class="sxs-lookup"><span data-stu-id="5ed93-144">An array of any length (including an empty array)</span></span>|`ParamArray`|  
  
## <a name="see-also"></a><span data-ttu-id="5ed93-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="5ed93-145">See Also</span></span>  
 [<span data-ttu-id="5ed93-146">可选参数</span><span class="sxs-lookup"><span data-stu-id="5ed93-146">Optional Parameters</span></span>](./optional-parameters.md)  
 [<span data-ttu-id="5ed93-147">参数数组</span><span class="sxs-lookup"><span data-stu-id="5ed93-147">Parameter Arrays</span></span>](./parameter-arrays.md)  
 [<span data-ttu-id="5ed93-148">过程重载</span><span class="sxs-lookup"><span data-stu-id="5ed93-148">Procedure Overloading</span></span>](./procedure-overloading.md)  
 [<span data-ttu-id="5ed93-149">过程疑难解答</span><span class="sxs-lookup"><span data-stu-id="5ed93-149">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)  
 [<span data-ttu-id="5ed93-150">如何：定义一个过程的多个版本</span><span class="sxs-lookup"><span data-stu-id="5ed93-150">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)  
 [<span data-ttu-id="5ed93-151">如何：调用重载过程</span><span class="sxs-lookup"><span data-stu-id="5ed93-151">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)  
 [<span data-ttu-id="5ed93-152">如何：重载带有可选参数的过程</span><span class="sxs-lookup"><span data-stu-id="5ed93-152">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)  
 [<span data-ttu-id="5ed93-153">如何：重载参数数量不确定的过程</span><span class="sxs-lookup"><span data-stu-id="5ed93-153">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)  
 [<span data-ttu-id="5ed93-154">重载过程注意事项</span><span class="sxs-lookup"><span data-stu-id="5ed93-154">Considerations in Overloading Procedures</span></span>](./considerations-in-overloading-procedures.md)  
 [<span data-ttu-id="5ed93-155">重载</span><span class="sxs-lookup"><span data-stu-id="5ed93-155">Overloads</span></span>](../../../../visual-basic/language-reference/modifiers/overloads.md)  
 [<span data-ttu-id="5ed93-156">扩展方法</span><span class="sxs-lookup"><span data-stu-id="5ed93-156">Extension Methods</span></span>](./extension-methods.md)
