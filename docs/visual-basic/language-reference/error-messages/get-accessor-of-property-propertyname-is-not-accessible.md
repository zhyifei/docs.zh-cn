---
title: '&#39;Get &#39;访问器的属性 &#39;&lt;propertyname&gt;&#39; 不可访问'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc31103
- bc31103
helpviewer_keywords:
- BC31103
ms.assetid: 3c346c32-7669-4b04-841d-7a9df9cb703e
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 167e040570af1fc78ce48f5e930e54981ba909ae
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="39get39-accessor-of-property-39ltpropertynamegt39-is-not-accessible"></a><span data-ttu-id="48b7b-102">&#39;Get &#39;访问器的属性 &#39;&lt;propertyname&gt;&#39; 不可访问</span><span class="sxs-lookup"><span data-stu-id="48b7b-102">&#39;Get&#39; accessor of property &#39;&lt;propertyname&gt;&#39; is not accessible</span></span>
<span data-ttu-id="48b7b-103">语句试图检索属性的值，如果它不具有对该属性的访问`Get`过程。</span><span class="sxs-lookup"><span data-stu-id="48b7b-103">A statement attempts to retrieve the value of a property when it does not have access to the property's `Get` procedure.</span></span>  
  
 <span data-ttu-id="48b7b-104">如果[Get 语句](../../../visual-basic/language-reference/statements/get-statement.md)标记具有限制性更强的访问权限级别比其[属性语句](../../../visual-basic/language-reference/statements/property-statement.md)，尝试读取属性值在以下情况可能会失败：</span><span class="sxs-lookup"><span data-stu-id="48b7b-104">If the [Get Statement](../../../visual-basic/language-reference/statements/get-statement.md) is marked with a more restrictive access level than its [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md), an attempt to read the property value could fail in the following cases:</span></span>  
  
-   <span data-ttu-id="48b7b-105">`Get`语句被标记为[私有](../../../visual-basic/language-reference/modifiers/private.md)，但调用代码以外的类或结构在其中定义该属性。</span><span class="sxs-lookup"><span data-stu-id="48b7b-105">The `Get` statement is marked [Private](../../../visual-basic/language-reference/modifiers/private.md) and the calling code is outside the class or structure in which the property is defined.</span></span>  
  
-   <span data-ttu-id="48b7b-106">`Get`语句被标记为[受保护](../../../visual-basic/language-reference/modifiers/protected.md)，调用代码不在类或结构在其中定义该属性，也不派生类中。</span><span class="sxs-lookup"><span data-stu-id="48b7b-106">The `Get` statement is marked [Protected](../../../visual-basic/language-reference/modifiers/protected.md) and the calling code is not in the class or structure in which the property is defined, nor in a derived class.</span></span>  
  
-   <span data-ttu-id="48b7b-107">`Get`语句被标记为[友元](../../../visual-basic/language-reference/modifiers/friend.md)而调用的代码不在同一程序集在其中定义该属性。</span><span class="sxs-lookup"><span data-stu-id="48b7b-107">The `Get` statement is marked [Friend](../../../visual-basic/language-reference/modifiers/friend.md) and the calling code is not in the same assembly in which the property is defined.</span></span>  
  
 <span data-ttu-id="48b7b-108">**错误 ID:** BC31103</span><span class="sxs-lookup"><span data-stu-id="48b7b-108">**Error ID:** BC31103</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="48b7b-109">更正此错误</span><span class="sxs-lookup"><span data-stu-id="48b7b-109">To correct this error</span></span>  
  
-   <span data-ttu-id="48b7b-110">如果已定义属性的源代码管理，请考虑声明`Get`属性本身的相同访问级别的过程。</span><span class="sxs-lookup"><span data-stu-id="48b7b-110">If you have control of the source code defining the property, consider declaring the `Get` procedure with the same access level as the property itself.</span></span>  
  
-   <span data-ttu-id="48b7b-111">如果你不能定义属性，对源代码的控制或必须限制`Get`过程访问级别的多个属性自身，尝试将读取对区域的代码具有更好地访问的属性值的语句属性。</span><span class="sxs-lookup"><span data-stu-id="48b7b-111">If you do not have control of the source code defining the property, or you must restrict the `Get` procedure access level more than the property itself, try to move the statement that reads the property value to a region of code that has better access to the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48b7b-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="48b7b-112">See Also</span></span>  
 [<span data-ttu-id="48b7b-113">属性过程</span><span class="sxs-lookup"><span data-stu-id="48b7b-113">Property Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)  
 [<span data-ttu-id="48b7b-114">如何：声明具有混合访问级别的属性</span><span class="sxs-lookup"><span data-stu-id="48b7b-114">How to: Declare a Property with Mixed Access Levels</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)
