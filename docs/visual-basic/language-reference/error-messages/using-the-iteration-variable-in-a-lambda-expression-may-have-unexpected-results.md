---
title: 在 lambda 表达式中使用迭代变量可能会产生意外的结果
ms.date: 07/20/2015
f1_keywords:
- vbc42324
- bc42324
helpviewer_keywords:
- BC42324
ms.assetid: b5c2c4bd-3b2a-4a73-aaeb-55728eb03b68
ms.openlocfilehash: 618fc88a2ca92ec911a3fbd82de580403d924430
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "58841090"
---
# <a name="using-the-iteration-variable-in-a-lambda-expression-may-have-unexpected-results"></a><span data-ttu-id="dee0e-102">在 lambda 表达式中使用迭代变量可能会产生意外的结果</span><span class="sxs-lookup"><span data-stu-id="dee0e-102">Using the iteration variable in a lambda expression may have unexpected results</span></span>
<span data-ttu-id="dee0e-103">Lambda 表达式中使用迭代变量可能会产生意外的结果。</span><span class="sxs-lookup"><span data-stu-id="dee0e-103">Using the iteration variable in a lambda expression may have unexpected results.</span></span> <span data-ttu-id="dee0e-104">相反，创建一个本地变量在循环内的，并将其分配的迭代变量的值。</span><span class="sxs-lookup"><span data-stu-id="dee0e-104">Instead, create a local variable within the loop and assign it the value of the iteration variable.</span></span>  
  
 <span data-ttu-id="dee0e-105">在循环中声明的 lambda 表达式中使用循环迭代变量时，会出现此警告。</span><span class="sxs-lookup"><span data-stu-id="dee0e-105">This warning appears when you use a loop iteration variable in a lambda expression that is declared inside the loop.</span></span> <span data-ttu-id="dee0e-106">例如，下面的示例会导致出现的警告。</span><span class="sxs-lookup"><span data-stu-id="dee0e-106">For example, the following example causes the warning to appear.</span></span>  
  
```vb  
For i As Integer = 1 To 10  
    ' The warning is given for the use of i.  
    Dim exampleFunc As Func(Of Integer) = Function() i  
Next  
```  
  
 <span data-ttu-id="dee0e-107">下面的示例显示了可能会出现意外的结果。</span><span class="sxs-lookup"><span data-stu-id="dee0e-107">The following example shows the unexpected results that might occur.</span></span>  
  
```vb  
Module Module1  
    Sub Main()  
        Dim array1 As Func(Of Integer)() = New Func(Of Integer)(4) {}  
  
        For i As Integer = 0 To 4  
            array1(i) = Function() i  
        Next  
  
        For Each funcElement In array1  
            System.Console.WriteLine(funcElement())  
        Next  
  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="dee0e-108">`For`循环创建的 lambda 表达式，其中每个循环迭代变量的值将返回一个数组`i`。</span><span class="sxs-lookup"><span data-stu-id="dee0e-108">The `For` loop creates an array of lambda expressions, each of which returns the value of the loop iteration variable `i`.</span></span> <span data-ttu-id="dee0e-109">当 lambda 表达式的计算`For Each`循环中，你可能希望看到 0、 1、 2、 3 和 4 显示，连续的值`i`中`For`循环。</span><span class="sxs-lookup"><span data-stu-id="dee0e-109">When the lambda expressions are evaluated in the `For Each` loop, you might expect to see 0, 1, 2, 3, and 4 displayed, the successive values of `i` in the `For` loop.</span></span> <span data-ttu-id="dee0e-110">相反，您看到的最终值`i`显示了五次：</span><span class="sxs-lookup"><span data-stu-id="dee0e-110">Instead, you see the final value of `i` displayed five times:</span></span>  
  
 `5`  
  
 `5`  
  
 `5`  
  
 `5`  
  
 `5`  
  
 <span data-ttu-id="dee0e-111">默认情况下，此消息是一个警告。</span><span class="sxs-lookup"><span data-stu-id="dee0e-111">By default, this message is a warning.</span></span> <span data-ttu-id="dee0e-112">若要深入了解如何隐藏警告或将警告视为错误，请参阅 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)。</span><span class="sxs-lookup"><span data-stu-id="dee0e-112">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="dee0e-113">**错误 ID:** BC42324</span><span class="sxs-lookup"><span data-stu-id="dee0e-113">**Error ID:** BC42324</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="dee0e-114">更正此错误</span><span class="sxs-lookup"><span data-stu-id="dee0e-114">To correct this error</span></span>  
  
-   <span data-ttu-id="dee0e-115">将迭代变量的值分配给本地变量，并在 lambda 表达式中使用本地变量。</span><span class="sxs-lookup"><span data-stu-id="dee0e-115">Assign the value of the iteration variable to a local variable, and use the local variable in the lambda expression.</span></span>  
  
```vb  
Module Module1  
    Sub Main()  
        Dim array1 As Func(Of Integer)() = New Func(Of Integer)(4) {}  
  
        For i As Integer = 0 To 4  
            Dim j = i  
            array1(i) = Function() j  
        Next  
  
        For Each funcElement In array1  
            System.Console.WriteLine(funcElement())  
        Next  
  
    End Sub  
End Module  
```  
  
## <a name="see-also"></a><span data-ttu-id="dee0e-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="dee0e-116">See also</span></span>

- [<span data-ttu-id="dee0e-117">Lambda 表达式</span><span class="sxs-lookup"><span data-stu-id="dee0e-117">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
