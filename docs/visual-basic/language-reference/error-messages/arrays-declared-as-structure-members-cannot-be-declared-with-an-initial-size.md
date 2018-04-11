---
title: 声明为结构成员的数组不能用初始大小声明
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc31043
- bc31043
helpviewer_keywords:
- BC31043
ms.assetid: 5bd90c71-1b78-444b-91e1-4789451ef085
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 983154a144a79991c86db5056ad0e0e563a3ba73
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="arrays-declared-as-structure-members-cannot-be-declared-with-an-initial-size"></a>声明为结构成员的数组不能用初始大小声明
初始大小声明一个结构的数组。 无法初始化任何结构元素，并声明的数组大小是一种形式的初始化。  
  
 **错误 ID:** BC31043  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  定义数组在结构中为动态 （不是初始大小）。  
  
2.  如果你需要特定大小的数组，你可以重新设置其维数的动态数组[ReDim 语句](../../../visual-basic/language-reference/statements/redim-statement.md)运行你的代码时。 下面的示例阐释了这一点。  
  
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
  
## <a name="see-also"></a>另请参阅  
 [阵列](../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [如何：声明结构](../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
