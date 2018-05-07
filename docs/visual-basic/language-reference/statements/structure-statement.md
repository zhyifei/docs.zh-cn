---
title: Structure 语句
ms.date: 07/20/2015
f1_keywords:
- vb.Structure
- Structure
helpviewer_keywords:
- user-defined types [Visual Basic], Structure statement
- compound data types [Visual Basic]
- Structure keyword [Visual Basic]
- Structure statement [Visual Basic]
- UDT (user-defined types)
- types [Visual Basic], user-defined
ms.assetid: 9bd1deea-2a89-4cdc-812c-6dcbb947c391
ms.openlocfilehash: 6a3626706b226b0be253fd35fa60b33a71b86007
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="structure-statement"></a>Structure 语句
声明结构的名称，并引入的变量、 属性、 事件和结构包含的过程的定义。  
  
## <a name="syntax"></a>语法  
  
```  
[ <attributelist> ] [ accessmodifier ] [ Shadows ] [ Partial ] _  
Structure name [ ( Of typelist ) ]  
    [ Implements interfacenames ]  
    [ datamemberdeclarations ]  
    [ methodmemberdeclarations ]  
End Structure  
```  
  
## <a name="parts"></a>部件  
  
|术语|定义|  
|---|---|  
|`attributelist`|可选。 请参阅[属性列表](../../../visual-basic/language-reference/statements/attribute-list.md)。|  
|`accessmodifier`|可选。 可以是以下各项之一：<br /><br /> -   [公共](../../../visual-basic/language-reference/modifiers/public.md)<br />-   [受保护](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [友元](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [私有](../../../visual-basic/language-reference/modifiers/private.md)<br />-   `Protected Friend`<br /><br /> 请参阅[访问 Visual Basic 中的级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。|  
|`Shadows`|可选。 请参阅[阴影](../../../visual-basic/language-reference/modifiers/shadows.md)。|  
|`Partial`|可选。 指示结构的部分定义。 请参阅[部分](../../../visual-basic/language-reference/modifiers/partial.md)。|  
|`name`|必须的。 此结构的名称。 请参阅[声明的元素名称](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)。|  
|`Of`|可选。 指定这是泛型的结构。|  
|`typelist`|如果你使用是必需的[的](../../../visual-basic/language-reference/statements/of-clause.md)关键字。 此结构的类型参数的列表。 请参阅[键入列表](../../../visual-basic/language-reference/statements/type-list.md)。|  
|`Implements`|可选。 指示此结构实现一个或多个接口的成员。 请参阅[实现语句](../../../visual-basic/language-reference/statements/implements-statement.md)。|  
|`interfacenames`|如果你使用是必需的`Implements`语句。 此结构实现的接口的名称。|  
|`datamemberdeclarations`|必须的。 零个或多`Const`， `Dim`， `Enum`，或`Event`语句声明*数据成员*的结构。|  
|`methodmemberdeclarations`|可选。 零个或多个声明的`Function`， `Operator`， `Property`，或`Sub`过程，充当*方法成员*的结构。|  
|`End Structure`|必须的。 终止`Structure`定义。|  
  
## <a name="remarks"></a>备注  
 `Structure`语句定义你可以自定义的复合值类型。 A*结构*是用户定义的类型 (UDT) 的 Visual Basic 早期版本的泛化。 有关详细信息，请参阅[结构](../../../visual-basic/programming-guide/language-features/data-types/structures.md)。  
  
 结构支持许多与类相同的功能。 例如，结构可以具有属性和过程，它们可以实现接口，并且也可以拥有参数化构造函数。 但是，有之间结构和类诸如继承、 声明和使用情况方面的重大差异。 此外，类是引用类型和结构是值类型。 有关详细信息，请参阅[结构和类](../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)。  
  
 你可以使用`Structure`只能在命名空间或模块级别。 这意味着*声明上下文*结构必须为源文件、 命名空间、 类、 结构、 模块或接口，并且不能为过程或块。 有关详细信息，请参阅[声明上下文和默认访问级别](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)。  
  
 结构默认为[友元](../../../visual-basic/language-reference/modifiers/friend.md)访问。 你可以调整其访问级别有访问修饰符。 有关详细信息，请参阅[访问 Visual Basic 中的级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。  
  
## <a name="rules"></a>规则  
  
-   **嵌套。** 你可以定义在另一个结构。 外部结构称为*包含结构*，和的内部结构称为*嵌套结构*。 但是，你无法访问通过包含结构的嵌套的结构的成员。 相反，您必须声明嵌套的结构的数据类型的变量。  
  
-   **成员声明。** 必须声明一个结构的每个成员。 结构成员不能为[受保护](../../../visual-basic/language-reference/modifiers/protected.md)或`Protected Friend`因为执行任何操作可以继承一个结构。 结构本身，但是，可以是`Protected`或`Protected Friend`。  
  
     您可以在结构中声明零个以上的非共享变量或非共享、非自定义的事件。 你不能具有仅常量、 属性和过程，即使其中一些非共享。  
  
-   **初始化。** 无法初始化结构用作其声明的一部分的任何非共享的数据成员的值。 必须通过对结构中，参数化构造函数初始化此类数据成员，也可以创建结构的一个实例后，将值分配给的成员。  
  
-   **继承。** 而不从任何类型继承结构，不能<xref:System.ValueType>，从所有结构都继承的。 具体而言，一个结构无法从另一个继承。  
  
     不能使用[继承语句](../../../visual-basic/language-reference/statements/inherits-statement.md)在结构定义中，即使指定<xref:System.ValueType>。  
  
-   **实现。** 如果结构使用[Implements 语句](../../../visual-basic/language-reference/statements/implements-statement.md)，则必须实现每个成员由指定在每个接口定义`interfacenames`。  
  
-   **默认属性。** 结构可以指定最多一个属性作为其*默认属性*，使用[默认](../../../visual-basic/language-reference/modifiers/default.md)修饰符。 有关详细信息，请参阅[默认](../../../visual-basic/language-reference/modifiers/default.md)。  
  
## <a name="behavior"></a>行为  
  
-   **访问级别。** 结构中，你可以声明每个成员使用其自己的访问级别。 所有的结构成员默认为[公共](../../../visual-basic/language-reference/modifiers/public.md)访问。 请注意，是否结构本身的更受限制的访问级别，这会自动限制的访问权限的成员，即使你调整其访问级别有访问修饰符。  
  
-   **作用域。** 结构是在其包含的命名空间、 类、 结构或模块整个范围内。  
  
     每个结构成员的作用域是整个结构。  
  
-   **生存期。** 一个结构本身没有生存期。 相反，该结构的每个实例都拥有独立于所有其他实例的生存期。  
  
     实例的生存期内开始通过创建时[New 运算符](../../../visual-basic/language-reference/operators/new-operator.md)子句。 包含变量的生存期结束时结束。  
  
     不能扩展结构实例的生存期。 由模块提供了近似的静态结构功能。 有关详细信息，请参阅[模块语句](../../../visual-basic/language-reference/statements/module-statement.md)。  
  
     结构成员具有具体取决于如何以及在何处声明它们的生存期。 有关详细信息，请参阅"生存期"[类语句](../../../visual-basic/language-reference/statements/class-statement.md)。  
  
-   **限定。** 结构外的代码必须限定该结构同名的成员的名称。  
  
     如果嵌套的结构内的代码进行到编程元素中的非限定的引用，Visual Basic 首先搜索搜索元素在嵌套结构中，然后在其包含的结构，依次类推到最外层包含元素。 有关详细信息，请参阅[对声明的元素的引用](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)。  
  
-   **内存消耗。** 与所有复合数据类型，不能安全地通过同时添加其成员的名义存储分配计算结构的总内存消耗。 此外，不能安全地假设存储在内存中的顺序是声明的顺序相同。 如果你需要控制结构的存储布局，则可以应用<xref:System.Runtime.InteropServices.StructLayoutAttribute>属性设为`Structure`语句。  
  
## <a name="example"></a>示例  
 下面的示例使用`Structure`语句以员工的定义一组相关的数据。 它演示如何使用`Public`， `Friend`，和`Private`成员以反映数据项的敏感度。 它还显示过程、 属性和事件成员。  
  
 [!code-vb[VbVbalrStatements#57](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/structure-statement_1.vb)]  
  
## <a name="see-also"></a>请参阅  
 [Class 语句](../../../visual-basic/language-reference/statements/class-statement.md)  
 [Interface 语句](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [Module 语句](../../../visual-basic/language-reference/statements/module-statement.md)  
 [Dim 语句](../../../visual-basic/language-reference/statements/dim-statement.md)  
 [Const 语句](../../../visual-basic/language-reference/statements/const-statement.md)  
 [Enum 语句](../../../visual-basic/language-reference/statements/enum-statement.md)  
 [Event 语句](../../../visual-basic/language-reference/statements/event-statement.md)  
 [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)  
 [Property 语句](../../../visual-basic/language-reference/statements/property-statement.md)  
 [结构和类](../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)
