---
title: Alias 子句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Alias
helpviewer_keywords:
- Alias keyword [Visual Basic]
ms.assetid: 58c06b11-465d-4d87-906a-73200a3d7f19
ms.openlocfilehash: 9cf97402d0b0a6cd16dd75a970c1d29a2fcc30a7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54498565"
---
# <a name="alias-clause-visual-basic"></a>Alias 子句 (Visual Basic)
指示外部过程在其 DLL 中具有另一个名称。  
  
## <a name="remarks"></a>备注  
 `Alias`关键字可在此上下文中：  
  
 [Declare 语句](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 在以下示例中，`Alias`关键字用于提供 advapi32.dll 中的函数的名称`GetUserNameA`，则该`getUserName`来代替此示例中使用。 函数`getUserName`sub 中名为`getUser`，后者将显示当前用户的名称。  
  
 [!code-vb[VbVbalrStatements#15](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/alias-clause_1.vb)]  
  
## <a name="see-also"></a>请参阅
- [关键字](../../../visual-basic/language-reference/keywords/index.md)
