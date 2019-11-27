---
title: Alias 子句
ms.date: 07/20/2015
f1_keywords:
- vb.Alias
helpviewer_keywords:
- Alias keyword [Visual Basic]
ms.assetid: 58c06b11-465d-4d87-906a-73200a3d7f19
ms.openlocfilehash: a7f67224c5d26816bdc1974dc4aa82d796c41284
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349144"
---
# <a name="alias-clause-visual-basic"></a>Alias 子句 (Visual Basic)
指示外部过程在其 DLL 中有另一个名称。  
  
## <a name="remarks"></a>备注  
 可以在此上下文中使用 `Alias` 关键字：  
  
 [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 在下面的示例中，`Alias` 关键字用于提供 advapi32.dll 中函数的名称，`GetUserNameA`，该 `getUserName` 用于替代本示例中的。 函数 `getUserName` 在 sub `getUser`中调用，后者显示当前用户的名称。  
  
 [!code-vb[VbVbalrStatements#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#15)]  
  
## <a name="see-also"></a>另请参阅

- [关键字](../../../visual-basic/language-reference/keywords/index.md)
