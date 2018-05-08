---
title: 前导&#39;。&#39;或&#39;！&#39;只能出现在&#39;与&#39;语句
ms.date: 07/20/2015
f1_keywords:
- vbc30157
- bc30157
helpviewer_keywords:
- BC30157
ms.assetid: 70daaee1-14f9-45b7-9f30-53794310b95e
ms.openlocfilehash: 7802b8e0aaf3dff83d5bfbe11f0b8bb1b5bb46cb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="leading-3939-or-3939-can-only-appear-inside-a-39with39-statement"></a>前导&#39;。&#39;或&#39;！&#39;只能出现在&#39;与&#39;语句
句点 （.） 或感叹号 （！） 不内部`With`块没有左侧的表达式时出现。 成员访问 (`.`) 和字典成员访问 (`!`) 需要一个表达式来指定包含该成员的元素。 这必须紧靠的左边的访问器或作为目标的`With`包含成员访问的块。  
  
 **错误 ID:** BC30157  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  确保`With`块的格式正确。  
  
2.  如果没有任何`With`块中，将表达式添加到包含成员的定义元素的计算结果的访问器的左侧。  
  
## <a name="see-also"></a>请参阅  
 [代码中的特殊字符](../../../visual-basic/programming-guide/program-structure/special-characters-in-code.md)  
 [With...End With 语句](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
