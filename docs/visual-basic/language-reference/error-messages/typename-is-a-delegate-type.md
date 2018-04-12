---
title: '&#39;&lt;typename&gt;&#39; 为委托类型'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc32008
- vbc32008
helpviewer_keywords:
- BC32008
ms.assetid: dc6abba0-a9ad-450f-8899-87265bc84abc
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9428f0ac321b90e36d4d987381ed69b6c968894c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="39lttypenamegt39-is-a-delegate-type"></a>&#39;&lt;typename&gt;&#39; 为委托类型
\<类型名称 > 是委托类型。 委托构造允许仅单个 AddressOf 表达式作为自变量列表。 通常可以而不是委托构造使用的 AddressOf 表达式。  
  
 A`New`子句创建委托类的实例为提供了无效自变量列表的委托构造函数。  
  
 你可以提供只有一个`AddressOf`表达式创建新的委托实例时。  
  
 如果不传递任何自变量到委托构造函数中，如果传递的多个参数，或者如果传递的单个参数不是有效，将产生此错误`AddressOf`表达式。  
  
 **错误 ID:** BC32008  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   使用单个`AddressOf`中的委托类的自变量列表中的表达式`New`子句。  
  
## <a name="see-also"></a>另请参阅  
 [New 运算符](../../../visual-basic/language-reference/operators/new-operator.md)  
 [AddressOf 运算符](../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [委托](../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [如何：调用委托方法](../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
