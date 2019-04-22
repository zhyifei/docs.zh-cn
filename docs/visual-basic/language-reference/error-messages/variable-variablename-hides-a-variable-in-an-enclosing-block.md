---
title: 变量“<variablename>”在封闭块中隐藏变量
ms.date: 07/20/2015
f1_keywords:
- vbc30616
- bc30616
helpviewer_keywords:
- BC30616
ms.assetid: e7658ebc-da45-451b-a409-a0f8915f0beb
ms.openlocfilehash: 15c35cbb829bec782771b584ea25b111b81b5e1f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "58827128"
---
# <a name="variable-variablename-hides-a-variable-in-an-enclosing-block"></a><span data-ttu-id="cb888-102">变量\<变量名 > 隐藏封闭块中的变量</span><span class="sxs-lookup"><span data-stu-id="cb888-102">Variable '\<variablename>' hides a variable in an enclosing block</span></span>
<span data-ttu-id="cb888-103">块中包含的变量具有与另一个本地变量相同的名称。</span><span class="sxs-lookup"><span data-stu-id="cb888-103">A variable enclosed in a block has the same name as another local variable.</span></span>  
  
 <span data-ttu-id="cb888-104">**错误 ID:** BC30616</span><span class="sxs-lookup"><span data-stu-id="cb888-104">**Error ID:** BC30616</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="cb888-105">更正此错误</span><span class="sxs-lookup"><span data-stu-id="cb888-105">To correct this error</span></span>  
  
-   <span data-ttu-id="cb888-106">重命名封闭块中的变量，以便它不与任何其他本地变量相同。</span><span class="sxs-lookup"><span data-stu-id="cb888-106">Rename the variable in the enclosed block so that it is not the same as any other local variables.</span></span> <span data-ttu-id="cb888-107">例如：</span><span class="sxs-lookup"><span data-stu-id="cb888-107">For example:</span></span>  
  
    ```  
    Dim a, b, x As Integer  
    If a = b Then  
       Dim y As Integer = 20 ' Uniquely named block variable.  
    End If  
    ```  
  
-   <span data-ttu-id="cb888-108">此错误的常见原因是使用`Catch e As Exception`的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="cb888-108">A common cause for this error is the use of `Catch e As Exception` inside an event handler.</span></span> <span data-ttu-id="cb888-109">如果是这样，命名`Catch`块变量`ex`而非`e`。</span><span class="sxs-lookup"><span data-stu-id="cb888-109">If this is the case, name the `Catch` block variable `ex` rather than `e`.</span></span>  
  
-   <span data-ttu-id="cb888-110">此错误的另一个常见原因是尝试访问中声明的局部变量`Try`块中单独`Catch`块。</span><span class="sxs-lookup"><span data-stu-id="cb888-110">Another common source of this error is an attempt to access a local variable declared within a `Try` block in a separate `Catch` block.</span></span> <span data-ttu-id="cb888-111">若要更正此问题，声明外部变量`Try...Catch...Finally`结构。</span><span class="sxs-lookup"><span data-stu-id="cb888-111">To correct this, declare the variable outside the `Try...Catch...Finally` structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb888-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="cb888-112">See also</span></span>

- [<span data-ttu-id="cb888-113">Try...Catch...Finally 语句</span><span class="sxs-lookup"><span data-stu-id="cb888-113">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="cb888-114">变量声明</span><span class="sxs-lookup"><span data-stu-id="cb888-114">Variable Declaration</span></span>](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
