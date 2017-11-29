---
title: "Module 语句"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- Module
- vb.Module
helpviewer_keywords:
- modules, classes
- modules
- Module statement [Visual Basic]
- modules, declaring
- standard modules
- classes [Visual Basic], vs. modules
- declarations [Visual Basic], modules
ms.assetid: a1243afc-14a5-45df-95d5-51118aeac362
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 92cdcd1919f21243118108da3bc382ea5d954130
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="module-statement"></a>Module 语句
声明的模块的名称，并引入的变量、 属性、 事件和模块包含的过程的定义。  
  
## <a name="syntax"></a>语法  
  
```  
[ <attributelist> ] [ accessmodifier ]  Module name  
    [ statements ]  
End Module  
```  
  
## <a name="parts"></a>部件  
 `attributelist`  
 可选。 请参阅[属性列表](../../../visual-basic/language-reference/statements/attribute-list.md)。  
  
 `accessmodifier`  
 可选。 可以是以下各项之一：  
  
-   [Public](../../../visual-basic/language-reference/modifiers/public.md)  
  
-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
  
 请参阅[访问 Visual Basic 中的级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。  
  
 `name`  
 必需。 此模块的名称。 请参阅[声明的元素名称](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)。  
  
 `statements`  
 可选。 定义变量、 属性、 事件、 过程和嵌套的类型，此模块的语句。  
  
 `End Module`  
 终止`Module`定义。  
  
## <a name="remarks"></a>备注  
 A`Module`语句定义引用类型可在其命名空间可用。 A*模块*(有时称为*标准模块*) 类似于类，但有一些重要区别。 每个模块具有恰好一个实例，不需要创建或分配给变量。 模块不支持继承或实现接口。 请注意，模块不是*类型*在类或结构的意义上，你不能声明为具有模块的数据类型的编程元素。  
  
 你可以使用`Module`只能在命名空间级别。 这意味着*声明上下文*模块必须为源文件或命名空间，并且不能为类、 结构、 模块、 接口、 过程或块。 不能嵌套在另一个模块内的任何类型或模块。 有关详细信息，请参阅[声明上下文和默认访问级别](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)。  
  
 模块具有程序相同的生存期。 因为所有其成员`Shared`，它们还具有相等的程序的生存期。  
  
 模块默认为[友元](../../../visual-basic/language-reference/modifiers/friend.md)访问。 你可以调整其访问级别有访问修饰符。 有关详细信息，请参阅[访问 Visual Basic 中的级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。  
  
 模块的所有成员都都隐式`Shared`。  
  
## <a name="classes-and-modules"></a>类和模块  
 这些元素包含的许多相似之处，但有一些重要的区别。  
  
-   **术语。** Visual Basic 早期版本识别两种类型的模块：*类模块*（.cls 文件） 和*标准模块*（.bas 文件）。 当前版本调用这些*类*和*模块*分别。  
  
-   **共享的成员。** 你可以控制类的成员是共享成员还是实例成员。  
  
-   **面向对象。** 类是面向对象的但模块不是。 因此，只能将类可以将实例化为对象。 有关详细信息，请参阅[对象和类](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)。  
  
## <a name="rules"></a>规则  
  
-   **修饰符。** 所有的模块成员为隐式[共享](../../../visual-basic/language-reference/modifiers/shared.md)。 不能使用`Shared`关键字时声明成员，并且你无法更改任何成员的共享的状态。  
  
-   **继承。** 模块不能从继承任何类型以外<xref:System.Object>，哪些所有模块从继承。 具体而言，一个模块不能继承自另一个。  
  
     不能使用[继承语句](../../../visual-basic/language-reference/statements/inherits-statement.md)在模块定义中，即使指定<xref:System.Object>。  
  
-   **默认属性。** 不能在模块中定义的任何默认属性。 有关详细信息，请参阅[默认](../../../visual-basic/language-reference/modifiers/default.md)。  
  
## <a name="behavior"></a>行为  
  
-   **访问级别。** 在模块中，你可以声明每个成员使用其自己的访问级别。 模块成员默认为[公共](../../../visual-basic/language-reference/modifiers/public.md)访问，除变量和常量，哪些默认为[私有](../../../visual-basic/language-reference/modifiers/private.md)访问。 如果模块具有相比限制更多访问其成员之一，指定的模块访问级别优先。  
  
-   **作用域。** 模块是在整个命名空间范围内。  
  
     每个模块成员的作用域是整个模块。 请注意，所有成员都会都经受*类型提升*，这将导致它们提升为包含该模块的命名空间的范围。 有关详细信息，请参阅[类型提升](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md)。  
  
-   **限定。** 你可以在项目中，有多个模块，你可以声明具有两个或多个模块中的同名成员。 但是，如果从该模块以外的引用为必须限定对具有适当的模块名称的此类的成员的任何引用。 有关详细信息，请参阅[对声明的元素的引用](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)。  
  
## <a name="example"></a>示例  
 [!code-vb[VbVbalrStatements#69](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/module-statement_1.vb)]  
  
## <a name="see-also"></a>另请参阅  
 [Class 语句](../../../visual-basic/language-reference/statements/class-statement.md)  
 [Namespace 语句](../../../visual-basic/language-reference/statements/namespace-statement.md)  
 [Structure 语句](../../../visual-basic/language-reference/statements/structure-statement.md)  
 [Interface 语句](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [Property 语句](../../../visual-basic/language-reference/statements/property-statement.md)  
 [类型提升](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md)
