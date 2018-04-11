---
title: 错误的文件名或文件号
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID52
ms.assetid: d0e96aea-7621-48f6-a78b-5d37d18aaa4e
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3d7c8bae3df0e75a1c4f9afacdff681a553503d2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="bad-file-name-or-number"></a>错误的文件名或文件号
尝试访问指定的文件时出错。 此错误的可能原因包括：  
  
-   语句引用中未指定文件名称或数字的文件`FileOpen`中指定的语句或，`FileOpen`语句但随后被关闭。  
  
-   语句引用的文件与大量超出文件数字的范围。  
  
-   语句引用的文件名称或不是有效的数字。  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  请确保文件名称中指定`FileOpen`语句。 请注意，如果你在调用`FileClose`语句无需自变量，你可能会意外地关闭所有打开的文件。  
  
2.  如果你的代码生成的文件数字算法，请确保两个数字是有效。  
  
3.  请检查以确保它们符合操作系统约定的文件名称。  
  
## <a name="see-also"></a>另请参阅  
 <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>  
 [Visual Basic 命名约定](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
