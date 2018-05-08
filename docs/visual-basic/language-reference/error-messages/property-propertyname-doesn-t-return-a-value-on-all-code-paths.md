---
title: 属性&#39; &lt;propertyname&gt; &#39;不&#39;t 在所有代码路径上返回值
ms.date: 07/20/2015
f1_keywords:
- bc42107
- vbc42107
helpviewer_keywords:
- BC42107
ms.assetid: 06800966-9c3b-4844-9f13-83ac95607d32
ms.openlocfilehash: 72bc7e45cadd2528f29c88bf6e80ee5f381052dd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="property-39ltpropertynamegt39-doesn39t-return-a-value-on-all-code-paths"></a>属性&#39; &lt;propertyname&gt; &#39;不&#39;t 在所有代码路径上返回值
属性\<属性名称 > 没有在所有代码路径上返回一个值。 使用该结果时，可能会在运行时发生 null 引用异常。  
  
 属性`Get`过程有至少一个通过其代码不会返回一个值的可能路径。  
  
 你可以从属性返回一个值`Get`处于以下任一过程：  
  
-   将值分配到属性名称，然后执行`Exit Property`语句。  
  
-   将值分配到属性名称，然后执行`End Get`语句。  
  
-   包括中的值[Return 语句](../../../visual-basic/language-reference/statements/return-statement.md)。  
  
 如果控制权传递给`Exit Property`或`End Get`并且你具有未分配到属性名称的任何值`Get`过程返回的属性的数据类型的默认值。 有关详细信息，请参阅"行为" [Function 语句](../../../visual-basic/language-reference/statements/function-statement.md)。  
  
 默认情况下，此消息是一个警告。 有关隐藏警告或将警告视为错误的详细信息，请参阅[在 Visual Basic 中的配置警告](/visualstudio/ide/configuring-warnings-in-visual-basic)。  
  
 **错误 ID:** BC42107  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   请检查控制流逻辑并确保导致返回每个语句之前赋值。  
  
     很容易地保证每个返回从过程返回一个值，如果始终使用`Return`语句。 如果你这样做，请在之前的最后一个语句`End Get`应`Return`语句。  
  
## <a name="see-also"></a>请参阅  
 [属性过程](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)  
 [Property 语句](../../../visual-basic/language-reference/statements/property-statement.md)  
 [Get 语句](../../../visual-basic/language-reference/statements/get-statement.md)
