---
title: Class 语句 (Visual Basic)
ms.date: 05/12/2018
f1_keywords:
- vb.Class
helpviewer_keywords:
- class modules
- Class statement [Visual Basic]
- classes [Visual Basic], fields
- fields [Visual Basic], of classes
- class types [Visual Basic], class statements
- classes [Visual Basic], creating
- classes [Visual Basic], data members
- data members [Visual Basic], of classes
ms.assetid: f2664f38-eb5a-4d4b-a374-1d041521fb6c
ms.openlocfilehash: 1d81ce148e237df6997934f70c294630f6cc7b8d
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2018
---
# <a name="class-statement-visual-basic"></a>Class 语句 (Visual Basic)
声明类的名称，并引入的变量、 属性、 事件和类包含的过程的定义。  
  
## <a name="syntax"></a>语法  
  
```  
[ <attributelist> ] [ accessmodifier ] [ Shadows ] [ MustInherit | NotInheritable ] [ Partial ] _  
Class name [ ( Of typelist ) ]  
    [ Inherits classname ]  
    [ Implements interfacenames ]  
    [ statements ]  
End Class  
```  
  
## <a name="parts"></a>部件  
  
|术语|定义|  
|---|---|  
|`attributelist`|可选。 请参阅[属性列表](../../../visual-basic/language-reference/statements/attribute-list.md)。|  
|`accessmodifier`|可选。 可以是以下各项之一：<br /><br /> -   [公共](../../../visual-basic/language-reference/modifiers/public.md)<br />-   [受保护](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [友元](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [私有](../../../visual-basic/language-reference/modifiers/private.md)<br />-   [受保护的友元](../../language-reference/modifiers/protected-friend.md)<br />- [私有受保护](../../language-reference/modifiers/private-protected.md)<br/><br/> 请参阅[访问 Visual Basic 中的级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。|  
|`Shadows`|可选。 请参阅[阴影](../../../visual-basic/language-reference/modifiers/shadows.md)。|  
|`MustInherit`|可选。 请参阅[MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md)。|  
|`NotInheritable`|可选。 请参阅[NotInheritable](../../../visual-basic/language-reference/modifiers/notinheritable.md)。|  
|`Partial`|可选。 指示类的分部定义。 请参阅[部分](../../../visual-basic/language-reference/modifiers/partial.md)。|  
|`name`|必须的。 此类的名称。 请参阅[声明的元素名称](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)。|  
|`Of`|可选。 指定这是一个泛型类。|  
|`typelist`|如果你使用是必需的[的](../../../visual-basic/language-reference/statements/of-clause.md)关键字。 此类的类型参数的列表。 请参阅[键入列表](../../../visual-basic/language-reference/statements/type-list.md)。|  
|`Inherits`|可选。 指示此类继承另一个类的成员。 请参阅[Inherits 语句](../../../visual-basic/language-reference/statements/inherits-statement.md)。|  
|`classname`|如果你使用是必需的`Inherits`语句。 此类派生自的类名称。|  
|`Implements`|可选。 指示此类实现一个或多个接口的成员。 请参阅[实现语句](../../../visual-basic/language-reference/statements/implements-statement.md)。|  
|`interfacenames`|如果你使用是必需的`Implements`语句。 此类实现的接口名称。|  
|`statements`|可选。 定义此类的成员的语句。|  
|`End Class`|必须的。 终止`Class`定义。|  
  
## <a name="remarks"></a>备注  
 A`Class`语句定义新的数据类型。 A*类*是面向对象的编程 (OOP) 的基本构建块。 有关详细信息，请参阅[对象和类](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)。  
  
 你可以使用`Class`只能在命名空间或模块级别。 这意味着*声明上下文*类必须为源文件、 命名空间、 类、 结构、 模块或接口，并且不能为过程或块。 有关详细信息，请参阅[声明上下文和默认访问级别](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)。  
  
 类的每个实例都拥有独立于所有其他实例的生存期。 此生存期开始通过创建时[New 运算符](../../../visual-basic/language-reference/operators/new-operator.md)子句或如函数<xref:Microsoft.VisualBasic.Interaction.CreateObject%2A>。 结束时指向该实例的所有变量已都设置为[执行任何操作](../../../visual-basic/language-reference/nothing.md)或其他类的实例。  
  
 类默认为[友元](../../../visual-basic/language-reference/modifiers/friend.md)访问。 你可以调整其访问级别有访问修饰符。 有关详细信息，请参阅[访问 Visual Basic 中的级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。  
  
## <a name="rules"></a>规则  
  
-   **嵌套。** 你可以定义在另一个类。 外部的类称为*包含类*，内部的类称为*嵌套类*。  
  
-   **继承。** 如果类使用[继承语句](../../../visual-basic/language-reference/statements/inherits-statement.md)，你可以指定只有一个基类或接口。 类不能从多个元素继承。  
  
     类不能从具有限制性更强的访问级别的另一个类继承。 例如，`Public`类不能继承自`Friend`类。  
  
     类不能从嵌套在它里面的类继承。  
  
-   **实现。** 如果类使用[Implements 语句](../../../visual-basic/language-reference/statements/implements-statement.md)，则必须实现每个成员由指定在每个接口定义`interfacenames`。 与此异常是重新实现的基类成员。 有关详细信息，请参阅"重新实现"[实现](../../../visual-basic/language-reference/statements/implements-clause.md)。  
  
-   **默认属性。** 一个类只能指定最多一个属性作为其*默认属性*。 有关详细信息，请参阅[默认](../../../visual-basic/language-reference/modifiers/default.md)。  
  
## <a name="behavior"></a>行为  
  
-   **访问级别。** 在类中，你可以声明每个成员使用其自己的访问级别。 类成员默认为[公共](../../../visual-basic/language-reference/modifiers/public.md)访问，除变量和常量，哪些默认为[私有](../../../visual-basic/language-reference/modifiers/private.md)访问。 如果类具有限制性更强的访问其成员之一不同，类访问级别优先。  
  
-   **作用域。** 类是在其包含的命名空间、 类、 结构或模块整个范围内。  
  
     每个类成员的作用域是整个类。  
  
     **生存期。** Visual Basic 不支持静态的类。 模块提供了在功能上等效的静态类。 有关详细信息，请参阅[模块语句](../../../visual-basic/language-reference/statements/module-statement.md)。  
  
     类成员具有具体取决于如何以及在何处声明它们的生存期。 有关详细信息，请参阅[Visual Basic 中的生存期](../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)。  
  
-   **限定。** 类外部的代码必须限定该类同名的成员的名称。  
  
     如果嵌套类中的代码进行到编程元素中的非限定的引用，Visual Basic 首先搜索搜索元素在嵌套类中，然后在它的包含类，依次类推到最外层包含元素。  
  
## <a name="classes-and-modules"></a>类和模块  
 这些元素包含的许多相似之处，但有一些重要的区别。  
  
-   **术语。** Visual Basic 早期版本识别两种类型的模块：*类模块*（.cls 文件） 和*标准模块*（.bas 文件）。 当前版本调用这些*类*和*模块*分别。  
  
-   **共享的成员。** 你可以控制类的成员是共享成员还是实例成员。  
  
-   **面向对象。** 类是面向对象的但模块不是。 你可以创建一个或多个类的实例。 有关详细信息，请参阅[对象和类](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)。  
  
## <a name="example"></a>示例  
 下面的示例使用`Class`语句以定义一个类和多个成员。  
  
 [!code-vb[VbVbalrStatements#62](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/class-statement_1.vb)]  
  
## <a name="see-also"></a>请参阅  
 [对象和类](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [结构和类](../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)  
 [Interface 语句](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [Module 语句](../../../visual-basic/language-reference/statements/module-statement.md)  
 [Property 语句](../../../visual-basic/language-reference/statements/property-statement.md)  
 [对象生存期：如何创建和销毁对象](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)  
 [Visual Basic 中的泛型类型](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [如何：使用泛型类](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
