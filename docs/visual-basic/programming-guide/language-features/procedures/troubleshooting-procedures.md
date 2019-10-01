---
title: 过程疑难解答 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting Visual Basic, procedures
- procedures [Visual Basic], troubleshooting
- Visual Basic code, procedures
- troubleshooting procedures
- procedures [Visual Basic], about procedures
ms.assetid: 525721e8-2e02-4f75-b5d8-6b893462cf2b
ms.openlocfilehash: d8309b9bd63a2a3d1b0b56f97be121a06b78d6b6
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700135"
---
# <a name="troubleshooting-procedures-visual-basic"></a><span data-ttu-id="7925d-102">过程疑难解答 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7925d-102">Troubleshooting Procedures (Visual Basic)</span></span>

<span data-ttu-id="7925d-103">此页列出了在使用过程时可能出现的一些常见问题。</span><span class="sxs-lookup"><span data-stu-id="7925d-103">This page lists some common problems that can occur when working with procedures.</span></span>

## <a name="returning-an-array-type-from-a-function-procedure"></a><span data-ttu-id="7925d-104">从函数过程返回数组类型</span><span class="sxs-lookup"><span data-stu-id="7925d-104">Returning an Array Type from a Function Procedure</span></span>

 <span data-ttu-id="7925d-105">如果 @no__t 0 过程返回数组数据类型，则不能使用 @no__t 的名称将值存储在数组的元素中。</span><span class="sxs-lookup"><span data-stu-id="7925d-105">If a `Function` procedure returns an array data type, you cannot use the `Function` name to store values in the elements of the array.</span></span> <span data-ttu-id="7925d-106">如果尝试执行此操作，编译器会将其解释为对 @no__t 的调用。</span><span class="sxs-lookup"><span data-stu-id="7925d-106">If you attempt to do this, the compiler interprets it as a call to the `Function`.</span></span> <span data-ttu-id="7925d-107">下面的示例生成编译器错误。</span><span class="sxs-lookup"><span data-stu-id="7925d-107">The following example generates compiler errors.</span></span>

 ```vb
 Function AllOnes(n As Integer) As Integer()
     For i = 1 To n - 1
         ' The following statement generates a COMPILER ERROR.
         AllOnes(i) = 1
     Next
     ' The following statement generates a COMPILER ERROR.
     Return AllOnes()
 End Function
 ```
  
 <span data-ttu-id="7925d-108">语句 @no__t 会生成编译器错误，因为它似乎使用错误数据类型（标量 `Integer` 而不是 @no__t 数组）的参数调用了 `AllOnes`。</span><span class="sxs-lookup"><span data-stu-id="7925d-108">The statement `AllOnes(i) = 1` generates a compiler error because it appears to call `AllOnes` with an argument of the wrong data type (a scalar `Integer` instead of an `Integer` array).</span></span> <span data-ttu-id="7925d-109">语句 `Return AllOnes()` 会生成编译器错误，因为它似乎调用不带参数 `AllOnes`。</span><span class="sxs-lookup"><span data-stu-id="7925d-109">The statement `Return AllOnes()` generates a compiler error because it appears to call `AllOnes` with no argument.</span></span>

 <span data-ttu-id="7925d-110">**正确的方法：** 为了能够修改要返回的数组元素，请将内部数组定义为局部变量。</span><span class="sxs-lookup"><span data-stu-id="7925d-110">**Correct Approach:** To be able to modify the elements of an array that is to be returned, define an internal array as a local variable.</span></span> <span data-ttu-id="7925d-111">下面的示例在编译时不会出错。</span><span class="sxs-lookup"><span data-stu-id="7925d-111">The following example compiles without error.</span></span>

 [!code-vb[VbVbcnProcedures#66](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#66)]

## <a name="argument-not-being-modified-by-procedure-call"></a><span data-ttu-id="7925d-112">过程调用未修改参数</span><span class="sxs-lookup"><span data-stu-id="7925d-112">Argument Not Being Modified by Procedure Call</span></span>

 <span data-ttu-id="7925d-113">如果打算允许过程更改调用代码中的参数基础的编程元素，则必须通过引用传递该元素。</span><span class="sxs-lookup"><span data-stu-id="7925d-113">If you intend to allow a procedure to change a programming element underlying an argument in the calling code, you must pass it by reference.</span></span> <span data-ttu-id="7925d-114">但过程可以访问引用类型参数的元素，即使你按值传递它。</span><span class="sxs-lookup"><span data-stu-id="7925d-114">But a procedure can access the elements of a reference type argument even if you pass it by value.</span></span>

- <span data-ttu-id="7925d-115">**基础变量**。</span><span class="sxs-lookup"><span data-stu-id="7925d-115">**Underlying Variable**.</span></span> <span data-ttu-id="7925d-116">若要允许该过程替换基础变量元素本身的值，该过程必须声明参数[ByRef](../../../language-reference/modifiers/byref.md)。</span><span class="sxs-lookup"><span data-stu-id="7925d-116">To allow the procedure to replace the value of the underlying variable element itself, the procedure must declare the parameter [ByRef](../../../language-reference/modifiers/byref.md).</span></span> <span data-ttu-id="7925d-117">此外，调用代码不能将参数括在括号中，因为这会重写 `ByRef` 传递机制。</span><span class="sxs-lookup"><span data-stu-id="7925d-117">Also, the calling code must not enclose the argument in parentheses, because that would override the `ByRef` passing mechanism.</span></span>

- <span data-ttu-id="7925d-118">**引用类型元素**。</span><span class="sxs-lookup"><span data-stu-id="7925d-118">**Reference Type Elements**.</span></span> <span data-ttu-id="7925d-119">如果声明参数[ByVal](../../../language-reference/modifiers/byval.md)，则该过程将无法修改基础变量元素本身。</span><span class="sxs-lookup"><span data-stu-id="7925d-119">If you declare a parameter [ByVal](../../../language-reference/modifiers/byval.md), the procedure cannot modify the underlying variable element itself.</span></span> <span data-ttu-id="7925d-120">但是，如果参数是引用类型，则该过程可以修改它所指向的对象的成员，即使它不能替换变量的值。</span><span class="sxs-lookup"><span data-stu-id="7925d-120">However, if the argument is a reference type, the procedure can modify the members of the object to which it points, even though it cannot replace the variable's value.</span></span> <span data-ttu-id="7925d-121">例如，如果参数是一个数组变量，则该过程无法向其分配新数组，但它可以更改其一个或多个元素。</span><span class="sxs-lookup"><span data-stu-id="7925d-121">For example, if the argument is an array variable, the procedure cannot assign a new array to it, but it can change one or more of its elements.</span></span> <span data-ttu-id="7925d-122">更改的元素将反映在调用代码的基础数组变量中。</span><span class="sxs-lookup"><span data-stu-id="7925d-122">The changed elements are reflected in the underlying array variable in the calling code.</span></span>

 <span data-ttu-id="7925d-123">下面的示例定义了两个过程，这些过程按值获取数组变量并对其元素进行操作。</span><span class="sxs-lookup"><span data-stu-id="7925d-123">The following example defines two procedures that take an array variable by value and operate on its elements.</span></span> <span data-ttu-id="7925d-124">过程 `increase` 只是向每个元素添加一个。</span><span class="sxs-lookup"><span data-stu-id="7925d-124">Procedure `increase` simply adds one to each element.</span></span> <span data-ttu-id="7925d-125">过程 `replace` 会将新数组分配给参数 `a()`，然后将其添加到每个元素。</span><span class="sxs-lookup"><span data-stu-id="7925d-125">Procedure `replace` assigns a new array to the parameter `a()` and then adds one to each element.</span></span> <span data-ttu-id="7925d-126">但是，重新分配不会影响调用代码中的基础数组变量，因为 `a()` 声明 @no__t 为-1。</span><span class="sxs-lookup"><span data-stu-id="7925d-126">However, the reassignment does not affect the underlying array variable in the calling code because `a()` is declared `ByVal`.</span></span>

 [!code-vb[VbVbcnProcedures#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#35)]

 [!code-vb[VbVbcnProcedures#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#38)]

 <span data-ttu-id="7925d-127">下面的示例调用 `increase` 并 `replace`。</span><span class="sxs-lookup"><span data-stu-id="7925d-127">The following example makes calls to `increase` and `replace`.</span></span>

 [!code-vb[VbVbcnProcedures#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#37)]

 <span data-ttu-id="7925d-128">第一个 `MsgBox` 调用显示 "增加后（n）：11、21、31、41 "。</span><span class="sxs-lookup"><span data-stu-id="7925d-128">The first `MsgBox` call displays "After increase(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="7925d-129">由于 @no__t 是引用类型，`increase` 可以更改其成员，即使将其传递 `ByVal`。</span><span class="sxs-lookup"><span data-stu-id="7925d-129">Because `n` is a reference type, `increase` can change its members, even though it is passed `ByVal`.</span></span>

 <span data-ttu-id="7925d-130">第二个 `MsgBox` 调用显示 "replace 后（n）：11、21、31、41 "。</span><span class="sxs-lookup"><span data-stu-id="7925d-130">The second `MsgBox` call displays "After replace(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="7925d-131">由于 `n` @no__t 为-1，`replace` 无法通过向其分配新数组来修改变量 `n`。</span><span class="sxs-lookup"><span data-stu-id="7925d-131">Because `n` is passed `ByVal`, `replace` cannot modify the variable `n` by assigning a new array to it.</span></span> <span data-ttu-id="7925d-132">如果 `replace` 会创建新的数组实例，`k`，并将其分配给本地变量 `a`，它将丢失对调用代码传入的 `n` 的引用。</span><span class="sxs-lookup"><span data-stu-id="7925d-132">When `replace` creates the new array instance `k` and assigns it to the local variable `a`, it loses the reference to `n` passed in by the calling code.</span></span> <span data-ttu-id="7925d-133">递增 `a` 的成员时，只会影响本地阵列 `k`。</span><span class="sxs-lookup"><span data-stu-id="7925d-133">When it increments the members of `a`, only the local array `k` is affected.</span></span>

 <span data-ttu-id="7925d-134">**正确的方法：** 若要能够修改基础变量元素本身，请按引用传递它。</span><span class="sxs-lookup"><span data-stu-id="7925d-134">**Correct Approach:** To be able to modify an underlying variable element itself, pass it by reference.</span></span> <span data-ttu-id="7925d-135">下面的示例演示 `replace` 的声明中的更改，它允许在调用代码中将一个数组替换为另一个数组。</span><span class="sxs-lookup"><span data-stu-id="7925d-135">The following example shows the change in the declaration of `replace` that allows it to replace one array with another in the calling code.</span></span>

 [!code-vb[VbVbcnProcedures#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#64)]

## <a name="unable-to-define-an-overload"></a><span data-ttu-id="7925d-136">无法定义重载</span><span class="sxs-lookup"><span data-stu-id="7925d-136">Unable to Define an Overload</span></span>

 <span data-ttu-id="7925d-137">如果要定义过程的重载版本，则必须使用相同的名称，但不能使用其他签名。</span><span class="sxs-lookup"><span data-stu-id="7925d-137">If you want to define an overloaded version of a procedure, you must use the same name but a different signature.</span></span> <span data-ttu-id="7925d-138">如果编译器无法将声明与具有相同签名的重载区分开来，则会生成错误。</span><span class="sxs-lookup"><span data-stu-id="7925d-138">If the compiler cannot differentiate your declaration from an overload with the same signature, it generates an error.</span></span>

 <span data-ttu-id="7925d-139">过程的*签名*由过程名称和参数列表确定。</span><span class="sxs-lookup"><span data-stu-id="7925d-139">The *signature* of a procedure is determined by the procedure name and the parameter list.</span></span> <span data-ttu-id="7925d-140">每个重载必须与所有其他重载具有相同的名称，但必须在签名的其他至少一个组件中与所有重载的名称不同。</span><span class="sxs-lookup"><span data-stu-id="7925d-140">Each overload must have the same name as all the other overloads but must differ from all of them in at least one of the other components of the signature.</span></span> <span data-ttu-id="7925d-141">有关更多信息，请参见 [Procedure Overloading](procedure-overloading.md)。</span><span class="sxs-lookup"><span data-stu-id="7925d-141">For more information, see [Procedure Overloading](procedure-overloading.md).</span></span>

 <span data-ttu-id="7925d-142">以下项（即使它们属于参数列表）不是过程签名的组成部分：</span><span class="sxs-lookup"><span data-stu-id="7925d-142">The following items, even though they pertain to the parameter list, are not components of a procedure's signature:</span></span>

- <span data-ttu-id="7925d-143">过程修饰符关键字，如 `Public`、`Shared` 和 `Static`</span><span class="sxs-lookup"><span data-stu-id="7925d-143">Procedure modifier keywords, such as `Public`, `Shared`, and `Static`</span></span>

- <span data-ttu-id="7925d-144">参数名称</span><span class="sxs-lookup"><span data-stu-id="7925d-144">Parameter names</span></span>

- <span data-ttu-id="7925d-145">参数修饰符关键字，如 `ByRef` 和 `Optional`</span><span class="sxs-lookup"><span data-stu-id="7925d-145">Parameter modifier keywords, such as `ByRef` and `Optional`</span></span>

- <span data-ttu-id="7925d-146">返回值的数据类型（转换运算符除外）</span><span class="sxs-lookup"><span data-stu-id="7925d-146">The data type of the return value (except for a conversion operator)</span></span>

 <span data-ttu-id="7925d-147">不能通过仅改变一个或多个前述项来重载过程。</span><span class="sxs-lookup"><span data-stu-id="7925d-147">You cannot overload a procedure by varying only one or more of the preceding items.</span></span>

 <span data-ttu-id="7925d-148">**正确的方法：** 若要定义过程重载，必须更改签名。</span><span class="sxs-lookup"><span data-stu-id="7925d-148">**Correct Approach:** To be able to define a procedure overload, you must vary the signature.</span></span> <span data-ttu-id="7925d-149">由于必须使用相同的名称，因此必须更改参数的数目、顺序或数据类型。</span><span class="sxs-lookup"><span data-stu-id="7925d-149">Because you must use the same name, you must vary the number, order, or data types of the parameters.</span></span> <span data-ttu-id="7925d-150">在泛型过程中，可以改变类型参数的数目。</span><span class="sxs-lookup"><span data-stu-id="7925d-150">In a generic procedure, you can vary the number of type parameters.</span></span> <span data-ttu-id="7925d-151">在转换运算符（[CType 函数](../../../language-reference/functions/ctype-function.md)）中，可以改变返回类型。</span><span class="sxs-lookup"><span data-stu-id="7925d-151">In a conversion operator ([CType Function](../../../language-reference/functions/ctype-function.md)), you can vary the return type.</span></span>

### <a name="overload-resolution-with-optional-and-paramarray-arguments"></a><span data-ttu-id="7925d-152">具有可选参数和 ParamArray 参数的重载决策</span><span class="sxs-lookup"><span data-stu-id="7925d-152">Overload Resolution with Optional and ParamArray Arguments</span></span>

 <span data-ttu-id="7925d-153">如果要重载具有一个或多个[可选](../../../language-reference/modifiers/optional.md)参数或[ParamArray](../../../language-reference/modifiers/paramarray.md)参数的过程，则必须避免复制任何*隐式重载*。</span><span class="sxs-lookup"><span data-stu-id="7925d-153">If you are overloading a procedure with one or more [Optional](../../../language-reference/modifiers/optional.md) parameters or a [ParamArray](../../../language-reference/modifiers/paramarray.md) parameter, you must avoid duplicating any of the *implicit overloads*.</span></span> <span data-ttu-id="7925d-154">有关信息，请参阅[重载过程中的注意事项](considerations-in-overloading-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="7925d-154">For information, see [Considerations in Overloading Procedures](considerations-in-overloading-procedures.md).</span></span>

## <a name="calling-a-wrong-version-of-an-overloaded-procedure"></a><span data-ttu-id="7925d-155">调用错误的重载过程版本</span><span class="sxs-lookup"><span data-stu-id="7925d-155">Calling a Wrong Version of an Overloaded Procedure</span></span>

 <span data-ttu-id="7925d-156">如果过程具有多个重载版本，你应该熟悉其所有参数列表，并了解 Visual Basic 如何在重载之间解析调用。</span><span class="sxs-lookup"><span data-stu-id="7925d-156">If a procedure has several overloaded versions, you should be familiar with all their parameter lists and understand how Visual Basic resolves calls among the overloads.</span></span> <span data-ttu-id="7925d-157">否则，可以调用非预期重载。</span><span class="sxs-lookup"><span data-stu-id="7925d-157">Otherwise you could call an overload other than the intended one.</span></span>

 <span data-ttu-id="7925d-158">确定要调用的重载时，请注意遵守以下规则：</span><span class="sxs-lookup"><span data-stu-id="7925d-158">When you have determined which overload you want to call, be careful to observe the following rules:</span></span>

- <span data-ttu-id="7925d-159">提供正确的参数数目，并按正确的顺序排列。</span><span class="sxs-lookup"><span data-stu-id="7925d-159">Supply the correct number of arguments, and in the correct order.</span></span>

- <span data-ttu-id="7925d-160">理想情况下，自变量的数据类型应与对应参数的数据类型完全相同。</span><span class="sxs-lookup"><span data-stu-id="7925d-160">Ideally, your arguments should have the exact same data types as the corresponding parameters.</span></span> <span data-ttu-id="7925d-161">在任何情况下，每个参数的数据类型必须扩大到其对应参数的数据类型。</span><span class="sxs-lookup"><span data-stu-id="7925d-161">In any case, the data type of each argument must widen to that of its corresponding parameter.</span></span> <span data-ttu-id="7925d-162">即使[Option Strict 语句](../../../language-reference/statements/option-strict-statement.md)设置为 `Off`，也是如此。</span><span class="sxs-lookup"><span data-stu-id="7925d-162">This is true even with the [Option Strict Statement](../../../language-reference/statements/option-strict-statement.md) set to `Off`.</span></span> <span data-ttu-id="7925d-163">如果重载需要自变量列表进行任何收缩转换，则不能调用该重载。</span><span class="sxs-lookup"><span data-stu-id="7925d-163">If an overload requires any narrowing conversion from your argument list, that overload is not eligible to be called.</span></span>

- <span data-ttu-id="7925d-164">如果提供需要扩大的参数，请将其数据类型尽可能靠近相应的参数数据类型。</span><span class="sxs-lookup"><span data-stu-id="7925d-164">If you supply arguments that require widening, make their data types as close as possible to the corresponding parameter data types.</span></span> <span data-ttu-id="7925d-165">如果两个或更多重载接受您的参数数据类型，则编译器会将调用解析为对最小扩大量进行调用的重载。</span><span class="sxs-lookup"><span data-stu-id="7925d-165">If two or more overloads accept your argument data types, the compiler resolves your call to the overload that calls for the least amount of widening.</span></span>

 <span data-ttu-id="7925d-166">在准备参数时，可以使用[CType 函数](../../../language-reference/functions/ctype-function.md)转换关键字来减少数据类型不匹配的几率。</span><span class="sxs-lookup"><span data-stu-id="7925d-166">You can reduce the chance of data type mismatches by using the [CType Function](../../../language-reference/functions/ctype-function.md) conversion keyword when preparing your arguments.</span></span>

### <a name="overload-resolution-failure"></a><span data-ttu-id="7925d-167">重载决策失败</span><span class="sxs-lookup"><span data-stu-id="7925d-167">Overload Resolution Failure</span></span>

 <span data-ttu-id="7925d-168">调用重载过程时，编译器会尝试消除除一个重载以外的所有重载。</span><span class="sxs-lookup"><span data-stu-id="7925d-168">When you call an overloaded procedure, the compiler attempts to eliminate all but one of the overloads.</span></span> <span data-ttu-id="7925d-169">如果成功，它将解析对该重载的调用。</span><span class="sxs-lookup"><span data-stu-id="7925d-169">If it succeeds, it resolves the call to that overload.</span></span> <span data-ttu-id="7925d-170">如果它消除了所有重载，或者无法将符合条件的重载减少到单个候选项，则会生成错误。</span><span class="sxs-lookup"><span data-stu-id="7925d-170">If it eliminates all the overloads, or if it cannot reduce the eligible overloads to a single candidate, it generates an error.</span></span>

 <span data-ttu-id="7925d-171">下面的示例演示了重载决策过程。</span><span class="sxs-lookup"><span data-stu-id="7925d-171">The following example illustrates the overload resolution process.</span></span>

 [!code-vb[VbVbcnProcedures#62](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#62)]

 [!code-vb[VbVbcnProcedures#63](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#63)]

 <span data-ttu-id="7925d-172">在第一次调用中，编译器将消除第一个重载，因为第一个参数的类型（`Short`）会缩小到相应参数的类型（@no__t 为-1）。</span><span class="sxs-lookup"><span data-stu-id="7925d-172">In the first call, the compiler eliminates the first overload because the type of the first argument (`Short`) narrows to the type of the corresponding parameter (`Byte`).</span></span> <span data-ttu-id="7925d-173">然后，它将消除第三个重载，因为第二个重载（@no__t 0 和 `Single`）中的每个参数类型扩大到第三个重载（`Integer` 和 `Single`）中的相应类型。</span><span class="sxs-lookup"><span data-stu-id="7925d-173">It then eliminates the third overload because each argument type in the second overload (`Short` and `Single`) widens to the corresponding type in the third overload (`Integer` and `Single`).</span></span> <span data-ttu-id="7925d-174">第二个重载需要更少的扩展，因此编译器将其用于调用。</span><span class="sxs-lookup"><span data-stu-id="7925d-174">The second overload requires less widening, so the compiler uses it for the call.</span></span>

 <span data-ttu-id="7925d-175">在第二次调用中，编译器无法根据收缩消除任何重载。</span><span class="sxs-lookup"><span data-stu-id="7925d-175">In the second call, the compiler cannot eliminate any of the overloads on the basis of narrowing.</span></span> <span data-ttu-id="7925d-176">它消除第三个重载的原因与第一次调用中的相同原因，因为它可以通过更少的参数类型来调用第二个重载。</span><span class="sxs-lookup"><span data-stu-id="7925d-176">It eliminates the third overload for the same reason as in the first call, because it can call the second overload with less widening of the argument types.</span></span> <span data-ttu-id="7925d-177">但编译器无法在第一个和第二个重载之间解析。</span><span class="sxs-lookup"><span data-stu-id="7925d-177">However, the compiler cannot resolve between the first and second overloads.</span></span> <span data-ttu-id="7925d-178">每个都有一个已定义的参数类型，该类型扩大到另一个中的相应类型（`Byte` 到 `Short`，但 `Single` 到 @no__t。</span><span class="sxs-lookup"><span data-stu-id="7925d-178">Each has one defined parameter type that widens to the corresponding type in the other (`Byte` to `Short`, but `Single` to `Double`).</span></span> <span data-ttu-id="7925d-179">因此，编译器将生成重载决策错误。</span><span class="sxs-lookup"><span data-stu-id="7925d-179">The compiler therefore generates an overload resolution error.</span></span>

 <span data-ttu-id="7925d-180">**正确的方法：** 若要能够无歧义地调用重载过程，请使用[CType 函数](../../../language-reference/functions/ctype-function.md)将参数数据类型与参数类型相匹配。</span><span class="sxs-lookup"><span data-stu-id="7925d-180">**Correct Approach:** To be able to call an overloaded procedure without ambiguity, use [CType Function](../../../language-reference/functions/ctype-function.md) to match the argument data types to the parameter types.</span></span> <span data-ttu-id="7925d-181">下面的示例演示对 `z` 的调用，该调用强制解析为第二个重载。</span><span class="sxs-lookup"><span data-stu-id="7925d-181">The following example shows a call to `z` that forces resolution to the second overload.</span></span>

 [!code-vb[VbVbcnProcedures#65](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#65)]

### <a name="overload-resolution-with-optional-and-paramarray-arguments"></a><span data-ttu-id="7925d-182">具有可选参数和 ParamArray 参数的重载决策</span><span class="sxs-lookup"><span data-stu-id="7925d-182">Overload Resolution with Optional and ParamArray Arguments</span></span>

 <span data-ttu-id="7925d-183">如果过程的两个重载具有相同的签名，但最后一个参数在另[一个中声明](../../../language-reference/modifiers/paramarray.md)为[可选](../../../language-reference/modifiers/optional.md)，则编译器将根据最接近的匹配项解析对该过程的调用。</span><span class="sxs-lookup"><span data-stu-id="7925d-183">If two overloads of a procedure have identical signatures except that the last parameter is declared [Optional](../../../language-reference/modifiers/optional.md) in one and [ParamArray](../../../language-reference/modifiers/paramarray.md) in the other, the compiler resolves a call to that procedure according to the closest match.</span></span> <span data-ttu-id="7925d-184">有关更多信息，请参见 [Overload Resolution](overload-resolution.md)。</span><span class="sxs-lookup"><span data-stu-id="7925d-184">For more information, see [Overload Resolution](overload-resolution.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7925d-185">请参阅</span><span class="sxs-lookup"><span data-stu-id="7925d-185">See also</span></span>

- [<span data-ttu-id="7925d-186">过程</span><span class="sxs-lookup"><span data-stu-id="7925d-186">Procedures</span></span>](index.md)
- [<span data-ttu-id="7925d-187">Sub 过程</span><span class="sxs-lookup"><span data-stu-id="7925d-187">Sub Procedures</span></span>](sub-procedures.md)
- [<span data-ttu-id="7925d-188">Function 过程</span><span class="sxs-lookup"><span data-stu-id="7925d-188">Function Procedures</span></span>](function-procedures.md)
- [<span data-ttu-id="7925d-189">属性过程</span><span class="sxs-lookup"><span data-stu-id="7925d-189">Property Procedures</span></span>](property-procedures.md)
- [<span data-ttu-id="7925d-190">运算符过程</span><span class="sxs-lookup"><span data-stu-id="7925d-190">Operator Procedures</span></span>](operator-procedures.md)
- [<span data-ttu-id="7925d-191">过程参数和自变量</span><span class="sxs-lookup"><span data-stu-id="7925d-191">Procedure Parameters and Arguments</span></span>](procedure-parameters-and-arguments.md)
- [<span data-ttu-id="7925d-192">过程重载</span><span class="sxs-lookup"><span data-stu-id="7925d-192">Procedure Overloading</span></span>](procedure-overloading.md)
- [<span data-ttu-id="7925d-193">重载过程注意事项</span><span class="sxs-lookup"><span data-stu-id="7925d-193">Considerations in Overloading Procedures</span></span>](considerations-in-overloading-procedures.md)
- [<span data-ttu-id="7925d-194">重载决策</span><span class="sxs-lookup"><span data-stu-id="7925d-194">Overload Resolution</span></span>](overload-resolution.md)
