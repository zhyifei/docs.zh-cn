---
title: "Is 运算符 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.is
helpviewer_keywords:
- comparison operators [Visual Basic]
- equivalent objects
- TypeOf...Is expression
- Is operator [Visual Basic]
ms.assetid: 8045a6c8-2a83-45b6-ad47-d09a704c656d
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4b1f3f0fa1fd782550c08c816f47b7541399198e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="is-operator-visual-basic"></a>Is 运算符 (Visual Basic)
比较两个对象引用变量。  
  
## <a name="syntax"></a>语法  
  
```  
result = object1 Is object2  
```  
  
## <a name="parts"></a>部件  
 `result`  
 必需。 任何`Boolean`值。  
  
 `object1`  
 必需。 任何`Object`名称。  
  
 `object2`  
 必需。 任何`Object`名称。  
  
## <a name="remarks"></a>备注  
 `Is`运算符确定两个对象引用是否引用同一对象。 但是，它不执行值的比较。 如果`object1`和`object2`都是指完全相同的对象实例，`result`是`True`; 如果不是这样，`result`是`False`。  
  
 `Is`也可以用于`TypeOf`关键字使`TypeOf`...`Is`表达式，测试的对象变量是否与数据类型兼容。  
  
> [!NOTE]
>  `Is`关键字还用于[选择...Case 语句](../../../visual-basic/language-reference/statements/select-case-statement.md)。  
  
## <a name="example"></a>示例  
 下面的示例使用`Is`运算符比较的对象引用的对。 结果分配给`Boolean`值表示两个对象是否相同。  
  
 [!code-vb[VbVbalrOperators#27](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/is-operator_1.vb)]  
  
 如前面的示例所示，你可以使用`Is`运算符测试早期绑定和后期绑定对象。  
  
## <a name="see-also"></a>另请参阅  
 [TypeOf 运算符](../../../visual-basic/language-reference/operators/typeof-operator.md)  
 [IsNot 运算符](../../../visual-basic/language-reference/operators/isnot-operator.md)  
 [在 Visual Basic 中的比较运算符](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)  
 [Visual Basic 中的运算符优先级](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [按功能列出的运算符](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [运算符和表达式](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
