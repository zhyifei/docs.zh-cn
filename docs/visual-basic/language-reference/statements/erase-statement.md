---
title: Erase 语句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Erase
helpviewer_keywords:
- Erase keyword [Visual Basic]
- Erase statement [Visual Basic]
ms.assetid: 7a8133d7-b750-4d74-8b66-ba1dd9778d4b
ms.openlocfilehash: 317e2a7dc5facb08388f3a3e635734e4daed5eac
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33601788"
---
# <a name="erase-statement-visual-basic"></a>Erase 语句 (Visual Basic)
用于释放数组变量和解除分配的内存用于其元素。  
  
## <a name="syntax"></a>语法  
  
```  
Erase arraylist  
```  
  
## <a name="parts"></a>部件  
 `arraylist`  
 必须的。 要消除的数组变量的列表。 以逗号分隔多个变量。  
  
## <a name="remarks"></a>备注  
 `Erase`语句只能出现在过程级别。 这意味着，你可以释放在过程中而不是在类或模块级别的数组。  
  
 `Erase`语句是等效于分配`Nothing`给每个数组变量。  
  
## <a name="example"></a>示例  
 下面的示例使用`Erase`语句以清除两个数组，并释放其内存 (1000年和 100 个存储元素分别)。 `ReDim`语句随后将新的数组实例分配给三维数组。  
  
 [!code-vb[VbVbalrStatements#19](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/erase-statement_1.vb)]  
  
## <a name="see-also"></a>请参阅  
 [Nothing](../../../visual-basic/language-reference/nothing.md)  
 [ReDim 语句](../../../visual-basic/language-reference/statements/redim-statement.md)
