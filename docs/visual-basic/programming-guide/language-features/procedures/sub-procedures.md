---
title: Sub 过程
ms.date: 07/20/2015
helpviewer_keywords:
- Sub procedures [Visual Basic], about Sub procedures
- statement blocks
- Sub procedures [Visual Basic], calling
- procedures [Visual Basic], calling
- Sub procedures [Visual Basic], syntax
- Sub procedures
- procedures [Visual Basic], Sub
- syntax [Visual Basic], Sub procedures
ms.assetid: 6a0a4958-ed0a-4d3d-8d31-0772c82bda58
ms.openlocfilehash: 9ca1d302a0bc8e989e0b2dddf8cce68e89211d57
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163808"
---
# <a name="sub-procedures-visual-basic"></a><span data-ttu-id="440c8-102">Sub 过程（Visual Basic）</span><span class="sxs-lookup"><span data-stu-id="440c8-102">Sub procedures (Visual Basic)</span></span>

<span data-ttu-id="440c8-103">`Sub` 过程是一系列由 `Sub` 和 `End Sub` 语句括起来的 Visual Basic 语句。</span><span class="sxs-lookup"><span data-stu-id="440c8-103">A `Sub` procedure is a series of Visual Basic statements enclosed by the `Sub` and `End Sub` statements.</span></span> <span data-ttu-id="440c8-104">`Sub` 过程执行任务，然后将控制权返回给调用代码，但它不会将值返回给调用代码。</span><span class="sxs-lookup"><span data-stu-id="440c8-104">The `Sub` procedure performs a task and then returns control to the calling code, but it does not return a value to the calling code.</span></span>

<span data-ttu-id="440c8-105">每次调用该过程时，都会执行其语句，从 `Sub` 语句后面的第一个可执行语句开始，到遇到的第一个 `End Sub`、`Exit Sub`或 `Return` 语句结束。</span><span class="sxs-lookup"><span data-stu-id="440c8-105">Each time the procedure is called, its statements are executed, starting with the first executable statement after the `Sub` statement and ending with the first `End Sub`, `Exit Sub`, or `Return` statement encountered.</span></span>

<span data-ttu-id="440c8-106">您可以在模块、类和结构中定义 `Sub` 过程。</span><span class="sxs-lookup"><span data-stu-id="440c8-106">You can define a `Sub` procedure in modules, classes, and structures.</span></span> <span data-ttu-id="440c8-107">默认情况下，它是 `Public`的，这意味着您可以从应用程序中可以访问您定义它的模块、类或结构的任何位置调用它。</span><span class="sxs-lookup"><span data-stu-id="440c8-107">By default, it is `Public`, which means you can call it from anywhere in your application that has access to the module, class, or structure in which you defined it.</span></span> <span data-ttu-id="440c8-108">术语*方法*描述了从其定义模块、类或结构外部访问的 `Sub` 或 `Function` 过程。</span><span class="sxs-lookup"><span data-stu-id="440c8-108">The term *method* describes a `Sub` or `Function` procedure that is accessed from outside its defining module, class, or structure.</span></span> <span data-ttu-id="440c8-109">有关详细信息，请参阅[过程](./index.md)。</span><span class="sxs-lookup"><span data-stu-id="440c8-109">For more information, see [Procedures](./index.md).</span></span>

<span data-ttu-id="440c8-110">`Sub` 过程可以采用由调用代码传递给它的参数，如常量、变量或表达式。</span><span class="sxs-lookup"><span data-stu-id="440c8-110">A `Sub` procedure can take arguments, such as constants, variables, or expressions, which are passed to it by the calling code.</span></span>

## <a name="declaration-syntax"></a><span data-ttu-id="440c8-111">声明语法</span><span class="sxs-lookup"><span data-stu-id="440c8-111">Declaration syntax</span></span>

<span data-ttu-id="440c8-112">声明 `Sub` 过程的语法如下所示：</span><span class="sxs-lookup"><span data-stu-id="440c8-112">The syntax for declaring a `Sub` procedure is as follows:</span></span>

```vb
[modifiers] Sub SubName[(parameterList)]
    ' Statements of the Sub procedure.
End Sub
```

<span data-ttu-id="440c8-113">`modifiers` 可以指定有关重载、重写、共享和隐藏的访问级别和信息。</span><span class="sxs-lookup"><span data-stu-id="440c8-113">The `modifiers` can specify access level and information about overloading, overriding, sharing, and shadowing.</span></span> <span data-ttu-id="440c8-114">有关详细信息，请参阅[Sub 语句](../../../language-reference/statements/sub-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="440c8-114">For more information, see [Sub Statement](../../../language-reference/statements/sub-statement.md).</span></span>

## <a name="parameter-declaration"></a><span data-ttu-id="440c8-115">参数声明</span><span class="sxs-lookup"><span data-stu-id="440c8-115">Parameter declaration</span></span>

<span data-ttu-id="440c8-116">声明每个过程参数的方式与声明变量的方式类似，即指定参数名称和数据类型。</span><span class="sxs-lookup"><span data-stu-id="440c8-116">You declare each procedure parameter similarly to how you declare a variable, specifying the parameter name and data type.</span></span> <span data-ttu-id="440c8-117">还可以指定传递机制，并指定参数是可选的还是参数数组。</span><span class="sxs-lookup"><span data-stu-id="440c8-117">You can also specify the passing mechanism, and whether the parameter is optional or a parameter array.</span></span>

<span data-ttu-id="440c8-118">参数列表中每个参数的语法如下所示：</span><span class="sxs-lookup"><span data-stu-id="440c8-118">The syntax for each parameter in the parameter list is as follows:</span></span>

```vb
[Optional] [ByVal | ByRef] [ParamArray] parameterName As DataType
```

<span data-ttu-id="440c8-119">如果该参数是可选的，则还必须提供默认值作为其声明的一部分。</span><span class="sxs-lookup"><span data-stu-id="440c8-119">If the parameter is optional, you must also supply a default value as part of its declaration.</span></span> <span data-ttu-id="440c8-120">指定默认值的语法如下所示：</span><span class="sxs-lookup"><span data-stu-id="440c8-120">The syntax for specifying a default value is as follows:</span></span>

```vb
Optional [ByVal | ByRef]  parameterName As DataType = defaultValue
```

### <a name="parameters-as-local-variables"></a><span data-ttu-id="440c8-121">参数作为局部变量</span><span class="sxs-lookup"><span data-stu-id="440c8-121">Parameters as local variables</span></span>

<span data-ttu-id="440c8-122">当控件传递给过程时，每个参数都被视为局部变量。</span><span class="sxs-lookup"><span data-stu-id="440c8-122">When control passes to the procedure, each parameter is treated as a local variable.</span></span> <span data-ttu-id="440c8-123">这意味着其生存期与过程的生存期相同，其作用域为整个过程。</span><span class="sxs-lookup"><span data-stu-id="440c8-123">This means that its lifetime is the same as that of the procedure, and its scope is the whole procedure.</span></span>

## <a name="calling-syntax"></a><span data-ttu-id="440c8-124">调用语法</span><span class="sxs-lookup"><span data-stu-id="440c8-124">Calling syntax</span></span>

<span data-ttu-id="440c8-125">使用独立调用语句显式调用 `Sub` 过程。</span><span class="sxs-lookup"><span data-stu-id="440c8-125">You invoke a `Sub` procedure explicitly with a stand-alone calling statement.</span></span> <span data-ttu-id="440c8-126">不能通过在表达式中使用其名称来调用它。</span><span class="sxs-lookup"><span data-stu-id="440c8-126">You cannot call it by using its name in an expression.</span></span> <span data-ttu-id="440c8-127">必须为所有非可选参数提供值，并且必须将参数列表括在括号中。</span><span class="sxs-lookup"><span data-stu-id="440c8-127">You must provide values for all arguments that are not optional, and you must enclose the argument list in parentheses.</span></span> <span data-ttu-id="440c8-128">如果未提供任何参数，则可以选择省略括号。</span><span class="sxs-lookup"><span data-stu-id="440c8-128">If no arguments are supplied, you can optionally omit the parentheses.</span></span> <span data-ttu-id="440c8-129">`Call` 关键字是可选的，但不建议使用。</span><span class="sxs-lookup"><span data-stu-id="440c8-129">The use of the `Call` keyword is optional but not recommended.</span></span>

<span data-ttu-id="440c8-130">调用 `Sub` 过程的语法如下所示：</span><span class="sxs-lookup"><span data-stu-id="440c8-130">The syntax for a call to a `Sub` procedure is as follows:</span></span>

```vb
[Call] SubName[(argumentlist)]
```

<span data-ttu-id="440c8-131">可以从定义它的类的外部调用 `Sub` 方法。</span><span class="sxs-lookup"><span data-stu-id="440c8-131">You can call a `Sub` method from outside the class that defines it.</span></span> <span data-ttu-id="440c8-132">首先，必须使用 `New` 关键字创建类的实例，或调用返回类的实例的方法。</span><span class="sxs-lookup"><span data-stu-id="440c8-132">First, you have to use the `New` keyword to create an instance of the class, or call a method that returns an instance of the class.</span></span> <span data-ttu-id="440c8-133">有关详细信息，请参阅[New 运算符](../../../language-reference/operators/new-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="440c8-133">For more information, see [New Operator](../../../language-reference/operators/new-operator.md).</span></span> <span data-ttu-id="440c8-134">然后，可以使用以下语法对实例对象调用 `Sub` 方法：</span><span class="sxs-lookup"><span data-stu-id="440c8-134">Then, you can use the following syntax to call the `Sub` method on the instance object:</span></span>

```vb
object.MethodName[(argumentList)]
```

### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="440c8-135">声明和调用的插图</span><span class="sxs-lookup"><span data-stu-id="440c8-135">Illustration of declaration and call</span></span>

<span data-ttu-id="440c8-136">以下 `Sub` 过程告知计算机操作员应用程序将要执行的任务，还会显示时间戳。</span><span class="sxs-lookup"><span data-stu-id="440c8-136">The following `Sub` procedure tells the computer operator which task the application is about to perform, and also displays a time stamp.</span></span> <span data-ttu-id="440c8-137">应用程序只会从不同位置调用 `tellOperator`，而不是在每个任务开始时重复此代码。</span><span class="sxs-lookup"><span data-stu-id="440c8-137">Instead of duplicating this code at the start of every task, the application just calls `tellOperator` from various locations.</span></span> <span data-ttu-id="440c8-138">每个调用都在 `task` 参数中传递一个字符串，该字符串标识要启动的任务。</span><span class="sxs-lookup"><span data-stu-id="440c8-138">Each call passes a string in the `task` argument that identifies the task being started.</span></span>

[!code-vb[VbVbcnProcedures#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#2)]

<span data-ttu-id="440c8-139">下面的示例演示对 `tellOperator`的典型调用。</span><span class="sxs-lookup"><span data-stu-id="440c8-139">The following example shows a typical call to `tellOperator`.</span></span>

[!code-vb[VbVbcnProcedures#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#3)]

## <a name="see-also"></a><span data-ttu-id="440c8-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="440c8-140">See also</span></span>

- [<span data-ttu-id="440c8-141">过程</span><span class="sxs-lookup"><span data-stu-id="440c8-141">Procedures</span></span>](./index.md)
- [<span data-ttu-id="440c8-142">Function 过程</span><span class="sxs-lookup"><span data-stu-id="440c8-142">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="440c8-143">属性过程</span><span class="sxs-lookup"><span data-stu-id="440c8-143">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="440c8-144">运算符过程</span><span class="sxs-lookup"><span data-stu-id="440c8-144">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="440c8-145">过程参数和自变量</span><span class="sxs-lookup"><span data-stu-id="440c8-145">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="440c8-146">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="440c8-146">Sub Statement</span></span>](../../../language-reference/statements/sub-statement.md)
- [<span data-ttu-id="440c8-147">如何：调用不返回值的过程</span><span class="sxs-lookup"><span data-stu-id="440c8-147">How to: Call a Procedure that Does Not Return a Value</span></span>](./how-to-call-a-procedure-that-does-not-return-a-value.md)
- [<span data-ttu-id="440c8-148">如何：在 Visual Basic 中调用事件处理程序</span><span class="sxs-lookup"><span data-stu-id="440c8-148">How to: Call an Event Handler in Visual Basic</span></span>](./how-to-call-an-event-handler.md)
