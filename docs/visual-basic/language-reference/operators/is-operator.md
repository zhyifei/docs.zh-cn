---
title: Is 运算符 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.is
helpviewer_keywords:
- comparison operators [Visual Basic]
- equivalent objects
- TypeOf...Is expression
- Is operator [Visual Basic]
ms.assetid: 8045a6c8-2a83-45b6-ad47-d09a704c656d
ms.openlocfilehash: 8beca1dc8788514224f70cacc5b8ede0974f5230
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33601945"
---
# <a name="is-operator-visual-basic"></a>Is 运算符 (Visual Basic)
比较两个对象引用变量。  
  
## <a name="syntax"></a>语法  
  
```  
result = object1 Is object2  
```  
  
## <a name="parts"></a>部件  
 `result`  
 必须的。 任何`Boolean`值。  
  
 `object1`  
 必须的。 任何`Object`名称。  
  
 `object2`  
 必须的。 任何`Object`名称。  
  
## <a name="remarks"></a>备注  
 `Is`运算符确定两个对象引用是否引用同一对象。 但是，它不执行值的比较。 如果`object1`和`object2`都是指完全相同的对象实例，`result`是`True`; 如果不是这样，`result`是`False`。  
  
 `Is` 也可以用于`TypeOf`关键字使`TypeOf`...`Is`表达式，测试的对象变量是否与数据类型兼容。  
  
> [!NOTE]
>  `Is`关键字还用于[选择...Case 语句](../../../visual-basic/language-reference/statements/select-case-statement.md)。  
  
## <a name="example"></a>示例  
 下面的示例使用`Is`运算符比较的对象引用的对。 结果分配给`Boolean`值表示两个对象是否相同。  
  
 [!code-vb[VbVbalrOperators#27](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/is-operator_1.vb)]  
  
 如前面的示例所示，你可以使用`Is`运算符测试早期绑定和后期绑定对象。  
  
## <a name="see-also"></a>请参阅  
 [TypeOf 运算符](../../../visual-basic/language-reference/operators/typeof-operator.md)  
 [IsNot 运算符](../../../visual-basic/language-reference/operators/isnot-operator.md)  
 [在 Visual Basic 中的比较运算符](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)  
 [Visual Basic 中的运算符优先级](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [按功能列出的运算符](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [运算符和表达式](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
