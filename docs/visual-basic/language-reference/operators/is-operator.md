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
ms.openlocfilehash: a5481a9bce01e84ce4f078335c8cd15a747a3c51
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917220"
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
 必需。 任意`Object`名称。  
  
 `object2`  
 必需。 任意`Object`名称。  
  
## <a name="remarks"></a>备注  
 `Is`运算符确定两个对象引用是否引用同一对象。 但是, 它不会执行值比较。 如果`object1`和`True` `result` `result` `False`都引用完全相同的对象实例, 则为; 如果不是, 则为; 如果不是, 则为。 `object2`  
  
 `Is`还可与`TypeOf`关键字一起使用来`TypeOf`生成 .。。`Is`表达式, 用于测试对象变量是否与数据类型兼容。  
  
> [!NOTE]
> `Is`关键字还用于[Select .。。Case 语句](../../../visual-basic/language-reference/statements/select-case-statement.md)。  
  
## <a name="example"></a>示例  
 下面的示例使用`Is`运算符比较对象引用对。 将结果分配给一个`Boolean`值, 该值表示两个对象是否相同。  
  
 [!code-vb[VbVbalrOperators#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#27)]  
  
 如前面的示例所示, 可以使用`Is`运算符来测试早期绑定和晚期绑定对象。  
  
## <a name="see-also"></a>请参阅

- [TypeOf 运算符](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [IsNot 运算符](../../../visual-basic/language-reference/operators/isnot-operator.md)
- [Visual Basic 中的比较运算符](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Visual Basic 中的运算符优先级](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [按功能列出的运算符](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [运算符和表达式](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
