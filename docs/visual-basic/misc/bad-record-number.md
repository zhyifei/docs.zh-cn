---
title: "错误的记录号"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrID63
ms.assetid: 1fcc33f8-822a-4de9-a6e3-228ddb5824a6
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: be04987353498775ec7dcef50b6acc1e6b4ec149
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="bad-record-number"></a>错误的记录号
中的记录号`a FileGet`， `FilePut`， `FileGetObject`，或`FilePutObject`语句是小于或等于零。  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  检查用于生成记录号的计算。 验证包含记录号或用于计算记录号的变量的拼写。 拼写错误的变量名称将被隐式声明并初始化为零，除非在此模块中使用 `Option Explicit On` 。  
  
## <a name="see-also"></a>另请参阅  
 [Option Explicit 语句](../../visual-basic/language-reference/statements/option-explicit-statement.md)
