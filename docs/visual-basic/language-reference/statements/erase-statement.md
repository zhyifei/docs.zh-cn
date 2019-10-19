---
title: Erase 语句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Erase
helpviewer_keywords:
- Erase keyword [Visual Basic]
- Erase statement [Visual Basic]
ms.assetid: 7a8133d7-b750-4d74-8b66-ba1dd9778d4b
ms.openlocfilehash: 7dec2a859f664ee8dcbb305082ec33aeacbaccb4
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583387"
---
# <a name="erase-statement-visual-basic"></a>Erase 语句 (Visual Basic)
用于释放数组变量并解除分配用于其元素的内存。  
  
## <a name="syntax"></a>语法  
  
```vb  
Erase arraylist  
```  
  
## <a name="parts"></a>部件  
 `arraylist`  
 必须的。 要清除的数组变量的列表。 以逗号分隔多个变量。  
  
## <a name="remarks"></a>备注  
 @No__t_0 语句只能出现在过程级别。 这意味着，可以在过程中释放数组，但不能在类或模块级别进行。  
  
 @No__t_0 语句等效于将 `Nothing` 赋给每个数组变量。  
  
## <a name="example"></a>示例  
 下面的示例使用 `Erase` 语句来清除两个数组，并分别释放其内存（1000和100存储元素）。 然后，`ReDim` 语句将新的数组实例赋给三维数组。  
  
 [!code-vb[VbVbalrStatements#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#19)]  
  
## <a name="see-also"></a>请参阅

- [Nothing](../../../visual-basic/language-reference/nothing.md)
- [ReDim 语句](../../../visual-basic/language-reference/statements/redim-statement.md)
