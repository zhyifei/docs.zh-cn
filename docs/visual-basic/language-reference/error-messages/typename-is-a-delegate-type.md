---
title: “<typename>”是委托类型
ms.date: 07/20/2015
f1_keywords:
- bc32008
- vbc32008
helpviewer_keywords:
- BC32008
ms.assetid: dc6abba0-a9ad-450f-8899-87265bc84abc
ms.openlocfilehash: 4278ea0fc6a8dc2c6a90b720d2da70b1c26f2a17
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55283447"
---
# <a name="typename-is-a-delegate-type"></a>\<类型名称 > 是委托类型
\<类型名称 > 是委托类型。 委托构造允许仅一个 AddressOf 表达式作为自变量列表。 通常可以而不是委托构造使用一个 AddressOf 表达式。  
  
 一个`New`子句创建委托类的实例为提供了无效的参数列表的委托构造函数。  
  
 你可以提供只有一个`AddressOf`表达式创建新的委托实例时。  
  
 如果不传递任何参数到委托构造函数中，如果传递多个自变量，或如果传递单个参数不是有效，可能发生此错误`AddressOf`表达式。  
  
 **错误 ID:** BC32008  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   使用单个`AddressOf`中的委托类的参数列表中表达式`New`子句。  
  
## <a name="see-also"></a>请参阅
- [New 运算符](../../../visual-basic/language-reference/operators/new-operator.md)
- [AddressOf 运算符](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [委托](../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [如何：调用委托方法](../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
