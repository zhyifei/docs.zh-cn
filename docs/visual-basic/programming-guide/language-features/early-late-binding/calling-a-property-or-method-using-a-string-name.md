---
title: "使用字符串名称 (Visual Basic 中) 调用属性或方法 |Microsoft 文档"
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
- passing operators
- strings [Visual Basic], passing new operators as
- objects [Visual Basic], setting properties
- setting properties, object properties at run time
- method calls, strings
- methods [Visual Basic], calling with string names
- calling methods, string names
- properties [Visual Basic], setting at run time
- CallByName function
ms.assetid: 79a7b8b4-b8c7-4ad8-aca8-12a9a2b32f03
caps.latest.revision: 17
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
ms.openlocfilehash: 6de5e655b3d4d42283b81507d7f08e0eb0b9424d
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="calling-a-property-or-method-using-a-string-name-visual-basic"></a><span data-ttu-id="a36e2-102">使用字符串名调用属性或方法 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a36e2-102">Calling a Property or Method Using a String Name (Visual Basic)</span></span>
<span data-ttu-id="a36e2-103">在大多数情况下，可以在设计时发现的属性和对象的方法，并编写代码来处理它们。</span><span class="sxs-lookup"><span data-stu-id="a36e2-103">In most cases, you can discover the properties and methods of an object at design time, and write code to handle them.</span></span> <span data-ttu-id="a36e2-104">但是，在某些情况下您可能事先不知道有关对象的属性和方法，或者可能只是需要灵活性，使最终用户可以指定属性或在运行时执行的方法。</span><span class="sxs-lookup"><span data-stu-id="a36e2-104">However, in some cases you may not know about an object's properties and methods in advance, or you may just want the flexibility of enabling an end user to specify properties or execute methods at run time.</span></span>  
  
## <a name="callbyname-function"></a><span data-ttu-id="a36e2-105">CallByName 函数</span><span class="sxs-lookup"><span data-stu-id="a36e2-105">CallByName Function</span></span>  
 <span data-ttu-id="a36e2-106">例如，考虑通过将运算符传递给 COM 组件的用户输入的表达式的计算结果的客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="a36e2-106">Consider, for example, a client application that evaluates expressions entered by the user by passing an operator to a COM component.</span></span> <span data-ttu-id="a36e2-107">假设要不断地向需要新的运算符的组件中添加新函数。</span><span class="sxs-lookup"><span data-stu-id="a36e2-107">Suppose you are constantly adding new functions to the component that require new operators.</span></span> <span data-ttu-id="a36e2-108">当您使用标准对象访问技术时，您必须重新编译并重新分发客户端应用程序，可以使用新的运算符之前。</span><span class="sxs-lookup"><span data-stu-id="a36e2-108">When you use standard object access techniques, you must recompile and redistribute the client application before it could use the new operators.</span></span> <span data-ttu-id="a36e2-109">若要避免此问题，可以使用`CallByName`函数运算符来传递新形式的字符串，而无需更改应用程序。</span><span class="sxs-lookup"><span data-stu-id="a36e2-109">To avoid this, you can use the `CallByName` function to pass the new operators as strings, without changing the application.</span></span>  
  
 <span data-ttu-id="a36e2-110">`CallByName`函数允许您使用一个字符串，在运行时指定的属性或方法。</span><span class="sxs-lookup"><span data-stu-id="a36e2-110">The `CallByName` function lets you use a string to specify a property or method at run time.</span></span> <span data-ttu-id="a36e2-111">签名`CallByName`函数如下所示︰</span><span class="sxs-lookup"><span data-stu-id="a36e2-111">The signature for the `CallByName` function looks like this:</span></span>  
  
 <span data-ttu-id="a36e2-112">*Result* = `CallByName`(*Object*, *ProcedureName*, *CallType*, *Arguments*())</span><span class="sxs-lookup"><span data-stu-id="a36e2-112">*Result* = `CallByName`(*Object*, *ProcedureName*, *CallType*, *Arguments*())</span></span>  
  
 <span data-ttu-id="a36e2-113">第一个参数，*对象*，采用您想要对其执行操作的对象的名称。</span><span class="sxs-lookup"><span data-stu-id="a36e2-113">The first argument, *Object*, takes the name of the object you want to act upon.</span></span> <span data-ttu-id="a36e2-114">*过程名*参数采用一个字符串，包含要调用的方法或属性的过程的名称。</span><span class="sxs-lookup"><span data-stu-id="a36e2-114">The *ProcedureName* argument takes a string that contains the name of the method or property procedure to be invoked.</span></span> <span data-ttu-id="a36e2-115">*CallType*参数采用一个常量，它表示要调用过程的类型︰ 一种方法 (`Microsoft.VisualBasic.CallType.Method`)，读取的属性 (`Microsoft.VisualBasic.CallType.Get`)，或一个设置的属性 (`Microsoft.VisualBasic.CallType.Set`)。</span><span class="sxs-lookup"><span data-stu-id="a36e2-115">The *CallType* argument takes a constant that represents the type of procedure to invoke: a method (`Microsoft.VisualBasic.CallType.Method`), a property read (`Microsoft.VisualBasic.CallType.Get`), or a property set (`Microsoft.VisualBasic.CallType.Set`).</span></span> <span data-ttu-id="a36e2-116">*参数*参数，它是可选的采用的类型数组`Object`，其中包含任何参数的过程。</span><span class="sxs-lookup"><span data-stu-id="a36e2-116">The *Arguments* argument, which is optional, takes an array of type `Object` that contains any arguments to the procedure.</span></span>  
  
 <span data-ttu-id="a36e2-117">您可以使用`CallByName`与您当前的解决方案，但它的类是最常用于访问 COM 对象或对象从[!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)]程序集。</span><span class="sxs-lookup"><span data-stu-id="a36e2-117">You can use `CallByName` with classes in your current solution, but it is most often used to access COM objects or objects from [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] assemblies.</span></span>  
  
 <span data-ttu-id="a36e2-118">假设您添加对包含一个名为类的程序集的引用`MathClass`，它具有一个名为的新函数`SquareRoot`，如下面的代码中所示︰</span><span class="sxs-lookup"><span data-stu-id="a36e2-118">Suppose you add a reference to an assembly that contains a class named `MathClass`, which has a new function named `SquareRoot`, as shown in the following code:</span></span>  
  
 <span data-ttu-id="a36e2-119">[!code-vb[VbVbalrOOP #&53;](../../../../visual-basic/misc/codesnippet/VisualBasic/calling-a-property-or-method-using-a-string-name_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="a36e2-119">[!code-vb[VbVbalrOOP#53](../../../../visual-basic/misc/codesnippet/VisualBasic/calling-a-property-or-method-using-a-string-name_1.vb)]</span></span>  
  
 <span data-ttu-id="a36e2-120">您的应用程序可以使用文本框控件来控制将要调用的方法和它的参数。</span><span class="sxs-lookup"><span data-stu-id="a36e2-120">Your application could use text box controls to control which method will be called and its arguments.</span></span> <span data-ttu-id="a36e2-121">例如，如果`TextBox1`包含要计算的表达式和`TextBox2`是用于输入的函数名称，可以使用下面的代码来调用`SquareRoot`函数中的表达式在`TextBox1`:</span><span class="sxs-lookup"><span data-stu-id="a36e2-121">For example, if `TextBox1` contains the expression to be evaluated, and `TextBox2` is used to enter the name of the function, you can use the following code to invoke the `SquareRoot` function on the expression in `TextBox1`:</span></span>  
  
 <span data-ttu-id="a36e2-122">[!code-vb[VbVbalrOOP #&54;](../../../../visual-basic/misc/codesnippet/VisualBasic/calling-a-property-or-method-using-a-string-name_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="a36e2-122">[!code-vb[VbVbalrOOP#54](../../../../visual-basic/misc/codesnippet/VisualBasic/calling-a-property-or-method-using-a-string-name_2.vb)]</span></span>  
  
 <span data-ttu-id="a36e2-123">如果在输入"64"`TextBox1`中的"SquareRoot" `TextBox2`，然后调用`CallMath`过程、 采用的数字的平方根`TextBox1`计算。</span><span class="sxs-lookup"><span data-stu-id="a36e2-123">If you enter "64" in `TextBox1`, "SquareRoot" in `TextBox2`, and then call the `CallMath` procedure, the square root of the number in `TextBox1` is evaluated.</span></span> <span data-ttu-id="a36e2-124">该示例中的代码时，将调用`SquareRoot`函数 （将一个字符串，包含要作为一个必需的参数计算的表达式），并返回以"8" `TextBox1` （64 的平方根）。</span><span class="sxs-lookup"><span data-stu-id="a36e2-124">The code in the example invokes the `SquareRoot` function (which takes a string that contains the expression to be evaluated as a required argument) and returns "8" in `TextBox1` (the square root of 64).</span></span> <span data-ttu-id="a36e2-125">当然，如果用户输入中的无效字符串`TextBox2`，如果该字符串包含而不是一种方法，属性的名称，或者如果该方法有一个额外的必需的参数，发生在运行时错误。</span><span class="sxs-lookup"><span data-stu-id="a36e2-125">Of course, if the user enters an invalid string in `TextBox2`, if the string contains the name of a property instead of a method, or if the method had an additional required argument, a run-time error occurs.</span></span> <span data-ttu-id="a36e2-126">您必须添加可靠的错误处理代码，当您使用`CallByName`以应对预期的这些数据或任何其他错误。</span><span class="sxs-lookup"><span data-stu-id="a36e2-126">You have to add robust error-handling code when you use `CallByName` to anticipate these or any other errors.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a36e2-127">虽然`CallByName`函数可能会很有用，在某些情况下，您必须权衡的性能影响针对其有用性 — 使用`CallByName`以调用过程会稍慢些比后期绑定调用。</span><span class="sxs-lookup"><span data-stu-id="a36e2-127">While the `CallByName` function may be useful in some cases, you must weigh its usefulness against the performance implications — using `CallByName` to invoke a procedure is slightly slower than a late-bound call.</span></span> <span data-ttu-id="a36e2-128">如果所调用的函数被重复调用，例如在循环中，如`CallByName`会产生严重影响性能。</span><span class="sxs-lookup"><span data-stu-id="a36e2-128">If you are invoking a function that is called repeatedly, such as inside a loop, `CallByName` can have a severe effect on performance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a36e2-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a36e2-129">See Also</span></span>  
 <span data-ttu-id="a36e2-130"><xref:Microsoft.VisualBasic.Interaction.CallByName%2A></xref:Microsoft.VisualBasic.Interaction.CallByName%2A></span><span class="sxs-lookup"><span data-stu-id="a36e2-130"><xref:Microsoft.VisualBasic.Interaction.CallByName%2A></span></span>   
<span data-ttu-id="a36e2-131"> [确定对象类型](../../../../visual-basic/programming-guide/language-features/early-late-binding/determining-object-type.md)</span><span class="sxs-lookup"><span data-stu-id="a36e2-131"> [Determining Object Type](../../../../visual-basic/programming-guide/language-features/early-late-binding/determining-object-type.md)</span></span>
