---
title: "#<a name=\"const-directive\"></a>Const 指令"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a6e162b01dc5c99fb7708337d259f9e66ddd6b64
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="const-directive"></a>#Const 指令
适用于 Visual Basic 中定义条件编译器常数。  
  
## <a name="syntax"></a>语法  
  
```  
#Const constname = expression  
```  
  
## <a name="parts"></a>部件  
 `constname`  
 必需。 正在定义的常数的名称。  
  
 `expression`  
 必需。 文本、 其他条件编译器常量或包括除之外的任何或所有算术或逻辑运算符的任意组合的`Is`。  
  
## <a name="remarks"></a>备注  
 条件编译器常数始终是私有它们出现的文件类型。 无法创建公共编译器常量使用`#Const`指令; 你可以创建它们仅在用户界面中或使用`/define`编译器选项。  
  
 你可以使用仅条件编译器常数和中的文本`expression`。 使用与定义的标准常量`Const`会导致错误。 相反，你可以使用定义的常数`#Const`关键字仅用于条件编译。 常量还定义，在这种情况下它们具有值为`Nothing`。  
  
## <a name="example"></a>示例  
 此示例使用 `#Const` 指令。  
  
 [!code-vb[VbVbalrConditionalComp#3](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/const-directive_1.vb)]  
  
## <a name="see-also"></a>另请参阅  
 [/define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md)  
 [#If...Then...#Else 指令](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
 [Const 语句](../../../visual-basic/language-reference/statements/const-statement.md)  
 [条件编译](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 [If...Then...Else 语句](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
