---
title: 派生类无法引发基类事件
ms.date: 07/20/2015
f1_keywords:
- vbc30029
- bc30029
helpviewer_keywords:
- BC30029
ms.assetid: 63afa1c6-2f93-4512-a2f0-372455979771
ms.openlocfilehash: 3cb61a40e4522695b876d85f67dac1a109d3c3e0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54595859"
---
# <a name="derived-classes-cannot-raise-base-class-events"></a><span data-ttu-id="f06b0-102">派生类无法引发基类事件</span><span class="sxs-lookup"><span data-stu-id="f06b0-102">Derived classes cannot raise base class events</span></span>
<span data-ttu-id="f06b0-103">只能从声明它的声明空间，可以引发一个事件。</span><span class="sxs-lookup"><span data-stu-id="f06b0-103">An event can be raised only from the declaration space in which it is declared.</span></span> <span data-ttu-id="f06b0-104">因此，一个类无法引发从任何其他类，甚至从其派生的其中一个事件。</span><span class="sxs-lookup"><span data-stu-id="f06b0-104">Therefore, a class cannot raise events from any other class, even one from which it is derived.</span></span>  
  
 <span data-ttu-id="f06b0-105">**错误 ID:** BC30029</span><span class="sxs-lookup"><span data-stu-id="f06b0-105">**Error ID:** BC30029</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f06b0-106">更正此错误</span><span class="sxs-lookup"><span data-stu-id="f06b0-106">To correct this error</span></span>  
  
-   <span data-ttu-id="f06b0-107">移动`Event`语句或`RaiseEvent`语句，使它们位于同一个类。</span><span class="sxs-lookup"><span data-stu-id="f06b0-107">Move the `Event` statement or the `RaiseEvent` statement so they are in the same class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f06b0-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="f06b0-108">See also</span></span>
- [<span data-ttu-id="f06b0-109">Event 语句</span><span class="sxs-lookup"><span data-stu-id="f06b0-109">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="f06b0-110">RaiseEvent 语句</span><span class="sxs-lookup"><span data-stu-id="f06b0-110">RaiseEvent Statement</span></span>](../../../visual-basic/language-reference/statements/raiseevent-statement.md)
