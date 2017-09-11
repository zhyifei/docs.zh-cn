---
title: "在 Visual Basic 中的生存期 |Microsoft 文档"
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
- static variables, lifetime
- static variables, Visual Basic
- declared elements, lifetime
- Shared variable lifetime
- lifetime, declared elements
- lifetime, Visual Basic
- lifetime
ms.assetid: bd91e390-690a-469a-9946-8dca70bc14e7
caps.latest.revision: 14
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
ms.openlocfilehash: 4e183d1fa36c967facbb81ebd6917a8fb75d48cd
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="lifetime-in-visual-basic"></a><span data-ttu-id="b8bd9-102">Visual Basic 中的生存期</span><span class="sxs-lookup"><span data-stu-id="b8bd9-102">Lifetime in Visual Basic</span></span>
<span data-ttu-id="b8bd9-103">*生存期*已声明元素的是一段时间期间它是可供使用。</span><span class="sxs-lookup"><span data-stu-id="b8bd9-103">The *lifetime* of a declared element is the period of time during which it is available for use.</span></span> <span data-ttu-id="b8bd9-104">变量是唯一具有生存期的元素。</span><span class="sxs-lookup"><span data-stu-id="b8bd9-104">Variables are the only elements that have lifetime.</span></span> <span data-ttu-id="b8bd9-105">出于此目的，则编译器会将过程参数和函数返回值视为变量的特殊情况。</span><span class="sxs-lookup"><span data-stu-id="b8bd9-105">For this purpose, the compiler treats procedure parameters and function returns as special cases of variables.</span></span> <span data-ttu-id="b8bd9-106">变量的生存期表示的时间在此期间，它可以保存一个值。</span><span class="sxs-lookup"><span data-stu-id="b8bd9-106">The lifetime of a variable represents the period of time during which it can hold a value.</span></span> <span data-ttu-id="b8bd9-107">其值可以更改的生存期内，但它始终包含一些值。</span><span class="sxs-lookup"><span data-stu-id="b8bd9-107">Its value can change over its lifetime, but it always holds some value.</span></span>  
  
## <a name="different-lifetimes"></a><span data-ttu-id="b8bd9-108">不同的生存期</span><span class="sxs-lookup"><span data-stu-id="b8bd9-108">Different Lifetimes</span></span>  
 <span data-ttu-id="b8bd9-109">一个*成员变量*（在模块级别，任何过程之外声明） 通常都有相同的生存期声明它的元素。</span><span class="sxs-lookup"><span data-stu-id="b8bd9-109">A *member variable* (declared at module level, outside any procedure) typically has the same lifetime as the element in which it is declared.</span></span> <span data-ttu-id="b8bd9-110">声明的类或结构中的非共享的变量作为单独的类或结构声明它的每个实例的副本存在。</span><span class="sxs-lookup"><span data-stu-id="b8bd9-110">A nonshared variable declared in a class or structure exists as a separate copy for each instance of the class or structure in which it is declared.</span></span> <span data-ttu-id="b8bd9-111">每个此类变量具有相同的生存期与它的实例。</span><span class="sxs-lookup"><span data-stu-id="b8bd9-111">Each such variable has the same lifetime as its instance.</span></span> <span data-ttu-id="b8bd9-112">但是，`Shared`变量仅有一个生存期，即持续运行您的应用程序的整个时间。</span><span class="sxs-lookup"><span data-stu-id="b8bd9-112">However, a `Shared` variable has only a single lifetime, which lasts for the entire time your application is running.</span></span>  
  
 <span data-ttu-id="b8bd9-113">一个*局部变量*（在过程内声明） 仅在声明它的过程的运行时才存在。</span><span class="sxs-lookup"><span data-stu-id="b8bd9-113">A *local variable* (declared inside a procedure) exists only while the procedure in which it is declared is running.</span></span> <span data-ttu-id="b8bd9-114">这同样适用于过程的参数和返回任何函数。</span><span class="sxs-lookup"><span data-stu-id="b8bd9-114">This applies also to that procedure's parameters and to any function return.</span></span> <span data-ttu-id="b8bd9-115">但是，如果该过程调用其他过程，本地变量保留其值在被调用的过程运行时。</span><span class="sxs-lookup"><span data-stu-id="b8bd9-115">However, if that procedure calls other procedures, the local variables retain their values while the called procedures are running.</span></span>  
  
## <a name="beginning-of-lifetime"></a><span data-ttu-id="b8bd9-116">生存期的开始</span><span class="sxs-lookup"><span data-stu-id="b8bd9-116">Beginning of Lifetime</span></span>  
 <span data-ttu-id="b8bd9-117">当控制权交给声明它的过程时，本地变量的生存期开始。</span><span class="sxs-lookup"><span data-stu-id="b8bd9-117">A local variable's lifetime begins when control enters the procedure in which it is declared.</span></span> <span data-ttu-id="b8bd9-118">每个本地变量初始化为其数据类型的默认值，该过程开始时运行。</span><span class="sxs-lookup"><span data-stu-id="b8bd9-118">Every local variable is initialized to the default value for its data type as soon as the procedure begins running.</span></span> <span data-ttu-id="b8bd9-119">当该过程中遇到`Dim`语句中指定初始值，它将设置这些变量为这些值，即使您的代码必须对其分配了其他值。</span><span class="sxs-lookup"><span data-stu-id="b8bd9-119">When the procedure encounters a `Dim` statement that specifies initial values, it sets those variables to those values, even if your code had already assigned other values to them.</span></span>  
  
 <span data-ttu-id="b8bd9-120">像它是一个单独的变量，会初始化结构变量的每个成员。</span><span class="sxs-lookup"><span data-stu-id="b8bd9-120">Each member of a structure variable is initialized as if it were a separate variable.</span></span> <span data-ttu-id="b8bd9-121">同样，分别初始化数组变量的每个元素。</span><span class="sxs-lookup"><span data-stu-id="b8bd9-121">Similarly, each element of an array variable is initialized individually.</span></span>  
  
 <span data-ttu-id="b8bd9-122">过程内部块中声明变量 (如`For`循环) 在进入过程上进行初始化。</span><span class="sxs-lookup"><span data-stu-id="b8bd9-122">Variables declared within a block inside a procedure (such as a `For` loop) are initialized on entry to the procedure.</span></span> <span data-ttu-id="b8bd9-123">曾经执行过代码块，这些初始化生效。</span><span class="sxs-lookup"><span data-stu-id="b8bd9-123">These initializations take effect whether or not your code ever executes the block.</span></span>  
  
## <a name="end-of-lifetime"></a><span data-ttu-id="b8bd9-124">生存期结束</span><span class="sxs-lookup"><span data-stu-id="b8bd9-124">End of Lifetime</span></span>  
 <span data-ttu-id="b8bd9-125">当一个过程终止时，不保留其本地变量的值，并[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]回收它们的内存。</span><span class="sxs-lookup"><span data-stu-id="b8bd9-125">When a procedure terminates, the values of its local variables are not preserved, and [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] reclaims their memory.</span></span> <span data-ttu-id="b8bd9-126">下次调用该过程，所有本地变量重新创建和重新初始化订阅。</span><span class="sxs-lookup"><span data-stu-id="b8bd9-126">The next time you call the procedure, all its local variables are created afresh and reinitialized.</span></span>  
  
 <span data-ttu-id="b8bd9-127">类或结构的实例终止时，将其非共享的变量会丢失其内存和它们的值。</span><span class="sxs-lookup"><span data-stu-id="b8bd9-127">When an instance of a class or structure terminates, its nonshared variables lose their memory and their values.</span></span> <span data-ttu-id="b8bd9-128">类或结构的每个新实例创建，并重新初始化其非共享的变量。</span><span class="sxs-lookup"><span data-stu-id="b8bd9-128">Each new instance of the class or structure creates and reinitializes its nonshared variables.</span></span> <span data-ttu-id="b8bd9-129">但是，`Shared`变量被保留，直到您的应用程序将停止运行。</span><span class="sxs-lookup"><span data-stu-id="b8bd9-129">However, `Shared` variables are preserved until your application stops running.</span></span>  
  
## <a name="extension-of-lifetime"></a><span data-ttu-id="b8bd9-130">生存期的扩展</span><span class="sxs-lookup"><span data-stu-id="b8bd9-130">Extension of Lifetime</span></span>  
 <span data-ttu-id="b8bd9-131">如果您声明的局部变量`Static`关键字，它的生存期即比其过程的执行时间更长。</span><span class="sxs-lookup"><span data-stu-id="b8bd9-131">If you declare a local variable with the `Static` keyword, its lifetime is longer than the execution time of its procedure.</span></span> <span data-ttu-id="b8bd9-132">下表显示了过程声明确定多长时间`Static`变量确实存在。</span><span class="sxs-lookup"><span data-stu-id="b8bd9-132">The following table shows how the procedure declaration determines how long a `Static` variable exists.</span></span>  
  
|<span data-ttu-id="b8bd9-133">过程位置与共享</span><span class="sxs-lookup"><span data-stu-id="b8bd9-133">Procedure location and sharing</span></span>|<span data-ttu-id="b8bd9-134">静态变量生存期开始</span><span class="sxs-lookup"><span data-stu-id="b8bd9-134">Static variable lifetime begins</span></span>|<span data-ttu-id="b8bd9-135">静态变量的生存期结束</span><span class="sxs-lookup"><span data-stu-id="b8bd9-135">Static variable lifetime ends</span></span>|  
|------------------------------------|-------------------------------------|-----------------------------------|  
|<span data-ttu-id="b8bd9-136">（默认情况下共享） 的模块中</span><span class="sxs-lookup"><span data-stu-id="b8bd9-136">In a module (shared by default)</span></span>|<span data-ttu-id="b8bd9-137">第一次调用该过程</span><span class="sxs-lookup"><span data-stu-id="b8bd9-137">The first time the procedure is called</span></span>|<span data-ttu-id="b8bd9-138">在您的应用程序停止运行时</span><span class="sxs-lookup"><span data-stu-id="b8bd9-138">When your application stops running</span></span>|  
|<span data-ttu-id="b8bd9-139">在类中， `Shared` （过程不是实例成员）</span><span class="sxs-lookup"><span data-stu-id="b8bd9-139">In a class, `Shared` (procedure is not an instance member)</span></span>|<span data-ttu-id="b8bd9-140">第一次调用该过程是对特定实例或者对自身的类或结构名称</span><span class="sxs-lookup"><span data-stu-id="b8bd9-140">The first time the procedure is called either on a specific instance or on the class or structure name itself</span></span>|<span data-ttu-id="b8bd9-141">在您的应用程序停止运行时</span><span class="sxs-lookup"><span data-stu-id="b8bd9-141">When your application stops running</span></span>|  
|<span data-ttu-id="b8bd9-142">一个类的实例中不`Shared`（过程是一个实例成员）</span><span class="sxs-lookup"><span data-stu-id="b8bd9-142">In an instance of a class, not `Shared` (procedure is an instance member)</span></span>|<span data-ttu-id="b8bd9-143">第一次特定实例调用该过程</span><span class="sxs-lookup"><span data-stu-id="b8bd9-143">The first time the procedure is called on the specific instance</span></span>|<span data-ttu-id="b8bd9-144">当垃圾回收 (GC) 释放该实例</span><span class="sxs-lookup"><span data-stu-id="b8bd9-144">When the instance is released for garbage collection (GC)</span></span>|  
  
## <a name="static-variables-of-the-same-name"></a><span data-ttu-id="b8bd9-145">具有相同名称的静态变量</span><span class="sxs-lookup"><span data-stu-id="b8bd9-145">Static Variables of the Same Name</span></span>  
 <span data-ttu-id="b8bd9-146">您可以声明具有多个过程中具有相同名称的静态变量。</span><span class="sxs-lookup"><span data-stu-id="b8bd9-146">You can declare static variables with the same name in more than one procedure.</span></span> <span data-ttu-id="b8bd9-147">如果执行此操作，[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]编译器会考虑每个此类变量视为一个单独的元素。</span><span class="sxs-lookup"><span data-stu-id="b8bd9-147">If you do this, the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler considers each such variable to be a separate element.</span></span> <span data-ttu-id="b8bd9-148">其中一个变量的初始化并不影响其他值。</span><span class="sxs-lookup"><span data-stu-id="b8bd9-148">The initialization of one of these variables does not affect the values of the others.</span></span> <span data-ttu-id="b8bd9-149">这同样适用于定义一个具有一组重载过程并声明中每个重载具有相同名称的静态变量。</span><span class="sxs-lookup"><span data-stu-id="b8bd9-149">The same applies if you define a procedure with a set of overloads and declare a static variable with the same name in each overload.</span></span>  
  
## <a name="containing-elements-for-static-variables"></a><span data-ttu-id="b8bd9-150">静态变量的包含元素</span><span class="sxs-lookup"><span data-stu-id="b8bd9-150">Containing Elements for Static Variables</span></span>  
 <span data-ttu-id="b8bd9-151">可以在该类中的过程，即声明一个类中的静态局部变量。</span><span class="sxs-lookup"><span data-stu-id="b8bd9-151">You can declare a static local variable within a class, that is, inside a procedure in that class.</span></span> <span data-ttu-id="b8bd9-152">但是，不能声明为静态局部变量在结构中，结构成员或该结构内的一个过程的本地变量。</span><span class="sxs-lookup"><span data-stu-id="b8bd9-152">However, you cannot declare a static local variable within a structure, either as a structure member or as a local variable of a procedure within that structure.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8bd9-153">示例</span><span class="sxs-lookup"><span data-stu-id="b8bd9-153">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="b8bd9-154">说明</span><span class="sxs-lookup"><span data-stu-id="b8bd9-154">Description</span></span>  
 <span data-ttu-id="b8bd9-155">下面的示例声明的变量[静态](../../../../visual-basic/language-reference/modifiers/static.md)关键字。</span><span class="sxs-lookup"><span data-stu-id="b8bd9-155">The following example declares a variable with the [Static](../../../../visual-basic/language-reference/modifiers/static.md) keyword.</span></span> <span data-ttu-id="b8bd9-156">(请注意，不需要`Dim`关键字时[Dim 语句](../../../../visual-basic/language-reference/statements/dim-statement.md)使用修饰符，如`Static`。)</span><span class="sxs-lookup"><span data-stu-id="b8bd9-156">(Note that you do not need the `Dim` keyword when the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) uses a modifier such as `Static`.)</span></span>  
  
### <a name="code"></a><span data-ttu-id="b8bd9-157">代码</span><span class="sxs-lookup"><span data-stu-id="b8bd9-157">Code</span></span>  
 <span data-ttu-id="b8bd9-158">[!code-vb[VbVbalrKeywords #&13;](../../../../visual-basic/language-reference/codesnippet/VisualBasic/lifetime_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="b8bd9-158">[!code-vb[VbVbalrKeywords#13](../../../../visual-basic/language-reference/codesnippet/VisualBasic/lifetime_1.vb)]</span></span>  
  
### <a name="comments"></a><span data-ttu-id="b8bd9-159">注释</span><span class="sxs-lookup"><span data-stu-id="b8bd9-159">Comments</span></span>  
 <span data-ttu-id="b8bd9-160">在前面的示例中，该变量`applesSold`会继续保留在过程后面从而`runningTotal`返回到调用代码。</span><span class="sxs-lookup"><span data-stu-id="b8bd9-160">In the preceding example, the variable `applesSold` continues to exist after the procedure `runningTotal` returns to the calling code.</span></span> <span data-ttu-id="b8bd9-161">下一次`runningTotal`调用时，`applesSold`保留其以前计算的值。</span><span class="sxs-lookup"><span data-stu-id="b8bd9-161">The next time `runningTotal` is called, `applesSold` retains its previously calculated value.</span></span>  
  
 <span data-ttu-id="b8bd9-162">如果`applesSold`内容而无需使用已声明`Static`，跨调用的将不会保留以前的累积的值`runningTotal`。</span><span class="sxs-lookup"><span data-stu-id="b8bd9-162">If `applesSold` had been declared without using `Static`, the previous accumulated values would not be preserved across calls to `runningTotal`.</span></span> <span data-ttu-id="b8bd9-163">下一次`runningTotal`调用了，`applesSold`本来会被重新创建和初始化为 0，和`runningTotal`将只返回与调用了相同的值。</span><span class="sxs-lookup"><span data-stu-id="b8bd9-163">The next time `runningTotal` was called, `applesSold` would have been recreated and initialized to 0, and `runningTotal` would have simply returned the same value with which it was called.</span></span>  
  
### <a name="compiling-the-code"></a><span data-ttu-id="b8bd9-164">编译代码</span><span class="sxs-lookup"><span data-stu-id="b8bd9-164">Compiling the Code</span></span>  
 <span data-ttu-id="b8bd9-165">您可以初始化为其声明的一部分的静态局部变量的值。</span><span class="sxs-lookup"><span data-stu-id="b8bd9-165">You can initialize the value of a static local variable as part of its declaration.</span></span> <span data-ttu-id="b8bd9-166">如果您声明为一系列`Static`，则可以初始化其秩 （维数）、 每个维度的长度和各个元素的值。</span><span class="sxs-lookup"><span data-stu-id="b8bd9-166">If you declare an array to be `Static`, you can initialize its rank (number of dimensions), the length of each dimension, and the values of the individual elements.</span></span>  
  
### <a name="security"></a><span data-ttu-id="b8bd9-167">安全性</span><span class="sxs-lookup"><span data-stu-id="b8bd9-167">Security</span></span>  
 <span data-ttu-id="b8bd9-168">在前面的示例中，您可以通过声明生成相同的生存期`applesSold`在模块级别。</span><span class="sxs-lookup"><span data-stu-id="b8bd9-168">In the preceding example, you can produce the same lifetime by declaring `applesSold` at module level.</span></span> <span data-ttu-id="b8bd9-169">如果发生这种方式更改变量的作用域，但是，该过程将不再具有独占访问。</span><span class="sxs-lookup"><span data-stu-id="b8bd9-169">If you changed the scope of a variable this way, however, the procedure would no longer have exclusive access to it.</span></span> <span data-ttu-id="b8bd9-170">由于其他过程可以访问`applesSold`和将其值更改、 运行总计可能是不可靠和代码可能会更难维护。</span><span class="sxs-lookup"><span data-stu-id="b8bd9-170">Because other procedures could access `applesSold` and change its value, the running total could be unreliable and the code could be more difficult to maintain.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8bd9-171">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b8bd9-171">See Also</span></span>  
 <span data-ttu-id="b8bd9-172">[共享](../../../../visual-basic/language-reference/modifiers/shared.md) </span><span class="sxs-lookup"><span data-stu-id="b8bd9-172">[Shared](../../../../visual-basic/language-reference/modifiers/shared.md) </span></span>  
<span data-ttu-id="b8bd9-173"> [执行任何操作](../../../../visual-basic/language-reference/nothing.md) </span><span class="sxs-lookup"><span data-stu-id="b8bd9-173"> [Nothing](../../../../visual-basic/language-reference/nothing.md) </span></span>  
<span data-ttu-id="b8bd9-174"> [已声明的元素名称](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md) </span><span class="sxs-lookup"><span data-stu-id="b8bd9-174"> [Declared Element Names](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md) </span></span>  
<span data-ttu-id="b8bd9-175"> [对已声明的元素的引用](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md) </span><span class="sxs-lookup"><span data-stu-id="b8bd9-175"> [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md) </span></span>  
<span data-ttu-id="b8bd9-176"> [在 Visual Basic 中的作用域](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md) </span><span class="sxs-lookup"><span data-stu-id="b8bd9-176"> [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md) </span></span>  
<span data-ttu-id="b8bd9-177"> [在 Visual Basic 中的访问级别](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md) </span><span class="sxs-lookup"><span data-stu-id="b8bd9-177"> [Access Levels in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md) </span></span>  
<span data-ttu-id="b8bd9-178"> [变量](../../../../visual-basic/programming-guide/language-features/variables/index.md) </span><span class="sxs-lookup"><span data-stu-id="b8bd9-178"> [Variables](../../../../visual-basic/programming-guide/language-features/variables/index.md) </span></span>  
<span data-ttu-id="b8bd9-179"> [变量声明](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md) </span><span class="sxs-lookup"><span data-stu-id="b8bd9-179"> [Variable Declaration](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md) </span></span>  
<span data-ttu-id="b8bd9-180"> [数据类型疑难解答](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="b8bd9-180"> [Troubleshooting Data Types](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md) </span></span>  
<span data-ttu-id="b8bd9-181"> [Static](../../../../visual-basic/language-reference/modifiers/static.md)</span><span class="sxs-lookup"><span data-stu-id="b8bd9-181"> [Static](../../../../visual-basic/language-reference/modifiers/static.md)</span></span>
