---
title: 声明为结构成员的数组不能用初始大小声明
ms.date: 07/20/2015
f1_keywords:
- vbc31043
- bc31043
helpviewer_keywords:
- BC31043
ms.assetid: 5bd90c71-1b78-444b-91e1-4789451ef085
ms.openlocfilehash: 06e5e36f3e0522e0449c0ef9698f3a1b01b9cb5f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54549062"
---
# <a name="arrays-declared-as-structure-members-cannot-be-declared-with-an-initial-size"></a>声明为结构成员的数组不能用初始大小声明
初始大小声明数组在结构中。 无法初始化结构的任何元素，并声明的数组大小是一种形式的初始化。  
  
 **错误 ID:** BC31043  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  定义数组结构中为动态 （不是初始大小）。  
  
2.  如果需要特定大小的数组，可以重新使用的动态数组设置其维数[ReDim 语句](../../../visual-basic/language-reference/statements/redim-statement.md)时运行代码。 下面的示例阐释了这一点。  
  
    ```  
    Structure demoStruct  
        Public demoArray() As Integer  
    End Structure  
    Sub useStruct()  
        Dim struct As demoStruct  
        ReDim struct.demoArray(9)  
        Struct.demoArray(2) = 777  
    End Sub  
    ```  
  
## <a name="see-also"></a>请参阅
- [数组](../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [如何：声明结构](../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
