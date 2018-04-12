---
title: 共享 WithEvents 变量的事件不能由非共享方法处理
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30594
- vbc30594
helpviewer_keywords:
- BC30594
ms.assetid: 5b9fceb4-ab11-41bb-ad3b-6f1a9da8ae7e
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 53372927b88df3946583564492df42170f302739
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="events-of-shared-withevents-variables-cannot-be-handled-by-non-shared-methods"></a><span data-ttu-id="d6a28-102">共享 WithEvents 变量的事件不能由非共享方法处理</span><span class="sxs-lookup"><span data-stu-id="d6a28-102">Events of shared WithEvents variables cannot be handled by non-shared methods</span></span>
<span data-ttu-id="d6a28-103">与声明的变量`Shared`修饰符是共享的变量。</span><span class="sxs-lookup"><span data-stu-id="d6a28-103">A variable declared with the `Shared` modifier is a shared variable.</span></span> <span data-ttu-id="d6a28-104">共享的变量标识恰好一个存储位置。</span><span class="sxs-lookup"><span data-stu-id="d6a28-104">A shared variable identifies exactly one storage location.</span></span> <span data-ttu-id="d6a28-105">与声明的变量`WithEvents`修饰符断言变量所属的类型处理一组变量引发的事件。</span><span class="sxs-lookup"><span data-stu-id="d6a28-105">A variable declared with the `WithEvents` modifier asserts that the type to which the variable belongs handles the set of events the variable raises.</span></span> <span data-ttu-id="d6a28-106">属性值分配给变量时，由`WithEvents`声明任何现有的事件处理程序将解除挂钩，并通过新的事件处理程序挂钩`Add`方法。</span><span class="sxs-lookup"><span data-stu-id="d6a28-106">When a value is assigned to the variable, the property created by the `WithEvents` declaration unhooks any existing event handler and hooks up the new event handler via the `Add` method.</span></span>  
  
 <span data-ttu-id="d6a28-107">**错误 ID:** BC30594</span><span class="sxs-lookup"><span data-stu-id="d6a28-107">**Error ID:** BC30594</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d6a28-108">更正此错误</span><span class="sxs-lookup"><span data-stu-id="d6a28-108">To correct this error</span></span>  
  
-   <span data-ttu-id="d6a28-109">声明事件处理程序`Shared`。</span><span class="sxs-lookup"><span data-stu-id="d6a28-109">Declare your event handler `Shared`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6a28-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d6a28-110">See Also</span></span>  
 [<span data-ttu-id="d6a28-111">Shared</span><span class="sxs-lookup"><span data-stu-id="d6a28-111">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)  
 [<span data-ttu-id="d6a28-112">WithEvents</span><span class="sxs-lookup"><span data-stu-id="d6a28-112">WithEvents</span></span>](../../../visual-basic/language-reference/modifiers/withevents.md)
