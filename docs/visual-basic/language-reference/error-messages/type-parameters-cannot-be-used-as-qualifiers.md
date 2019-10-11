---
title: 类型参数不能用作限定符
ms.date: 07/20/2015
f1_keywords:
- vbc32098
- bc32098
helpviewer_keywords:
- BC32098
ms.assetid: bab05325-dde8-4621-a5f6-368b5b7b2d76
ms.openlocfilehash: 3ff4b189539bf119351a94dabadd596c336ac723
ms.sourcegitcommit: d7c298f6c2e3aab0c7498bfafc0a0a94ea1fe23e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/10/2019
ms.locfileid: "72250332"
---
# <a name="type-parameters-cannot-be-used-as-qualifiers"></a>类型参数不能用作限定符

使用包含类型参数的限定字符串限定编程元素。

类型参数表示在构造泛型类型时要提供的类型的要求。 它不表示特定的已定义类型。 限定字符串必须只包含在编译时定义的元素。

以下代码可能会生成此错误：

```vb  
Public Function CheckText(Of c As System.Windows.Forms.Control)(
    badText As String) As Boolean
  
    Dim saveText As c.Text  
    ' Insert code to look for badText within saveText.
End Function  
```  
  
 **错误 ID：** BC32098  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1. 从限定字符串中删除类型参数，或将其替换为定义的类型。  
  
2. 如果需要使用构造类型来查找要限定的编程元素，则必须使用其他程序逻辑。  
  
## <a name="see-also"></a>请参阅

- [对已声明元素的引用](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Generic Types in Visual Basic](../../programming-guide/language-features/data-types/generic-types.md)
- [类型列表](../statements/type-list.md)
