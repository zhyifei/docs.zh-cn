---
title: Erase 语句 (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Erase
helpviewer_keywords:
- Erase keyword [Visual Basic]
- Erase statement [Visual Basic]
ms.assetid: 7a8133d7-b750-4d74-8b66-ba1dd9778d4b
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 45a2b439cf5ad04d59cea59bb21d345d0057b322
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="erase-statement-visual-basic"></a>Erase 语句 (Visual Basic)
用于释放数组变量和解除分配的内存用于其元素。  
  
## <a name="syntax"></a>语法  
  
```  
Erase arraylist  
```  
  
## <a name="parts"></a>部件  
 `arraylist`  
 必需。 要消除的数组变量的列表。 以逗号分隔多个变量。  
  
## <a name="remarks"></a>备注  
 `Erase`语句只能出现在过程级别。 这意味着，你可以释放在过程中而不是在类或模块级别的数组。  
  
 `Erase`语句是等效于分配`Nothing`给每个数组变量。  
  
## <a name="example"></a>示例  
 下面的示例使用`Erase`语句以清除两个数组，并释放其内存 (1000年和 100 个存储元素分别)。 `ReDim`语句随后将新的数组实例分配给三维数组。  
  
 [!code-vb[VbVbalrStatements#19](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/erase-statement_1.vb)]  
  
## <a name="see-also"></a>另请参阅  
 [Nothing](../../../visual-basic/language-reference/nothing.md)  
 [ReDim 语句](../../../visual-basic/language-reference/statements/redim-statement.md)
