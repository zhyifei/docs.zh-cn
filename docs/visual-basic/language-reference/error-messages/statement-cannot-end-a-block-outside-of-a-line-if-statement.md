---
title: 语句不能结尾行之外的块&#39;如果&#39;语句
ms.date: 07/20/2015
f1_keywords:
- vbc32005
- bc32005
helpviewer_keywords:
- BC32005
ms.assetid: 4039f51b-e0ee-4789-a89b-45d06de06b5d
ms.openlocfilehash: af3006ddc35dfcaa52a54229881baa48cfb7809a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="statement-cannot-end-a-block-outside-of-a-line-39if39-statement"></a>语句不能结尾行之外的块&#39;如果&#39;语句
单线条`If`语句包含用冒号 （:），其中之一是分隔的多条语句`End`控制块的外部的单行语句`If`。 单行`If`语句不使用`End If`语句。  
  
 **错误 ID:** BC32005  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   移动单线条`If`外部控制块包含语句`End If`语句。  
  
## <a name="see-also"></a>请参阅  
 [If...Then...Else 语句](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
