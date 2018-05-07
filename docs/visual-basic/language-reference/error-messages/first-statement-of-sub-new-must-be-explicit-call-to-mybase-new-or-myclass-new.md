---
title: 此第一个语句&#39;Sub New&#39;必须显式调用&#39;MyBase.New&#39;或&#39;MyClass.New&#39;因为&#39; &lt;n a m e&gt; &#39;基类中&#39;&lt;n a m e&gt; &#39;的&#39; &lt;derivedclassname&gt; &#39;标记为已过时： &#39; &lt;errormessage&gt;&#39;
ms.date: 07/20/2015
f1_keywords:
- vbc30920
- bc30920
helpviewer_keywords:
- BC30920
ms.assetid: e47dc755-4294-4368-b813-2177b7677957
ms.openlocfilehash: dbce2a9edcc38ff137cb7ec0c97e5c259c0a0979
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="first-statement-of-this-39sub-new39-must-be-an-explicit-call-to-39mybasenew39-or-39myclassnew39-because-the-39ltconstructornamegt39-in-the-base-class-39ltbaseclassnamegt39-of-39ltderivedclassnamegt39-is-marked-obsolete-39lterrormessagegt39"></a>此第一个语句&#39;Sub New&#39;必须显式调用&#39;MyBase.New&#39;或&#39;MyClass.New&#39;因为&#39; &lt;n a m e&gt; &#39;基类中&#39;&lt;n a m e&gt; &#39;的&#39; &lt;derivedclassname&gt; &#39;标记为已过时： &#39; &lt;errormessage&gt;&#39;
类构造函数不显式调用基类构造函数，并且隐式基类构造函数标有 <xref:System.ObsoleteAttribute> 特性和将其视为错误的指令。  
  
 当派生的类构造函数不调用基类构造函数时，Visual Basic 会尝试生成对无参数基类构造函数的隐式调用。 如果可以无需参数调用基类中没有任何可访问的构造函数，Visual Basic 无法生成隐式调用。 在这种情况下，将所需的构造函数标记为<xref:System.ObsoleteAttribute>特性，因此 Visual Basic 不能调用它。  
  
 可以通过将 <xref:System.ObsoleteAttribute> 应用于任意编程元素，将其标记为不再使用。 如果执行此操作，则可以将特性的 <xref:System.ObsoleteAttribute.IsError%2A> 属性设置为 `True` 或 `False`。 如果设置为 `True`，则编译器将尝试使用该元素的操作视为错误。 如果设置为 `False`，或让它默认为 `False`，则编译器会在尝试使用该元素时发出警告。  
  
 **错误 ID:** BC30920  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  检查引用的错误信息并采取相应的操作。  
  
2.  将对 `MyBase.New()` 或 `MyClass.New()` 的调用包括为派生类中 `Sub New` 的第一个语句。  
  
## <a name="see-also"></a>请参阅  
 [属性概述](../../../visual-basic/programming-guide/concepts/attributes/index.md)
 
