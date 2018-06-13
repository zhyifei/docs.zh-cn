---
title: 错误的 DLL 调用约定
ms.date: 07/20/2015
f1_keywords:
- vbrID49
ms.assetid: 7c7def45-b0ab-450f-ad3f-4383dfd9aed7
ms.openlocfilehash: d8c7f7aea46162215115689305f4010cb513b020
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33583833"
---
# <a name="bad-dll-calling-convention"></a><span data-ttu-id="8e2b7-102">错误的 DLL 调用约定</span><span class="sxs-lookup"><span data-stu-id="8e2b7-102">Bad DLL calling convention</span></span>
<span data-ttu-id="8e2b7-103">自变量传递给动态链接库 (DLL) 必须完全匹配所需要的例程。</span><span class="sxs-lookup"><span data-stu-id="8e2b7-103">Arguments passed to a dynamic-link library (DLL) must exactly match those expected by the routine.</span></span> <span data-ttu-id="8e2b7-104">调用约定处理数量、 类型和参数的顺序。</span><span class="sxs-lookup"><span data-stu-id="8e2b7-104">Calling conventions deal with number, type, and order of arguments.</span></span> <span data-ttu-id="8e2b7-105">程序可能在错误的类型或数量的参数被传递的 DLL 中调用例程。</span><span class="sxs-lookup"><span data-stu-id="8e2b7-105">Your program may be calling a routine in a DLL that is being passed the wrong type or number of arguments.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="8e2b7-106">更正此错误</span><span class="sxs-lookup"><span data-stu-id="8e2b7-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="8e2b7-107">请确保所有自变量类型与要调用的例程声明中指定一致。</span><span class="sxs-lookup"><span data-stu-id="8e2b7-107">Make sure all argument types agree with those specified in the declaration of the routine that you are calling.</span></span>  
  
2.  <span data-ttu-id="8e2b7-108">请确保您要传递要调用的例程的声明中指定的参数的相同数目。</span><span class="sxs-lookup"><span data-stu-id="8e2b7-108">Make sure you are passing the same number of arguments indicated in the declaration of the routine that you are calling.</span></span>  
  
3.  <span data-ttu-id="8e2b7-109">如果 DLL 例程需要按值的自变量，请确保`ByVal`例程的声明中为这些参数指定。</span><span class="sxs-lookup"><span data-stu-id="8e2b7-109">If the DLL routine expects arguments by value, make sure `ByVal` is specified for those arguments in the declaration for the routine.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e2b7-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="8e2b7-110">See Also</span></span>  
 [<span data-ttu-id="8e2b7-111">错误类型</span><span class="sxs-lookup"><span data-stu-id="8e2b7-111">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)  
 [<span data-ttu-id="8e2b7-112">Call 语句</span><span class="sxs-lookup"><span data-stu-id="8e2b7-112">Call Statement</span></span>](../../../visual-basic/language-reference/statements/call-statement.md)  
 [<span data-ttu-id="8e2b7-113">Declare 语句</span><span class="sxs-lookup"><span data-stu-id="8e2b7-113">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
