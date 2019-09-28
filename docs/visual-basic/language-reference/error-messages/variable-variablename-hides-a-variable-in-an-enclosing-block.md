---
title: 变量“<variablename>”在封闭块中隐藏变量
ms.date: 07/20/2015
f1_keywords:
- vbc30616
- bc30616
helpviewer_keywords:
- BC30616
ms.assetid: e7658ebc-da45-451b-a409-a0f8915f0beb
ms.openlocfilehash: 4312abef83728f432e2f6a492e5acad3450719b1
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592065"
---
# <a name="variable-variablename-hides-a-variable-in-an-enclosing-block"></a><span data-ttu-id="9a280-102">变量 "\<variablename >" 隐藏封闭块中的变量</span><span class="sxs-lookup"><span data-stu-id="9a280-102">Variable '\<variablename>' hides a variable in an enclosing block</span></span>
<span data-ttu-id="9a280-103">块中包含的变量与另一个本地变量的名称相同。</span><span class="sxs-lookup"><span data-stu-id="9a280-103">A variable enclosed in a block has the same name as another local variable.</span></span>  
  
 <span data-ttu-id="9a280-104">**错误 ID：** BC30616</span><span class="sxs-lookup"><span data-stu-id="9a280-104">**Error ID:** BC30616</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9a280-105">更正此错误</span><span class="sxs-lookup"><span data-stu-id="9a280-105">To correct this error</span></span>  
  
- <span data-ttu-id="9a280-106">重命名封闭块中的变量，使其与其他任何局部变量不同。</span><span class="sxs-lookup"><span data-stu-id="9a280-106">Rename the variable in the enclosed block so that it is not the same as any other local variables.</span></span> <span data-ttu-id="9a280-107">例如：</span><span class="sxs-lookup"><span data-stu-id="9a280-107">For example:</span></span>  
  
    ```vb  
    Dim a, b, x As Integer  
    If a = b Then  
       Dim y As Integer = 20 ' Uniquely named block variable.  
    End If  
    ```  
  
- <span data-ttu-id="9a280-108">此错误的一个常见原因是在事件处理程序中使用 `Catch e As Exception`。</span><span class="sxs-lookup"><span data-stu-id="9a280-108">A common cause for this error is the use of `Catch e As Exception` inside an event handler.</span></span> <span data-ttu-id="9a280-109">如果是这种情况，请将 `Catch` 块变量命名为 `ex` 而不是 `e`。</span><span class="sxs-lookup"><span data-stu-id="9a280-109">If this is the case, name the `Catch` block variable `ex` rather than `e`.</span></span>  
  
- <span data-ttu-id="9a280-110">此错误的另一个常见原因是尝试访问在单独的 @no__t 块中的 `Try` 块内声明的局部变量。</span><span class="sxs-lookup"><span data-stu-id="9a280-110">Another common source of this error is an attempt to access a local variable declared within a `Try` block in a separate `Catch` block.</span></span> <span data-ttu-id="9a280-111">若要更正此错误，请在 `Try...Catch...Finally` 结构之外声明变量。</span><span class="sxs-lookup"><span data-stu-id="9a280-111">To correct this, declare the variable outside the `Try...Catch...Finally` structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a280-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="9a280-112">See also</span></span>

- [<span data-ttu-id="9a280-113">Try...Catch...Finally 语句</span><span class="sxs-lookup"><span data-stu-id="9a280-113">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="9a280-114">变量声明</span><span class="sxs-lookup"><span data-stu-id="9a280-114">Variable Declaration</span></span>](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
