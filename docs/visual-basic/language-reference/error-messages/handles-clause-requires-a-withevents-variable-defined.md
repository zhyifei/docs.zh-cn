---
title: Handles 子句需要在包含类型或它的基类型之一中定义的 WithEvents 变量
ms.date: 07/20/2015
f1_keywords:
- vbc30506
- bc30506
helpviewer_keywords:
- BC30506
ms.assetid: 5b66f6a8-f050-4e03-a57f-a64e85f80cb5
ms.openlocfilehash: 99901432375c02e6a0e500cb772f8fd029276b2d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33587428"
---
# <a name="handles-clause-requires-a-withevents-variable-defined-in-the-containing-type-or-one-of-its-base-types"></a><span data-ttu-id="7ed9e-102">Handles 子句需要在包含类型或它的基类型之一中定义的 WithEvents 变量</span><span class="sxs-lookup"><span data-stu-id="7ed9e-102">Handles clause requires a WithEvents variable defined in the containing type or one of its base types</span></span>
<span data-ttu-id="7ed9e-103">你没有提供`WithEvents`变量中你`Handles`子句。</span><span class="sxs-lookup"><span data-stu-id="7ed9e-103">You did not supply a `WithEvents` variable in your `Handles` clause.</span></span> <span data-ttu-id="7ed9e-104">`Handles`过程声明的末尾处关键字后，即可处理由使用声明的对象变量引发的事件`WithEvents`关键字。</span><span class="sxs-lookup"><span data-stu-id="7ed9e-104">The `Handles` keyword at the end of a procedure declaration causes it to handle events raised by an object variable declared using the `WithEvents` keyword.</span></span>  
  
 <span data-ttu-id="7ed9e-105">**错误 ID:** BC30506</span><span class="sxs-lookup"><span data-stu-id="7ed9e-105">**Error ID:** BC30506</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7ed9e-106">更正此错误</span><span class="sxs-lookup"><span data-stu-id="7ed9e-106">To correct this error</span></span>  
  
-   <span data-ttu-id="7ed9e-107">提供所需`WithEvents`变量。</span><span class="sxs-lookup"><span data-stu-id="7ed9e-107">Supply the necessary `WithEvents` variable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ed9e-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="7ed9e-108">See Also</span></span>  
 [<span data-ttu-id="7ed9e-109">Handles</span><span class="sxs-lookup"><span data-stu-id="7ed9e-109">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)
