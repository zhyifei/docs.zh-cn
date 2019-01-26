---
title: 前导&#39;。&#39;或&#39;！&#39;只能出现在&#39;与&#39;语句
ms.date: 07/20/2015
f1_keywords:
- vbc30157
- bc30157
helpviewer_keywords:
- BC30157
ms.assetid: 70daaee1-14f9-45b7-9f30-53794310b95e
ms.openlocfilehash: e64318d4ececbd887f55a1a202cc2d58c90c8fc7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54625947"
---
# <a name="leading-3939-or-3939-can-only-appear-inside-a-39with39-statement"></a>前导&#39;。&#39;或&#39;！&#39;只能出现在&#39;与&#39;语句
句点 （.） 或感叹号 （！） 不深入了解`With`块内不使用左侧的表达式。 成员访问 (`.`) 和字典成员访问 (`!`) 需要一个表达式，指定包含该成员的元素。 这必须紧靠左侧的访问器或作为目标的`With`块，其中包含成员访问。  
  
 **错误 ID:** BC30157  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  确保`With`块的格式正确。  
  
2.  如果没有任何`With`块中，将表达式添加到包含该成员的定义元素的计算结果的访问器的左侧。  
  
## <a name="see-also"></a>请参阅
- [代码中的特殊字符](../../../visual-basic/programming-guide/program-structure/special-characters-in-code.md)
- [With...End With 语句](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
