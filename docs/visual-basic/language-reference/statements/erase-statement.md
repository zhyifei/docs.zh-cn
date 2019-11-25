---
title: Erase 语句
ms.date: 07/20/2015
f1_keywords:
- vb.Erase
helpviewer_keywords:
- Erase keyword [Visual Basic]
- Erase statement [Visual Basic]
ms.assetid: 7a8133d7-b750-4d74-8b66-ba1dd9778d4b
ms.openlocfilehash: 6d2052ceccbecd772c4e4bb18052aed74223a36e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343703"
---
# <a name="erase-statement-visual-basic"></a>Erase 语句 (Visual Basic)
Used to release array variables and deallocate the memory used for their elements.  
  
## <a name="syntax"></a>语法  
  
```vb  
Erase arraylist  
```  
  
## <a name="parts"></a>部件  
 `arraylist`  
 必须的。 List of array variables to be erased. 以逗号分隔多个变量。  
  
## <a name="remarks"></a>备注  
 The `Erase` statement can appear only at procedure level. This means you can release arrays inside a procedure but not at class or module level.  
  
 The `Erase` statement is equivalent to assigning `Nothing` to each array variable.  
  
## <a name="example"></a>示例  
 The following example uses the `Erase` statement to clear two arrays and free their memory (1000 and 100 storage elements, respectively). The `ReDim` statement then assigns a new array instance to the three-dimensional array.  
  
 [!code-vb[VbVbalrStatements#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#19)]  
  
## <a name="see-also"></a>请参阅

- [Nothing](../../../visual-basic/language-reference/nothing.md)
- [ReDim 语句](../../../visual-basic/language-reference/statements/redim-statement.md)
