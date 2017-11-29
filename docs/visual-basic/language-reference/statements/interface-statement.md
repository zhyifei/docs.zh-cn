---
title: "Interface 语句 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Interface
helpviewer_keywords:
- interface statement [Visual Basic]
- interfaces [Visual Basic], interface definition
ms.assetid: 8997af73-bda3-4f79-bd41-ca396b610260
caps.latest.revision: "26"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9418dc86ac6947ae951cb8fb757aed6e092a6668
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="interface-statement-visual-basic"></a>Interface 语句 (Visual Basic)
声明的接口的名称，并引入了接口包含成员的定义。  
  
## <a name="syntax"></a>语法  
  
```  
[ <attributelist> ] [ accessmodifier ] [ Shadows ] _  
Interface name [ ( Of typelist ) ]  
    [ Inherits interfacenames ]  
    [ [ modifiers ] Property membername ]  
    [ [ modifiers ] Function membername ]  
    [ [ modifiers ] Sub membername ]  
    [ [ modifiers ] Event membername ]  
    [ [ modifiers ] Interface membername ]  
    [ [ modifiers ] Class membername ]  
    [ [ modifiers ] Structure membername ]  
End Interface  
```  
  
## <a name="parts"></a>部件  
  
|术语|定义|  
|---|---|  
|`attributelist`|可选。 请参阅[属性列表](../../../visual-basic/language-reference/statements/attribute-list.md)。|  
|`accessmodifier`|可选。 可以是以下各项之一：<br /><br /> -   [公共](../../../visual-basic/language-reference/modifiers/public.md)<br />-   [受保护](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [友元](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [私有](../../../visual-basic/language-reference/modifiers/private.md)<br />-   `Protected Friend`<br /><br /> 请参阅[访问 Visual Basic 中的级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。|  
|`Shadows`|可选。 请参阅[阴影](../../../visual-basic/language-reference/modifiers/shadows.md)。|  
|`name`|必需。 此接口的名称。 请参阅[声明的元素名称](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)。|  
|`Of`|可选。 指定这是一个泛型接口。|  
|`typelist`|如果你使用是必需的[的](../../../visual-basic/language-reference/statements/of-clause.md)关键字。 此接口的类型参数的列表。 （可选），每个类型参数可以声明变体使用`In`和`Out`泛型修饰符。 请参阅[键入列表](../../../visual-basic/language-reference/statements/type-list.md)。|  
|`Inherits`|可选。 指示此接口继承的属性和另一个接口或接口的成员。 请参阅[Inherits 语句](../../../visual-basic/language-reference/statements/inherits-statement.md)。|  
|`interfacenames`|如果你使用是必需的`Inherits`语句。 此接口派生的接口名称。|  
|`modifiers`|可选。 正在定义的接口成员的的相应修饰符。|  
|`Property`|可选。 定义接口成员的属性。|  
|`Function`|可选。 定义`Function`是接口成员的过程。|  
|`Sub`|可选。 定义`Sub`是接口成员的过程。|  
|`Event`|可选。 定义接口成员的事件。|  
|`Interface`|可选。 定义嵌套在此接口的接口。 嵌套的接口定义必须终止与`End Interface`语句。|  
|`Class`|可选。 定义接口成员的类。 成员类定义必须终止与`End Class`语句。|  
|`Structure`|可选。 定义接口成员的结构。 成员结构定义必须终止与`End Structure`语句。|  
|`membername`|所需的每个属性、 过程、 事件、 接口、 类或结构定义为接口成员。 成员名。|  
|`End Interface`|终止`Interface`定义。|  
  
## <a name="remarks"></a>备注  
 *接口*定义一组的成员，如属性和过程，类和结构可以实现。 接口定义仅成员不是其内部的工作原理的签名。  
  
 类或结构实现接口，方法是为每个成员由接口定义的代码。 最后，当应用程序创建从该类或结构的实例，则对象存在，并且在内存中运行。 有关详细信息，请参阅[对象和类](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)和[接口](../../../visual-basic/programming-guide/language-features/interfaces/index.md)。  
  
 你可以使用`Interface`只能在命名空间或模块级别。 这意味着*声明上下文*接口必须为源文件、 命名空间、 类、 结构、 模块或接口，并且不能为过程或块。 有关详细信息，请参阅[声明上下文和默认访问级别](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)。  
  
 接口默认为[友元](../../../visual-basic/language-reference/modifiers/friend.md)访问。 你可以调整其访问级别有访问修饰符。 有关详细信息，请参阅[访问 Visual Basic 中的级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。  
  
## <a name="rules"></a>规则  
  
-   **嵌套接口。** 你可以定义在另一个接口。 外部接口称为*包含接口*，而内部接口称为*嵌套的接口*。  
  
-   **成员声明。** 在作为接口的成员声明属性或过程时，你将仅定义*签名*的属性或过程。 这包括元素类型 （属性或过程），其参数和参数类型和其返回类型。 因此，成员定义使用只有一个代码行，并终止语句`End Function`或`End Property`不能在接口中。  
  
     与此相反，当你定义枚举或结构，或嵌套的类或接口，并需要包含的数据成员。  
  
-   **成员修饰符。** 定义模块成员时，不能使用任何访问修饰符，也不能指定[共享](../../../visual-basic/language-reference/modifiers/shared.md)或除任何过程修饰符[重载](../../../visual-basic/language-reference/modifiers/overloads.md)。 你可以声明具有任何成员[阴影](../../../visual-basic/language-reference/modifiers/shadows.md)，并且你可以使用[默认](../../../visual-basic/language-reference/modifiers/default.md)定义属性时，以及[ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)或[WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md)。  
  
-   **继承。** 如果该界面使用[继承语句](../../../visual-basic/language-reference/statements/inherits-statement.md)，你可以指定一个或多个基接口。 你可以即使它们各自定义具有相同名称的成员，从两个接口继承。 如果这样做，实现代码必须使用名称限定指定它正在实现的成员。  
  
     一个接口不能从具有限制性更强的访问级别的另一个接口继承。 例如，`Public`接口不能继承自`Friend`接口。  
  
     接口不能从嵌套在它里面的接口继承。  
  
-   **实现。** 当类使用[实现](../../../visual-basic/language-reference/statements/implements-clause.md)语句来实现此接口，它必须实现该接口内定义的每个成员。 此外，实现代码中的每个签名必须精确匹配在此接口中定义的相应签名。 但是，实现代码中的成员的名称不必与在接口中定义的成员名称匹配。  
  
     当一个类实现过程时，它不能将作为过程指定`Shared`。  
  
-   **默认属性。** 接口可以指定最多一个属性作为其*默认属性*，这可以无需使用的属性名称引用。 通过声明其与指定此属性[默认](../../../visual-basic/language-reference/modifiers/default.md)修饰符。  
  
     请注意，这意味着接口可以定义的默认属性，仅当未进行任何继承它。  
  
## <a name="behavior"></a>行为  
  
-   **访问级别。** 所有接口成员隐式都具有[公共](../../../visual-basic/language-reference/modifiers/public.md)访问。 定义成员时，不能使用任何访问修饰符。 但是，实现该接口的类可以为每个实现的成员声明的访问级别。  
  
     如果向变量分配的类实例，其成员的访问级别可以依赖于该变量的数据类型是基础接口或实现的类。 下面的示例阐释了这一点。  
  
     [!code-vb[VbVbalrStatements#39](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/interface-statement_1.vb)]  
  
     如果访问类成员通过`varAsInterface`，它们都具有公共访问权限。 但是，如果访问通过成员`varAsClass`、`Sub`过程`doSomething`具有私有访问权限。  
  
-   **作用域。** 接口是在其命名空间、 类、 结构或模块整个范围内。  
  
     每个接口成员的作用域是整个接口。  
  
-   **生存期。** 接口本身没有生存期内，也不要其成员。 当类将实现接口和一个对象来创建的实例类，该对象具有在其中运行的应用程序中的生存期。 有关详细信息，请参阅"生存期"[类语句](../../../visual-basic/language-reference/statements/class-statement.md)。  
  
## <a name="example"></a>示例  
 下面的示例使用`Interface`语句以定义名为接口`thisInterface`，其必须与实现`Property`语句和`Function`语句。  
  
 [!code-vb[VbVbalrStatements#40](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/interface-statement_2.vb)]  
  
 请注意，`Property`和`Function`语句不会引入、 结束块`End Property`和`End Function`在界面中。 接口定义仅其成员的签名。 完整`Property`和`Function`块显示的类中实现`thisInterface`。  
  
## <a name="see-also"></a>另请参阅  
 [接口](../../../visual-basic/programming-guide/language-features/interfaces/index.md)  
 [Class 语句](../../../visual-basic/language-reference/statements/class-statement.md)  
 [Module 语句](../../../visual-basic/language-reference/statements/module-statement.md)  
 [Structure 语句](../../../visual-basic/language-reference/statements/structure-statement.md)  
 [Property 语句](../../../visual-basic/language-reference/statements/property-statement.md)  
 [Function 语句](../../../visual-basic/language-reference/statements/function-statement.md)  
 [Sub 语句](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Visual Basic 中的泛型类型](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [泛型接口中的变体](../../programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)  
 [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)  
 [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
