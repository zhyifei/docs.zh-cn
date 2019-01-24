---
title: '&#39;&lt;关键字&gt;&#39;只在实例方法中有效'
ms.date: 07/20/2015
f1_keywords:
- bc30043
- vbc30043
helpviewer_keywords:
- BC30043
ms.assetid: 7973aa82-a681-440c-9bca-242627d7ba86
ms.openlocfilehash: a464a059aa2d13e3472b9770960384b6be398092
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54595937"
---
# <a name="39ltkeywordgt39-is-valid-only-within-an-instance-method"></a><span data-ttu-id="3118f-102">&#39;&lt;关键字&gt;&#39;只在实例方法中有效</span><span class="sxs-lookup"><span data-stu-id="3118f-102">&#39;&lt;keyword&gt;&#39; is valid only within an instance method</span></span>
<span data-ttu-id="3118f-103">`Me`， `MyClass`，和`MyBase`关键字是指特定类实例。</span><span class="sxs-lookup"><span data-stu-id="3118f-103">The `Me`, `MyClass`, and `MyBase` keywords refer to specific class instances.</span></span> <span data-ttu-id="3118f-104">不能使用它们在共享内`Function`或`Sub`过程。</span><span class="sxs-lookup"><span data-stu-id="3118f-104">You cannot use them inside a shared `Function` or `Sub` procedure.</span></span>  
  
 <span data-ttu-id="3118f-105">**错误 ID:** BC30043</span><span class="sxs-lookup"><span data-stu-id="3118f-105">**Error ID:** BC30043</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="3118f-106">更正此错误</span><span class="sxs-lookup"><span data-stu-id="3118f-106">To correct this error</span></span>  
  
-   <span data-ttu-id="3118f-107">从过程中删除关键字或删除`Shared`过程声明中的关键字。</span><span class="sxs-lookup"><span data-stu-id="3118f-107">Remove the keyword from the procedure, or remove the `Shared` keyword from the procedure declaration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3118f-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="3118f-108">See also</span></span>
- [<span data-ttu-id="3118f-109">对象变量赋值</span><span class="sxs-lookup"><span data-stu-id="3118f-109">Object Variable Assignment</span></span>](../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [<span data-ttu-id="3118f-110">Me、My、MyBase 和 MyClass</span><span class="sxs-lookup"><span data-stu-id="3118f-110">Me, My, MyBase, and MyClass</span></span>](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="3118f-111">继承的基础知识</span><span class="sxs-lookup"><span data-stu-id="3118f-111">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
