---
title: "错误的 DLL 调用约定"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrID49
ms.assetid: 7c7def45-b0ab-450f-ad3f-4383dfd9aed7
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: daa84e82d2fbe1041af56fdd5cc3855efd814ddf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="bad-dll-calling-convention"></a><span data-ttu-id="72779-102">错误的 DLL 调用约定</span><span class="sxs-lookup"><span data-stu-id="72779-102">Bad DLL calling convention</span></span>
<span data-ttu-id="72779-103">自变量传递给动态链接库 (DLL) 必须完全匹配所需要的例程。</span><span class="sxs-lookup"><span data-stu-id="72779-103">Arguments passed to a dynamic-link library (DLL) must exactly match those expected by the routine.</span></span> <span data-ttu-id="72779-104">调用约定处理数量、 类型和参数的顺序。</span><span class="sxs-lookup"><span data-stu-id="72779-104">Calling conventions deal with number, type, and order of arguments.</span></span> <span data-ttu-id="72779-105">程序可能在错误的类型或数量的参数被传递的 DLL 中调用例程。</span><span class="sxs-lookup"><span data-stu-id="72779-105">Your program may be calling a routine in a DLL that is being passed the wrong type or number of arguments.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="72779-106">更正此错误</span><span class="sxs-lookup"><span data-stu-id="72779-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="72779-107">请确保所有自变量类型与要调用的例程声明中指定一致。</span><span class="sxs-lookup"><span data-stu-id="72779-107">Make sure all argument types agree with those specified in the declaration of the routine that you are calling.</span></span>  
  
2.  <span data-ttu-id="72779-108">请确保您要传递要调用的例程的声明中指定的参数的相同数目。</span><span class="sxs-lookup"><span data-stu-id="72779-108">Make sure you are passing the same number of arguments indicated in the declaration of the routine that you are calling.</span></span>  
  
3.  <span data-ttu-id="72779-109">如果 DLL 例程需要按值的自变量，请确保`ByVal`例程的声明中为这些参数指定。</span><span class="sxs-lookup"><span data-stu-id="72779-109">If the DLL routine expects arguments by value, make sure `ByVal` is specified for those arguments in the declaration for the routine.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72779-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="72779-110">See Also</span></span>  
 [<span data-ttu-id="72779-111">错误类型</span><span class="sxs-lookup"><span data-stu-id="72779-111">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)  
 [<span data-ttu-id="72779-112">Call 语句</span><span class="sxs-lookup"><span data-stu-id="72779-112">Call Statement</span></span>](../../../visual-basic/language-reference/statements/call-statement.md)  
 [<span data-ttu-id="72779-113">Declare 语句</span><span class="sxs-lookup"><span data-stu-id="72779-113">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
