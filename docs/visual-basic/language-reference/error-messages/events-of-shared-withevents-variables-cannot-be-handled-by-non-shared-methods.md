---
title: 共享 WithEvents 变量的事件不能由非共享方法处理
ms.date: 07/20/2015
f1_keywords:
- bc30594
- vbc30594
helpviewer_keywords:
- BC30594
ms.assetid: 5b9fceb4-ab11-41bb-ad3b-6f1a9da8ae7e
ms.openlocfilehash: f61f4cd17b1bb3088117e0a0d91b186fd40db3b2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33585166"
---
# <a name="events-of-shared-withevents-variables-cannot-be-handled-by-non-shared-methods"></a><span data-ttu-id="a842a-102">共享 WithEvents 变量的事件不能由非共享方法处理</span><span class="sxs-lookup"><span data-stu-id="a842a-102">Events of shared WithEvents variables cannot be handled by non-shared methods</span></span>
<span data-ttu-id="a842a-103">与声明的变量`Shared`修饰符是共享的变量。</span><span class="sxs-lookup"><span data-stu-id="a842a-103">A variable declared with the `Shared` modifier is a shared variable.</span></span> <span data-ttu-id="a842a-104">共享的变量标识恰好一个存储位置。</span><span class="sxs-lookup"><span data-stu-id="a842a-104">A shared variable identifies exactly one storage location.</span></span> <span data-ttu-id="a842a-105">与声明的变量`WithEvents`修饰符断言变量所属的类型处理一组变量引发的事件。</span><span class="sxs-lookup"><span data-stu-id="a842a-105">A variable declared with the `WithEvents` modifier asserts that the type to which the variable belongs handles the set of events the variable raises.</span></span> <span data-ttu-id="a842a-106">属性值分配给变量时，由`WithEvents`声明任何现有的事件处理程序将解除挂钩，并通过新的事件处理程序挂钩`Add`方法。</span><span class="sxs-lookup"><span data-stu-id="a842a-106">When a value is assigned to the variable, the property created by the `WithEvents` declaration unhooks any existing event handler and hooks up the new event handler via the `Add` method.</span></span>  
  
 <span data-ttu-id="a842a-107">**错误 ID:** BC30594</span><span class="sxs-lookup"><span data-stu-id="a842a-107">**Error ID:** BC30594</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a842a-108">更正此错误</span><span class="sxs-lookup"><span data-stu-id="a842a-108">To correct this error</span></span>  
  
-   <span data-ttu-id="a842a-109">声明事件处理程序`Shared`。</span><span class="sxs-lookup"><span data-stu-id="a842a-109">Declare your event handler `Shared`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a842a-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="a842a-110">See Also</span></span>  
 [<span data-ttu-id="a842a-111">Shared</span><span class="sxs-lookup"><span data-stu-id="a842a-111">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)  
 [<span data-ttu-id="a842a-112">WithEvents</span><span class="sxs-lookup"><span data-stu-id="a842a-112">WithEvents</span></span>](../../../visual-basic/language-reference/modifiers/withevents.md)
