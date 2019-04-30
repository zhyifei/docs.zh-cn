---
title: 除数为零（Visual Basic 运行时错误）
ms.date: 07/20/2015
f1_keywords:
- vbrID11
ms.assetid: 5b9bc5d6-792e-48bc-a974-012e07ad95f3
ms.openlocfilehash: 194dcebe40b7f14ba4bf4ebce6f2b1294d3e6791
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61970334"
---
# <a name="division-by-zero-visual-basic-run-time-error"></a><span data-ttu-id="1b041-102">除数为零（Visual Basic 运行时错误）</span><span class="sxs-lookup"><span data-stu-id="1b041-102">Division by zero (Visual Basic Run-Time Error)</span></span>
<span data-ttu-id="1b041-103">用作除数的表达式有一个值为零。</span><span class="sxs-lookup"><span data-stu-id="1b041-103">An expression being used as a divisor has a value of zero.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1b041-104">更正此错误</span><span class="sxs-lookup"><span data-stu-id="1b041-104">To correct this error</span></span>  
  
1. <span data-ttu-id="1b041-105">检查表达式中变量的拼写是否正确。</span><span class="sxs-lookup"><span data-stu-id="1b041-105">Check the spelling of variables in the expression.</span></span> <span data-ttu-id="1b041-106">拼写错误的变量名可能会隐式创建一个初始化为零的数值变量。</span><span class="sxs-lookup"><span data-stu-id="1b041-106">A misspelled variable name can implicitly create a numeric variable that is initialized to zero.</span></span>  
  
2. <span data-ttu-id="1b041-107">检查之前对表达式中的变量进行的操作，尤其是那些从其他过程作为参数传递给该过程的操作。</span><span class="sxs-lookup"><span data-stu-id="1b041-107">Check previous operations on variables in the expression, especially those passed into the procedure as arguments from other procedures.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b041-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="1b041-108">See also</span></span>

- [<span data-ttu-id="1b041-109">按值和按引用传递自变量</span><span class="sxs-lookup"><span data-stu-id="1b041-109">Passing Arguments by Value and by Reference</span></span>](../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
