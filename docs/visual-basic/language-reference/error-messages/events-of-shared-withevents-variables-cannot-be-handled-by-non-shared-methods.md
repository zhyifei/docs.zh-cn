---
title: 共享 WithEvents 变量的事件不能由非共享方法处理
ms.date: 07/20/2015
f1_keywords:
- bc30594
- vbc30594
helpviewer_keywords:
- BC30594
ms.assetid: 5b9fceb4-ab11-41bb-ad3b-6f1a9da8ae7e
ms.openlocfilehash: 2b32043898986b3e3e68fab18c5f907843d7691c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "58838646"
---
# <a name="events-of-shared-withevents-variables-cannot-be-handled-by-non-shared-methods"></a><span data-ttu-id="e3cf3-102">共享 WithEvents 变量的事件不能由非共享方法处理</span><span class="sxs-lookup"><span data-stu-id="e3cf3-102">Events of shared WithEvents variables cannot be handled by non-shared methods</span></span>
<span data-ttu-id="e3cf3-103">与声明的变量`Shared`修饰符是共享的变量。</span><span class="sxs-lookup"><span data-stu-id="e3cf3-103">A variable declared with the `Shared` modifier is a shared variable.</span></span> <span data-ttu-id="e3cf3-104">共享的变量标识恰好一个存储位置。</span><span class="sxs-lookup"><span data-stu-id="e3cf3-104">A shared variable identifies exactly one storage location.</span></span> <span data-ttu-id="e3cf3-105">与声明的变量`WithEvents`修饰符声明该变量所属的类型处理一组变量引发的事件。</span><span class="sxs-lookup"><span data-stu-id="e3cf3-105">A variable declared with the `WithEvents` modifier asserts that the type to which the variable belongs handles the set of events the variable raises.</span></span> <span data-ttu-id="e3cf3-106">该属性值分配给变量时，创建的`WithEvents`声明卸载任何现有的事件处理程序，并通过新的事件处理程序挂钩`Add`方法。</span><span class="sxs-lookup"><span data-stu-id="e3cf3-106">When a value is assigned to the variable, the property created by the `WithEvents` declaration unhooks any existing event handler and hooks up the new event handler via the `Add` method.</span></span>  
  
 <span data-ttu-id="e3cf3-107">**错误 ID:** BC30594</span><span class="sxs-lookup"><span data-stu-id="e3cf3-107">**Error ID:** BC30594</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e3cf3-108">更正此错误</span><span class="sxs-lookup"><span data-stu-id="e3cf3-108">To correct this error</span></span>  
  
-   <span data-ttu-id="e3cf3-109">声明事件处理程序`Shared`。</span><span class="sxs-lookup"><span data-stu-id="e3cf3-109">Declare your event handler `Shared`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3cf3-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="e3cf3-110">See also</span></span>

- [<span data-ttu-id="e3cf3-111">Shared</span><span class="sxs-lookup"><span data-stu-id="e3cf3-111">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)
- [<span data-ttu-id="e3cf3-112">WithEvents</span><span class="sxs-lookup"><span data-stu-id="e3cf3-112">WithEvents</span></span>](../../../visual-basic/language-reference/modifiers/withevents.md)
