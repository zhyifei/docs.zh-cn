---
title: 声明为结构成员的数组不能用初始大小声明
ms.date: 07/20/2015
f1_keywords:
- vbc31043
- bc31043
helpviewer_keywords:
- BC31043
ms.assetid: 5bd90c71-1b78-444b-91e1-4789451ef085
ms.openlocfilehash: de9d77aa9ea853b6f044e91878044115588ca77c
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701249"
---
# <a name="arrays-declared-as-structure-members-cannot-be-declared-with-an-initial-size"></a>声明为结构成员的数组不能用初始大小声明
用初始大小声明了结构中的数组。 不能初始化任何结构元素，并且声明数组大小是一种初始化形式。  
  
 **错误 ID：** BC31043  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1. 将结构中的数组定义为动态（无初始大小）。  
  
2. 如果需要特定大小的数组，则可以在代码运行时使用[ReDim 语句](../../../visual-basic/language-reference/statements/redim-statement.md)将动态数组的维数。 下面的示例阐释了这一点。  
  
    ```vb  
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
