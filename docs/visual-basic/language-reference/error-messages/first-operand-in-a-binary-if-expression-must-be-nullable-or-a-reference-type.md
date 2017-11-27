---
title: "第一个操作数中二进制 &#39; 如果 &#39;表达式必须是可以为 null 或类型的引用"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc33107
- vbc33107
helpviewer_keywords: BC33107
ms.assetid: 493c8899-3f6b-4471-8eb6-9284e8492768
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f66b110c02076120c55a3bff28c3d7614bf8be26
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="first-operand-in-a-binary-39if39-expression-must-be-nullable-or-a-reference-type"></a><span data-ttu-id="ba99b-102">第一个操作数中二进制 &#39; 如果 &#39;表达式必须是可以为 null 或类型的引用</span><span class="sxs-lookup"><span data-stu-id="ba99b-102">First operand in a binary &#39;If&#39; expression must be nullable or a reference type</span></span>
<span data-ttu-id="ba99b-103">`If`表达式可以采用两个或三个自变量。</span><span class="sxs-lookup"><span data-stu-id="ba99b-103">An `If` expression can take either two or three arguments.</span></span> <span data-ttu-id="ba99b-104">当你发送只有两个自变量时，第一个参数必须是引用类型或可以为 null 的类型。</span><span class="sxs-lookup"><span data-stu-id="ba99b-104">When you send only two arguments, the first argument must be a reference type or a nullable type.</span></span> <span data-ttu-id="ba99b-105">如果第一个自变量的计算结果为任何内容而不是`Nothing`，返回其值。</span><span class="sxs-lookup"><span data-stu-id="ba99b-105">If the first argument evaluates to anything other than `Nothing`, its value is returned.</span></span> <span data-ttu-id="ba99b-106">如果第一个自变量的计算结果为`Nothing`，计算第二个参数并将其返回。</span><span class="sxs-lookup"><span data-stu-id="ba99b-106">If the first argument evaluates to `Nothing`, the second argument is evaluated and returned.</span></span>  
  
 <span data-ttu-id="ba99b-107">例如，下面的代码包含两个`If`表达式、 另一个具有三个参数和另一个具有两个参数。</span><span class="sxs-lookup"><span data-stu-id="ba99b-107">For example, the following code contains two `If` expressions, one with three arguments and one with two arguments.</span></span> <span data-ttu-id="ba99b-108">表达式计算并返回相同的值。</span><span class="sxs-lookup"><span data-stu-id="ba99b-108">The expressions calculate and return the same value.</span></span>  
  
```vb  
' firstChoice is a nullable value type.  
Dim firstChoice? As Integer = Nothing  
Dim secondChoice As Integer = 1128  
' If expression with three arguments.  
Console.WriteLine(If(firstChoice IsNot Nothing, firstChoice, secondChoice))  
' If expression with two arguments.  
Console.WriteLine(If(firstChoice, secondChoice))  
```  
  
 <span data-ttu-id="ba99b-109">以下表达式会导致此错误：</span><span class="sxs-lookup"><span data-stu-id="ba99b-109">The following expressions cause this error:</span></span>  
  
```vb  
Dim choice1 = 4  
Dim choice2 = 5  
Dim booleanVar = True  
  
' Not valid.  
'Console.WriteLine(If(choice1 < choice2, 1))  
' Not valid.  
'Console.WriteLine(If(booleanVar, "Test returns True."))  
```  
  
 <span data-ttu-id="ba99b-110">**错误 ID:** BC33107</span><span class="sxs-lookup"><span data-stu-id="ba99b-110">**Error ID:** BC33107</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ba99b-111">更正此错误</span><span class="sxs-lookup"><span data-stu-id="ba99b-111">To correct this error</span></span>  
  
-   <span data-ttu-id="ba99b-112">如果你不能更改代码，以便第一个参数是可以为 null 的类型或引用类型，请考虑将转换为三个参数`If`表达式，或`If...Then...Else`语句。</span><span class="sxs-lookup"><span data-stu-id="ba99b-112">If you cannot change the code so that the first argument is a nullable type or reference type, consider converting to a three-argument `If` expression, or to an `If...Then...Else` statement.</span></span>  
  
```vb  
Console.WriteLine(If(choice1 < choice2, 1, 2))  
Console.WriteLine(If(booleanVar, "Test returns True.", "Test returns False."))  
```  
  
## <a name="see-also"></a><span data-ttu-id="ba99b-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ba99b-113">See Also</span></span>  
 [<span data-ttu-id="ba99b-114">If 运算符</span><span class="sxs-lookup"><span data-stu-id="ba99b-114">If Operator</span></span>](../../../visual-basic/language-reference/operators/if-operator.md)  
 [<span data-ttu-id="ba99b-115">If...Then...Else 语句</span><span class="sxs-lookup"><span data-stu-id="ba99b-115">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)  
 [<span data-ttu-id="ba99b-116">可以为 null 的值类型</span><span class="sxs-lookup"><span data-stu-id="ba99b-116">Nullable Value Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
