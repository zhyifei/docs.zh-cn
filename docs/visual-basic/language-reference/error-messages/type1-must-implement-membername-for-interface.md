---
title: '&lt;type1&gt;&#39;&lt;typename&gt;&#39; 必须实现 &#39;&lt;membername&gt;&#39; 对于接口 &#39;&lt;interfacename&gt;&#39;'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30154
- bc30154
helpviewer_keywords:
- BC30154
ms.assetid: 259afdfa-3608-4760-adcb-88ec0da5020d
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 05e0229d0259c519d4db265c017a5040b425c79a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="lttype1gt39lttypenamegt39-must-implement-39ltmembernamegt39-for-interface-39ltinterfacenamegt39"></a>&lt;type1&gt;&#39;&lt;typename&gt;&#39; 必须实现 &#39;&lt;membername&gt;&#39; 对于接口 &#39;&lt;interfacename&gt;&#39;
\<类型名称 > 必须实现\<成员名称 > 接口\<n a m e >。 实现属性必须拥有匹配的 ReadOnly / WriteOnly 说明符。  
  
 类或结构实现接口声明，但不实现过程、 属性或由接口定义的事件。 必须实现该接口的每个成员。  
  
 **错误 ID:** BC30154  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  声明具有相同的名称和签名在接口中定义的成员。 请务必包括至少`End Function`， `End Sub`，或`End Property`语句。  
  
2.  添加`Implements`子句的末尾`Function`， `Sub`， `Property`，或`Event`语句。 例如：  
  
    ```  
    Public Event ItHappened() Implements IBaseInterface.ItHappened  
    ```  
  
3.  在实施一个属性，请确保`ReadOnly`或`WriteOnly`中与接口定义相同的方式使用。  
  
4.  当实现一个属性，将声明`Get`和`Set`于相应过程。  
  
## <a name="see-also"></a>另请参阅  
 [Implements 语句](../../../visual-basic/language-reference/statements/implements-statement.md)  
 [接口](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
