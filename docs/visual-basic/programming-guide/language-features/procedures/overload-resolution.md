---
title: 重载决策
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- overload resolution
- procedures [Visual Basic], overloading
- procedures [Visual Basic], calling
- procedure overloading [Visual Basic], overload resolution
- signatures [Visual Basic], procedure
- overloads [Visual Basic], resolution
ms.assetid: 766115d1-4352-45fb-859f-6063e0de0ec0
ms.openlocfilehash: 0e69136b1e3015055cad9852bf04151f57558b88
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352650"
---
# <a name="overload-resolution-visual-basic"></a><span data-ttu-id="981c2-102">重载决策 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="981c2-102">Overload Resolution (Visual Basic)</span></span>
<span data-ttu-id="981c2-103">当 Visual Basic 编译器遇到多个重载版本中定义的过程时，编译器必须确定要调用的重载。</span><span class="sxs-lookup"><span data-stu-id="981c2-103">When the Visual Basic compiler encounters a call to a procedure that is defined in several overloaded versions, the compiler must decide which of the overloads to call.</span></span> <span data-ttu-id="981c2-104">它通过执行以下步骤来执行此操作：</span><span class="sxs-lookup"><span data-stu-id="981c2-104">It does this by performing the following steps:</span></span>  
  
1. <span data-ttu-id="981c2-105">**辅助功能。**</span><span class="sxs-lookup"><span data-stu-id="981c2-105">**Accessibility.**</span></span> <span data-ttu-id="981c2-106">它消除了具有访问级别的任何重载，使调用代码无法调用它。</span><span class="sxs-lookup"><span data-stu-id="981c2-106">It eliminates any overload with an access level that prevents the calling code from calling it.</span></span>  
  
2. <span data-ttu-id="981c2-107">**参数的数目。**</span><span class="sxs-lookup"><span data-stu-id="981c2-107">**Number of Parameters.**</span></span> <span data-ttu-id="981c2-108">它消除了任何定义与调用中提供的参数数量不同的参数的重载。</span><span class="sxs-lookup"><span data-stu-id="981c2-108">It eliminates any overload that defines a different number of parameters than are supplied in the call.</span></span>  
  
3. <span data-ttu-id="981c2-109">**参数数据类型。**</span><span class="sxs-lookup"><span data-stu-id="981c2-109">**Parameter Data Types.**</span></span> <span data-ttu-id="981c2-110">编译器使实例方法优先于扩展方法。</span><span class="sxs-lookup"><span data-stu-id="981c2-110">The compiler gives instance methods preference over extension methods.</span></span> <span data-ttu-id="981c2-111">如果找到了只需要扩大转换才能匹配过程调用的任何实例方法，则将删除所有扩展方法，并且编译器仅以实例方法候选继续。</span><span class="sxs-lookup"><span data-stu-id="981c2-111">If any instance method is found that requires only widening conversions to match the procedure call, all extension methods are dropped and the compiler continues with only the instance method candidates.</span></span> <span data-ttu-id="981c2-112">如果未找到此类实例方法，则它将继续执行实例和扩展方法。</span><span class="sxs-lookup"><span data-stu-id="981c2-112">If no such instance method is found, it continues with both instance and extension methods.</span></span>  
  
     <span data-ttu-id="981c2-113">在此步骤中，它将消除调用参数的数据类型无法转换为重载中定义的参数类型的任何重载。</span><span class="sxs-lookup"><span data-stu-id="981c2-113">In this step, it eliminates any overload for which the data types of the calling arguments cannot be converted to the parameter types defined in the overload.</span></span>  
  
4. <span data-ttu-id="981c2-114">**收缩转换。**</span><span class="sxs-lookup"><span data-stu-id="981c2-114">**Narrowing Conversions.**</span></span> <span data-ttu-id="981c2-115">它消除了任何需要从调用参数类型到已定义参数类型的收缩转换的重载。</span><span class="sxs-lookup"><span data-stu-id="981c2-115">It eliminates any overload that requires a narrowing conversion from the calling argument types to the defined parameter types.</span></span> <span data-ttu-id="981c2-116">无论类型检查开关（[Option Strict 语句](../../../../visual-basic/language-reference/statements/option-strict-statement.md)） `On` 还是 `Off`，都是如此。</span><span class="sxs-lookup"><span data-stu-id="981c2-116">This is true whether the type checking switch ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) is `On` or `Off`.</span></span>  
  
5. <span data-ttu-id="981c2-117">**最小扩大。**</span><span class="sxs-lookup"><span data-stu-id="981c2-117">**Least Widening.**</span></span> <span data-ttu-id="981c2-118">编译器将其余重载视为成对。</span><span class="sxs-lookup"><span data-stu-id="981c2-118">The compiler considers the remaining overloads in pairs.</span></span> <span data-ttu-id="981c2-119">对于每个对，它将比较已定义参数的数据类型。</span><span class="sxs-lookup"><span data-stu-id="981c2-119">For each pair, it compares the data types of the defined parameters.</span></span> <span data-ttu-id="981c2-120">如果其中一个重载中的类型扩大到另一个重载中的相应类型，则编译器将消除后者。</span><span class="sxs-lookup"><span data-stu-id="981c2-120">If the types in one of the overloads all widen to the corresponding types in the other, the compiler eliminates the latter.</span></span> <span data-ttu-id="981c2-121">也就是说，它会保留要求最小扩大量的重载。</span><span class="sxs-lookup"><span data-stu-id="981c2-121">That is, it retains the overload that requires the least amount of widening.</span></span>  
  
6. <span data-ttu-id="981c2-122">**单个候选项。**</span><span class="sxs-lookup"><span data-stu-id="981c2-122">**Single Candidate.**</span></span> <span data-ttu-id="981c2-123">它继续考虑成对重载，直到只保留一个重载，并解析对该重载的调用。</span><span class="sxs-lookup"><span data-stu-id="981c2-123">It continues considering overloads in pairs until only one overload remains, and it resolves the call to that overload.</span></span> <span data-ttu-id="981c2-124">如果编译器无法将重载减少到单个候选项，则会生成错误。</span><span class="sxs-lookup"><span data-stu-id="981c2-124">If the compiler cannot reduce the overloads to a single candidate, it generates an error.</span></span>  
  
 <span data-ttu-id="981c2-125">下图显示了确定要调用的一组重载版本的过程。</span><span class="sxs-lookup"><span data-stu-id="981c2-125">The following illustration shows the process that determines which of a set of overloaded versions to call.</span></span>  
  
 <span data-ttu-id="981c2-126">![重载解析过程的流程图](./media/overload-resolution/determine-overloaded-version.gif "在重载版本之间进行解析")</span><span class="sxs-lookup"><span data-stu-id="981c2-126">![Flow diagram of overload resolution process](./media/overload-resolution/determine-overloaded-version.gif "Resolving among overloaded versions")</span></span>    
  
 <span data-ttu-id="981c2-127">下面的示例演示了此重载决策过程。</span><span class="sxs-lookup"><span data-stu-id="981c2-127">The following example illustrates this overload resolution process.</span></span>  
  
 [!code-vb[VbVbcnProcedures#62](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#62)]  
  
 [!code-vb[VbVbcnProcedures#63](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#63)]  
  
 <span data-ttu-id="981c2-128">在第一次调用中，编译器将消除第一个重载，因为第一个参数的类型（`Short`）会缩小到相应参数的类型（`Byte`）。</span><span class="sxs-lookup"><span data-stu-id="981c2-128">In the first call, the compiler eliminates the first overload because the type of the first argument (`Short`) narrows to the type of the corresponding parameter (`Byte`).</span></span> <span data-ttu-id="981c2-129">然后，它将消除第三个重载，因为第二个重载（`Short` 和 `Single`）中的每个参数类型扩大为第三个重载（`Integer` 和 `Single`）中的相应类型。</span><span class="sxs-lookup"><span data-stu-id="981c2-129">It then eliminates the third overload because each argument type in the second overload (`Short` and `Single`) widens to the corresponding type in the third overload (`Integer` and `Single`).</span></span> <span data-ttu-id="981c2-130">第二个重载需要更少的扩展，因此编译器将其用于调用。</span><span class="sxs-lookup"><span data-stu-id="981c2-130">The second overload requires less widening, so the compiler uses it for the call.</span></span>  
  
 <span data-ttu-id="981c2-131">在第二次调用中，编译器无法根据收缩消除任何重载。</span><span class="sxs-lookup"><span data-stu-id="981c2-131">In the second call, the compiler cannot eliminate any of the overloads on the basis of narrowing.</span></span> <span data-ttu-id="981c2-132">它消除第三个重载的原因与第一次调用中的相同原因，因为它可以通过更少的参数类型来调用第二个重载。</span><span class="sxs-lookup"><span data-stu-id="981c2-132">It eliminates the third overload for the same reason as in the first call, because it can call the second overload with less widening of the argument types.</span></span> <span data-ttu-id="981c2-133">但编译器无法在第一个和第二个重载之间解析。</span><span class="sxs-lookup"><span data-stu-id="981c2-133">However, the compiler cannot resolve between the first and second overloads.</span></span> <span data-ttu-id="981c2-134">每个都有一个已定义的参数类型，该类型扩大到另一个中的相应类型（`Byte` 到 `Short`，但 `Single` `Double`）。</span><span class="sxs-lookup"><span data-stu-id="981c2-134">Each has one defined parameter type that widens to the corresponding type in the other (`Byte` to `Short`, but `Single` to `Double`).</span></span> <span data-ttu-id="981c2-135">因此，编译器将生成重载决策错误。</span><span class="sxs-lookup"><span data-stu-id="981c2-135">The compiler therefore generates an overload resolution error.</span></span>  
  
## <a name="overloaded-optional-and-paramarray-arguments"></a><span data-ttu-id="981c2-136">重载的可选参数和 ParamArray 参数</span><span class="sxs-lookup"><span data-stu-id="981c2-136">Overloaded Optional and ParamArray Arguments</span></span>  
 <span data-ttu-id="981c2-137">如果过程的两个重载具有相同的签名，则除了最后一个参数在另[一个中声明](../../../../visual-basic/language-reference/modifiers/paramarray.md)为[可选](../../../../visual-basic/language-reference/modifiers/optional.md)外，编译器将解析对该过程的调用，如下所示：</span><span class="sxs-lookup"><span data-stu-id="981c2-137">If two overloads of a procedure have identical signatures except that the last parameter is declared [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) in one and [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) in the other, the compiler resolves a call to that procedure as follows:</span></span>  
  
|<span data-ttu-id="981c2-138">如果调用提供了最后一个参数</span><span class="sxs-lookup"><span data-stu-id="981c2-138">If the call supplies the last argument as</span></span>|<span data-ttu-id="981c2-139">编译器解析对声明最后一个参数的重载的调用</span><span class="sxs-lookup"><span data-stu-id="981c2-139">The compiler resolves the call to the overload declaring the last argument as</span></span>|  
|---|---|  
|<span data-ttu-id="981c2-140">无值（忽略参数）</span><span class="sxs-lookup"><span data-stu-id="981c2-140">No value (argument omitted)</span></span>|`Optional`|  
|<span data-ttu-id="981c2-141">单个值</span><span class="sxs-lookup"><span data-stu-id="981c2-141">A single value</span></span>|`Optional`|  
|<span data-ttu-id="981c2-142">以逗号分隔的列表中的两个或多个值</span><span class="sxs-lookup"><span data-stu-id="981c2-142">Two or more values in a comma-separated list</span></span>|`ParamArray`|  
|<span data-ttu-id="981c2-143">任意长度的数组（包括空数组）</span><span class="sxs-lookup"><span data-stu-id="981c2-143">An array of any length (including an empty array)</span></span>|`ParamArray`|  
  
## <a name="see-also"></a><span data-ttu-id="981c2-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="981c2-144">See also</span></span>

- [<span data-ttu-id="981c2-145">可选参数</span><span class="sxs-lookup"><span data-stu-id="981c2-145">Optional Parameters</span></span>](./optional-parameters.md)
- [<span data-ttu-id="981c2-146">参数数组</span><span class="sxs-lookup"><span data-stu-id="981c2-146">Parameter Arrays</span></span>](./parameter-arrays.md)
- [<span data-ttu-id="981c2-147">过程重载</span><span class="sxs-lookup"><span data-stu-id="981c2-147">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="981c2-148">过程疑难解答</span><span class="sxs-lookup"><span data-stu-id="981c2-148">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)
- [<span data-ttu-id="981c2-149">如何：定义一个过程的多个版本</span><span class="sxs-lookup"><span data-stu-id="981c2-149">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)
- [<span data-ttu-id="981c2-150">如何：调用重载过程</span><span class="sxs-lookup"><span data-stu-id="981c2-150">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)
- [<span data-ttu-id="981c2-151">如何：重载带有可选参数的过程</span><span class="sxs-lookup"><span data-stu-id="981c2-151">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [<span data-ttu-id="981c2-152">如何：重载参数数量不确定的过程</span><span class="sxs-lookup"><span data-stu-id="981c2-152">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [<span data-ttu-id="981c2-153">重载过程注意事项</span><span class="sxs-lookup"><span data-stu-id="981c2-153">Considerations in Overloading Procedures</span></span>](./considerations-in-overloading-procedures.md)
- [<span data-ttu-id="981c2-154">Overloads</span><span class="sxs-lookup"><span data-stu-id="981c2-154">Overloads</span></span>](../../../../visual-basic/language-reference/modifiers/overloads.md)
- [<span data-ttu-id="981c2-155">扩展方法</span><span class="sxs-lookup"><span data-stu-id="981c2-155">Extension Methods</span></span>](./extension-methods.md)
