---
title: 重载决策 (Visual Basic)
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
ms.openlocfilehash: 4f81c7377423899c142c4270f325bbd7ed20b877
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61792012"
---
# <a name="overload-resolution-visual-basic"></a><span data-ttu-id="f057e-102">重载决策 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f057e-102">Overload Resolution (Visual Basic)</span></span>
<span data-ttu-id="f057e-103">当 Visual Basic 编译器遇到多个重载版本中定义的过程调用时，编译器必须确定哪个重载来调用。</span><span class="sxs-lookup"><span data-stu-id="f057e-103">When the Visual Basic compiler encounters a call to a procedure that is defined in several overloaded versions, the compiler must decide which of the overloads to call.</span></span> <span data-ttu-id="f057e-104">做到这一点，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="f057e-104">It does this by performing the following steps:</span></span>  
  
1. <span data-ttu-id="f057e-105">**辅助功能。**</span><span class="sxs-lookup"><span data-stu-id="f057e-105">**Accessibility.**</span></span> <span data-ttu-id="f057e-106">它消除了一种访问级别，以防止调用代码中调用它的任何重载。</span><span class="sxs-lookup"><span data-stu-id="f057e-106">It eliminates any overload with an access level that prevents the calling code from calling it.</span></span>  
  
2. <span data-ttu-id="f057e-107">**参数数目。**</span><span class="sxs-lookup"><span data-stu-id="f057e-107">**Number of Parameters.**</span></span> <span data-ttu-id="f057e-108">它消除了定义不同数量的参数提供的调用中的任何重载。</span><span class="sxs-lookup"><span data-stu-id="f057e-108">It eliminates any overload that defines a different number of parameters than are supplied in the call.</span></span>  
  
3. <span data-ttu-id="f057e-109">**参数数据类型。**</span><span class="sxs-lookup"><span data-stu-id="f057e-109">**Parameter Data Types.**</span></span> <span data-ttu-id="f057e-110">编译器则报告实例方法优先于扩展方法。</span><span class="sxs-lookup"><span data-stu-id="f057e-110">The compiler gives instance methods preference over extension methods.</span></span> <span data-ttu-id="f057e-111">如果需要仅进行扩大转换来匹配的过程调用找到的任何实例方法，则所有扩展方法将被都删除，并且编译器将通过仅候选实例方法继续。</span><span class="sxs-lookup"><span data-stu-id="f057e-111">If any instance method is found that requires only widening conversions to match the procedure call, all extension methods are dropped and the compiler continues with only the instance method candidates.</span></span> <span data-ttu-id="f057e-112">如果找到此类的实例方法，则将继续使用实例和扩展方法。</span><span class="sxs-lookup"><span data-stu-id="f057e-112">If no such instance method is found, it continues with both instance and extension methods.</span></span>  
  
     <span data-ttu-id="f057e-113">在此步骤中，它消除了所有重载的调用参数的数据类型无法转换的重载中定义的参数类型。</span><span class="sxs-lookup"><span data-stu-id="f057e-113">In this step, it eliminates any overload for which the data types of the calling arguments cannot be converted to the parameter types defined in the overload.</span></span>  
  
4. <span data-ttu-id="f057e-114">**收缩转换。**</span><span class="sxs-lookup"><span data-stu-id="f057e-114">**Narrowing Conversions.**</span></span> <span data-ttu-id="f057e-115">它消除了所有需要收缩转换从调用的参数类型为定义的参数类型的重载。</span><span class="sxs-lookup"><span data-stu-id="f057e-115">It eliminates any overload that requires a narrowing conversion from the calling argument types to the defined parameter types.</span></span> <span data-ttu-id="f057e-116">这是 true 还是类型检查开关 ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) 是`On`或`Off`。</span><span class="sxs-lookup"><span data-stu-id="f057e-116">This is true whether the type checking switch ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) is `On` or `Off`.</span></span>  
  
5. <span data-ttu-id="f057e-117">**最小扩大。**</span><span class="sxs-lookup"><span data-stu-id="f057e-117">**Least Widening.**</span></span> <span data-ttu-id="f057e-118">编译器会考虑对其余的重载。</span><span class="sxs-lookup"><span data-stu-id="f057e-118">The compiler considers the remaining overloads in pairs.</span></span> <span data-ttu-id="f057e-119">对于每个对，它将进行比较已定义的参数的数据的类型。</span><span class="sxs-lookup"><span data-stu-id="f057e-119">For each pair, it compares the data types of the defined parameters.</span></span> <span data-ttu-id="f057e-120">如果所有的重载之一中的类型扩大到中的其他的相应类型，编译器消除了后者。</span><span class="sxs-lookup"><span data-stu-id="f057e-120">If the types in one of the overloads all widen to the corresponding types in the other, the compiler eliminates the latter.</span></span> <span data-ttu-id="f057e-121">也就是说，它将保留要求最少量的扩大转换的重载。</span><span class="sxs-lookup"><span data-stu-id="f057e-121">That is, it retains the overload that requires the least amount of widening.</span></span>  
  
6. <span data-ttu-id="f057e-122">**单个候选项。**</span><span class="sxs-lookup"><span data-stu-id="f057e-122">**Single Candidate.**</span></span> <span data-ttu-id="f057e-123">它会持续假设重载直到只有一个成对重载会保留，并解析对重载的调用。</span><span class="sxs-lookup"><span data-stu-id="f057e-123">It continues considering overloads in pairs until only one overload remains, and it resolves the call to that overload.</span></span> <span data-ttu-id="f057e-124">如果编译器不能减少到单个的候选版本的重载，则将生成错误。</span><span class="sxs-lookup"><span data-stu-id="f057e-124">If the compiler cannot reduce the overloads to a single candidate, it generates an error.</span></span>  
  
 <span data-ttu-id="f057e-125">下图显示了确定哪一组重载版本来调用的进程。</span><span class="sxs-lookup"><span data-stu-id="f057e-125">The following illustration shows the process that determines which of a set of overloaded versions to call.</span></span>  
  
 <span data-ttu-id="f057e-126">![重载解析过程的流程图](./media/overload-resolution/determine-overloaded-version.gif "在重载版本中")</span><span class="sxs-lookup"><span data-stu-id="f057e-126">![Flow diagram of overload resolution process](./media/overload-resolution/determine-overloaded-version.gif "Resolving among overloaded versions")</span></span>    
  
 <span data-ttu-id="f057e-127">下面的示例阐释了此重载决策过程。</span><span class="sxs-lookup"><span data-stu-id="f057e-127">The following example illustrates this overload resolution process.</span></span>  
  
 [!code-vb[VbVbcnProcedures#62](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#62)]  
  
 [!code-vb[VbVbcnProcedures#63](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#63)]  
  
 <span data-ttu-id="f057e-128">在第一次调用，编译器无第一个重载，因为第一个参数的类型 (`Short`) 收缩到的相应参数的类型 (`Byte`)。</span><span class="sxs-lookup"><span data-stu-id="f057e-128">In the first call, the compiler eliminates the first overload because the type of the first argument (`Short`) narrows to the type of the corresponding parameter (`Byte`).</span></span> <span data-ttu-id="f057e-129">它然后能消除第三个重载，因为每个自变量类型中的第二个重载 (`Short`并`Single`) 将扩展到第三个重载中的相应类型 (`Integer`和`Single`)。</span><span class="sxs-lookup"><span data-stu-id="f057e-129">It then eliminates the third overload because each argument type in the second overload (`Short` and `Single`) widens to the corresponding type in the third overload (`Integer` and `Single`).</span></span> <span data-ttu-id="f057e-130">第二个重载需要较少扩大转换，因此编译器将其用于调用。</span><span class="sxs-lookup"><span data-stu-id="f057e-130">The second overload requires less widening, so the compiler uses it for the call.</span></span>  
  
 <span data-ttu-id="f057e-131">在第二个调用中，编译器不能消除任何根据收缩的重载。</span><span class="sxs-lookup"><span data-stu-id="f057e-131">In the second call, the compiler cannot eliminate any of the overloads on the basis of narrowing.</span></span> <span data-ttu-id="f057e-132">因为它可以调用与自变量类型的最少扩大的第二个重载，它可以消除第三个重载了如下所示的第一个调用中，由于同一原因。</span><span class="sxs-lookup"><span data-stu-id="f057e-132">It eliminates the third overload for the same reason as in the first call, because it can call the second overload with less widening of the argument types.</span></span> <span data-ttu-id="f057e-133">但是，编译器无法解析的第一个和第二个重载之间。</span><span class="sxs-lookup"><span data-stu-id="f057e-133">However, the compiler cannot resolve between the first and second overloads.</span></span> <span data-ttu-id="f057e-134">每个都有一个定义的参数类型扩展到其他相应的类型 (`Byte`到`Short`，但`Single`到`Double`)。</span><span class="sxs-lookup"><span data-stu-id="f057e-134">Each has one defined parameter type that widens to the corresponding type in the other (`Byte` to `Short`, but `Single` to `Double`).</span></span> <span data-ttu-id="f057e-135">因此，编译器将生成重载解析错误。</span><span class="sxs-lookup"><span data-stu-id="f057e-135">The compiler therefore generates an overload resolution error.</span></span>  
  
## <a name="overloaded-optional-and-paramarray-arguments"></a><span data-ttu-id="f057e-136">重载可选和 ParamArray 参数</span><span class="sxs-lookup"><span data-stu-id="f057e-136">Overloaded Optional and ParamArray Arguments</span></span>  
 <span data-ttu-id="f057e-137">如果过程的两个重载具有相同的签名，只不过声明的最后一个参数[可选](../../../../visual-basic/language-reference/modifiers/optional.md)合一和[ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)中另一个，则编译器将解析对作为该过程的调用如下所示：</span><span class="sxs-lookup"><span data-stu-id="f057e-137">If two overloads of a procedure have identical signatures except that the last parameter is declared [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) in one and [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) in the other, the compiler resolves a call to that procedure as follows:</span></span>  
  
|<span data-ttu-id="f057e-138">如果调用提供了最后一个参数为</span><span class="sxs-lookup"><span data-stu-id="f057e-138">If the call supplies the last argument as</span></span>|<span data-ttu-id="f057e-139">编译器解析对声明为的最后一个参数的重载的调用</span><span class="sxs-lookup"><span data-stu-id="f057e-139">The compiler resolves the call to the overload declaring the last argument as</span></span>|  
|---|---|  
|<span data-ttu-id="f057e-140">没有值 （省略该参数）</span><span class="sxs-lookup"><span data-stu-id="f057e-140">No value (argument omitted)</span></span>|`Optional`|  
|<span data-ttu-id="f057e-141">单个值</span><span class="sxs-lookup"><span data-stu-id="f057e-141">A single value</span></span>|`Optional`|  
|<span data-ttu-id="f057e-142">以逗号分隔的列表中的两个或多个值</span><span class="sxs-lookup"><span data-stu-id="f057e-142">Two or more values in a comma-separated list</span></span>|`ParamArray`|  
|<span data-ttu-id="f057e-143">（包括一个空数组） 任何长度的数组</span><span class="sxs-lookup"><span data-stu-id="f057e-143">An array of any length (including an empty array)</span></span>|`ParamArray`|  
  
## <a name="see-also"></a><span data-ttu-id="f057e-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="f057e-144">See also</span></span>

- [<span data-ttu-id="f057e-145">可选参数</span><span class="sxs-lookup"><span data-stu-id="f057e-145">Optional Parameters</span></span>](./optional-parameters.md)
- [<span data-ttu-id="f057e-146">参数数组</span><span class="sxs-lookup"><span data-stu-id="f057e-146">Parameter Arrays</span></span>](./parameter-arrays.md)
- [<span data-ttu-id="f057e-147">过程重载</span><span class="sxs-lookup"><span data-stu-id="f057e-147">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="f057e-148">过程疑难解答</span><span class="sxs-lookup"><span data-stu-id="f057e-148">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)
- [<span data-ttu-id="f057e-149">如何：定义一个过程的多个版本</span><span class="sxs-lookup"><span data-stu-id="f057e-149">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)
- [<span data-ttu-id="f057e-150">如何：调用重载的过程</span><span class="sxs-lookup"><span data-stu-id="f057e-150">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)
- [<span data-ttu-id="f057e-151">如何：重载带有可选参数的过程</span><span class="sxs-lookup"><span data-stu-id="f057e-151">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [<span data-ttu-id="f057e-152">如何：重载的参数数量不确定的过程</span><span class="sxs-lookup"><span data-stu-id="f057e-152">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [<span data-ttu-id="f057e-153">重载过程注意事项</span><span class="sxs-lookup"><span data-stu-id="f057e-153">Considerations in Overloading Procedures</span></span>](./considerations-in-overloading-procedures.md)
- [<span data-ttu-id="f057e-154">重载</span><span class="sxs-lookup"><span data-stu-id="f057e-154">Overloads</span></span>](../../../../visual-basic/language-reference/modifiers/overloads.md)
- [<span data-ttu-id="f057e-155">扩展方法</span><span class="sxs-lookup"><span data-stu-id="f057e-155">Extension Methods</span></span>](./extension-methods.md)
