---
title: 语句不能在“If”语句行之外结束块
ms.date: 07/20/2015
f1_keywords:
- vbc32005
- bc32005
helpviewer_keywords:
- BC32005
ms.assetid: 4039f51b-e0ee-4789-a89b-45d06de06b5d
ms.openlocfilehash: 0e645ccf17d0aba702a576791622aa4e9b3dd5e0
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64593259"
---
# <a name="statement-cannot-end-a-block-outside-of-a-line-if-statement"></a>语句不能在“If”语句行之外结束块
单行`If`语句包含多个语句之一就是的冒号 （:） 分隔`End`语句的控制块的外部的单行`If`。 单行`If`语句不使用`End If`语句。  
  
 **错误 ID:** BC32005  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
- 移动的单行`If`语句包含的控制块之外`End If`语句。  
  
## <a name="see-also"></a>请参阅

- [If...Then...Else 语句](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
