---
title: "这 &#39; 第一条语句新的子 &#39;必须显式调用 &#39;MyBase.New &#39;或 &#39;MyClass.New &#39;因为 &#39;&lt;n a m e&gt;&#39; 中的基类 &#39;&lt;n a m e&gt;&#39; &#39;&lt;derivedclassname&gt;&#39; 标记为已过时： &#39;&lt;errormessage&gt;&#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30920
- bc30920
helpviewer_keywords: BC30920
ms.assetid: e47dc755-4294-4368-b813-2177b7677957
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8882acd947251d85804fbefd54267ce078e31b95
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="first-statement-of-this-39sub-new39-must-be-an-explicit-call-to-39mybasenew39-or-39myclassnew39-because-the-39ltconstructornamegt39-in-the-base-class-39ltbaseclassnamegt39-of-39ltderivedclassnamegt39-is-marked-obsolete-39lterrormessagegt39"></a>这 &#39; 第一条语句新的子 &#39;必须显式调用 &#39;MyBase.New &#39;或 &#39;MyClass.New &#39;因为 &#39;&lt;n a m e&gt;&#39; 中的基类 &#39;&lt;n a m e&gt;&#39; &#39;&lt;derivedclassname&gt;&#39; 标记为已过时： &#39;&lt;errormessage&gt;&#39;
类构造函数不显式调用基类构造函数，并且隐式基类构造函数标有 <xref:System.ObsoleteAttribute> 特性和将其视为错误的指令。  
  
 当派生的类构造函数不调用基类构造函数时， [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 会尝试生成对无参数基类构造函数的隐式调用。 如果基类中没有无需参数即可调用的构造函数，则 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 无法生成隐式调用。 在这种情况下，所需的构造函数标记有 <xref:System.ObsoleteAttribute> 特性，因此 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 不能调用它。  
  
 可以通过将 <xref:System.ObsoleteAttribute> 应用于任意编程元素，将其标记为不再使用。 如果执行此操作，则可以将特性的 <xref:System.ObsoleteAttribute.IsError%2A> 属性设置为 `True` 或 `False`。 如果设置为 `True`，则编译器将尝试使用该元素的操作视为错误。 如果设置为 `False`，或将其默认为 `False`，则编译器会在有操作尝试使用该元素时发出警告。  
  
 **错误 ID:** BC30920  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  检查引用的错误信息并采取相应的操作。  
  
2.  将对 `MyBase.New()` 或 `MyClass.New()` 的调用包括为派生类中 `Sub New` 的第一个语句。  
  
## <a name="see-also"></a>另请参阅  
 [属性概述](../../../visual-basic/programming-guide/concepts/attributes/index.md)
 
