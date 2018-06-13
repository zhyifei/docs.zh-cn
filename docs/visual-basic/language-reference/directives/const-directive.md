---
title: '#Const 指令'
ms.date: 07/20/2015
f1_keywords:
- vb.#Const
- '#vb.Const'
- '#Const'
helpviewer_keywords:
- '#Const directive'
- conditional compilation [Visual Basic], directives
- Const directive (#Const)
- Visual Basic compiler, compiler directives
- constants [Visual Basic], Const directive
- constants [Visual Basic], declaring
- Const statement [Visual Basic], directive (#Const)
- 'declaring constants [Visual Basic], #const directive'
ms.assetid: 707669e5-23f9-4f17-8622-a0d534429386
ms.openlocfilehash: a3b3318f6b44f7d1798e08195be5aeb920b61c0c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33588062"
---
# <a name="const-directive"></a>#Const 指令
适用于 Visual Basic 中定义条件编译器常数。  
  
## <a name="syntax"></a>语法  
  
```  
#Const constname = expression  
```  
  
## <a name="parts"></a>部件  
 `constname`  
 必须的。 正在定义的常数的名称。  
  
 `expression`  
 必须的。 文本、 其他条件编译器常量或包括除之外的任何或所有算术或逻辑运算符的任意组合的`Is`。  
  
## <a name="remarks"></a>备注  
 条件编译器常数始终是私有它们出现的文件类型。 无法创建公共编译器常量使用`#Const`指令; 你可以创建它们仅在用户界面中或使用`/define`编译器选项。  
  
 你可以使用仅条件编译器常数和中的文本`expression`。 使用与定义的标准常量`Const`会导致错误。 相反，你可以使用定义的常数`#Const`关键字仅用于条件编译。 常量还定义，在这种情况下它们具有值为`Nothing`。  
  
## <a name="example"></a>示例  
 此示例使用 `#Const` 指令。  
  
 [!code-vb[VbVbalrConditionalComp#3](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/const-directive_1.vb)]  
  
## <a name="see-also"></a>请参阅  
 [/define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md)  
 [#If...Then...#Else 指令](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
 [Const 语句](../../../visual-basic/language-reference/statements/const-statement.md)  
 [条件编译](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 [If...Then...Else 语句](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
