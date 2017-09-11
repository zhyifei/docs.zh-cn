---
title: "此 Sub New 的第一条语句必须是对 MyBase.New 或 MyClass.New 的显式调用，因为&lt;constructorname&gt;in 基类&lt;baseclassname&gt;of&lt;derivedclassname&gt;标记为已过时:&lt;errormessage&gt;&quot; |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30920
- bc30920
dev_langs:
- VB
helpviewer_keywords:
- BC30920
ms.assetid: e47dc755-4294-4368-b813-2177b7677957
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: d46192bc9a9f2807f56cbdd7bdd4fd21f6c9a7b0
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="first-statement-of-this-39sub-new39-must-be-an-explicit-call-to-39mybasenew39-or-39myclassnew39-because-the-39ltconstructornamegt39-in-the-base-class-39ltbaseclassnamegt39-of-39ltderivedclassnamegt39-is-marked-obsolete-39lterrormessagegt39"></a><span data-ttu-id="37ce6-102">此 Sub New 的第一条语句必须是对 MyBase.New 或 MyClass.New 的显式调用，因为&lt;constructorname&gt;in 基类&lt;baseclassname&gt;of&lt;derivedclassname&gt;标记为已过时:&lt;errormessage&gt;</span><span class="sxs-lookup"><span data-stu-id="37ce6-102">First statement of this &#39;Sub New&#39; must be an explicit call to &#39;MyBase.New&#39; or &#39;MyClass.New&#39; because the &#39;&lt;constructorname&gt;&#39; in the base class &#39;&lt;baseclassname&gt;&#39; of &#39;&lt;derivedclassname&gt;&#39; is marked obsolete: &#39;&lt;errormessage&gt;&#39;</span></span>
<span data-ttu-id="37ce6-103">类构造函数不显式调用基类构造函数，并且隐式基类构造函数标有<xref:System.ObsoleteAttribute>特性，指令会将其视为错误。</xref:System.ObsoleteAttribute></span><span class="sxs-lookup"><span data-stu-id="37ce6-103">A class constructor does not explicitly call a base class constructor, and the implicit base class constructor is marked with the <xref:System.ObsoleteAttribute> attribute and the directive to treat it as an error.</span></span>  
  
 <span data-ttu-id="37ce6-104">在派生的类构造函数未调用基类构造函数，[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]尝试生成隐式调用无参数的基类构造函数。</span><span class="sxs-lookup"><span data-stu-id="37ce6-104">When a derived class constructor does not call a base class constructor, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] attempts to generate an implicit call to a parameterless base class constructor.</span></span> <span data-ttu-id="37ce6-105">如果没有可访问的构造函数可以调用不带参数，基类中[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]无法生成的隐式调用。</span><span class="sxs-lookup"><span data-stu-id="37ce6-105">If there is no accessible constructor in the base class that can be called without arguments, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] cannot generate an implicit call.</span></span> <span data-ttu-id="37ce6-106">在这种情况下，需要的构造函数标有<xref:System.ObsoleteAttribute>属性，因此[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]不能调用它。</xref:System.ObsoleteAttribute></span><span class="sxs-lookup"><span data-stu-id="37ce6-106">In this case, the required constructor is marked with the <xref:System.ObsoleteAttribute> attribute, so [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] cannot call it.</span></span>  
  
 <span data-ttu-id="37ce6-107">您可以将标记为不再使用通过将应用<xref:System.ObsoleteAttribute>于它。</xref:System.ObsoleteAttribute>所有编程元素</span><span class="sxs-lookup"><span data-stu-id="37ce6-107">You can mark any programming element as being no longer in use by applying <xref:System.ObsoleteAttribute> to it.</span></span> <span data-ttu-id="37ce6-108">如果执行此操作，则可以设置该属性的<xref:System.ObsoleteAttribute.IsError%2A>属性设置为任何一个`True`或`False`。</xref:System.ObsoleteAttribute.IsError%2A></span><span class="sxs-lookup"><span data-stu-id="37ce6-108">If you do this, you can set the attribute's <xref:System.ObsoleteAttribute.IsError%2A> property to either `True` or `False`.</span></span> <span data-ttu-id="37ce6-109">如果设置为 `True`，则编译器将尝试使用该元素的操作视为错误。</span><span class="sxs-lookup"><span data-stu-id="37ce6-109">If you set it to `True`, the compiler treats an attempt to use the element as an error.</span></span> <span data-ttu-id="37ce6-110">如果设置为 `False`，或将其默认为 `False`，则编译器会在有操作尝试使用该元素时发出警告。</span><span class="sxs-lookup"><span data-stu-id="37ce6-110">If you set it to `False`, or let it default to `False`, the compiler issues a warning if there is an attempt to use the element.</span></span>  
  
 <span data-ttu-id="37ce6-111">**错误 ID:** BC30920</span><span class="sxs-lookup"><span data-stu-id="37ce6-111">**Error ID:** BC30920</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="37ce6-112">更正此错误</span><span class="sxs-lookup"><span data-stu-id="37ce6-112">To correct this error</span></span>  
  
1.  <span data-ttu-id="37ce6-113">检查引用的错误信息并采取相应的操作。</span><span class="sxs-lookup"><span data-stu-id="37ce6-113">Examine the quoted error message and take appropriate action.</span></span>  
  
2.  <span data-ttu-id="37ce6-114">将对 `MyBase.New()` 或 `MyClass.New()` 的调用包括为派生类中 `Sub New` 的第一个语句。</span><span class="sxs-lookup"><span data-stu-id="37ce6-114">Include a call to `MyBase.New()` or `MyClass.New()` as the first statement of the `Sub New` in the derived class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37ce6-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="37ce6-115">See Also</span></span>  
 [<span data-ttu-id="37ce6-116">属性概述</span><span class="sxs-lookup"><span data-stu-id="37ce6-116">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)
 
