---
title: "Lambda 表达式不是有效的第一个表达式中 &#39;选择用例 &#39;语句"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc36635
- vbc36635
helpviewer_keywords: BC36635
ms.assetid: 74609979-9c03-4864-bbce-f588aa2e0917
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e91401d6891d4e38014bb716a337560885cf73a2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="lambda-expressions-are-not-valid-in-the-first-expression-of-a-39select-case39-statement"></a><span data-ttu-id="dc2f2-102">Lambda 表达式不是有效的第一个表达式中 &#39;选择用例 &#39;语句</span><span class="sxs-lookup"><span data-stu-id="dc2f2-102">Lambda expressions are not valid in the first expression of a &#39;Select Case&#39; statement</span></span>
<span data-ttu-id="dc2f2-103">不能使用 lambda 表达式中的测试表达式`Select Case`语句。</span><span class="sxs-lookup"><span data-stu-id="dc2f2-103">You cannot use a lambda expression for the test expression in a `Select Case` statement.</span></span> <span data-ttu-id="dc2f2-104">Lambda 表达式定义返回函数和的测试表达式`Select Case`语句必须是基本数据类型。</span><span class="sxs-lookup"><span data-stu-id="dc2f2-104">Lambda expression definitions return functions, and the test expression of a `Select Case` statement must be an elementary data type.</span></span>  
  
 <span data-ttu-id="dc2f2-105">下面的代码会导致此错误：</span><span class="sxs-lookup"><span data-stu-id="dc2f2-105">The following code causes this error:</span></span>  
  
```vb  
' Select Case (Function(arg) arg Is Nothing)  
    ' List of the cases.  
' End Select  
```  
  
 <span data-ttu-id="dc2f2-106">**错误 ID:** BC36635</span><span class="sxs-lookup"><span data-stu-id="dc2f2-106">**Error ID:** BC36635</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="dc2f2-107">更正此错误</span><span class="sxs-lookup"><span data-stu-id="dc2f2-107">To correct this error</span></span>  
  
-   <span data-ttu-id="dc2f2-108">检查你的代码以确定是否可以使用其他条件构造，例如 `If...Then...Else` 语句。</span><span class="sxs-lookup"><span data-stu-id="dc2f2-108">Examine your code to determine whether a different conditional construction, such as an `If...Then...Else` statement, would work for you.</span></span>  
  
-   <span data-ttu-id="dc2f2-109">你可能具有想要调用函数，如下面的代码中所示：</span><span class="sxs-lookup"><span data-stu-id="dc2f2-109">You may have intended to call the function, as shown in the following code:</span></span>  
  
```vb  
Dim num? As Integer  
Select Case ((Function(arg? As Integer) arg Is Nothing)(num))  
    ' List of the cases  
End Select  
```  
  
## <a name="see-also"></a><span data-ttu-id="dc2f2-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dc2f2-110">See Also</span></span>  
 [<span data-ttu-id="dc2f2-111">Lambda 表达式</span><span class="sxs-lookup"><span data-stu-id="dc2f2-111">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)  
 [<span data-ttu-id="dc2f2-112">If...Then...Else 语句</span><span class="sxs-lookup"><span data-stu-id="dc2f2-112">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)  
 [<span data-ttu-id="dc2f2-113">Select...Case 语句</span><span class="sxs-lookup"><span data-stu-id="dc2f2-113">Select...Case Statement</span></span>](../../../visual-basic/language-reference/statements/select-case-statement.md)
