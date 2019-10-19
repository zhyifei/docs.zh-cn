---
title: Set 语句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Set
helpviewer_keywords:
- property procedures [Visual Basic], Set statements
- Set statement [Visual Basic]
- Set statement [Visual Basic], syntax
- write-only properties
- properties [Visual Basic], write-only
ms.assetid: 9ecc27b4-df84-420d-9075-db25455fb3cd
ms.openlocfilehash: cb0dc76d110f3e6a3ea3e74cc0bfb5a669b35396
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583237"
---
# <a name="set-statement-visual-basic"></a>Set 语句 (Visual Basic)
声明一个 `Set` 属性过程，该过程用于为属性赋值。  
  
## <a name="syntax"></a>语法  
  
```vb  
[ <attributelist> ] [ accessmodifier ] Set (ByVal value [ As datatype ])  
    [ statements ]  
End Set  
```  
  
## <a name="parts"></a>部件  
 `attributelist`  
 可选。 请参阅[特性列表](../../../visual-basic/language-reference/statements/attribute-list.md)。  
  
 `accessmodifier`  
 在此属性中的最多一个 `Get` 和 `Set` 语句上是可选的。 可以是以下各项之一：  
  
- [Protected](../../../visual-basic/language-reference/modifiers/protected.md)  
  
- [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
  
- [Private](../../../visual-basic/language-reference/modifiers/private.md)  
  
- `Protected Friend`  
  
 请参阅 [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。  
  
 `value`  
 必须的。 包含属性新值的参数。  
  
 `datatype`  
 如果 `Option Strict` `On`，则为必需。 @No__t_0 参数的数据类型。 指定的数据类型必须与声明此 `Set` 语句的属性的数据类型相同。  
  
 `statements`  
 可选。 调用 `Set` 属性过程时运行的一个或多个语句。  
  
 `End Set`  
 必须的。 终止 `Set` 属性过程的定义。  
  
## <a name="remarks"></a>备注  
 每个属性都必须具有 `Set` 属性过程，除非该属性被标记为 `ReadOnly`。 @No__t_0 过程用于设置属性的值。  
  
 当赋值语句提供要存储在属性中的值时，Visual Basic 会自动调用属性的 `Set` 过程。  
  
 Visual Basic 在属性赋值期间将参数传递给 `Set` 过程。 如果没有为 `Set` 提供参数，集成开发环境（IDE）将使用名为 `value` 的隐式参数。 参数保留要赋给属性的值。 通常将此值存储在私有本地变量中，并在调用 `Get` 过程时返回此值。  
  
 属性声明的主体只能包含属性的 `Get`，并在[Property 语句](../../../visual-basic/language-reference/statements/property-statement.md)和 `End Property` 语句之间包含 `Set` 过程。 它无法存储这些过程以外的任何内容。 特别是，它无法存储属性的当前值。 您必须将此值存储在属性的外部，因为如果将其存储在任一属性过程中，则其他属性过程将无法访问它。 常见的方法是将值存储在与属性在同一级别上声明的[私有](../../../visual-basic/language-reference/modifiers/private.md)变量中。 必须在应用的属性中定义 `Set` 过程。  
  
 除非在 `Set` 语句中使用 `accessmodifier`，否则 `Set` 过程默认为其包含属性的访问级别。  
  
## <a name="rules"></a>规则  
  
- **混合访问级别。** 如果要定义读写属性，则可以选择为 `Get` 或 `Set` 过程指定不同的访问级别，但不能同时指定两者。 如果执行此操作，则过程访问级别必须比属性的访问级别更严格。 例如，如果属性已 `Friend` 声明，则可以将 `Set` 过程声明 `Private` 但不 `Public`。  
  
     如果正在定义 `WriteOnly` 属性，则 `Set` 过程表示整个属性。 不能为 `Set` 声明不同的访问级别，因为这会为属性设置两个访问级别。  
  
## <a name="behavior"></a>行为  
  
- **从属性过程返回。** 当 `Set` 过程返回到调用代码时，执行将继续执行提供要存储的值的语句之后。  
  
     `Set` 属性过程可以使用[Return 语句](../../../visual-basic/language-reference/statements/return-statement.md)或[Exit 语句](../../../visual-basic/language-reference/statements/exit-statement.md)返回。  
  
     @No__t_0 和 `Return` 语句导致直接从属性过程退出。 任意数量的 `Exit Property` 和 `Return` 语句可以出现在过程中的任何位置，并且可以混合 `Exit Property` 和 `Return` 语句。  
  
## <a name="example"></a>示例  
 下面的示例使用 `Set` 语句设置属性的值。  
  
 [!code-vb[VbVbalrStatements#55](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#55)]  
  
## <a name="see-also"></a>请参阅

- [Get 语句](../../../visual-basic/language-reference/statements/get-statement.md)
- [Property 语句](../../../visual-basic/language-reference/statements/property-statement.md)
- [Sub 语句](../../../visual-basic/language-reference/statements/sub-statement.md)
- [属性过程](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)
