---
title: “<keyword>”只在实例方法中有效
ms.date: 07/20/2015
f1_keywords:
- bc30043
- vbc30043
helpviewer_keywords:
- BC30043
ms.assetid: 7973aa82-a681-440c-9bca-242627d7ba86
ms.openlocfilehash: 5ff82b932f9bea4c7fd087651e34277ef94bc27c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61946635"
---
# <a name="keyword-is-valid-only-within-an-instance-method"></a><span data-ttu-id="aa8e3-102">\<关键字 > 只在实例方法中有效</span><span class="sxs-lookup"><span data-stu-id="aa8e3-102">'\<keyword>' is valid only within an instance method</span></span>
<span data-ttu-id="aa8e3-103">`Me`， `MyClass`，和`MyBase`关键字是指特定类实例。</span><span class="sxs-lookup"><span data-stu-id="aa8e3-103">The `Me`, `MyClass`, and `MyBase` keywords refer to specific class instances.</span></span> <span data-ttu-id="aa8e3-104">不能使用它们在共享内`Function`或`Sub`过程。</span><span class="sxs-lookup"><span data-stu-id="aa8e3-104">You cannot use them inside a shared `Function` or `Sub` procedure.</span></span>  
  
 <span data-ttu-id="aa8e3-105">**错误 ID:** BC30043</span><span class="sxs-lookup"><span data-stu-id="aa8e3-105">**Error ID:** BC30043</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="aa8e3-106">更正此错误</span><span class="sxs-lookup"><span data-stu-id="aa8e3-106">To correct this error</span></span>  
  
- <span data-ttu-id="aa8e3-107">从过程中删除关键字或删除`Shared`过程声明中的关键字。</span><span class="sxs-lookup"><span data-stu-id="aa8e3-107">Remove the keyword from the procedure, or remove the `Shared` keyword from the procedure declaration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa8e3-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="aa8e3-108">See also</span></span>

- [<span data-ttu-id="aa8e3-109">对象变量赋值</span><span class="sxs-lookup"><span data-stu-id="aa8e3-109">Object Variable Assignment</span></span>](../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [<span data-ttu-id="aa8e3-110">Me、My、MyBase 和 MyClass</span><span class="sxs-lookup"><span data-stu-id="aa8e3-110">Me, My, MyBase, and MyClass</span></span>](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="aa8e3-111">继承的基础知识</span><span class="sxs-lookup"><span data-stu-id="aa8e3-111">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
