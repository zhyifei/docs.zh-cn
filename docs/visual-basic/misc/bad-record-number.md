---
title: 错误的记录号
ms.date: 07/20/2015
f1_keywords:
- vbrID63
ms.assetid: 1fcc33f8-822a-4de9-a6e3-228ddb5824a6
ms.openlocfilehash: 400879ba37c6b3215d9570ca6eb8eaa06edea03b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="bad-record-number"></a>错误的记录号
中的记录号`a FileGet`， `FilePut`， `FileGetObject`，或`FilePutObject`语句是小于或等于零。  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  检查用于生成记录号的计算。 验证包含记录号或用于计算记录号的变量的拼写。 拼写错误的变量名称将被隐式声明并初始化为零，除非在此模块中使用 `Option Explicit On` 。  
  
## <a name="see-also"></a>请参阅  
 [Option Explicit 语句](../../visual-basic/language-reference/statements/option-explicit-statement.md)
