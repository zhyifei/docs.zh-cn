---
title: "AddressOf 运算符 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- AddressOf
- vb.AddressOf
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- addresses, passing to API procedures
ms.assetid: 8105a59d-60d8-4ab5-b221-5899cdfacbf4
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 52560a2d9071373fd28f7aad2e485da08324656d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="addressof-operator-visual-basic"></a>AddressOf 运算符 (Visual Basic)
创建引用特定过程的过程委托实例。  
  
## <a name="syntax"></a>语法  
  
```  
AddressOf procedurename  
```  
  
## <a name="parts"></a>部件  
 `procedurename`  
 必需。 指定要由新创建的过程委托引用的过程。  
  
## <a name="remarks"></a>备注  
 `AddressOf`运算符创建一个函数委托，指向由指定的函数`procedurename`。 当指定的过程是实例方法然后的函数委托引用实例和方法。 然后，调用的函数委托时调用的指定实例的指定的方法。  
  
 `AddressOf`运算符可以用作委托构造函数的操作数，或它可在其中可以由编译器确定委托的类型的上下文中。  
  
## <a name="example"></a>示例  
 此示例使用`AddressOf`运算符指定一个委托来处理`Click`的按钮的事件。  
  
 [!code-vb[VbVbalrDelegates#8](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addressof-operator_1.vb)]  
  
## <a name="example"></a>示例  
 下面的示例使用`AddressOf`运算符指定线程的启动函数。  
  
 [!code-vb[VbVbalrDelegates#9](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addressof-operator_2.vb)]  
  
## <a name="see-also"></a>另请参阅  
 [Declare 语句](../../../visual-basic/language-reference/statements/declare-statement.md)  
 [Function 语句](../../../visual-basic/language-reference/statements/function-statement.md)  
 [Sub 语句](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [委托](../../../visual-basic/programming-guide/language-features/delegates/index.md)
