---
title: 使用字符串名调用属性或方法 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- passing operators [Visual Basic]
- strings [Visual Basic], passing new operators as
- objects [Visual Basic], setting properties
- setting properties, object properties at run time
- method calls [Visual Basic], strings
- methods [Visual Basic], calling with string names
- calling methods [Visual Basic], string names
- properties [Visual Basic], setting at run time
- CallByName function
ms.assetid: 79a7b8b4-b8c7-4ad8-aca8-12a9a2b32f03
ms.openlocfilehash: 76be426049489bb58e50878822c03fa5cd5cca8e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649222"
---
# <a name="calling-a-property-or-method-using-a-string-name-visual-basic"></a><span data-ttu-id="6a3d8-102">使用字符串名调用属性或方法 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6a3d8-102">Calling a Property or Method Using a String Name (Visual Basic)</span></span>
<span data-ttu-id="6a3d8-103">在大多数情况下，可以在设计时发现的属性和方法的对象，并编写代码来处理它们。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-103">In most cases, you can discover the properties and methods of an object at design time, and write code to handle them.</span></span> <span data-ttu-id="6a3d8-104">但是，在某些情况下你可能事先不知道有关对象的属性和方法，或者您可能只想启用最终用户可以指定属性或在运行时执行方法的灵活性。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-104">However, in some cases you may not know about an object's properties and methods in advance, or you may just want the flexibility of enabling an end user to specify properties or execute methods at run time.</span></span>  
  
## <a name="callbyname-function"></a><span data-ttu-id="6a3d8-105">CallByName 函数</span><span class="sxs-lookup"><span data-stu-id="6a3d8-105">CallByName Function</span></span>  
 <span data-ttu-id="6a3d8-106">例如，考虑通过将运算符传递给 COM 组件的用户输入的表达式的计算结果的客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-106">Consider, for example, a client application that evaluates expressions entered by the user by passing an operator to a COM component.</span></span> <span data-ttu-id="6a3d8-107">假设你要不断地将新的函数添加到需要新的运算符的组件。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-107">Suppose you are constantly adding new functions to the component that require new operators.</span></span> <span data-ttu-id="6a3d8-108">当你使用标准的对象访问技术时，你必须重新编译并重新分发客户端应用程序，可以使用新的运算符之前。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-108">When you use standard object access techniques, you must recompile and redistribute the client application before it could use the new operators.</span></span> <span data-ttu-id="6a3d8-109">若要避免此问题，可以使用`CallByName`函数新的运算符作为字符串来传递，而无需更改应用程序。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-109">To avoid this, you can use the `CallByName` function to pass the new operators as strings, without changing the application.</span></span>  
  
 <span data-ttu-id="6a3d8-110">`CallByName`函数，你可以使用一个字符串以在运行时指定的属性或方法。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-110">The `CallByName` function lets you use a string to specify a property or method at run time.</span></span> <span data-ttu-id="6a3d8-111">签名`CallByName`函数如下所示：</span><span class="sxs-lookup"><span data-stu-id="6a3d8-111">The signature for the `CallByName` function looks like this:</span></span>  
  
 <span data-ttu-id="6a3d8-112">*结果* = `CallByName`(*对象*，*过程名称*， *CallType*，*参数*（)）</span><span class="sxs-lookup"><span data-stu-id="6a3d8-112">*Result* = `CallByName`(*Object*, *ProcedureName*, *CallType*, *Arguments*())</span></span>  
  
 <span data-ttu-id="6a3d8-113">第一个参数，*对象*，将你想要执行操作的对象的名称。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-113">The first argument, *Object*, takes the name of the object you want to act upon.</span></span> <span data-ttu-id="6a3d8-114">*过程名称*参数接受包含要调用的方法或属性的过程的名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-114">The *ProcedureName* argument takes a string that contains the name of the method or property procedure to be invoked.</span></span> <span data-ttu-id="6a3d8-115">*CallType*参数采用一个常数，用于表示的过程调用的类型： 一种方法 (`Microsoft.VisualBasic.CallType.Method`)，读取的属性 (`Microsoft.VisualBasic.CallType.Get`)，或设置的属性 (`Microsoft.VisualBasic.CallType.Set`)。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-115">The *CallType* argument takes a constant that represents the type of procedure to invoke: a method (`Microsoft.VisualBasic.CallType.Method`), a property read (`Microsoft.VisualBasic.CallType.Get`), or a property set (`Microsoft.VisualBasic.CallType.Set`).</span></span> <span data-ttu-id="6a3d8-116">*参数*自变量，这是可选的采用的类型数组`Object`包含到过程的任何自变量。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-116">The *Arguments* argument, which is optional, takes an array of type `Object` that contains any arguments to the procedure.</span></span>  
  
 <span data-ttu-id="6a3d8-117">你可以使用`CallByName`中当前解决方案，但它的类是最常用于访问 COM 对象或对象从[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]程序集。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-117">You can use `CallByName` with classes in your current solution, but it is most often used to access COM objects or objects from [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] assemblies.</span></span>  
  
 <span data-ttu-id="6a3d8-118">假设你添加对该程序集包含一个名为类的引用`MathClass`，它具有一个名为的新函数`SquareRoot`，如下面的代码中所示：</span><span class="sxs-lookup"><span data-stu-id="6a3d8-118">Suppose you add a reference to an assembly that contains a class named `MathClass`, which has a new function named `SquareRoot`, as shown in the following code:</span></span>  
  
 [!code-vb[VbVbalrOOP#53](../../../../visual-basic/misc/codesnippet/VisualBasic/calling-a-property-or-method-using-a-string-name_1.vb)]  
  
 <span data-ttu-id="6a3d8-119">你的应用程序可以使用文本框控件对控件将调用哪个方法以及其自变量。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-119">Your application could use text box controls to control which method will be called and its arguments.</span></span> <span data-ttu-id="6a3d8-120">例如，如果`TextBox1`包含要计算的表达式和`TextBox2`是用于输入函数的名称，可以使用下面的代码来调用`SquareRoot`函数中的表达式上`TextBox1`:</span><span class="sxs-lookup"><span data-stu-id="6a3d8-120">For example, if `TextBox1` contains the expression to be evaluated, and `TextBox2` is used to enter the name of the function, you can use the following code to invoke the `SquareRoot` function on the expression in `TextBox1`:</span></span>  
  
 [!code-vb[VbVbalrOOP#54](../../../../visual-basic/misc/codesnippet/VisualBasic/calling-a-property-or-method-using-a-string-name_2.vb)]  
  
 <span data-ttu-id="6a3d8-121">如果在输入"64"`TextBox1`中的"SquareRoot" `TextBox2`，然后调用`CallMath`过程、 中的数字的平方根`TextBox1`计算。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-121">If you enter "64" in `TextBox1`, "SquareRoot" in `TextBox2`, and then call the `CallMath` procedure, the square root of the number in `TextBox1` is evaluated.</span></span> <span data-ttu-id="6a3d8-122">示例中的代码时，将调用`SquareRoot`函数 （将包含要作为一个必需的参数计算的表达式的字符串），并返回"8"中`TextBox1`（64 的平方根）。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-122">The code in the example invokes the `SquareRoot` function (which takes a string that contains the expression to be evaluated as a required argument) and returns "8" in `TextBox1` (the square root of 64).</span></span> <span data-ttu-id="6a3d8-123">当然，如果用户输入中的无效字符串`TextBox2`，如果字符串包含而不是一种方法，属性的名称，或如果该方法具有一个其他的必需自变量，会发生运行时错误。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-123">Of course, if the user enters an invalid string in `TextBox2`, if the string contains the name of a property instead of a method, or if the method had an additional required argument, a run-time error occurs.</span></span> <span data-ttu-id="6a3d8-124">你必须添加可靠的错误处理代码，当你使用`CallByName`以应对预期的这些文件路径或任何其他错误。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-124">You have to add robust error-handling code when you use `CallByName` to anticipate these or any other errors.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6a3d8-125">虽然`CallByName`函数可能在某些情况下有用，您必须权衡的性能影响对其用途-使用`CallByName`来调用过程是比后期绑定调用稍慢。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-125">While the `CallByName` function may be useful in some cases, you must weigh its usefulness against the performance implications — using `CallByName` to invoke a procedure is slightly slower than a late-bound call.</span></span> <span data-ttu-id="6a3d8-126">如果正在调用的函数，重复调用，如循环内,`CallByName`会对性能产生严重。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-126">If you are invoking a function that is called repeatedly, such as inside a loop, `CallByName` can have a severe effect on performance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a3d8-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="6a3d8-127">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Interaction.CallByName%2A>  
 [<span data-ttu-id="6a3d8-128">确定对象类型</span><span class="sxs-lookup"><span data-stu-id="6a3d8-128">Determining Object Type</span></span>](../../../../visual-basic/programming-guide/language-features/early-late-binding/determining-object-type.md)
