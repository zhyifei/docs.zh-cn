---
title: '&#39;ReDim&#39;无法更改维度数'
ms.date: 07/20/2015
f1_keywords:
- vbrArray_RankMismatch
ms.assetid: 52505298-9985-4682-8f6e-ff7d56077f34
ms.openlocfilehash: bfd4096141833b85a2126340ef549e1e1d1f8e3c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33640376"
---
# <a name="39redim39-cannot-change-the-number-of-dimensions"></a>&#39;ReDim&#39;无法更改维度数
某操作尝试使用 `ReDim` 更改数组的秩（维数）。 `ReDim` 可以更改已形式声明的数组的一个或多个维度的大小，但它不能更改数组的秩。  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   确保想要更改的是数组的秩而不是其维度的大小，尽可能使用 `Dim` 声明具有所需秩的新数组。  
  
## <a name="see-also"></a>请参阅  
 [Visual Basic 中的数组](~/docs/visual-basic/programming-guide/language-features/arrays/index.md)  
 [在 Visual Basic 中的数组维数](~/docs/visual-basic/programming-guide/language-features/arrays/array-dimensions.md)  
 [ReDim 语句](../../visual-basic/language-reference/statements/redim-statement.md)  
 [Dim 语句](../../visual-basic/language-reference/statements/dim-statement.md)
