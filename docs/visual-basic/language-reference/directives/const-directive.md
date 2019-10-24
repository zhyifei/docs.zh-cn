---
title: '#Const 指令（Visual Basic）'
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
ms.openlocfilehash: 031f35df24fd52aeeafcb7b4c0208806d7fc5fc4
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2019
ms.locfileid: "72774760"
---
# <a name="const-directive"></a>#Const 指令
为 Visual Basic 定义条件编译器常量。  
  
## <a name="syntax"></a>语法  
  
```vb  
#Const constname = expression  
```  
  
## <a name="parts"></a>部件  
 `constname`  
 必须的。 要定义的常数的名称。  
  
 `expression`  
 必须的。 文本、其他条件编译器常量或包含除 `Is` 以外的任何或所有算术或逻辑运算符的任意组合。  
  
## <a name="remarks"></a>备注  
 条件编译器常量总是专用于它们所在的文件。 不能使用 `#Const` 指令创建公共编译器常量;只能在用户界面中创建它们，也可以通过 `/define` 编译器选项来创建它们。  
  
 只能在 `expression` 中使用条件编译器常量和文本。 使用使用定义的标准常数 `Const` 会导致错误。 相反，您可以将使用 `#Const` 关键字定义的常量仅用于条件编译。 常数也可以是未定义的，在这种情况下，它们的值为 `Nothing`。  
  
## <a name="example"></a>示例  
 此示例使用 `#Const` 指令。  
  
 [!code-vb[VbVbalrConditionalComp#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#3)]  
  
## <a name="see-also"></a>请参阅

- [-define （Visual Basic）](../../../visual-basic/reference/command-line-compiler/define.md)
- [#If...Then...#Else 指令](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [Const 语句](../../../visual-basic/language-reference/statements/const-statement.md)
- [条件编译](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- [If...Then...Else 语句](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
