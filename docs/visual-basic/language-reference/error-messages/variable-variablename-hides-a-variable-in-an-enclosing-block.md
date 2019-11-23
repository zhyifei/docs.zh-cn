---
title: 变量“<variablename>”在封闭块中隐藏变量
ms.date: 07/20/2015
f1_keywords:
- vbc30616
- bc30616
helpviewer_keywords:
- BC30616
ms.assetid: e7658ebc-da45-451b-a409-a0f8915f0beb
ms.openlocfilehash: 4312abef83728f432e2f6a492e5acad3450719b1
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592065"
---
# <a name="variable-variablename-hides-a-variable-in-an-enclosing-block"></a>变量 "\<variablename >" 隐藏封闭块中的变量
块中包含的变量与另一个本地变量的名称相同。  
  
 **错误 ID：** BC30616  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
- 重命名封闭块中的变量，使其与其他任何局部变量不同。 例如：  
  
    ```vb  
    Dim a, b, x As Integer  
    If a = b Then  
       Dim y As Integer = 20 ' Uniquely named block variable.  
    End If  
    ```  
  
- 此错误的一个常见原因是在事件处理程序中使用 `Catch e As Exception`。 如果是这种情况，请将 `Catch` 块变量命名为 `ex` 而不是 `e`。  
  
- 此错误的另一个常见原因是尝试访问在单独的 `Catch` 块中 `Try` 块内声明的局部变量。 若要更正此错误，请在 `Try...Catch...Finally` 结构之外声明变量。  
  
## <a name="see-also"></a>另请参阅

- [Try...Catch...Finally 语句](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [变量声明](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
