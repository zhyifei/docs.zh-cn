---
title: Set 语句 (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Set
helpviewer_keywords:
- property procedures [Visual Basic], Set statements
- Set statement [Visual Basic]
- Set statement [Visual Basic], syntax
- write-only properties
- properties [Visual Basic], write-only
ms.assetid: 9ecc27b4-df84-420d-9075-db25455fb3cd
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3b18e6c858e64e78d7ab85fdaafd70e510f7a02f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="set-statement-visual-basic"></a>Set 语句 (Visual Basic)
声明`Set`用于将值分配给属性的属性过程。  
  
## <a name="syntax"></a>语法  
  
```  
[ <attributelist> ] [ accessmodifier ] Set (ByVal value [ As datatype ])  
    [ statements ]  
End Set  
```  
  
## <a name="parts"></a>部件  
 `attributelist`  
 可选。 请参阅[属性列表](../../../visual-basic/language-reference/statements/attribute-list.md)。  
  
 `accessmodifier`  
 在最多一种可选`Get`和`Set`此属性中的语句。 可以是以下各项之一：  
  
-   [Protected](../../../visual-basic/language-reference/modifiers/protected.md)  
  
-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
  
-   [Private](../../../visual-basic/language-reference/modifiers/private.md)  
  
-   `Protected Friend`  
  
 请参阅[访问 Visual Basic 中的级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。  
  
 `value`  
 必需。 参数，其中包含属性的新值。  
  
 `datatype`  
 如果存在`Option Strict`是`On`。 数据类型的`value`参数。 指定的数据类型必须是属性的数据类型相同，这`Set`声明语句。  
  
 `statements`  
 可选。 运行时的一个或多个语句`Set`调用属性过程。  
  
 `End Set`  
 必需。 终止的定义`Set`属性过程。  
  
## <a name="remarks"></a>备注  
 每个属性必须具有`Set`属性过程除非该属性被标记为`ReadOnly`。 `Set`过程用于设置属性的值。  
  
 Visual Basic 将自动调用属性的`Set`在赋值语句将提供一个值，以在属性中存储的过程。  
  
 Visual Basic 将传递到参数`Set`属性分配期间的过程。 如果未提供的参数`Set`，集成的开发环境 (IDE) 使用名为的隐式参数`value`。 参数包含要分配给属性的值。 通常将此值存储在专用的本地变量，并将其返回每当`Get`调用过程。  
  
 属性声明的主体可以包含仅属性的`Get`和`Set`之间过程[属性语句](../../../visual-basic/language-reference/statements/property-statement.md)和`End Property`语句。 无法将存储这些过程之外的任何内容。 具体而言，它不能存储属性的当前值。 必须存储此值超出了该属性，因为如果将其存储在属性过程之一，另一个属性过程无法访问它。 常用方法是存储中的值[私有](../../../visual-basic/language-reference/modifiers/private.md)作为属性的相同级别声明的变量。 必须定义`Set`所适用的属性的内部过程。  
  
 `Set`过程默认为其包含的属性的访问级别，除非使用`accessmodifier`中`Set`语句。  
  
## <a name="rules"></a>规则  
  
-   **混合的访问级别。** 如果你正在定义一个读 / 写属性，你可以选择指定不同的访问级别也`Get`或`Set`过程中，但不是两者。 如果执行此操作时，过程访问级别必须比属性访问级别限制性更强。 例如，如果属性声明`Friend`，可以声明`Set`过程`Private`，但不是`Public`。  
  
     如果你正在定义`WriteOnly`属性，`Set`过程表示整个属性。 你不能声明不同的访问级别`Set`，因为这会设置属性的两个访问级别。  
  
## <a name="behavior"></a>行为  
  
-   **返回从属性过程。** 当`Set`过程返回到调用代码时，将会继续执行提供了要存储的值的语句。  
  
     `Set`属性过程可以返回使用[Return 语句](../../../visual-basic/language-reference/statements/return-statement.md)或[退出语句](../../../visual-basic/language-reference/statements/exit-statement.md)。  
  
     `Exit Property`和`Return`语句从属性过程会导致立即退出。 任意数量的`Exit Property`和`Return`语句可以出现的任何位置在过程中，并可混合`Exit Property`和`Return`语句。  
  
## <a name="example"></a>示例  
 下面的示例使用`Set`语句将设置属性的值。  
  
 [!code-vb[VbVbalrStatements#55](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/set-statement_1.vb)]  
  
## <a name="see-also"></a>另请参阅  
 [Get 语句](../../../visual-basic/language-reference/statements/get-statement.md)  
 [Property 语句](../../../visual-basic/language-reference/statements/property-statement.md)  
 [Sub 语句](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [属性过程](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)
