---
title: Get 语句
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Get
helpviewer_keywords:
- Get statement [Visual Basic], syntax
- Get statement [Visual Basic]
- properties [Visual Basic], read-only
- read-only properties
- Get keyword [Visual Basic]
- property procedures [Visual Basic], Get statements
ms.assetid: 56b05cdc-bd64-4dfd-bb12-824eacec6f94
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c1ff062a5e3bf41794bd5b4c90f1e188d6d97480
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="get-statement"></a>Get 语句
声明`Get`属性过程用于检索属性的值。  
  
## <a name="syntax"></a>语法  
  
```  
[ <attributelist> ] [ accessmodifier ] Get()  
    [ statements ]  
End Get  
```  
  
## <a name="parts"></a>部件  
  
|术语|定义|  
|---|---|  
|`attributelist`|可选。 请参阅[属性列表](../../../visual-basic/language-reference/statements/attribute-list.md)。|  
|`accessmodifier`|在最多一种可选`Get`和`Set`此属性中的语句。 可以是以下各项之一：<br /><br /> -   [受保护](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [友元](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [私有](../../../visual-basic/language-reference/modifiers/private.md)<br />-   `Protected Friend`<br /><br /> 请参阅[访问 Visual Basic 中的级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。|  
|`statements`|可选。 运行时的一个或多个语句`Get`调用属性过程。|  
|`End Get`|必需。 终止的定义`Get`属性过程。|  
  
## <a name="remarks"></a>备注  
 每个属性必须具有`Get`属性过程除非该属性被标记为`WriteOnly`。 `Get`过程用于返回属性的当前值。  
  
 Visual Basic 将自动调用属性的`Get`过程当表达式请求属性的值。  
  
 属性声明的主体可以包含仅属性的`Get`和`Set`之间过程[属性语句](../../../visual-basic/language-reference/statements/property-statement.md)和`End Property`语句。 无法将存储这些过程之外的任何内容。 具体而言，它不能存储属性的当前值。 必须存储此值超出了该属性，因为如果将其存储在属性过程之一，另一个属性过程无法访问它。 常用方法是存储中的值[私有](../../../visual-basic/language-reference/modifiers/private.md)作为属性的相同级别声明的变量。 必须定义`Get`所适用的属性的内部过程。  
  
 `Get`过程默认为其包含的属性的访问级别，除非使用`accessmodifier`中`Get`语句。  
  
## <a name="rules"></a>规则  
  
-   **混合的访问级别。** 如果你正在定义一个读 / 写属性，你可以选择指定不同的访问级别也`Get`或`Set`过程中，但不是两者。 如果执行此操作时，过程访问级别必须比属性访问级别限制性更强。 例如，如果属性声明`Friend`，可以声明`Get`过程`Private`，但不是`Public`。  
  
     如果你正在定义`ReadOnly`属性，`Get`过程表示整个属性。 你不能声明不同的访问级别`Get`，因为这会设置属性的两个访问级别。  
  
-   **返回类型。** [属性语句](../../../visual-basic/language-reference/statements/property-statement.md)可声明它返回的值的数据类型。 `Get`过程会自动返回数据类型。 你可以指定任何数据类型或枚举、 结构、 类或接口的名称。  
  
     如果`Property`语句不指定`returntype`，该过程返回`Object`。  
  
## <a name="behavior"></a>行为  
  
-   **从过程返回。** 当`Get`过程返回到调用代码时，执行会继续在请求的属性值的语句内。  
  
     `Get`属性过程可以返回值使用[Return 语句](../../../visual-basic/language-reference/statements/return-statement.md)或通过将返回值分配给属性名称。 有关详细信息，请参阅"返回值" [Function 语句](../../../visual-basic/language-reference/statements/function-statement.md)。  
  
     `Exit Property`和`Return`语句从属性过程会导致立即退出。 任意数量的`Exit Property`和`Return`语句可以出现的任何位置在过程中，并可混合`Exit Property`和`Return`语句。  
  
-   **返回值。** 返回一个介于`Get`过程中，您可以将值分配到属性名称或将其包含在[Return 语句](../../../visual-basic/language-reference/statements/return-statement.md)。 `Return`语句将同时分配`Get`过程返回值并退出该过程。  
  
     如果你使用`Exit Property`而不将值分配到属性名称，`Get`过程返回该属性的数据类型的默认值。 有关详细信息，请参阅"返回值" [Function 语句](../../../visual-basic/language-reference/statements/function-statement.md)。  
  
     下面的示例演示两种方法的只读属性`quoteForTheDay`可以返回的私有变量中保存的值`quoteValue`。  
  
     [!code-vb[VbVbalrStatements#27](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/get-statement_1.vb)]  
  
     [!code-vb[VbVbalrStatements#28](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/get-statement_2.vb)]  
  
     [!code-vb[VbVbalrStatements#29](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/get-statement_3.vb)]  
  
## <a name="example"></a>示例  
 下面的示例使用`Get`语句以返回属性的值。  
  
 [!code-vb[VbVbalrStatements#30](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/get-statement_4.vb)]  
  
## <a name="see-also"></a>另请参阅  
 [Set 语句](../../../visual-basic/language-reference/statements/set-statement.md)  
 [Property 语句](../../../visual-basic/language-reference/statements/property-statement.md)  
 [Exit 语句](../../../visual-basic/language-reference/statements/exit-statement.md)  
 [对象和类](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [演练：定义类](../../../visual-basic/programming-guide/language-features/objects-and-classes/walkthrough-defining-classes.md)
