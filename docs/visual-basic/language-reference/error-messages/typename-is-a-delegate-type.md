---
title: '&#39;&lt;typename&gt; &#39;是委托类型'
ms.date: 07/20/2015
f1_keywords:
- bc32008
- vbc32008
helpviewer_keywords:
- BC32008
ms.assetid: dc6abba0-a9ad-450f-8899-87265bc84abc
ms.openlocfilehash: c6d4244ce72dedee50b65ba19978149ce86b9e87
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33595643"
---
# <a name="39lttypenamegt39-is-a-delegate-type"></a>&#39;&lt;typename&gt; &#39;是委托类型
\<类型名称 > 是委托类型。 委托构造允许仅单个 AddressOf 表达式作为自变量列表。 通常可以而不是委托构造使用的 AddressOf 表达式。  
  
 A`New`子句创建委托类的实例为提供了无效自变量列表的委托构造函数。  
  
 你可以提供只有一个`AddressOf`表达式创建新的委托实例时。  
  
 如果不传递任何自变量到委托构造函数中，如果传递的多个参数，或者如果传递的单个参数不是有效，将产生此错误`AddressOf`表达式。  
  
 **错误 ID:** BC32008  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   使用单个`AddressOf`中的委托类的自变量列表中的表达式`New`子句。  
  
## <a name="see-also"></a>请参阅  
 [New 运算符](../../../visual-basic/language-reference/operators/new-operator.md)  
 [AddressOf 运算符](../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [委托](../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [如何：调用委托方法](../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
