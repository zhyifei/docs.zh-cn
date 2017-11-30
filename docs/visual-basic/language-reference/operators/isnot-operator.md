---
title: "IsNot 运算符 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.isnot
helpviewer_keywords: IsNot operator [Visual Basic]
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 969fdebdf15a1f779075c58616ccd16c64976a35
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="isnot-operator-visual-basic"></a>IsNot 运算符 (Visual Basic)
比较两个对象引用变量。  
  
## <a name="syntax"></a>语法  
  
```  
result = object1 IsNot object2  
```  
  
## <a name="parts"></a>部件  
 `result`  
 必需。 一个 `Boolean` 值。  
  
 `object1`  
 必需。 任何`Object`变量或表达式。  
  
 `object2`  
 必需。 任何`Object`变量或表达式。  
  
## <a name="remarks"></a>备注  
 `IsNot`运算符确定两个对象引用是否引用不同的对象。 但是，它不执行值的比较。 如果`object1`和`object2`都是指完全相同的对象实例，`result`是`False`; 如果不是这样，`result`是`True`。  
  
 `IsNot`截然相反`Is`运算符。 利用`IsNot`是你可以避免繁琐语法与`Not`和`Is`，这可能很难读取。  
  
 你可以使用`Is`和`IsNot`运算符来测试早期绑定和后期绑定对象。  
  
> [!NOTE]
>  `IsNot`运算符不能用于比较表达式从返回`TypeOf`运算符。 相反，你必须使用`Not`和`Is`运算符。  
  
## <a name="example"></a>示例  
 下面的代码示例使用这两个`Is`运算符和`IsNot`运算符，以完成相同的比较。  
  
 [!code-vb[VbVbalrOperators#29](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/isnot-operator_1.vb)]  
  
## <a name="see-also"></a>另请参阅  
 [Is 运算符](../../../visual-basic/language-reference/operators/is-operator.md)  
 [TypeOf 运算符](../../../visual-basic/language-reference/operators/typeof-operator.md)  
 [Visual Basic 中的运算符优先级](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [如何：测试两个对象是否相同](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)
