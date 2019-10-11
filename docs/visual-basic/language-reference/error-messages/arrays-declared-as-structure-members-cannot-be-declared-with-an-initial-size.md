---
title: 声明为结构成员的数组不能用初始大小声明
ms.date: 07/20/2015
f1_keywords:
- vbc31043
- bc31043
helpviewer_keywords:
- BC31043
ms.assetid: 5bd90c71-1b78-444b-91e1-4789451ef085
ms.openlocfilehash: 83342b780c0fa7c3a2e0a6797b80ef788117ae92
ms.sourcegitcommit: d7c298f6c2e3aab0c7498bfafc0a0a94ea1fe23e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/10/2019
ms.locfileid: "72250153"
---
# <a name="arrays-declared-as-structure-members-cannot-be-declared-with-an-initial-size"></a>声明为结构成员的数组不能用初始大小声明

用初始大小声明了结构中的数组。 不能初始化任何结构元素，并且声明数组大小是一种初始化形式。

**错误 ID：** BC31043

## <a name="example"></a>示例

下面的示例生成 BC31043：

```vb
Structure DemoStruct
    Public demoArray(9) As Integer
End Structure
```

## <a name="to-correct-this-error"></a>更正此错误

1. 将结构中的数组定义为动态（无初始大小）。

2. 如果需要特定大小的数组，则可以在代码运行时使用[ReDim 语句](../statements/redim-statement.md)将动态数组的维数。 下面的示例阐释了这一点：
  
    ```vb
    Structure DemoStruct
        Public demoArray() As Integer
    End Structure
    Sub UseStruct()
        Dim struct As DemoStruct  
        ReDim struct.demoArray(9)
        Struct.demoArray(2) = 777
    End Sub  
    ```
  
## <a name="see-also"></a>请参阅

- [数组](../../programming-guide/language-features/arrays/index.md)
- [如何：声明结构](../../programming-guide/language-features/data-types/how-to-declare-a-structure.md)
