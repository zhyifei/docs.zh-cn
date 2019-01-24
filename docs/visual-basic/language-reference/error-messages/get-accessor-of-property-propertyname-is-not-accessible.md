---
title: '&#39;获取&#39;属性访问器&#39; &lt;propertyname&gt; &#39;不可访问'
ms.date: 07/20/2015
f1_keywords:
- vbc31103
- bc31103
helpviewer_keywords:
- BC31103
ms.assetid: 3c346c32-7669-4b04-841d-7a9df9cb703e
ms.openlocfilehash: 10b7168ac40ca7c7d696cd63cd823454f404bb94
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54582209"
---
# <a name="39get39-accessor-of-property-39ltpropertynamegt39-is-not-accessible"></a><span data-ttu-id="40254-102">&#39;获取&#39;属性访问器&#39; &lt;propertyname&gt; &#39;不可访问</span><span class="sxs-lookup"><span data-stu-id="40254-102">&#39;Get&#39; accessor of property &#39;&lt;propertyname&gt;&#39; is not accessible</span></span>
<span data-ttu-id="40254-103">语句试图检索属性的值不包含属性的访问权限时`Get`过程。</span><span class="sxs-lookup"><span data-stu-id="40254-103">A statement attempts to retrieve the value of a property when it does not have access to the property's `Get` procedure.</span></span>  
  
 <span data-ttu-id="40254-104">如果[Get 语句](../../../visual-basic/language-reference/statements/get-statement.md)标记具有限制性更强的访问权限级别比其[Property 语句](../../../visual-basic/language-reference/statements/property-statement.md)，尝试读取属性值在以下情况下可能会失败：</span><span class="sxs-lookup"><span data-stu-id="40254-104">If the [Get Statement](../../../visual-basic/language-reference/statements/get-statement.md) is marked with a more restrictive access level than its [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md), an attempt to read the property value could fail in the following cases:</span></span>  
  
-   <span data-ttu-id="40254-105">`Get`标记语句[专用](../../../visual-basic/language-reference/modifiers/private.md)且调用代码外部的类或结构在其中定义该属性。</span><span class="sxs-lookup"><span data-stu-id="40254-105">The `Get` statement is marked [Private](../../../visual-basic/language-reference/modifiers/private.md) and the calling code is outside the class or structure in which the property is defined.</span></span>  
  
-   <span data-ttu-id="40254-106">`Get`标记语句[受保护](../../../visual-basic/language-reference/modifiers/protected.md)，调用代码不在类或结构定义属性，也不在派生类中。</span><span class="sxs-lookup"><span data-stu-id="40254-106">The `Get` statement is marked [Protected](../../../visual-basic/language-reference/modifiers/protected.md) and the calling code is not in the class or structure in which the property is defined, nor in a derived class.</span></span>  
  
-   <span data-ttu-id="40254-107">`Get`标记语句[友元](../../../visual-basic/language-reference/modifiers/friend.md)并且调用代码不是在其中定义该属性在同一程序集中。</span><span class="sxs-lookup"><span data-stu-id="40254-107">The `Get` statement is marked [Friend](../../../visual-basic/language-reference/modifiers/friend.md) and the calling code is not in the same assembly in which the property is defined.</span></span>  
  
 <span data-ttu-id="40254-108">**错误 ID:** BC31103</span><span class="sxs-lookup"><span data-stu-id="40254-108">**Error ID:** BC31103</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="40254-109">更正此错误</span><span class="sxs-lookup"><span data-stu-id="40254-109">To correct this error</span></span>  
  
-   <span data-ttu-id="40254-110">如果将属性定义的源代码管理后，请考虑声明`Get`与属性本身相同的访问级别的过程。</span><span class="sxs-lookup"><span data-stu-id="40254-110">If you have control of the source code defining the property, consider declaring the `Get` procedure with the same access level as the property itself.</span></span>  
  
-   <span data-ttu-id="40254-111">如果您不能将属性定义的源代码控制，或者您必须限制`Get`过程访问级别的多个属性本身，试着继续读取属性值设置为更好地访问某个区域的代码的语句属性。</span><span class="sxs-lookup"><span data-stu-id="40254-111">If you do not have control of the source code defining the property, or you must restrict the `Get` procedure access level more than the property itself, try to move the statement that reads the property value to a region of code that has better access to the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40254-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="40254-112">See also</span></span>
- [<span data-ttu-id="40254-113">属性过程</span><span class="sxs-lookup"><span data-stu-id="40254-113">Property Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)
- [<span data-ttu-id="40254-114">如何：声明具有混合的访问级别的属性</span><span class="sxs-lookup"><span data-stu-id="40254-114">How to: Declare a Property with Mixed Access Levels</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)
