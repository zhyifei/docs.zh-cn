---
title: 变量&#39; &lt;variablename&gt; &#39;隐藏封闭块中的变量
ms.date: 07/20/2015
f1_keywords:
- vbc30616
- bc30616
helpviewer_keywords:
- BC30616
ms.assetid: e7658ebc-da45-451b-a409-a0f8915f0beb
ms.openlocfilehash: 23ec659535b71ee9af189f5c4fec0dec2bb1cd8f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54719425"
---
# <a name="variable-39ltvariablenamegt39-hides-a-variable-in-an-enclosing-block"></a><span data-ttu-id="6ecb6-102">变量&#39; &lt;variablename&gt; &#39;隐藏封闭块中的变量</span><span class="sxs-lookup"><span data-stu-id="6ecb6-102">Variable &#39;&lt;variablename&gt;&#39; hides a variable in an enclosing block</span></span>
<span data-ttu-id="6ecb6-103">块中包含的变量具有与另一个本地变量相同的名称。</span><span class="sxs-lookup"><span data-stu-id="6ecb6-103">A variable enclosed in a block has the same name as another local variable.</span></span>  
  
 <span data-ttu-id="6ecb6-104">**错误 ID:** BC30616</span><span class="sxs-lookup"><span data-stu-id="6ecb6-104">**Error ID:** BC30616</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="6ecb6-105">更正此错误</span><span class="sxs-lookup"><span data-stu-id="6ecb6-105">To correct this error</span></span>  
  
-   <span data-ttu-id="6ecb6-106">重命名封闭块中的变量，以便它不与任何其他本地变量相同。</span><span class="sxs-lookup"><span data-stu-id="6ecb6-106">Rename the variable in the enclosed block so that it is not the same as any other local variables.</span></span> <span data-ttu-id="6ecb6-107">例如：</span><span class="sxs-lookup"><span data-stu-id="6ecb6-107">For example:</span></span>  
  
    ```  
    Dim a, b, x As Integer  
    If a = b Then  
       Dim y As Integer = 20 ' Uniquely named block variable.  
    End If  
    ```  
  
-   <span data-ttu-id="6ecb6-108">此错误的常见原因是使用`Catch e As Exception`的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="6ecb6-108">A common cause for this error is the use of `Catch e As Exception` inside an event handler.</span></span> <span data-ttu-id="6ecb6-109">如果是这样，命名`Catch`块变量`ex`而非`e`。</span><span class="sxs-lookup"><span data-stu-id="6ecb6-109">If this is the case, name the `Catch` block variable `ex` rather than `e`.</span></span>  
  
-   <span data-ttu-id="6ecb6-110">此错误的另一个常见原因是尝试访问中声明的局部变量`Try`块中单独`Catch`块。</span><span class="sxs-lookup"><span data-stu-id="6ecb6-110">Another common source of this error is an attempt to access a local variable declared within a `Try` block in a separate `Catch` block.</span></span> <span data-ttu-id="6ecb6-111">若要更正此问题，声明外部变量`Try...Catch...Finally`结构。</span><span class="sxs-lookup"><span data-stu-id="6ecb6-111">To correct this, declare the variable outside the `Try...Catch...Finally` structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ecb6-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="6ecb6-112">See also</span></span>
- [<span data-ttu-id="6ecb6-113">Try...Catch...Finally 语句</span><span class="sxs-lookup"><span data-stu-id="6ecb6-113">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="6ecb6-114">变量声明</span><span class="sxs-lookup"><span data-stu-id="6ecb6-114">Variable Declaration</span></span>](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
