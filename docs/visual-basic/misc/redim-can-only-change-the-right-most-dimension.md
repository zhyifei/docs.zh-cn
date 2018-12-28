---
title: “ReDim”只能更改最右边的维度
ms.date: 07/20/2015
f1_keywords:
- vbrArray_TypeMismatch
ms.assetid: d53cf41b-7a7a-466c-a29a-920d99698fa9
ms.openlocfilehash: 5b4f054c5d1dfad52ce19e1a9f9d246945866703
ms.sourcegitcommit: 0888d7b24f475c346a3f444de8d83ec1ca7cd234
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2018
ms.locfileid: "53767383"
---
# <a name="redim-can-only-change-the-right-most-dimension"></a>“ReDim”只能更改最右边的维度
`ReDim` 语句尝试使用 `Preserve` 关键字来更改一个数组的维度，它不是最后一个维度。 使用 `Preserve`时，只能调整数组最后一个维度的大小。 对于其他所有维度，必须指定与现有数组相同的大小。  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   删除 `Preserve` 关键字。  
  
## <a name="see-also"></a>请参阅  
 [Visual Basic 中的数组](~/docs/visual-basic/programming-guide/language-features/arrays/index.md)  
 [在 Visual Basic 中的数组维数](~/docs/visual-basic/programming-guide/language-features/arrays/array-dimensions.md)  
 [ReDim 语句](../../visual-basic/language-reference/statements/redim-statement.md)  
 [Dim 语句](../../visual-basic/language-reference/statements/dim-statement.md)  
 [保留 - 删除](https://msdn.microsoft.com/library/91badeab-b4e0-48b6-92c9-9f0c8f995d81)
