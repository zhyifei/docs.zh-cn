---
title: "重载决策 (Visual Basic 中) |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic code, procedures
- overload resolution
- procedures, overloading
- procedures, calling
- procedure overloading, overload resolution
- signatures, procedure
- overloads, resolution
ms.assetid: 766115d1-4352-45fb-859f-6063e0de0ec0
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: a4f350af0f7d964df45974990991a2e94b26551e
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="overload-resolution-visual-basic"></a><span data-ttu-id="289c3-102">重载决策 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="289c3-102">Overload Resolution (Visual Basic)</span></span>
<span data-ttu-id="289c3-103">当[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]编译器遇到对在多个重载版本中定义的过程的调用，编译器必须决定哪要调用的重载。</span><span class="sxs-lookup"><span data-stu-id="289c3-103">When the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler encounters a call to a procedure that is defined in several overloaded versions, the compiler must decide which of the overloads to call.</span></span> <span data-ttu-id="289c3-104">这是通过执行以下步骤︰</span><span class="sxs-lookup"><span data-stu-id="289c3-104">It does this by performing the following steps:</span></span>  
  
1.  <span data-ttu-id="289c3-105">**可访问性。**</span><span class="sxs-lookup"><span data-stu-id="289c3-105">**Accessibility.**</span></span> <span data-ttu-id="289c3-106">它会消除具有防止调用代码中调用它的访问级别的任何重载。</span><span class="sxs-lookup"><span data-stu-id="289c3-106">It eliminates any overload with an access level that prevents the calling code from calling it.</span></span>  
  
2.  <span data-ttu-id="289c3-107">**参数个数。**</span><span class="sxs-lookup"><span data-stu-id="289c3-107">**Number of Parameters.**</span></span> <span data-ttu-id="289c3-108">它会消除定义不同数量的参数提供的调用中的任何重载。</span><span class="sxs-lookup"><span data-stu-id="289c3-108">It eliminates any overload that defines a different number of parameters than are supplied in the call.</span></span>  
  
3.  <span data-ttu-id="289c3-109">**参数数据类型。**</span><span class="sxs-lookup"><span data-stu-id="289c3-109">**Parameter Data Types.**</span></span> <span data-ttu-id="289c3-110">编译器会通过扩展方法为实例方法的优先级。</span><span class="sxs-lookup"><span data-stu-id="289c3-110">The compiler gives instance methods preference over extension methods.</span></span> <span data-ttu-id="289c3-111">如果找到了，只需要经过扩大转换就能匹配的过程调用的任何实例方法，将删除所有扩展方法，并且编译器继续仅候选实例方法。</span><span class="sxs-lookup"><span data-stu-id="289c3-111">If any instance method is found that requires only widening conversions to match the procedure call, all extension methods are dropped and the compiler continues with only the instance method candidates.</span></span> <span data-ttu-id="289c3-112">如果未不找到任何此类的实例方法，它将使用实例方法和扩展方法继续。</span><span class="sxs-lookup"><span data-stu-id="289c3-112">If no such instance method is found, it continues with both instance and extension methods.</span></span>  
  
     <span data-ttu-id="289c3-113">在此步骤中，它消除了调用参数的数据类型无法转换为形参类型中定义的任何重载。</span><span class="sxs-lookup"><span data-stu-id="289c3-113">In this step, it eliminates any overload for which the data types of the calling arguments cannot be converted to the parameter types defined in the overload.</span></span>  
  
4.  <span data-ttu-id="289c3-114">**收缩转换。**</span><span class="sxs-lookup"><span data-stu-id="289c3-114">**Narrowing Conversions.**</span></span> <span data-ttu-id="289c3-115">它会消除需要从调用的参数类型收缩转换为已定义的参数类型的任何重载。</span><span class="sxs-lookup"><span data-stu-id="289c3-115">It eliminates any overload that requires a narrowing conversion from the calling argument types to the defined parameter types.</span></span> <span data-ttu-id="289c3-116">这是 true 还是类型检查开关 ([Option Strict 语句](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) 是`On`或`Off`。</span><span class="sxs-lookup"><span data-stu-id="289c3-116">This is true whether the type checking switch ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) is `On` or `Off`.</span></span>  
  
5.  <span data-ttu-id="289c3-117">**最小扩大。**</span><span class="sxs-lookup"><span data-stu-id="289c3-117">**Least Widening.**</span></span> <span data-ttu-id="289c3-118">编译器会考虑对其余的重载。</span><span class="sxs-lookup"><span data-stu-id="289c3-118">The compiler considers the remaining overloads in pairs.</span></span> <span data-ttu-id="289c3-119">对于每一对，它比较已定义的参数的数据类型。</span><span class="sxs-lookup"><span data-stu-id="289c3-119">For each pair, it compares the data types of the defined parameters.</span></span> <span data-ttu-id="289c3-120">如果中所有的重载之一类型扩大到中其他的相应类型，编译器可以消除后者。</span><span class="sxs-lookup"><span data-stu-id="289c3-120">If the types in one of the overloads all widen to the corresponding types in the other, the compiler eliminates the latter.</span></span> <span data-ttu-id="289c3-121">也就是说，它将保留需要扩大的最少的重载。</span><span class="sxs-lookup"><span data-stu-id="289c3-121">That is, it retains the overload that requires the least amount of widening.</span></span>  
  
6.  <span data-ttu-id="289c3-122">**单个候选项。**</span><span class="sxs-lookup"><span data-stu-id="289c3-122">**Single Candidate.**</span></span> <span data-ttu-id="289c3-123">它将继续考虑重载直到只有一个成对重载仍将保留，并可消除对该重载的调用。</span><span class="sxs-lookup"><span data-stu-id="289c3-123">It continues considering overloads in pairs until only one overload remains, and it resolves the call to that overload.</span></span> <span data-ttu-id="289c3-124">如果编译器不能减少为单个候选的重载，它会生成错误。</span><span class="sxs-lookup"><span data-stu-id="289c3-124">If the compiler cannot reduce the overloads to a single candidate, it generates an error.</span></span>  
  
 <span data-ttu-id="289c3-125">下图显示可确定哪一组要调用的重载版本的过程。</span><span class="sxs-lookup"><span data-stu-id="289c3-125">The following illustration shows the process that determines which of a set of overloaded versions to call.</span></span>  
  
 <span data-ttu-id="289c3-126">![重载解析过程的数据流关系图](./media/overloadres.gif "OverloadRes")</span><span class="sxs-lookup"><span data-stu-id="289c3-126">![Flow diagram of overload resolution process](./media/overloadres.gif "OverloadRes")</span></span>  
<span data-ttu-id="289c3-127">在重载版本中</span><span class="sxs-lookup"><span data-stu-id="289c3-127">Resolving among overloaded versions</span></span>  
  
 <span data-ttu-id="289c3-128">下面的示例阐释了此重载决策过程。</span><span class="sxs-lookup"><span data-stu-id="289c3-128">The following example illustrates this overload resolution process.</span></span>  
  
 <span data-ttu-id="289c3-129">[!code-vb[VbVbcnProcedures #&62;](./codesnippet/VisualBasic/overload-resolution_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="289c3-129">[!code-vb[VbVbcnProcedures#62](./codesnippet/VisualBasic/overload-resolution_1.vb)]</span></span>  
  
 <span data-ttu-id="289c3-130">[!code-vb[VbVbcnProcedures #&63;](./codesnippet/VisualBasic/overload-resolution_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="289c3-130">[!code-vb[VbVbcnProcedures#63](./codesnippet/VisualBasic/overload-resolution_2.vb)]</span></span>  
  
 <span data-ttu-id="289c3-131">在第一个调用中，编译器消除第一个重载，因为第一个参数的类型 (`Short`) 缩小到相应的参数的类型 (`Byte`)。</span><span class="sxs-lookup"><span data-stu-id="289c3-131">In the first call, the compiler eliminates the first overload because the type of the first argument (`Short`) narrows to the type of the corresponding parameter (`Byte`).</span></span> <span data-ttu-id="289c3-132">它然后能消除第三个重载，因为每个参数类型中的第二个重载 (`Short`和`Single`) 加宽到第三个重载中的相应类型 (`Integer`和`Single`)。</span><span class="sxs-lookup"><span data-stu-id="289c3-132">It then eliminates the third overload because each argument type in the second overload (`Short` and `Single`) widens to the corresponding type in the third overload (`Integer` and `Single`).</span></span> <span data-ttu-id="289c3-133">第二个重载需要扩大量较少，因此编译器将用它的调用。</span><span class="sxs-lookup"><span data-stu-id="289c3-133">The second overload requires less widening, so the compiler uses it for the call.</span></span>  
  
 <span data-ttu-id="289c3-134">在第二个调用中，编译器不能消除任何根据收缩重载。</span><span class="sxs-lookup"><span data-stu-id="289c3-134">In the second call, the compiler cannot eliminate any of the overloads on the basis of narrowing.</span></span> <span data-ttu-id="289c3-135">因为它可以调用带参数类型的最少扩大的第二个重载，它会出于同样的原因如下所示的第一个调用，消除第三个重载。</span><span class="sxs-lookup"><span data-stu-id="289c3-135">It eliminates the third overload for the same reason as in the first call, because it can call the second overload with less widening of the argument types.</span></span> <span data-ttu-id="289c3-136">但是，编译器无法解析的第一个和第二个重载之间。</span><span class="sxs-lookup"><span data-stu-id="289c3-136">However, the compiler cannot resolve between the first and second overloads.</span></span> <span data-ttu-id="289c3-137">每个已扩大为中其他的相应类型的一种已定义的参数类型 (`Byte`到`Short`，但`Single`到`Double`)。</span><span class="sxs-lookup"><span data-stu-id="289c3-137">Each has one defined parameter type that widens to the corresponding type in the other (`Byte` to `Short`, but `Single` to `Double`).</span></span> <span data-ttu-id="289c3-138">因此，编译器会生成重载解析错误。</span><span class="sxs-lookup"><span data-stu-id="289c3-138">The compiler therefore generates an overload resolution error.</span></span>  
  
## <a name="overloaded-optional-and-paramarray-arguments"></a><span data-ttu-id="289c3-139">重载可选和 ParamArray 参数</span><span class="sxs-lookup"><span data-stu-id="289c3-139">Overloaded Optional and ParamArray Arguments</span></span>  
 <span data-ttu-id="289c3-140">如果某个过程的两个重载具有相同的签名只是声明的最后一个参数[可选](../../../../visual-basic/language-reference/modifiers/optional.md)合一和[ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)中另一个，则编译器将解析对该过程的调用，如下所示︰</span><span class="sxs-lookup"><span data-stu-id="289c3-140">If two overloads of a procedure have identical signatures except that the last parameter is declared [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) in one and [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) in the other, the compiler resolves a call to that procedure as follows:</span></span>  
  
|<span data-ttu-id="289c3-141">如果该调用提供的最后一个参数为</span><span class="sxs-lookup"><span data-stu-id="289c3-141">If the call supplies the last argument as</span></span>|<span data-ttu-id="289c3-142">编译器会将解析到声明作为最后一个参数的重载的调用</span><span class="sxs-lookup"><span data-stu-id="289c3-142">The compiler resolves the call to the overload declaring the last argument as</span></span>|  
|---|---|  
|<span data-ttu-id="289c3-143">没有值 （省略该参数）</span><span class="sxs-lookup"><span data-stu-id="289c3-143">No value (argument omitted)</span></span>|`Optional`|  
|<span data-ttu-id="289c3-144">单个值</span><span class="sxs-lookup"><span data-stu-id="289c3-144">A single value</span></span>|`Optional`|  
|<span data-ttu-id="289c3-145">以逗号分隔的列表中的两个或多个值</span><span class="sxs-lookup"><span data-stu-id="289c3-145">Two or more values in a comma-separated list</span></span>|`ParamArray`|  
|<span data-ttu-id="289c3-146">（包括一个空数组） 任何长度的数组</span><span class="sxs-lookup"><span data-stu-id="289c3-146">An array of any length (including an empty array)</span></span>|`ParamArray`|  
  
## <a name="see-also"></a><span data-ttu-id="289c3-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="289c3-147">See Also</span></span>  
 <span data-ttu-id="289c3-148">[可选参数](./optional-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="289c3-148">[Optional Parameters](./optional-parameters.md) </span></span>  
<span data-ttu-id="289c3-149"> [参数数组](./parameter-arrays.md) </span><span class="sxs-lookup"><span data-stu-id="289c3-149"> [Parameter Arrays](./parameter-arrays.md) </span></span>  
<span data-ttu-id="289c3-150"> [过程重载](./procedure-overloading.md) </span><span class="sxs-lookup"><span data-stu-id="289c3-150"> [Procedure Overloading](./procedure-overloading.md) </span></span>  
<span data-ttu-id="289c3-151"> [故障排除过程](./troubleshooting-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="289c3-151"> [Troubleshooting Procedures](./troubleshooting-procedures.md) </span></span>  
<span data-ttu-id="289c3-152"> [如何︰ 定义一个过程的多个版本](./how-to-define-multiple-versions-of-a-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="289c3-152"> [How to: Define Multiple Versions of a Procedure](./how-to-define-multiple-versions-of-a-procedure.md) </span></span>  
<span data-ttu-id="289c3-153"> [如何︰ 调用重载的过程](./how-to-call-an-overloaded-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="289c3-153"> [How to: Call an Overloaded Procedure](./how-to-call-an-overloaded-procedure.md) </span></span>  
<span data-ttu-id="289c3-154"> [如何︰ 重载带有可选参数的过程](./how-to-overload-a-procedure-that-takes-optional-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="289c3-154"> [How to: Overload a Procedure that Takes Optional Parameters](./how-to-overload-a-procedure-that-takes-optional-parameters.md) </span></span>  
<span data-ttu-id="289c3-155"> [如何︰ 重载参数数量不确定的过程](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="289c3-155"> [How to: Overload a Procedure that Takes an Indefinite Number of Parameters](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md) </span></span>  
<span data-ttu-id="289c3-156"> [重载过程注意事项](./considerations-in-overloading-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="289c3-156"> [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md) </span></span>  
<span data-ttu-id="289c3-157"> [重载](../../../../visual-basic/language-reference/modifiers/overloads.md) </span><span class="sxs-lookup"><span data-stu-id="289c3-157"> [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) </span></span>  
<span data-ttu-id="289c3-158"> [扩展方法](./extension-methods.md)</span><span class="sxs-lookup"><span data-stu-id="289c3-158"> [Extension Methods](./extension-methods.md)</span></span>
