---
title: Lambda 表达式不是有效的第一个表达式中&#39;Select Case&#39;语句
ms.date: 07/20/2015
f1_keywords:
- bc36635
- vbc36635
helpviewer_keywords:
- BC36635
ms.assetid: 74609979-9c03-4864-bbce-f588aa2e0917
ms.openlocfilehash: afefa821f9695dbbfe2a96aee5afd3171ae5b1db
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54700216"
---
# <a name="lambda-expressions-are-not-valid-in-the-first-expression-of-a-39select-case39-statement"></a><span data-ttu-id="1cbe4-102">Lambda 表达式不是有效的第一个表达式中&#39;Select Case&#39;语句</span><span class="sxs-lookup"><span data-stu-id="1cbe4-102">Lambda expressions are not valid in the first expression of a &#39;Select Case&#39; statement</span></span>
<span data-ttu-id="1cbe4-103">不能使用 lambda 表达式中的测试表达式`Select Case`语句。</span><span class="sxs-lookup"><span data-stu-id="1cbe4-103">You cannot use a lambda expression for the test expression in a `Select Case` statement.</span></span> <span data-ttu-id="1cbe4-104">返回的函数，测试表达式的 lambda 表达式定义`Select Case`语句必须是基本数据类型。</span><span class="sxs-lookup"><span data-stu-id="1cbe4-104">Lambda expression definitions return functions, and the test expression of a `Select Case` statement must be an elementary data type.</span></span>  
  
 <span data-ttu-id="1cbe4-105">下面的代码会导致此错误：</span><span class="sxs-lookup"><span data-stu-id="1cbe4-105">The following code causes this error:</span></span>  
  
```vb  
' Select Case (Function(arg) arg Is Nothing)  
    ' List of the cases.  
' End Select  
```  
  
 <span data-ttu-id="1cbe4-106">**错误 ID:** BC36635</span><span class="sxs-lookup"><span data-stu-id="1cbe4-106">**Error ID:** BC36635</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1cbe4-107">更正此错误</span><span class="sxs-lookup"><span data-stu-id="1cbe4-107">To correct this error</span></span>  
  
-   <span data-ttu-id="1cbe4-108">检查你的代码以确定是否可以使用其他条件构造，例如 `If...Then...Else` 语句。</span><span class="sxs-lookup"><span data-stu-id="1cbe4-108">Examine your code to determine whether a different conditional construction, such as an `If...Then...Else` statement, would work for you.</span></span>  
  
-   <span data-ttu-id="1cbe4-109">您可能打算调用该函数，如下面的代码中所示：</span><span class="sxs-lookup"><span data-stu-id="1cbe4-109">You may have intended to call the function, as shown in the following code:</span></span>  
  
```vb  
Dim num? As Integer  
Select Case ((Function(arg? As Integer) arg Is Nothing)(num))  
    ' List of the cases  
End Select  
```  
  
## <a name="see-also"></a><span data-ttu-id="1cbe4-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="1cbe4-110">See also</span></span>
- [<span data-ttu-id="1cbe4-111">Lambda 表达式</span><span class="sxs-lookup"><span data-stu-id="1cbe4-111">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
- [<span data-ttu-id="1cbe4-112">If...Then...Else 语句</span><span class="sxs-lookup"><span data-stu-id="1cbe4-112">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [<span data-ttu-id="1cbe4-113">Select...Case 语句</span><span class="sxs-lookup"><span data-stu-id="1cbe4-113">Select...Case Statement</span></span>](../../../visual-basic/language-reference/statements/select-case-statement.md)
