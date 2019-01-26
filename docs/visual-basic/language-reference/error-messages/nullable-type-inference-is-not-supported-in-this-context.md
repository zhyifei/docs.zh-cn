---
title: 该上下文中不支持可以为 null 的类型推理
ms.date: 07/20/2015
f1_keywords:
- vbc36629
- bc36629
helpviewer_keywords:
- BC36629
ms.assetid: 0a1e2dbc-d9a4-433d-9306-c5540782b81d
ms.openlocfilehash: 7dffc5233656257cd892f573a2f8b9f91d781c21
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54611886"
---
# <a name="nullable-type-inference-is-not-supported-in-this-context"></a>该上下文中不支持可以为 null 的类型推理
值类型和结构可以声明可以为 null。  
  
```vb  
Dim a? As Integer  
Dim b As Integer?  
```  
  
 但是，不能与类型推断结合使用可以为 null 的声明。 下面的示例会导致此错误。  
  
```vb  
' Not valid.  
' Dim c? = 10  
' Dim d? = a  
```  
  
 **错误 ID:** BC36629  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   使用`As`子句，以将变量声明为可以为 null。  
  
## <a name="see-also"></a>请参阅
- [可以为 null 的值类型](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [局部类型推理](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
