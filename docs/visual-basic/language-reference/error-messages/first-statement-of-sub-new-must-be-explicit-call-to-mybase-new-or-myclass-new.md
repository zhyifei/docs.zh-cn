---
title: 此第一条语句&#39;Sub New&#39;必须是显式调用&#39;MyBase.New&#39;或&#39;MyClass.New&#39;因为&#39; &lt;constructorname&gt; &#39;在基类中&#39;&lt;a m e&gt; &#39;的&#39; &lt;derivedclassname&gt; &#39;标记为已过时： &#39; &lt;errormessage&gt;&#39;
ms.date: 07/20/2015
f1_keywords:
- vbc30920
- bc30920
helpviewer_keywords:
- BC30920
ms.assetid: e47dc755-4294-4368-b813-2177b7677957
ms.openlocfilehash: 9d07a68fd8d9790178427c512375323f23f46772
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54566762"
---
# <a name="first-statement-of-this-39sub-new39-must-be-an-explicit-call-to-39mybasenew39-or-39myclassnew39-because-the-39ltconstructornamegt39-in-the-base-class-39ltbaseclassnamegt39-of-39ltderivedclassnamegt39-is-marked-obsolete-39lterrormessagegt39"></a><span data-ttu-id="0fb38-102">此第一条语句&#39;Sub New&#39;必须是显式调用&#39;MyBase.New&#39;或&#39;MyClass.New&#39;因为&#39; &lt;constructorname&gt; &#39;在基类中&#39;&lt;a m e&gt; &#39;的&#39; &lt;derivedclassname&gt; &#39;标记为已过时： &#39; &lt;errormessage&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="0fb38-102">First statement of this &#39;Sub New&#39; must be an explicit call to &#39;MyBase.New&#39; or &#39;MyClass.New&#39; because the &#39;&lt;constructorname&gt;&#39; in the base class &#39;&lt;baseclassname&gt;&#39; of &#39;&lt;derivedclassname&gt;&#39; is marked obsolete: &#39;&lt;errormessage&gt;&#39;</span></span>
<span data-ttu-id="0fb38-103">类构造函数不显式调用基类构造函数，并且隐式基类构造函数标有 <xref:System.ObsoleteAttribute> 特性和将其视为错误的指令。</span><span class="sxs-lookup"><span data-stu-id="0fb38-103">A class constructor does not explicitly call a base class constructor, and the implicit base class constructor is marked with the <xref:System.ObsoleteAttribute> attribute and the directive to treat it as an error.</span></span>  
  
 <span data-ttu-id="0fb38-104">当在派生的类构造函数未调用基类构造函数时，Visual Basic 将尝试生成对无参数基类构造函数的隐式调用。</span><span class="sxs-lookup"><span data-stu-id="0fb38-104">When a derived class constructor does not call a base class constructor, Visual Basic attempts to generate an implicit call to a parameterless base class constructor.</span></span> <span data-ttu-id="0fb38-105">如果可以调用不带参数的基类中没有任何可访问的构造函数，Visual Basic 不能生成的隐式调用。</span><span class="sxs-lookup"><span data-stu-id="0fb38-105">If there is no accessible constructor in the base class that can be called without arguments, Visual Basic cannot generate an implicit call.</span></span> <span data-ttu-id="0fb38-106">在这种情况下，所需的构造函数标有<xref:System.ObsoleteAttribute>属性，因此 Visual Basic 不能调用它。</span><span class="sxs-lookup"><span data-stu-id="0fb38-106">In this case, the required constructor is marked with the <xref:System.ObsoleteAttribute> attribute, so Visual Basic cannot call it.</span></span>  
  
 <span data-ttu-id="0fb38-107">可以通过将 <xref:System.ObsoleteAttribute> 应用于任意编程元素，将其标记为不再使用。</span><span class="sxs-lookup"><span data-stu-id="0fb38-107">You can mark any programming element as being no longer in use by applying <xref:System.ObsoleteAttribute> to it.</span></span> <span data-ttu-id="0fb38-108">如果执行此操作，则可以将特性的 <xref:System.ObsoleteAttribute.IsError%2A> 属性设置为 `True` 或 `False`。</span><span class="sxs-lookup"><span data-stu-id="0fb38-108">If you do this, you can set the attribute's <xref:System.ObsoleteAttribute.IsError%2A> property to either `True` or `False`.</span></span> <span data-ttu-id="0fb38-109">如果设置为 `True`，则编译器将尝试使用该元素的操作视为错误。</span><span class="sxs-lookup"><span data-stu-id="0fb38-109">If you set it to `True`, the compiler treats an attempt to use the element as an error.</span></span> <span data-ttu-id="0fb38-110">如果设置为 `False`，或让它默认为 `False`，则编译器会在尝试使用该元素时发出警告。</span><span class="sxs-lookup"><span data-stu-id="0fb38-110">If you set it to `False`, or let it default to `False`, the compiler issues a warning if there is an attempt to use the element.</span></span>  
  
 <span data-ttu-id="0fb38-111">**错误 ID:** BC30920</span><span class="sxs-lookup"><span data-stu-id="0fb38-111">**Error ID:** BC30920</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="0fb38-112">更正此错误</span><span class="sxs-lookup"><span data-stu-id="0fb38-112">To correct this error</span></span>  
  
1.  <span data-ttu-id="0fb38-113">检查引用的错误信息并采取相应的操作。</span><span class="sxs-lookup"><span data-stu-id="0fb38-113">Examine the quoted error message and take appropriate action.</span></span>  
  
2.  <span data-ttu-id="0fb38-114">将对 `MyBase.New()` 或 `MyClass.New()` 的调用包括为派生类中 `Sub New` 的第一个语句。</span><span class="sxs-lookup"><span data-stu-id="0fb38-114">Include a call to `MyBase.New()` or `MyClass.New()` as the first statement of the `Sub New` in the derived class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fb38-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="0fb38-115">See also</span></span>
- [<span data-ttu-id="0fb38-116">属性概述</span><span class="sxs-lookup"><span data-stu-id="0fb38-116">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)

