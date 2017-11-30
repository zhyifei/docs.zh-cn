---
title: "Visual Basic 中的运算符优先级"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- arithmetic operators [Visual Basic], precedence
- operator precedence
- logical operators [Visual Basic], precedence
- operators [Visual Basic], associativity
- operators [Visual Basic], resolution
- associativity of operators [Visual Basic]
- operators [Visual Basic], precedence
- precedence [Visual Basic], of operators
- comparison operators [Visual Basic], precedence
- math operators [Visual Basic]
- order of precedence
ms.assetid: cbbdb282-f572-458e-a520-008a675f8063
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6c0fb466b404cafdd4b91d061971fd683375c715
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="operator-precedence-in-visual-basic"></a>Visual Basic 中的运算符优先级
如果在表达式中出现多个运算，计算和解析按预设的顺序调用每个部分*运算符优先级*。  
  
## <a name="precedence-rules"></a>优先规则  
 当表达式包含从多个类别的运算符时，它们会根据下列规则进行评估：  
  
-   算术运算符和串联运算符具有的下一节中所述的优先顺序，都具有优先级高于比较、 逻辑和按位运算符。  
  
-   所有比较运算符都具有相同的优先级，以及所有都具有优先级高于逻辑运算符和位运算符，但优先级低于算术和串联运算符。  
  
-   逻辑和按位运算符具有的下一节中所述的优先顺序，都具有较低的优先级比算术、 串联和比较运算符。  
  
-   具有相等的优先级的运算符从左向右进行计算右侧表达式中出现的顺序。  
  
## <a name="precedence-order"></a>优先顺序  
 按以下优先顺序计算运算符：  
  
### <a name="await-operator"></a>Await 运算符  
 await  
  
### <a name="arithmetic-and-concatenation-operators"></a>算术运算符和串联运算符  
 求幂 (`^`)  
  
 一元标识和求反 (`+`， `–`)  
  
 乘法和浮点除法运算 (`*`， `/`)  
  
 整数除法 (`\`)  
  
 取模算术 (`Mod`)  
  
 加法和减法 (`+`， `–`)  
  
 字符串串联 (`&`)  
  
 算术移位 (`<<`， `>>`)  
  
### <a name="comparison-operators"></a>比较运算符  
 所有比较运算符 (`=`， `<>`， `<`， `<=`， `>`， `>=`， `Is`， `IsNot`， `Like`， `TypeOf`...`Is`)  
  
### <a name="logical-and-bitwise-operators"></a>逻辑和按位运算符  
 求反 (`Not`)  
  
 结合使用 (`And`， `AndAlso`)  
  
 包含析取 (`Or`， `OrElse`)  
  
 异或结果 (`Xor`)  
  
### <a name="comments"></a>注释  
 `=`运算符是仅相等性比较运算符，而不是赋值运算符。  
  
 字符串串联运算符 (`&`) 不是算术的运算符，但它在优先级方面与算术运算符一组。  
  
 `Is`和`IsNot`运算符是对象的引用比较运算符。 它们不比较两个对象的值它们检查仅以确定是否两个对象变量引用同一对象实例。  
  
## <a name="associativity"></a>结合性  
 当相等的优先级的运算符一起出现在表达式中，例如乘法和除法，编译器将评估每个操作，当它从左到右进行遇到。 下面的示例阐释了这一点。  
  
```  
Dim n1 As Integer = 96 / 8 / 4  
Dim n2 As Integer = (96 / 8) / 4  
Dim n3 As Integer = 96 / (8 / 4)  
```  
  
 第一个表达式的计算结果除法 96 / 8 （这会导致 12），然后除法 12 / 4，结果为 3。 因为编译器将评估的操作`n1`从左到右，评估时相同为显式指明该顺序`n2`。 同时`n1`和`n2`具有三个结果。 与此相反，`n3`的结果为 48，是因为圆括号强制编译器可以计算 8 / 4 第一个。  
  
 由于此行为，运算符被认为是*左结合运算符*中[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]。  
  
## <a name="overriding-precedence-and-associativity"></a>重写优先级和关联性  
 可以使用括号来强制先于其他计算的表达式的某些部分。 这会重写的优先顺序和左的关联性。 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]始终执行括在括号之前以外的操作。 但是，在括号内，这样可保持普通优先级和关联性，除非你使用在括号内的括号。 下面的示例阐释了这一点。  
  
```  
Dim a, b, c, d, e, f, g As Double  
a = 8.0  
b = 3.0  
c = 4.0  
d = 2.0  
e = 1.0  
f = a - b + c / d * e  
' The preceding line sets f to 7.0. Because of natural operator   
' precedence and associativity, it is exactly equivalent to the   
' following line.  
f = (a - b) + ((c / d) * e)  
' The following line overrides the natural operator precedence   
' and left associativity.  
g = (a - (b + c)) / (d * e)  
' The preceding line sets g to 0.5.  
```  
  
## <a name="see-also"></a>另请参阅  
 [= 运算符](../../../visual-basic/language-reference/operators/assignment-operator.md)  
 [Is 运算符](../../../visual-basic/language-reference/operators/is-operator.md)  
 [IsNot 运算符](../../../visual-basic/language-reference/operators/isnot-operator.md)  
 [Like 运算符](../../../visual-basic/language-reference/operators/like-operator.md)  
 [TypeOf 运算符](../../../visual-basic/language-reference/operators/typeof-operator.md)  
 [Await 运算符](../../../visual-basic/language-reference/operators/await-operator.md)  
 [按功能列出的运算符](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [运算符和表达式](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
