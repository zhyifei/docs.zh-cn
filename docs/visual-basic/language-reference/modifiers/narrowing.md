---
title: Narrowing (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.narrowing
helpviewer_keywords:
- conversions [Visual Basic], type
- type conversion [Visual Basic]
- conversions [Visual Basic], data type
- Narrowing keyword [Visual Basic]
- data type conversion [Visual Basic]
ms.assetid: a207ee91-aca4-4771-b4e2-713f029bf2bb
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 50116c6212e919d4b9b35fc933d80dee14bd4ecf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="narrowing-visual-basic"></a>Narrowing (Visual Basic)
指示转换运算符 (`CType`) 将一个类或结构转换为可能无法保存某些可能的值的原始类或结构类型。  
  
## <a name="converting-with-the-narrowing-keyword"></a>转换使用收缩关键字  
 必须指定转换过程`Public Shared`除了`Narrowing`。  
  
 收缩转换执行并非总是在运行时，成功，失败或导致数据丢失。 示例包括`Long`到`Integer`，`String`到`Date`，以及从基类型转换为派生类型。 最后一个转换收缩转换，因为基类型可能不包含派生类型的所有成员，因此不是派生类型的实例。  
  
 如果`Option Strict`是`On`，则使用代码必须使用`CType`针对所有收缩转换。  
  
 `Narrowing`关键字可在此上下文中：  
  
 [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
## <a name="see-also"></a>另请参阅  
 [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)  
 [Widening](../../../visual-basic/language-reference/modifiers/widening.md)  
 [扩大转换和收缩转换](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [如何：定义运算符](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [CType 函数](../../../visual-basic/language-reference/functions/ctype-function.md)  
 [Option Strict 语句](../../../visual-basic/language-reference/statements/option-strict-statement.md)
