---
title: AddressOf 运算符 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- AddressOf
- vb.AddressOf
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- addresses, passing to API procedures
ms.assetid: 8105a59d-60d8-4ab5-b221-5899cdfacbf4
ms.openlocfilehash: 4f4f88551b6708ac3d0ee0f0f5bdcbdec1dfaaa9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54721055"
---
# <a name="addressof-operator-visual-basic"></a>AddressOf 运算符 (Visual Basic)
创建引用特定过程的过程委托实例。  
  
## <a name="syntax"></a>语法  
  
```  
AddressOf procedurename  
```  
  
## <a name="parts"></a>部件  
 `procedurename`  
 必需。 指定引用的新创建的过程委托的过程。  
  
## <a name="remarks"></a>备注  
 `AddressOf`运算符创建一个函数委托，指向由指定的函数`procedurename`。 当指定的过程是实例方法然后的函数委托引用在实例和方法。 然后，调用的函数委托时指定实例的指定的方法调用。  
  
 `AddressOf`运算符可以用作委托构造函数的操作数，或可在其中可以由编译器确定委托类型的上下文中。  
  
## <a name="example"></a>示例  
 此示例使用`AddressOf`运算符来指定一个委托来处理`Click`按钮的事件。  
  
 [!code-vb[VbVbalrDelegates#8](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addressof-operator_1.vb)]  
  
## <a name="example"></a>示例  
 下面的示例使用`AddressOf`运算符来指定线程的启动函数。  
  
 [!code-vb[VbVbalrDelegates#9](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addressof-operator_2.vb)]  
  
## <a name="see-also"></a>请参阅
- [Declare 语句](../../../visual-basic/language-reference/statements/declare-statement.md)
- [Function 语句](../../../visual-basic/language-reference/statements/function-statement.md)
- [Sub 语句](../../../visual-basic/language-reference/statements/sub-statement.md)
- [委托](../../../visual-basic/programming-guide/language-features/delegates/index.md)
