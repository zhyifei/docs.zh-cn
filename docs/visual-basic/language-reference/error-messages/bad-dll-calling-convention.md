---
title: 错误的 DLL 调用约定
ms.date: 07/20/2015
f1_keywords:
- vbrID49
ms.assetid: 7c7def45-b0ab-450f-ad3f-4383dfd9aed7
ms.openlocfilehash: c4f9917a7fb807cf7da92a3bba2d3edec8045bd2
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58813515"
---
# <a name="bad-dll-calling-convention"></a><span data-ttu-id="0eebd-102">错误的 DLL 调用约定</span><span class="sxs-lookup"><span data-stu-id="0eebd-102">Bad DLL calling convention</span></span>
<span data-ttu-id="0eebd-103">自变量传递给动态链接库 (DLL) 必须完全符合这些例程的要求。</span><span class="sxs-lookup"><span data-stu-id="0eebd-103">Arguments passed to a dynamic-link library (DLL) must exactly match those expected by the routine.</span></span> <span data-ttu-id="0eebd-104">调用约定处理数量、 类型和参数的顺序。</span><span class="sxs-lookup"><span data-stu-id="0eebd-104">Calling conventions deal with number, type, and order of arguments.</span></span> <span data-ttu-id="0eebd-105">您的程序可能调用例程在传递错误的类型或数量的参数传递的 DLL 中。</span><span class="sxs-lookup"><span data-stu-id="0eebd-105">Your program may be calling a routine in a DLL that is being passed the wrong type or number of arguments.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="0eebd-106">更正此错误</span><span class="sxs-lookup"><span data-stu-id="0eebd-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="0eebd-107">请确保所有参数类型与要调用的例程的声明中指定的都一致。</span><span class="sxs-lookup"><span data-stu-id="0eebd-107">Make sure all argument types agree with those specified in the declaration of the routine that you are calling.</span></span>  
  
2.  <span data-ttu-id="0eebd-108">请确保传递的参数调用的例程的声明中指定的相同数目。</span><span class="sxs-lookup"><span data-stu-id="0eebd-108">Make sure you are passing the same number of arguments indicated in the declaration of the routine that you are calling.</span></span>  
  
3.  <span data-ttu-id="0eebd-109">如果 DLL 例程需要按值参数，请确保`ByVal`例程的声明中为这些参数指定。</span><span class="sxs-lookup"><span data-stu-id="0eebd-109">If the DLL routine expects arguments by value, make sure `ByVal` is specified for those arguments in the declaration for the routine.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0eebd-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="0eebd-110">See also</span></span>

- [<span data-ttu-id="0eebd-111">错误类型</span><span class="sxs-lookup"><span data-stu-id="0eebd-111">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
- [<span data-ttu-id="0eebd-112">Call 语句</span><span class="sxs-lookup"><span data-stu-id="0eebd-112">Call Statement</span></span>](../../../visual-basic/language-reference/statements/call-statement.md)
- [<span data-ttu-id="0eebd-113">Declare 语句</span><span class="sxs-lookup"><span data-stu-id="0eebd-113">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
