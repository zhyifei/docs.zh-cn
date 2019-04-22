---
title: 属性“<propertyname>”的“Set”访问器不可访问
ms.date: 07/20/2015
f1_keywords:
- vbc31102
- bc31102
helpviewer_keywords:
- BC31102
ms.assetid: 6f7b31b7-3656-4ae1-8851-90f5f4c6950a
ms.openlocfilehash: 3bc50d6762998ca5d8f445d84c8b698c9f46436f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "58834460"
---
# <a name="set-accessor-of-property-propertyname-is-not-accessible"></a><span data-ttu-id="b4391-102">Set 访问器属性的\<属性名称 > 不可访问</span><span class="sxs-lookup"><span data-stu-id="b4391-102">'Set' accessor of property '\<propertyname>' is not accessible</span></span>
<span data-ttu-id="b4391-103">语句试图存储属性的值不包含属性的访问权限时`Set`过程。</span><span class="sxs-lookup"><span data-stu-id="b4391-103">A statement attempts to store the value of a property when it does not have access to the property's `Set` procedure.</span></span>  
  
 <span data-ttu-id="b4391-104">如果[Set 语句](../../../visual-basic/language-reference/statements/set-statement.md)标记具有限制性更强的访问权限级别比其[Property 语句](../../../visual-basic/language-reference/statements/property-statement.md)，尝试设置属性值在以下情况下可能会失败：</span><span class="sxs-lookup"><span data-stu-id="b4391-104">If the [Set Statement](../../../visual-basic/language-reference/statements/set-statement.md) is marked with a more restrictive access level than its [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md), an attempt to set the property value could fail in the following cases:</span></span>  
  
-   <span data-ttu-id="b4391-105">`Set`标记语句[专用](../../../visual-basic/language-reference/modifiers/private.md)且调用代码外部的类或结构在其中定义该属性。</span><span class="sxs-lookup"><span data-stu-id="b4391-105">The `Set` statement is marked [Private](../../../visual-basic/language-reference/modifiers/private.md) and the calling code is outside the class or structure in which the property is defined.</span></span>  
  
-   <span data-ttu-id="b4391-106">`Set`标记语句[受保护](../../../visual-basic/language-reference/modifiers/protected.md)，调用代码不在类或结构定义属性，也不在派生类中。</span><span class="sxs-lookup"><span data-stu-id="b4391-106">The `Set` statement is marked [Protected](../../../visual-basic/language-reference/modifiers/protected.md) and the calling code is not in the class or structure in which the property is defined, nor in a derived class.</span></span>  
  
-   <span data-ttu-id="b4391-107">`Set`标记语句[友元](../../../visual-basic/language-reference/modifiers/friend.md)并且调用代码不是在其中定义该属性在同一程序集中。</span><span class="sxs-lookup"><span data-stu-id="b4391-107">The `Set` statement is marked [Friend](../../../visual-basic/language-reference/modifiers/friend.md) and the calling code is not in the same assembly in which the property is defined.</span></span>  
  
 <span data-ttu-id="b4391-108">**错误 ID:** BC31102</span><span class="sxs-lookup"><span data-stu-id="b4391-108">**Error ID:** BC31102</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b4391-109">更正此错误</span><span class="sxs-lookup"><span data-stu-id="b4391-109">To correct this error</span></span>  
  
-   <span data-ttu-id="b4391-110">如果将属性定义的源代码管理后，请考虑声明`Set`与属性本身相同的访问级别的过程。</span><span class="sxs-lookup"><span data-stu-id="b4391-110">If you have control of the source code defining the property, consider declaring the `Set` procedure with the same access level as the property itself.</span></span>  
  
-   <span data-ttu-id="b4391-111">如果您不能将属性定义的源代码控制，或者您必须限制`Set`过程访问级别的多个属性本身，在尝试将移动到具有更好地访问的代码区域设置的属性值的语句属性。</span><span class="sxs-lookup"><span data-stu-id="b4391-111">If you do not have control of the source code defining the property, or you must restrict the `Set` procedure access level more than the property itself, try to move the statement that sets the property value to a region of code that has better access to the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4391-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="b4391-112">See also</span></span>

- [<span data-ttu-id="b4391-113">属性过程</span><span class="sxs-lookup"><span data-stu-id="b4391-113">Property Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)
- [<span data-ttu-id="b4391-114">如何：声明具有混合的访问级别的属性</span><span class="sxs-lookup"><span data-stu-id="b4391-114">How to: Declare a Property with Mixed Access Levels</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)
