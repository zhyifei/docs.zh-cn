---
title: '&#39;设置&#39;的属性访问器&#39; &lt;propertyname&gt; &#39;不可访问'
ms.date: 07/20/2015
f1_keywords:
- vbc31102
- bc31102
helpviewer_keywords:
- BC31102
ms.assetid: 6f7b31b7-3656-4ae1-8851-90f5f4c6950a
ms.openlocfilehash: d047d03755de89d4740482db4845d5db72003ac0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33595847"
---
# <a name="39set39-accessor-of-property-39ltpropertynamegt39-is-not-accessible"></a><span data-ttu-id="25094-102">&#39;设置&#39;的属性访问器&#39; &lt;propertyname&gt; &#39;不可访问</span><span class="sxs-lookup"><span data-stu-id="25094-102">&#39;Set&#39; accessor of property &#39;&lt;propertyname&gt;&#39; is not accessible</span></span>
<span data-ttu-id="25094-103">语句试图存储属性的值，如果它不具有对该属性的访问`Set`过程。</span><span class="sxs-lookup"><span data-stu-id="25094-103">A statement attempts to store the value of a property when it does not have access to the property's `Set` procedure.</span></span>  
  
 <span data-ttu-id="25094-104">如果[Set 语句](../../../visual-basic/language-reference/statements/set-statement.md)标记具有限制性更强的访问权限级别比其[属性语句](../../../visual-basic/language-reference/statements/property-statement.md)，尝试设置的属性值在以下情况可能会失败：</span><span class="sxs-lookup"><span data-stu-id="25094-104">If the [Set Statement](../../../visual-basic/language-reference/statements/set-statement.md) is marked with a more restrictive access level than its [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md), an attempt to set the property value could fail in the following cases:</span></span>  
  
-   <span data-ttu-id="25094-105">`Set`语句被标记为[私有](../../../visual-basic/language-reference/modifiers/private.md)，但调用代码以外的类或结构在其中定义该属性。</span><span class="sxs-lookup"><span data-stu-id="25094-105">The `Set` statement is marked [Private](../../../visual-basic/language-reference/modifiers/private.md) and the calling code is outside the class or structure in which the property is defined.</span></span>  
  
-   <span data-ttu-id="25094-106">`Set`语句被标记为[受保护](../../../visual-basic/language-reference/modifiers/protected.md)，调用代码不在类或结构在其中定义该属性，也不派生类中。</span><span class="sxs-lookup"><span data-stu-id="25094-106">The `Set` statement is marked [Protected](../../../visual-basic/language-reference/modifiers/protected.md) and the calling code is not in the class or structure in which the property is defined, nor in a derived class.</span></span>  
  
-   <span data-ttu-id="25094-107">`Set`语句被标记为[友元](../../../visual-basic/language-reference/modifiers/friend.md)而调用的代码不在同一程序集在其中定义该属性。</span><span class="sxs-lookup"><span data-stu-id="25094-107">The `Set` statement is marked [Friend](../../../visual-basic/language-reference/modifiers/friend.md) and the calling code is not in the same assembly in which the property is defined.</span></span>  
  
 <span data-ttu-id="25094-108">**错误 ID:** BC31102</span><span class="sxs-lookup"><span data-stu-id="25094-108">**Error ID:** BC31102</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="25094-109">更正此错误</span><span class="sxs-lookup"><span data-stu-id="25094-109">To correct this error</span></span>  
  
-   <span data-ttu-id="25094-110">如果已定义属性的源代码管理，请考虑声明`Set`属性本身的相同访问级别的过程。</span><span class="sxs-lookup"><span data-stu-id="25094-110">If you have control of the source code defining the property, consider declaring the `Set` procedure with the same access level as the property itself.</span></span>  
  
-   <span data-ttu-id="25094-111">如果你不能定义属性，对源代码的控制或必须限制`Set`过程访问级别限制性比强属性自身，尝试移动到具有更好地访问的代码区域设置的属性值的语句属性。</span><span class="sxs-lookup"><span data-stu-id="25094-111">If you do not have control of the source code defining the property, or you must restrict the `Set` procedure access level more than the property itself, try to move the statement that sets the property value to a region of code that has better access to the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25094-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="25094-112">See Also</span></span>  
 [<span data-ttu-id="25094-113">属性过程</span><span class="sxs-lookup"><span data-stu-id="25094-113">Property Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)  
 [<span data-ttu-id="25094-114">如何：声明具有混合访问级别的属性</span><span class="sxs-lookup"><span data-stu-id="25094-114">How to: Declare a Property with Mixed Access Levels</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)
