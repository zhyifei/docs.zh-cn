---
title: "Lambda 表达式中使用迭代变量可能会产生意外的结果 |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42324
- bc42324
dev_langs:
- VB
helpviewer_keywords:
- BC42324
ms.assetid: b5c2c4bd-3b2a-4a73-aaeb-55728eb03b68
caps.latest.revision: 8
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
ms.openlocfilehash: 1c2e0e322ff46b9e215a169cd4cf3805c7dc3943
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="using-the-iteration-variable-in-a-lambda-expression-may-have-unexpected-results"></a><span data-ttu-id="b70a9-102">在 lambda 表达式中使用迭代变量可能会产生意外的结果</span><span class="sxs-lookup"><span data-stu-id="b70a9-102">Using the iteration variable in a lambda expression may have unexpected results</span></span>
<span data-ttu-id="b70a9-103">在 lambda 表达式中使用迭代变量可能会产生意外的结果。</span><span class="sxs-lookup"><span data-stu-id="b70a9-103">Using the iteration variable in a lambda expression may have unexpected results.</span></span> <span data-ttu-id="b70a9-104">相反，创建一个在循环内的局部变量，并将其分配的迭代变量的值。</span><span class="sxs-lookup"><span data-stu-id="b70a9-104">Instead, create a local variable within the loop and assign it the value of the iteration variable.</span></span>  
  
 <span data-ttu-id="b70a9-105">在循环内声明的 lambda 表达式中使用循环迭代变量时，会出现此警告。</span><span class="sxs-lookup"><span data-stu-id="b70a9-105">This warning appears when you use a loop iteration variable in a lambda expression that is declared inside the loop.</span></span> <span data-ttu-id="b70a9-106">例如，下面的示例会导致出现警告。</span><span class="sxs-lookup"><span data-stu-id="b70a9-106">For example, the following example causes the warning to appear.</span></span>  
  
```vb  
For i As Integer = 1 To 10  
    ' The warning is given for the use of i.  
    Dim exampleFunc As Func(Of Integer) = Function() i  
Next  
```  
  
 <span data-ttu-id="b70a9-107">下面的示例演示可能出现的意外的结果。</span><span class="sxs-lookup"><span data-stu-id="b70a9-107">The following example shows the unexpected results that might occur.</span></span>  
  
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
  
 <span data-ttu-id="b70a9-108">`For`循环创建 lambda 表达式的数组，其中每个返回的循环迭代变量值`i`。</span><span class="sxs-lookup"><span data-stu-id="b70a9-108">The `For` loop creates an array of lambda expressions, each of which returns the value of the loop iteration variable `i`.</span></span> <span data-ttu-id="b70a9-109">Lambda 表达式中的评估时`For Each`循环中，您可能希望看到 0、 1、 2、 3 和 4 显示的连续值`i`中`For`循环。</span><span class="sxs-lookup"><span data-stu-id="b70a9-109">When the lambda expressions are evaluated in the `For Each` loop, you might expect to see 0, 1, 2, 3, and 4 displayed, the successive values of `i` in the `For` loop.</span></span> <span data-ttu-id="b70a9-110">相反，您看到的最终值`i`显示了五次︰</span><span class="sxs-lookup"><span data-stu-id="b70a9-110">Instead, you see the final value of `i` displayed five times:</span></span>  
  
 `5`  
  
 `5`  
  
 `5`  
  
 `5`  
  
 `5`  
  
 <span data-ttu-id="b70a9-111">默认情况下，此消息是一个警告。</span><span class="sxs-lookup"><span data-stu-id="b70a9-111">By default, this message is a warning.</span></span> <span data-ttu-id="b70a9-112">有关隐藏警告或将警告视为错误的详细信息，请参阅[在 Visual Basic 中配置警告](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic)。</span><span class="sxs-lookup"><span data-stu-id="b70a9-112">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="b70a9-113">**错误 ID:** BC42324</span><span class="sxs-lookup"><span data-stu-id="b70a9-113">**Error ID:** BC42324</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b70a9-114">更正此错误</span><span class="sxs-lookup"><span data-stu-id="b70a9-114">To correct this error</span></span>  
  
-   <span data-ttu-id="b70a9-115">将迭代变量的值分配给本地变量，并使用 lambda 表达式中的本地变量。</span><span class="sxs-lookup"><span data-stu-id="b70a9-115">Assign the value of the iteration variable to a local variable, and use the local variable in the lambda expression.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b70a9-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b70a9-116">See Also</span></span>  
 [<span data-ttu-id="b70a9-117">Lambda 表达式</span><span class="sxs-lookup"><span data-stu-id="b70a9-117">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
