---
title: 结束&lt;关键字&gt;语句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.EndDefinition
helpviewer_keywords:
- End keyword [Visual Basic]
ms.assetid: 42d6e088-ab0f-4cda-88e8-fdce3e5fcf4f
ms.openlocfilehash: 8137434bfd8c26144d78b1761b784cdba4894eaf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33605259"
---
# <a name="end-ltkeywordgt-statement-visual-basic"></a>结束&lt;关键字&gt;语句 (Visual Basic)
在后面带有其他关键字，终止引起该关键字的语句块的定义。  
  
## <a name="syntax"></a>语法  
  
```  
End AddHandler  
End Class   
End Enum   
End Event   
End Function   
End Get   
End If   
End Interface   
End Module   
End Namespace   
End Operator   
End Property   
End RaiseEvent  
End RemoveHandler  
End Select   
End Set   
End Structure   
End Sub   
End SyncLock   
End Try   
End While   
End With  
```  
  
## <a name="parts"></a>部件  
 `End`  
 必须的。 终止编程元素的定义。  
  
 `AddHandler`  
 必选`AddHandler`访问器是匹配的开始`AddHandler`中自定义语句[Event 语句](../../../visual-basic/language-reference/statements/event-statement.md)。  
  
 `Class`  
 必选的类定义是匹配的开始[类语句](../../../visual-basic/language-reference/statements/class-statement.md)。  
  
 `Enum`  
 必选枚举定义是匹配的开始[Enum 语句](../../../visual-basic/language-reference/statements/enum-statement.md)。  
  
 `Event`  
 必选`Custom`是匹配的开始事件定义[Event 语句](../../../visual-basic/language-reference/statements/event-statement.md)。  
  
 `Function`  
 必选`Function`过程定义是匹配的开始[Function 语句](../../../visual-basic/language-reference/statements/function-statement.md)。 如果执行时遇到`End``Function`语句，控制权返回给调用代码。  
  
 `Get`  
 必选`Property`过程定义是匹配的开始[Get 语句](../../../visual-basic/language-reference/statements/get-statement.md)。 如果执行时遇到`End``Get`语句，控制权返回给请求的属性值的语句。  
  
 `If`  
 必选`If`...`Then`...`Else`阻止定义是匹配的开始`If`语句。 请参阅[如果...然后...Else 语句](../../../visual-basic/language-reference/statements/if-then-else-statement.md)。  
  
 `Interface`  
 必选开始是匹配的接口定义[接口语句](../../../visual-basic/language-reference/statements/interface-statement.md)。  
  
 `Module`  
 必选是匹配的开始的模块定义[模块语句](../../../visual-basic/language-reference/statements/module-statement.md)。  
  
 `Namespace`  
 必选命名空间定义是匹配的开始[Namespace 语句](../../../visual-basic/language-reference/statements/namespace-statement.md)。  
  
 `Operator`  
 必选开始是匹配的运算符定义[Operator 语句](../../../visual-basic/language-reference/statements/operator-statement.md)。  
  
 `Property`  
 必选开始是匹配的属性定义[属性语句](../../../visual-basic/language-reference/statements/property-statement.md)。  
  
 `RaiseEvent`  
 必选`RaiseEvent`访问器是匹配的开始`RaiseEvent`中自定义语句[Event 语句](../../../visual-basic/language-reference/statements/event-statement.md)。  
  
 `RemoveHandler`  
 必选`RemoveHandler`访问器是匹配的开始`RemoveHandler`中自定义语句[Event 语句](../../../visual-basic/language-reference/statements/event-statement.md)。  
  
 `Select`  
 必选`Select`...`Case`阻止定义是匹配的开始`Select`语句。 请参阅[选择...Case 语句](../../../visual-basic/language-reference/statements/select-case-statement.md)。  
  
 `Set`  
 必选`Property`过程定义是匹配的开始[Set 语句](../../../visual-basic/language-reference/statements/set-statement.md)。 如果执行时遇到`End``Set`语句，控制权返回给语句设置该属性的值。  
  
 `Structure`  
 必选是匹配的开始的结构定义[Structure 语句](../../../visual-basic/language-reference/statements/structure-statement.md)。  
  
 `Sub`  
 必选`Sub`过程定义是匹配的开始[Sub 语句](../../../visual-basic/language-reference/statements/sub-statement.md)。 如果执行时遇到`End``Sub`语句，控制权返回给调用代码。  
  
 `SyncLock`  
 必选`SyncLock`阻止定义是匹配的开始`SyncLock`语句。 请参阅[SyncLock 语句](../../../visual-basic/language-reference/statements/synclock-statement.md)。  
  
 `Try`  
 必选`Try`...`Catch`...`Finally`阻止定义是匹配的开始`Try`语句。 请参阅[重试...Catch...Finally 语句](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)。  
  
 `While`  
 必选`While`循环定义是匹配的开始`While`语句。 请参阅[时...While 语句结束](../../../visual-basic/language-reference/statements/while-end-while-statement.md)。  
  
 `With`  
 必选`With`阻止定义是匹配的开始`With`语句。 请参阅[与...使用语句结束](../../../visual-basic/language-reference/statements/with-end-with-statement.md)。  
  
## <a name="remarks"></a>备注  
 [End 语句](../../../visual-basic/language-reference/statements/end-statement.md)，没有其他关键字时，执行会立即终止。  
  
 当跟在数字符号 (`#`)，则`End`关键字终止由相应的指令引入的预处理块。  
  
 `#End`  
 必须的。 终止预处理块的定义。  
  
 `#ExternalSource`  
 必选开始是匹配的外部源块[#ExternalSource 指令](../../../visual-basic/language-reference/directives/externalsource-directive.md)。  
  
 `#If`  
 必选开始是匹配的条件编译块`#If`指令。 请参阅[#If......#Else 指令](../../../visual-basic/language-reference/directives/if-then-else-directives.md)。  
  
 `#Region`  
 必选开始是匹配的源区域块[#Region 指令](../../../visual-basic/language-reference/directives/region-directive.md)。  
  
## <a name="smart-device-developer-notes"></a>智能设备的开发人员说明  
 `End`不支持语句，而无需其他关键字。  
  
## <a name="see-also"></a>请参阅  
 [End 语句](../../../visual-basic/language-reference/statements/end-statement.md)
